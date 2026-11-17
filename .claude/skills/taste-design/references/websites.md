# Websites

For pages that sell or explain: landing pages, company sites, product and service pages,
one-pagers, shop, cafe and studio sites. The bar is the sites of well-funded product companies
(Linear, Stripe, Figma, Vercel) and good independent shops: plain words, real pictures, lots of
space, one strong idea per screen.

## Contents

1. What kind of business decides the look
2. Page structure
3. The hero
4. Sections and cards
5. Pictures
6. Nav and footer
7. Motion
8. Common failures

## 1. What kind of business decides the look

| Kind | Examples | Lead with | Allowed extras |
|---|---|---|---|
| Software | SaaS, AI tool, CRM, app | The product's own screen, built in HTML at true size | A subtle grid or lit background in the hero; small UI fragments in cards; dark theme |
| Physical product | Furniture, bikes, coffee | Large photographs of the product, a different view each section | One flat brand-colour band |
| Service | Trades, clinic, agency, consultant | Photographs of the people, the work, the result | One simple diagram at most |
| Place | Cafe, bakery, shop, hotel, gym | Many photographs (8 to 20), address and hours early | Flat colour only; no effects, no dark theme |

Effects (animated backgrounds, shader gradients, glowing grids) belong only to tech and software.
A cafe or plumber with a glowing animated background looks fake.

## 2. Page structure

- **One section per screen.** At a laptop size (1440 × 900), each section is about one screen tall,
  sometimes two. The hero fills the first screen alone; the next section's heading should not peek
  in.
- Order sections by the visitor's questions, not by a template:
  1. What is it, for whom? (hero)
  2. Show me it working (the product, the work, the place)
  3. What exactly do I get? (features, menu, services, rooms)
  4. What does it cost / how do I start? (pricing, booking, contact)
  5. Can I trust it? (only real proof: named clients, real reviews the user gave, years trading)
  6. Close: one action, then the footer
- Skip any section there is no real material for. No invented testimonials, no fake logo walls, no
  "Trusted by 10,000+ teams".
- Vary the composition between sections (full-bleed picture, split 6/6, three cards, a big type
  moment), but never vary the system (fonts, colours, radius, buttons).

## 3. The hero

- A headline of 3 to 9 words that says what it is, in plain words. A sub-line of one or two
  sentences with the specific: for whom, what it does, what it costs or where it is.
- One primary button and at most one secondary. The button names the action ("Book a table",
  "Start free trial", "Get a quote"), never "Learn more" as the main one.
- A real visual on the first screen: the product UI, a photograph, the place. Never an empty
  gradient, never an abstract 3D blob.
- At most one small line of quieter text (a fact line or a small pill above the headline).
- One entrance on load: headline and visual fade and rise 8 to 16px over 400 to 700ms, staggered.
  Once only.

## 4. Sections and cards

- Section heading (h2) 32 to 48px, with a short lead under it; then the content 48px below.
- A clean trick for headings: the claim in ink, then a second clause in grey in the same line:
  "Quotes in two minutes. <span class=muted>Sent straight from your phone.</span>"
- **Cards are barely there**: one step off the page colour, a 1px hairline, generous padding (24 to
  32px), radius from the token set. No heavy shadow at rest.
- **Two levels, never three**: card → picture (or UI) → content. Never a card holding a patterned
  box holding another card.
- Cards in a row: same height, titles on one line, at most two lines of 16px text under each.
- Feature cards show the thing (a small piece of real UI, a photograph, a number in context), not
  an icon in a coloured circle with three lines of text. If you must use icons, use one icon set
  (Lucide, Phosphor or Heroicons), one size, one stroke, in ink colour.
- Pricing: two or three plans, the same card style, the recommended plan marked by the filled
  button only, not by a glowing border and a "Most popular" ribbon.
- FAQs open in full, no accordions unless there are many.

## 5. Pictures

- Real photographs beat everything. Use the user's own. Otherwise use free stock (Unsplash,
  Pexels) of the same kind of thing, and say in the reply which are stand-ins to replace.
- No captions under pictures. Credits for stock go in one line in the footer.
- Photographs keep their own colour; never tint them with the brand colour or lay a gradient over
  them. Text over a photograph only in the hero or a final band, and only on a dark, empty part of
  the picture or on a solid box.
- Software: build the product screen in HTML/CSS at real size, showing the product's actual
  subject (a CRM shows a pipeline with named deals and amounts; an invoicing app shows an invoice).
  Never a generic "analytics dashboard" with random charts standing in.
- Real brand logos in their own colours, never redrawn or tinted.

## 6. Nav and footer

- Nav: fixed, solid background, 1px hairline under it, 64 to 72px tall. Logo left, 4 to 6 one-word
  links, the main button on the right. No blur, no floating pill, no shrinking on scroll.
- Phone: a menu button opening a full-screen sheet; the main action stays visible.
- Footer: the logo again, link columns, a single legal line with the current year. No "Made with
  love in…" sign-off.

## 7. Motion

Quiet and quick. Everything under 300ms except the hero entrance.

- Buttons: slight colour step on hover, a 1px press-down on click.
- Linked cards: lift 2px on hover with a soft shadow appearing. Photographs inside a frame zoom to
  1.02 to 1.03.
- Text links: an underline that draws in.
- Respect `prefers-reduced-motion`.
- Never: carousels, auto-rotating tabs, parallax on every section, tilt-on-hover, scroll-jacking,
  things flying in from the sides.

## 8. Common failures (and the fix)

| Looks AI-made | Do instead |
|---|---|
| Purple/blue gradient hero with a floating 3D shape | Flat neutral ground, the real product or a photograph |
| Every section: small caps label, big heading, three icon cards | Shape each section by what it shows; vary composition |
| A strip of four big round numbers under the hero | Put each real number in the sentence it proves |
| Three polished testimonials with first names | Only reviews the user supplied, word for word, or none |
| Glass cards, glowing borders, drop shadows everywhere | Hairline border, one step of background |
| "Unlock the power of…" headline | Say what it is and for whom |
| Emoji bullets | Plain lists, or one consistent icon set |
| Random fonts and sizes per section | One type scale from tokens.md |
