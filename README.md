# SENTA APP SKILLS

`github.com/SENTA-Partners/SENTA-APP-SKILLS`

The skills shipped inside the **SENTA Analytics** desktop app. Managed by the data team.

> The local checkout may still be in a folder called `SENTA-Analytics-Skills`; the build
> accepts either name. Git does not care what the directory is called.

This repository is deliberately **separate from anyone's personal skill library**. Skills here are a
published artifact used by ~185 people, so they carry a different lifecycle, a different review bar, and a
different owner than a personal working library. Two practical consequences:

- Nobody's uncommitted work-in-progress can block an app release.
- What ships is an explicit, reviewed decision — see `MANIFEST.json`.

## Why this is a security boundary, not just tidiness

**Skills are instructions to the agent.** Whoever can change them changes what the tool does, for everyone
who has it installed. A wrong instruction is as consequential as a wrong query — arguably more, because it
applies silently and repeatedly.

So this repo is treated like application code:

| Control | Mechanism |
|---|---|
| What ships | `MANIFEST.json` — an allowlist. A skill in `skills/` that isn't in the manifest is **not** shipped. |
| Who can change it | Branch protection on `main` + CODEOWNERS (data team) |
| Review | Pull request required; no direct pushes to `main` |
| Traceability | The app records the commit its bundle was built from and stamps it on every audit row |
| Distribution | Vendored into the signed installer at package time — not pulled live at runtime |

## Layout

```
skills/
  <skill-name>/
    SKILL.md            # the skill itself; keep it small
    references/         # detail loaded on demand, not inlined
MANIFEST.json           # the allowlist — the publication gate
```

Keep `SKILL.md` small and push detail into `references/`. The app loads `SKILL.md` into a cached system
prefix and reads reference files on demand, so bulk in `SKILL.md` is paid for on **every** request while
bulk in `references/` is paid for only when relevant. For scale: a ~2,500-token `SKILL.md` over ~900 KB of
references is a healthy shape; inlining the same content would cost roughly $0.69 per request.

## Adding or changing a skill

1. Branch, edit, open a PR. Someone other than the author reviews.
2. If a **new** skill should ship, add it to `MANIFEST.json` in the same PR. That entry is the decision to
   publish, and it's reviewable on its own.
3. Merge to `main`.
4. Cut an app release. The build vendors exactly what the manifest lists, records this repo's commit, and
   the update reaches users through the signed installer.

## ⚠ Temporary state — duplication to unwind

`senta-warehouse-analytics` currently exists in **two places**: here, and in Dean's personal
`SKILLS/SkillRepo`, which is still where he uses it day to day. This is deliberate for
development and is **not** a durable arrangement — two copies drift, and drift is silent.
The app would go on shipping instructions that no longer match the ones actually in use.

**Mitigation in place:** `scripts/vendor-skills.mjs` hashes both trees on every build and
prints a `DRIFT` warning listing the differing files. The build always ships *this* repo's
version, so the warning tells you when the other copy has diverged.

**To unwind, when the app goes into real use:**

1. Confirm this repo has the current content — run `npm run vendor-skills` and check it
   reports "currently identical", or reconcile whatever it flags.
2. Remove the skill from SkillRepo: `git rm -r skills/senta-warehouse-analytics` and commit.
3. Re-point the junction so day-to-day use follows the move:
   ```
   rmdir "%USERPROFILE%\.claude\skills\senta-warehouse-analytics"
   mklink /J "%USERPROFILE%\.claude\skills\senta-warehouse-analytics" ^
     "%USERPROFILE%\OneDrive - Senta Partners\Desktop\SENTA-Analytics-Skills\skills\senta-warehouse-analytics"
   ```
4. Delete the drift-check block at the bottom of `vendor-skills.mjs` — it has no purpose
   once there is only one copy.

## What does NOT belong here

- Personal or experimental workflows — keep those in your own library.
- Anything unreviewed. If it isn't ready for 185 people, it isn't ready for `main`.
- Credentials or connection strings of any kind. Skills are shipped to end-user machines in plain text.
