---
name: taste-design
description: >-
  Makes websites and dashboards look professionally designed instead of generic or "AI-made".
  Covers two kinds of page: marketing websites (landing pages, company sites, one-pagers, product
  and service pages, shop or cafe sites) and dashboards (personal life dashboards, CRM and sales
  dashboards, KPI and admin panels, trackers, finance and health dashboards). Use this skill
  whenever the user asks to build, design, redesign, restyle, polish or review a web page, landing
  page, site, dashboard, panel or app screen as HTML, CSS, React or Tailwind, or says something
  looks generic, templated, cheap, cluttered, AI-made or "not quite right", even if they don't ask
  for "design" by name.
---

# Taste design

The goal is a page a good design team would ship: it says plainly what it is, shows the real
thing, and looks made for this person or business, not poured from a template. Most of that comes
from restraint and consistency, not decoration.

## Step 1: Decide which kind of page this is

The two kinds pull in opposite directions, so decide first and say which one you chose.

| | Website (sells or explains) | Dashboard (used every day) |
|---|---|---|
| Job | Persuade a stranger in seconds | Let the owner see and act fast |
| Reading | Top to bottom, one idea a screen | Scanned, returned to, many panels at once |
| Density | Low: big type, lots of space | Medium to high: compact, aligned, calm |
| Visuals | Real photographs, product shots | Real numbers, small charts, states |
| Motion | An entrance and a few hover touches | Almost none; changes, not decoration |

- Website → read `references/websites.md`.
- Dashboard → read `references/dashboards.md`.
- A product page that shows a dashboard (selling a CRM, say) is a website, with the dashboard as
  its main picture: read both, and build the dashboard screenshot with the dashboard rules.

Always read `references/copy.md` before writing any words, and use `references/tokens.md` as the
starting design system so every page begins from the same consistent base.

## Step 2: Get the real material

Generic results come from generic input. Before designing, collect what is real:

- Who it is for and what it sells or tracks, in one sentence.
- Real names, prices, figures, logos, screenshots and photographs the user has given or can give.
- For a dashboard: which numbers they actually check, how often, and what they do next when a
  number is bad.

Ask one short question if the gap is large (no idea who a site is for, no idea what a dashboard
tracks). Otherwise go ahead and make sensible choices. When you must use stand-in data, make it
believable and say clearly in your reply that it is sample data. Never present invented figures,
reviews or client names as real.

## Step 3: Set one system, then build

Pick and write down, before any layout:

1. **The feel** in three words (e.g. "calm, precise, warm"), taken from the user or the trade.
2. **One typeface** (two at most: a display face for big headings plus a text face). Good safe
   choices: Inter, Geist, IBM Plex Sans, Manrope, Source Serif 4 for a serif. Load from Google
   Fonts, with a system fallback.
3. **One accent colour**, from the brand, product or subject. Everything else is neutrals.
4. **One radius family, one spacing scale, one button style, one card style.** See `tokens.md`.

Then build using only those. Consistency is most of what reads as "professional". Almost every
"AI-made" look comes from mixing: three shadows, four radii, gradients on some cards and not
others, a different font weight in every section.

## House rules (apply to both kinds)

- **Neutral interface, colour with meaning.** The page is 90 to 95% neutral. The accent marks the
  main action, links, focus and the one thing that matters. Red, amber and green are for status
  only, never decoration.
- **No AI-default decoration.** No purple-to-blue gradients, no glassmorphism, no glowing neon
  borders, no floating blobs, no emoji as icons or bullets, no rainbow of pastel icon tiles, no
  drop shadows on everything. Use a 1px hairline border and a slight change of background instead.
- **Never violet or lavender as the brand colour** unless the user's brand already is. It is the
  strongest single tell of a model-made page.
- **Readable text.** Body text 16px or more with line height around 1.5 to 1.7, near-black on light
  (never pure #000), at least 4.5:1 contrast; grey only for labels, dates and secondary info.
  Lines no longer than about 65 characters.
- **Sentence case** for headings, buttons and labels. No ALL-CAPS tracked labels over every
  section.
- **Equal edges and one grid.** Content lines up on a 12-column grid with equal left and right
  margins. Cards in a row share one height. Titles in a row sit level.
- **One main action per view.** One filled button; everything else is secondary or a text link.
- **Real things over drawings.** Real photographs, real product UI built in HTML, real brand logos
  in their own colours. No clip-art illustrations, no fake 3D shapes standing in for a product.
- **Works on a phone.** Check at 390px wide: nothing overflows sideways, tap targets are at least
  44px, the most important thing is still first.
- **Light and dark.** Define colours as CSS variables and give a dark version via
  `prefers-color-scheme`. Dark is a re-mapping of the same tokens, not a new design.
- **Accessible by default.** Every image has alt text, every icon button a label, focus is visible,
  headings go h1 → h2 → h3 in order, and colour is never the only signal (add an arrow, sign or
  word).

## Step 4: Check before handing over

Go through this list yourself and fix what fails before replying. Say in one line what you
checked.

1. Can someone tell in five seconds what this page is and what to do next?
2. Is there exactly one accent colour, one radius family, one button style, one card style?
3. Any gradient, glass, glow, blob, emoji-as-icon, or violet that wasn't asked for? Remove it.
4. Read every sentence against `copy.md`. Any banned word, stock phrase or invented fact? Rewrite.
5. Do cards in each row line up, with equal heights and level titles?
6. Does it hold together at 390px wide, with no sideways scroll?
7. Is text at least 16px for anything people read, with good contrast in light and dark?
8. Dashboard only: does every number have a unit, a time frame and a "compared to what"?
   Is the most important thing top-left? Do empty, loading and error states exist?
9. Is any sample data clearly flagged as sample in your reply?

## Credits

Several website and copy rules here are adapted and condensed from tasteskill by Leonxlnx
(github.com/Leonxlnx/taste-skill, MIT licence; see `LICENSE`). The dashboard guidance is
original to this skill.
