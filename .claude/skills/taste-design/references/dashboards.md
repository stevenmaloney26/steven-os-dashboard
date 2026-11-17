# Dashboards

For screens people use every day: personal life dashboards, CRM and sales dashboards, KPI and
admin panels, money, health or habit trackers. The bar is tools like Linear, Stripe's dashboard,
Vercel and Apple Health: calm, dense without being cramped, every number explained, nothing
decorative.

A dashboard answers three questions in this order: **What needs me now? How am I doing? Where do I
go to act?** Design for those, not to show off charts.

## Contents

1. Plan before layout
2. Layout and hierarchy
3. Cards (tiles)
4. Numbers
5. Charts
6. Lists and tables
7. Colour and status
8. States: empty, loading, error, stale
9. Interaction and editing
10. Phone layout
11. Personal life dashboards
12. Business dashboards (CRM, sales)
13. Common failures

## 1. Plan before layout

Write a short plan first (in your reasoning or as a comment):

- Who looks at it, how often (glance at 7am? all day at work?), on what device.
- The 3 to 5 numbers or items that matter most, ranked.
- For each: what "good" and "bad" look like, and what the person does next.
- Everything else is secondary and goes lower or behind a click.

If the user lists 20 things, push back gently and rank them. A dashboard showing everything at
equal weight shows nothing.

## 2. Layout and hierarchy

- **Top-left is the most important.** People read in a Z or F pattern. Put the "today / needs
  attention" zone first.
- A clear structure: a slim header (title, date or period picker, one action), a top row of the
  key items, then grouped sections below.
- **Group by domain**, each group with a small plain heading (e.g. Today, Money, Health, Work).
  Groups are separated by space (32 to 48px), not by boxes inside boxes.
- **One grid**: 12 columns, a 16 to 24px gap. Tiles take 3, 4, 6 or 12 columns. Every tile in a row
  has the same height. Never a masonry pile of odd sizes.
- **A small set of tile sizes** (e.g. small 3-col stat, medium 6-col chart or list, wide 12-col
  table). Reuse them.
- Maximum width around 1440px, centred, so lines don't run across a giant monitor.
- Density: tighter than a website. Body text 14 to 15px is fine in tables and lists; key numbers
  large; headings small (16 to 20px). Spacing still follows the 4/8 scale.

## 3. Cards (tiles)

- One card style everywhere: background one step off the page, 1px hairline border, radius from
  tokens, padding 16 to 24px, no shadow (or the faintest one).
- Card header: a short title in sentence case (14 to 15px, weight 500), optional small muted meta
  on the right ("This week", "Updated 5 min ago"), optional single icon button (⋯ or edit).
- One idea per card. If a card needs a scrollbar, it's two cards or a page.
- No coloured card backgrounds to signal category. Colour belongs to the data inside.
- No icons in coloured circles on every card. If an icon helps recognition, one small line icon
  next to the title, ink or muted.

## 4. Numbers

Numbers are the content; treat them like typography.

- `font-variant-numeric: tabular-nums` everywhere numbers appear, so digits line up and don't
  jiggle when they update.
- Key figure 28 to 40px, weight 500 to 600. Never bigger than the page title by a silly amount.
- **Every number has a unit, a period and a comparison.** "£2,340" alone means nothing; "£2,340
  this month · +12% vs October" means something.
- Change shown with sign and arrow plus colour: ▲ +12% in green, ▼ −4% in red. Never colour alone.
  Decide per metric whether up is good (revenue) or bad (spending, weight if cutting).
- Format for humans: £12.4k not £12,400.37 in a tile; full precision in a table or tooltip. Dates as
  "Tue 17 Nov" or "2 days ago", not ISO strings.
- Right-align numbers in tables; left-align text.
- Progress toward a goal: a thin bar (4 to 8px) with the value and target in words ("6,200 of
  10,000 steps"), not a giant ring for everything.

## 5. Charts

- Pick by question:
  - Change over time → line (or area for one series).
  - Compare items → horizontal bar, sorted.
  - Part of a whole → a single stacked bar or simple bar; a donut only with 2 to 4 parts.
  - Trend at a glance in a tile → a sparkline (no axes) next to the number.
- No 3D, no pie with 8 slices, no gauges/speedometers, no gradients inside bars, no shadows.
- Direct labels beat legends: write the series name at the end of its line.
- Light gridlines (horizontal only, 10% ink) or none; axis labels muted 12px; no chart borders.
- Bars start at zero. Lines may not, but then make the range clear.
- Colour: one series in the accent, comparison series in grey. Up to 5 categorical colours, with
  consistent meaning across the whole dashboard (Health is always the same colour).
- A tooltip on hover with the exact value and date.
- Libraries that look clean by default: Chart.js with defaults toned down, Recharts, ECharts,
  or hand-built SVG for sparklines. Strip default borders, legends and animations.

## 6. Lists and tables

- Lists for "what's next": tasks, upcoming events, deals to chase. Each row 40 to 48px, one line
  of title, muted meta on the right, a checkbox or one action on hover.
- Tables: hairline row dividers (not zebra stripes and full grid), sticky header, sortable columns,
  numbers right-aligned, a row hover. Status as a small dot plus a word, not a bright pill per cell.
- Show 5 to 8 rows in a tile and a "View all" link, not a 40-row table squeezed into a card.

## 7. Colour and status

- Neutral base: page background a very light warm or cool grey (light) or near-black (dark); cards
  one step off it.
- One accent for actions, selection and the primary series.
- Status colours reserved: green good, amber watch, red act now, blue info. Muted versions for
  backgrounds (10 to 15% opacity), full for text and dots. Check contrast in light and dark.
- A dashboard full of red and green looks like an alarm. Most things should look normal (ink),
  and only exceptions get colour.

## 8. States: empty, loading, error, stale

Real dashboards are rarely full. Design every tile for:

- **Empty**: a short plain sentence and the one action ("No meals logged today. Log breakfast").
  Not a sad illustration.
- **Loading**: skeleton shapes in the tile's layout, a soft shimmer, no spinners in every card.
- **Error**: what failed and a retry ("Couldn't load prices. Try again"), keeping old data visible
  with a "last updated" note when possible.
- **Stale or manual data**: show when it was last updated. A number from three weeks ago must not
  look like today's.

## 9. Interaction and editing

- Edit in place or in a small side sheet/modal with one clear save button; close on Escape.
- Instant feedback on save (the value updates, a brief "Saved"). Never a full page reload.
- Filters and period pickers in the header, affecting the whole page, and the current choice is
  always visible ("This week").
- Keyboard: tab order follows the layout; focus visible; Escape closes overlays.
- Persist personal settings (collapsed sections, chosen period) in localStorage.

## 10. Phone layout

- Single column in priority order: "needs me now" first, then the key numbers, then the rest.
- Key stats can sit two per row as small tiles; charts go full width and shorter.
- Tables become lists (title, key value, status) with a tap to open.
- Bottom tab bar for 3 to 5 main areas if it is an app; tap targets 44px.

## 11. Personal life dashboards

A life dashboard is checked at a glance, often first thing in the morning and on a phone. Make it
feel like a calm morning briefing, not a cockpit.

- **Top: Today.** Date, weather, the 1 to 3 focus items, the next calendar event, today's targets
  (training, meals, habits). This is the "what needs me now" zone.
- **Then domains as sections**, each with 2 to 4 tiles: Money (net worth or balance, this month's
  spending vs budget, portfolio change), Health (training done this week, weight or sleep trend,
  habit streaks), Work or projects (next actions, pipeline), Interests (next tee time, a trip
  countdown, ideas captured).
- Habit and streak tracking: a compact row of days (7 or 30 small squares) beats big flames and
  confetti.
- Use the person's own words and units (stone or kg, £, their habit names).
- Warm, personal but restrained: a good typeface, one accent, a subtle photo or map tile at most.
  No motivational quotes in giant type unless they ask.
- Quick capture: one obvious "+ Add" or capture box (idea, food, spend) reachable from anywhere.

## 12. Business dashboards (CRM, sales)

- Top row: the 3 to 4 numbers the owner is judged on (revenue this month vs target, open pipeline
  value, deals won, overdue follow-ups), each with comparison.
- Then "act now": overdue follow-ups, deals stuck too long, unpaid invoices, as a short list with
  names, amounts and one action each.
- Pipeline as columns or a horizontal stacked bar by stage, with count and value per stage.
- Customer or account lists as tables with a health status dot and last contact date.
- Name things in the client's language (their stage names, product names).
- When this dashboard is a screenshot on a sales website, use believable named sample data for the
  client's trade and keep the real layout; never an abstract "analytics" mock.

## 13. Common failures (and the fix)

| Looks AI-made | Do instead |
|---|---|
| Every card has a gradient icon circle and a giant number | Plain title, number with unit and comparison |
| Neon colours on a dark background, glowing charts | Neutral dark (#0f1012-ish), one accent, flat charts |
| Ten different card sizes in a masonry jumble | A few tile sizes on one 12-column grid, equal heights per row |
| Donuts and gauges for everything | Line, bar, sparkline, progress bar |
| "Welcome back, John! 👋" hero banner taking half the screen | A slim header; Today content immediately |
| Numbers with no period or comparison | "this month · +12% vs Oct" |
| Random fake data that doesn't add up | Believable sample data that sums correctly, flagged as sample |
| Red/green everywhere | Ink by default; colour only for exceptions |
| No empty or loading states | Design all four states for every tile |
