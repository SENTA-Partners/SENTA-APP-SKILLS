---
name: senta-decks
description: "Build board-ready PowerPoint decks and Word documents in the Senta house style. Use whenever the user asks for a deck, slides, a presentation, a board pack, a review, a summary document, or anything to be read by executives or a board — and whenever write_output is about to produce a .pptx or .docx. Carries the exact grid, type scale, colour values, table style, and composition rules, plus the editorial rules that make a slide read as analysis rather than a status update. Also covers what NOT to do: no bullet soup, no placeholder layouts, no default Office palette, no pie charts."
---

# Senta Decks

Every deck you produce should be board-ready without anyone reformatting it.

This is not a general guide to PowerPoint. It is the house standard, reverse-engineered by
measuring a deck that was accepted by the Senta executive team, then brought onto the brand
palette with the contrast arithmetic done. Follow the numbers exactly. They are not preferences.

## The single most important thing

**Build every slide from hand-placed shapes on a blank layout. Never use placeholder layouts.**

The reference deck uses `Blank` for all ten slides, with between 13 and 58 individually positioned
shapes each. That is where the control comes from. `slide_layouts[6]` is the blank layout in the
default template; use it and place everything yourself.

```python
from pptx import Presentation
from pptx.util import Inches, Pt
from pptx.dml.color import RGBColor

prs = Presentation()
prs.slide_width, prs.slide_height = Inches(13.333), Inches(7.5)   # 16:9, not 4:3
slide = prs.slides.add_slide(prs.slide_layouts[6])                 # blank
```

If you find yourself typing `slide.placeholders[1]`, stop. You are building the wrong kind of deck.

## The grid

| | Value |
|---|---|
| Canvas | 13.333 × 7.5 in (16:9) |
| Left margin | **0.42 in** — every element aligns to it |
| Right edge | **12.91 in** (so the right margin matches at 0.42) |
| Usable width | 12.49 in |
| Slide title | x 0.42, y 0.10 |
| Content top | 0.60 in |
| Footnote band | bottom 0.8 in, i.e. y from 6.70 |

The left margin is the whole discipline. In the reference deck 83 shapes share x = 0.42. Nothing
looks composed if elements start at slightly different places, and nothing looks amateur faster.

## Type scale

Calibri throughout. The hierarchy does the work, not the typeface.

| Role | Size | Weight |
|---|---|---|
| Cover title | 27 pt | bold |
| Slide title | **19 pt** | bold |
| Big stat / callout number | 25 pt | bold |
| Section label | 17 pt | bold |
| Body | 11 pt | regular, bold for emphasis |
| Table body / dense text | **9 pt** | regular |
| Table dense / secondary | **8 pt** | regular |
| Footnote | 7–8 pt | regular |

8 and 9 pt carry the majority of the words — 92 of 171 runs in the reference deck. This is a
document to be **read at a desk**, not projected. If the user says the deck will be projected,
raise body text to 12 pt minimum and cut the content per slide rather than shrinking it further.

Use bold inside sentences to carry the eye to what matters. The reference deck has 85 bold runs
across 10 slides. That is deliberate density, not emphasis inflation.

## Colour

Measured against every surface these are used on. The ratios are WCAG contrast against the
background named; the 4.5 floor applies to all body text.

### Structure and text

```
#005f7f  teal      titles, structural bands, table headers   7.13 white / 6.30 card
#4c5560  grey      body and secondary text                   7.57 white / 6.68 card
#a31e22  dark red  negative values, adverse findings         7.59 white / 6.70 card
#1e6b3a  dark green positive values, favourable findings     6.52 white / 5.76 card
#eef1f5  pale grey card fills, alternating table rows        (surface)
#fae9e9  pale red  row tint for an adverse row               (surface)
#ffffff  white     text on a teal band                       7.13 on #005f7f
```

**Teal `#005f7f` is the structural colour** — it does the job navy did in the reference deck, and
it is the brand's designated chrome colour. Titles, header bands, table headers, rules.

### Two exclusions, both measured, both easy to get wrong

**`#0071ce` brand blue is a DATA colour, never text on a card.** It measures 4.36:1 on `#eef1f5`
and 4.21 on `#fae9e9` — both under the floor. Use it for chart bars, lines and markers, and for
text only on white (4.94). Never for a title, never on a shaded row.

**`#68727e` muted grey fails on cards too** at 4.31:1. On any `#eef1f5` fill use `#4c5560`
instead. Reserve `#68727e` for white backgrounds only.

### Chart series

When a chart genuinely earns its place, series colours in this order. This order was validated for
colour-vision deficiency: worst adjacent-pair ΔE 9.1, and only the first three pass an all-pairs
check, so **cap a line chart at three series**.

```
1 #0071ce   2 #eb6834   3 #1baf7a   4 #eda100
5 #e87ba4   6 #008300   7 #4a3aa7   8 #e34948
```

Never use teal `#005f7f` as a series colour. It is only ΔE 13.0 from brand blue in normal vision,
below the 15 floor, so the two cannot appear as two series in one chart.

## The logo

`senta-logo.png` — the full logo including the wordmark, 1200 x 254 with a transparent
background.

**It is already in your working directory.** The app stages it there before the question starts, so
open it by bare filename with no path. Do not go looking for it, do not fetch it from the website,
and do not ask the user to send it.

**Cover slide only.** Bottom-left at x 0.42, sized to 1.6 in wide, top around y 6.35. Do not repeat
it on every slide: a logo on all ten is a template, and it costs you the space where the source line
belongs.

```python
slide.shapes.add_picture('senta-logo.png', Inches(0.42), Inches(6.35), width=Inches(1.6))
```

Rendered from the live SVG at sentapartners.com and verified: aspect 4.72 against the source's 4.73,
and the three brand colours present exactly. The square icon in the app's build directory is **not**
this file; its wordmark was stripped to make an app icon.

## Composition

**Tables over bullets.** The reference deck has 15 tables and zero bullet lists. A board reads a
table; a bulleted list of sentences is a status update.

Table style:
- Header row filled `#005f7f`, white text, bold, 9 pt
- Body 8–9 pt, `#4c5560`
- Alternate row fill `#eef1f5`; an adverse row may take `#fae9e9`
- **Numbers right-aligned** with consistent decimals and thousands separators
- Units in the column header, never repeated in cells
- A negative number is `#a31e22`, a strong positive `#1e6b3a` — and it also carries a sign or a
  label, because colour alone must never be the carrier

**Charts are the exception, not the default.** Reference deck: zero. Include one when the *shape*
of the data is the point — a trend over many periods, a distribution. For four practices and one
number each, a table is clearer and smaller. When you do chart, use a **native** pptx chart so the
user can restyle and re-point it; never paste an image of a chart.

**One idea per slide, and say it in the title.** Not "Q3 Results" but "Contribution per APP FTE
varies 6x across practices". The reference deck titles are findings: *What the numbers say*,
*Recommended actions*, *Opportunity sizing*, *APP versus physician economics, and the loss-making
tail*. A title that names the conclusion means the slide can be skimmed and still land.

**Every data slide carries a source line** in the footnote band: what the figures are, the period,
the source, and any caveat that changes how they should be read. Half the reference slides do this,
including plain admissions like *"Not yet decision-grade — six defects in the measurement layer"*.
A number a board cannot trace should not be on the slide.

## Standing rules

- **Never a pie chart.** Not for payor mix, not for anything. More than three parts is unreadable
  and payor mix always has more.
- **No default Office palette.** If a colour is not on the list above, it does not go in the deck.
- **No clip art, no stock photography, no gradients, no drop shadows.**
- **Do not restate the table in prose beneath it.** Say what it means or say nothing.
- **Aggregate only** while the app is in its current posture: no patient names, MRNs or dates of
  birth on a slide, whatever the question asked for.
- **Verify before you claim it is done.** `write_output` opens the file and reports what it found;
  read that back. "Saved" is not "correct", and a deck with an empty table opens perfectly.

## Word documents

Same palette, same type hierarchy, same source-line discipline. Body 11 pt, headings 19 pt bold in
`#005f7f`, tables styled as above. A memo is a deck without the slide breaks; the standards do not
change.
