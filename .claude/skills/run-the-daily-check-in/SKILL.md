---
name: run-the-daily-check-in
description: >
  Produces a clean daily health card for Steven showing today's meals, workout, and habit targets — then prompts him to log yesterday.
  Use this skill whenever Steven says "daily check-in", "what's my plan today", "health check", "what should I eat today",
  "what's my workout today", "morning check-in", or any variant asking what he should eat or train today.
  Also trigger if he asks how the day looks from a health or fitness angle.
---

# Daily Health Check-In

Steven wants a fast, scannable daily card — not a lecture, not a wall of text. Get in, show what matters, get out. The whole output should be readable in 30 seconds.

## Step 1: Read the plans

Read both files:
- `references/diet-plan.md` — meal options for each part of the day
- `references/workout-plan.md` — session for each day of the week + 7-week progression

## Step 2: Determine today's context

You need two things:

**Day of week** — use today's date to identify the day (Monday, Tuesday, etc.). This maps directly to the workout plan:
- Monday → Upper Body Strength (Back Focus)
- Tuesday → Lower Body + KneesOverToes
- Wednesday → Mobility Day
- Thursday → Upper Body Hypertrophy
- Friday → Lower Body Power (Golf Power)
- Saturday → Core + Neck + Speed + Golf Speed Training
- Sunday → Rest day

**Programme week** — check if `references/programme-start.md` exists. If it does, read the start date and calculate which of the 7 weeks Steven is currently in. If the file doesn't exist, ask him: "What date did you start the programme? I'll track your week from there." Then save his answer to `references/programme-start.md` as:
```
Start date: YYYY-MM-DD
```

## Step 3: Pick today's meals

The diet plan has 5 options per meal slot. Rather than listing all 5, pick one suggestion for each slot — rotate through them so it doesn't feel repetitive. A simple rule: use (day_of_week_number mod 5) + 1 to pick the option number. So Monday = option 2, Tuesday = option 3, etc. This gives variety without randomness. Remember the current offset so you can shift it if Steven asks for a swap (see Meal Swap below).

Show meals for: Breakfast, Morning Snack, Lunch, Afternoon Snack, Dinner, Pre-Bed.

**Weekend note:** Saturday and Sunday flag as "Free recipe day — cook what you fancy, just keep it on-plan ingredients."

## Step 4: Identify today's habits

These are the same every day regardless of training:
- Supplements: creatine (5g), magnesium glycinate (400mg before bed), fish oil (2g), collagen (10g), vitamin D3 (2000 IU)
- Daily walk: 20–30 minutes
- Hydration: water throughout the day
- Pre-bed: one of the pre-bed snack options

## Step 5: Write the daily card

Use this exact structure:

---

## Daily Check-In — [Day], [Date] *(Week [N] of 7)*

### Today's Meals
**Breakfast:** [meal]
**Snack:** [meal]
**Lunch:** [meal]
**Snack:** [meal]
**Dinner:** [meal]
**Pre-bed:** [meal]

*Not feeling these? Say "swap meals" or "give me different meals" for a fresh set.*

### Today's Workout
**[Session name]**
[List exercises with sets x reps — keep it tight, one line per exercise]

*[Week progression note — e.g. "Week 3–4: increase weight 5–10%"]*

### Today's Habits
- [ ] Supplements (creatine, mag glycinate, fish oil, collagen, D3)
- [ ] 20–30 min walk
- [ ] Pre-bed snack done

---

*Yesterday: How did training go, and what did you eat? Drop a quick note and I'll log it.*

---

## Meal Swap

If Steven says "swap meals", "give me different meals", "not feeling these", or similar, regenerate the meals section only using the next offset: (current_offset + 1) mod 5. So if today's card used option 3, the swap uses option 4. If he swaps again, use option 5, then wrap back to option 1.

Reprint only the **Today's Meals** section with the new options — don't reprint the whole card. Keep the swap prompt line at the bottom of the meals section so he can keep swapping if needed.

Example response to a swap request:
```
### Today's Meals (swapped)
**Breakfast:** [new meal]
**Snack:** [new meal]
**Lunch:** [new meal]
**Snack:** [new meal]
**Dinner:** [new meal]
**Pre-bed:** [new meal]

*Still not right? Say "swap meals" again.*
```

## Rules

- **Under 200 words total.** Cut anything that doesn't help Steven act.
- **No explanations, no motivational filler.** Just the plan.
- **Rest day (Sunday):** Replace workout section with "Rest day — mobility and walking only."
- **Mobility day (Wednesday):** Show the mobility stretches from the plan, not gym exercises.
- **The log prompt is always the last line** — one sentence, never more.
