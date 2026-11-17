# Starting tokens

A small, consistent design system to start every page from. Change the accent, font and radius to
fit the brand; keep the structure. Use only these variables in the page's CSS so nothing drifts.

```css
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&display=swap');

:root {
  /* Type */
  --font: 'Inter', ui-sans-serif, system-ui, -apple-system, 'Segoe UI', sans-serif;
  --t-xs: 12px;  --t-sm: 14px;  --t-base: 16px;  --t-lg: 18px;
  --t-xl: 20px;  --t-2xl: 24px; --t-3xl: 32px;   --t-4xl: clamp(36px, 4vw, 56px);
  --t-hero: clamp(40px, 6vw, 76px);

  /* Spacing: use only these */
  --s-1: 4px;  --s-2: 8px;  --s-3: 12px; --s-4: 16px; --s-5: 24px;
  --s-6: 32px; --s-7: 48px; --s-8: 64px; --s-9: 96px; --s-10: 128px;

  /* Radius: one family. Sharp 4/6/8, soft 8/12/16 (default), round 10/16/24 */
  --r-sm: 8px; --r-md: 12px; --r-lg: 16px; --r-pill: 999px;

  /* Colour: neutrals + one accent + status */
  --bg: #f6f6f4;          /* page */
  --surface: #ffffff;     /* cards */
  --surface-2: #efefec;   /* hover, inputs, subtle fills */
  --ink: #18181a;         /* text, never pure black */
  --ink-2: #4a4a4f;       /* secondary text (7:1+) */
  --muted: #6e6e74;       /* labels, meta only (4.5:1+) */
  --line: rgba(24, 24, 26, 0.10);   /* hairlines */
  --accent: #1f6feb;      /* ONE accent: buttons, links, focus, primary series */
  --accent-ink: #ffffff;  /* text on accent */
  --good: #1a7f37; --warn: #9a6700; --bad: #cf222e; --info: #0969da;

  --shadow-hover: 0 6px 20px rgba(0, 0, 0, 0.06);
  --ease: cubic-bezier(.2, .7, .2, 1);
}

@media (prefers-color-scheme: dark) {
  :root {
    --bg: #0e0f11; --surface: #16171a; --surface-2: #1d1f23;
    --ink: #ececee; --ink-2: #b4b4ba; --muted: #8b8b93;
    --line: rgba(255, 255, 255, 0.09);
    --accent: #4c8dff; --accent-ink: #0b0c0e;
    --good: #3fb950; --warn: #d29922; --bad: #f85149; --info: #58a6ff;
    --shadow-hover: 0 6px 20px rgba(0, 0, 0, 0.35);
  }
}

*, *::before, *::after { box-sizing: border-box; }
html, body { margin: 0; }
body {
  font-family: var(--font); font-size: var(--t-base); line-height: 1.6;
  color: var(--ink); background: var(--bg);
  -webkit-font-smoothing: antialiased;
}
h1, h2, h3 { line-height: 1.12; letter-spacing: -0.02em; font-weight: 600; margin: 0; }
.num { font-variant-numeric: tabular-nums; }
.muted { color: var(--muted); }

.wrap { max-width: 1280px; margin: 0 auto; padding: 0 clamp(16px, 5vw, 80px); }
.grid { display: grid; grid-template-columns: repeat(12, 1fr); gap: var(--s-5); }
@media (max-width: 640px) { .grid { gap: var(--s-3); } }

.card {
  background: var(--surface); border: 1px solid var(--line);
  border-radius: var(--r-lg); padding: var(--s-5);
}
a.card { transition: transform .2s var(--ease), box-shadow .2s var(--ease); }
a.card:hover { transform: translateY(-2px); box-shadow: var(--shadow-hover); }

.btn {
  display: inline-flex; align-items: center; gap: var(--s-2);
  height: 44px; padding: 0 var(--s-5); border-radius: var(--r-sm);
  font: 500 var(--t-base)/1 var(--font); cursor: pointer;
  border: 1px solid var(--line); background: var(--surface); color: var(--ink);
  transition: background .15s, transform .1s;
}
.btn:hover { background: var(--surface-2); }
.btn:active { transform: translateY(1px); }
.btn--primary { background: var(--accent); color: var(--accent-ink); border-color: transparent; }
.btn--primary:hover { background: color-mix(in srgb, var(--accent) 88%, var(--ink)); }

:focus-visible { outline: 2px solid var(--accent); outline-offset: 2px; }

@media (prefers-reduced-motion: reduce) {
  * { animation: none !important; transition: none !important; }
}
```

## Notes

- Websites: use the larger sizes (`--t-hero`, `--t-4xl`) and big section spacing (`--s-9`,
  `--s-10`). Dashboards: headings at `--t-lg`/`--t-xl`, key numbers at `--t-3xl`, gaps at `--s-4`
  to `--s-5`.
- Pick the accent from the brand or subject. Avoid violet/lavender unless it is the real brand.
  Check it reaches 4.5:1 contrast with its button text, in both themes.
- Swap Inter for another face to give personality (Geist, Manrope, IBM Plex Sans; Source Serif 4
  or Fraunces for headings on a warmer brand), but keep to one or two families.
- If the page has a theme toggle, set the dark values on `:root[data-theme="dark"]` too, and guard
  the media query with `:root:not([data-theme="light"])`.
