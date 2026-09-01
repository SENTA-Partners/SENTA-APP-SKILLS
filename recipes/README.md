# Recipes

A **recipe** is an approved methodology + parameters + a trigger.

That one shape covers three things that looked separate:

| | Trigger |
|---|---|
| **Catalogue** — the ~139 viewer seats shouldn't face a blank prompt box | a button |
| **Login briefing** — "the five things to focus on today" | sign-in |
| **A settled definition** — everyone measures net collection rate the same way | either |

## Why these are files and not database rows

A recipe is **agent instructions reaching people who did not ask for them**, running under
their credentials and spending their budget. That is the same thing a skill is, so it gets
the same governance: a pull request, a reviewer, a diff, and a commit that
`skill_bundle_version` pins on every audit row.

A database row has none of that. It changes silently, has no reviewer, and can't be tied to
a version — so six months later you can't prove which definition produced a number.

## Why one branch and not a branch per job

Targeting lives **in the file**, not in the branch. Everything ships to everyone and the app
filters at runtime.

A branch per role would mean a correction has to land N times — miss one and that role keeps
running the wrong definition, silently. It would also mean N installers, N signing runs, and
N version floors, for a population where people change jobs and installers don't.

Branches are for divergence in time: `main` is what ships, feature branches are work in
progress, and `next` is the pilot cohort during a staged rollout.

## Format

One JSON file per recipe, named `<id>.json`. Files starting with `_` are never loaded.

```jsonc
{
  "id": "daily-practice-briefing",         // must match the filename
  "name": "Daily practice briefing",       // shown in the catalogue
  "description": "One line: what question this answers.",

  // Empty array = everyone. Both must match if both are set.
  "audience": { "roles": ["practice_admin"], "tiers": [] },

  // "catalogue" = a button. "login" = also runs at sign-in.
  "trigger": "catalogue",

  "parameters": [
    { "name": "month", "label": "Month", "type": "month", "default": "last_complete" },
    { "name": "practice", "label": "Practice", "type": "select",
      "options": ["Reston ENT", "ADVENT", "CAAG"] }
  ],

  // {{placeholders}} are substituted from the parameters above.
  "prompt": "Report charges for {{practice}} in {{month}}, broken out by provider.",

  // The approved definition. Required unless the question is a plain count —
  // the build validator applies the same rule the app's methodology gate does.
  "methodology": { /* see below */ },

  "review": {
    "author": "someone@sentapartners.com",
    "approvedBy": "dean.demerritt@sentapartners.com",  // required to publish
    "approvedAt": "2026-08-31"
  }
}
```

### Parameter types

`text` · `select` (needs `options`) · `month` · `date` · `daterange`

`default` accepts a literal, or one of `last_complete`, `current`, `last_7`, `last_30`.

### Methodology

The same eleven fields the app's methodology gate collects, so an ad-hoc question that
cleared the gate can be exported straight into a recipe file:

`metricName` · `source` · `tables[]` · `joins[]` · `dateColumn` · `amountColumn` ·
`formula` · `grain` · `inclusions[]` · `exclusions[]` · `knownTraps[]` · `assumptions[]`

When a recipe carries a methodology the app skips the gate and runs straight to execution —
because the review already happened, in the pull request, by a named person.

**That is the whole reason to be strict here.** A recipe bypasses the control that protects
everyone else, so the file has to earn it.

## Publishing

Add the id to `MANIFEST.json` under `recipes`. Presence in this directory is not enough —
the same publication gate as skills.

The build refuses to publish a recipe that:

- has no `approvedBy`
- names a parameter its prompt never uses, or uses a `{{placeholder}}` it never declares
- has neither a `methodology` nor a `methodologyWaiver`
- has an `id` that doesn't match its filename

`methodologyWaiver` is a sentence saying why this question doesn't need a definition —
`"plain row count, no derived metric"`. It exists so that "we didn't get round to it" has to
be written down rather than shipped silently.

## Cost note for `"trigger": "login"`

A login briefing costs one run per user per day whether or not anyone reads it, so spend
scales with headcount rather than usage. At 185 users that is real money before anyone asks
a question.

Measure the actual cost per run before turning it on broadly.
