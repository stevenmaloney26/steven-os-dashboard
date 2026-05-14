---
name: capture-the-idea
description: >
  Captures any raw idea or thought Steven drops — however messy or half-formed — files it instantly into raw/,
  and asks one follow-up question. Use this skill whenever Steven says "capture this", "log this idea",
  "I just had an idea", "note this down", "don't let me forget", "park this", "save this thought",
  or drops any idea or random thought that needs catching before it disappears. Also trigger if he says
  something like "idea:" or "thought:" at the start of a message, or if the message reads like a brain dump
  that he clearly wants stored rather than acted on immediately.
---

# Capture the Idea

Steven has a fast-moving brain — ideas arrive quickly and disappear just as fast. Your job is to be the catcher: take whatever he drops, make sense of it in seconds, file it properly, and get out of the way.

Speed and lightness matter here. This is not a planning session. Don't explore the idea, don't ask multiple questions, don't explain your reasoning at length. Capture, confirm, ask one thing.

## Step 1: Understand the idea

Read what Steven has shared. It might be a single sentence, a rambling paragraph, or just a few words. Extract:

- **The core of the idea** — what is he actually describing or suggesting?
- **Which domain it belongs to** — pick the best fit from this list based on CLAUDE.md:
  - `crm-client-work` — anything about Caterspares, dashboard builds, or client work
  - `trading-money` — stocks, crypto, investing, portfolio ideas
  - `building-selling` — turning the CRM into a product, pitches, pricing, prospects
  - `health-body` — diet, training, habits, fitness
  - `learning-intel` — AI tools, tech research, things to read or explore
  - `life-admin` — general life organisation, finances, admin, scheduling
  - `adventures-interests` — golf, photography, walks, travel, hobbies
  - `new-project` — if it doesn't fit any existing domain and feels like the seed of something new
- **Whether it links to an existing project** — check if it mentions or clearly relates to anything in `projects/` (caterspares-crm, plumber-crm, etc.)
- **1–3 tags** — short lowercase descriptors (e.g. `#ai`, `#revenue`, `#health`, `#golf`, `#tool`)

## Step 2: Create a short title

Write a clear, punchy title in 3–6 words that captures the essence. This is what Steven will scan later when reviewing raw/. Make it specific enough to be useful — "AI dashboard idea" is bad, "Auto-chase overdue Caterspares invoices" is good.

## Step 3: Save the file

Save a markdown file to `raw/` using this naming format:
```
raw/YYYY-MM-DD-[slug].md
```
Where `[slug]` is the title in lowercase with spaces replaced by hyphens (e.g. `2026-05-12-auto-chase-overdue-caterspares-invoices.md`).

Use this file template:

```markdown
# [Title]

**Date:** YYYY-MM-DD  
**Domain:** [domain]  
**Tags:** #tag1 #tag2 #tag3  
**Linked project:** [project name, or "none"]  
**Status:** raw

---

## Raw idea

[Steven's original words, exactly as he wrote them — don't paraphrase or clean up]

## Notes

[Any brief context you spotted that might be useful — a connection to another idea, a potential blocker, or a relevant tool. Keep this to 1–2 sentences max. Leave blank if nothing useful to add.]
```

## Step 4: Confirm and ask one question

Respond with a short confirmation — no more than 4 lines — then ask the single follow-up question.

Format:
```
Filed: **[Title]**  
Domain: [domain] | Tags: #tag1 #tag2  
[Linked to: project-name — only include this line if there's a project link]

Do you want to act on this now, park it for later, or just store it?
```

That's it. Don't elaborate. Don't start analysing the idea. Wait for his answer.

## If he says "act on it now"
Ask: "What's the first move?" then help him get started.

## If he says "park it" or "store it"
Say: "Stored. You'll find it in raw/ when you're ready." Nothing more.
