# FitQuest — Personal Fitness RPG

A gamified fitness tracking web app built for a 15-year-old, 190cm, BMI 14.4, dealing with anterior pelvic tilt. No gym. No equipment. 20 minutes a day at home.

---

## What It Is

FitQuest turns your daily workout into an RPG. You level up by actually completing sessions, defeat bosses to unlock new zones, track nutrition, and see your progress through charts. Everything is saved locally in your browser — no account, no server, no internet required after the first load.

---

## How to Use

1. Open `fitquest-v2.html` in your phone's browser
2. Tap **Add to Home Screen** (iOS: Share → Add to Home Screen / Android: browser menu → Add to Home Screen) for an app-like experience
3. Enter your warrior name and begin

That's it. Your data persists automatically via localStorage.

---

## Screens

### 🏠 Home
Your main dashboard. Shows current zone, level, XP bar, weekly streak, and today's dynamic missions. Tap **Start Today's Workout** to begin a guided session.

### ⚡ Train
Full exercise list for your current level, organized by phase (Warm Up → Main Work → Cool Down). Tap any exercise to see detailed trainer notes. The **Begin Guided Session** button walks you through every exercise step by step with auto-timers.

### 👹 Boss
Boss challenges unlock when you meet session count and level requirements — they aren't always available. Tick off each challenge as you complete it in real life, then claim victory. Bosses gate access to new zones.

### 🥗 Food
Log everything you eat from a pre-built Indian vegetarian food database (~30 items). Tap a food → adjust quantity → it's logged. Tracks calories, protein, carbs, fat, fiber, calcium, and iron against your daily targets. Water intake tracked separately with no maximum cap. Add custom foods if something isn't in the list.

### 📊 Stats
Six visualizations built from your recorded data:
- **Activity Heatmap** — 56-day grid, darker = more XP
- **Level Progress** — dual radial rings for XP and session count toward next level
- **XP Per Day** — 14-day bar chart
- **Sessions Per Week** — 8-week history, color coded by volume
- **Nutrition 7-day chart** — switchable between all macros and micros, with min/ideal reference lines
- **Nutrient Radar** — today's intake across 6 nutrients vs your targets
- BMI calculator with history

---

## Progression System

### Zones & Levels
| Zone | Levels | Theme |
|------|--------|-------|
| Rookie Grounds | 1–3 | Build the habit, fix APT foundation |
| Iron District | 4–6 | Real push-ups, resistance, power |
| Power Forge | 7–9 | Planned for future unlock |

You advance levels by completing a minimum number of sessions **and** reaching the XP threshold for the next level. Levels 3 and 6 require defeating the zone boss instead of a session count.

### XP
- Completing a full guided workout session: **+80 XP**
- Completing a dynamic mission: **+20–80 XP** depending on mission
- Defeating a boss: **+150–300 bonus XP**
- One workout per day maximum — no exploit possible

### Bosses
Bosses unlock when you hit a minimum session count and level. They aren't available from day one. Each boss has 4 real-world physical challenges you tick off after completing them. All 4 must be done to claim victory.

### Dynamic Missions
Missions are generated from your actual data — they change based on your streak, recent nutrition logs, workout history, and boss availability. Examples:
- *You're on a 5-day streak. Don't break it.*
- *Your last 3 days averaged under 50g protein. Hit 70g today.*
- *You haven't trained in 2 days. Get back on the mat.*
- *3 sessions this week. Hit a 4th for a streak bonus.*

---

## Nutrition Targets

Based on a 15-year-old male, 190cm, trying to gain weight and build muscle:

| Nutrient | Minimum | Ideal |
|----------|---------|-------|
| Calories | 2200 kcal | 2700 kcal |
| Protein | 70g | 90g |
| Carbs | 250g | 350g |
| Fat | 50g | 80g |
| Fiber | 25g | 35g |
| Calcium | 1000mg | 1300mg |
| Iron | 11mg | 15mg |

---

## Guided Workout Timer

The guided session auto-walks through every exercise in order:
- **Timed exercises** (planks, stretches, holds) — countdown runs automatically, auto-advances after completion with a 1.2 second buffer
- **Rep exercises** (push-ups, squats, bridges) — shows rep count and a **Done → Next** button
- **Rest periods** — countdown between sets, auto-advances
- Pause button available on all timed steps
- Quit button shows inline confirmation — no XP awarded for incomplete sessions

---

## APT (Anterior Pelvic Tilt) Notes

Every session includes APT-specific work baked in:
- Glute bridges and single-leg variations (strengthens weak glutes)
- Dead bug (core stability, lumbar control)
- Bird dog (hip and spine stability)
- Hip flexor stretches in every cool-down — **never skipped**
- Superman holds (lower back strengthening)

The cool-down is not optional. The hip flexor stretch is the single most important thing for correcting APT caused by prolonged sitting.

---

## Technical Notes

- Single HTML file, no frameworks, no build tools
- All data stored in `localStorage` under key `fitquest_v2_state`
- Charts drawn on native Canvas API — no external chart libraries
- Fonts loaded from Google Fonts (requires internet on first load, then cached)
- Works offline after first load if added to home screen
- To reset all data: open browser console and run `localStorage.clear()` then refresh
