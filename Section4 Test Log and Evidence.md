# Section 4 – Test Log & Evidence

*Behavioural Influence & Ethical Theories · DoHabit ethics coursework Part 2*

- **App tested:** DoHabit web app ([dohabit.app](https://dohabit.app))
- **Testing started:** 16 November 2026, ~00:20 (Malaysia time)
- **Browser:** Google Chrome, separate test profile
- **Screenshots:** [`S4-evidence/`](S4-evidence/)

## 1. Status after Day 1

**Done**

- S4-T1 Explored the app and found every place streaks, badges and progress appear
- S4-T2 Created 3 habits (Walking 5/day, Read 10 mins, Drink 2 litres of water)
- S4-T3 Built a streak using "Done Y'day" (Read reached a 2-day streak)
- S4-T4 Captured 5 achievement pop-ups, 2 of them with mocking wording
- S4-T6 Confirmed there is no setting to turn off streaks, achievements or pop-ups
- Perfect Day achievement earned (all habits completed on 16 Nov)
- Achievement pop-up closes by clicking outside it, so there is no forced action

**Still to do**

I Swear I Did It!: reach 5 uses of "Done Y'day" in total and screenshot the pop-up
Missed-day test, 17–19 Nov (plan in section 5)
Scroll the full Achievements list and screenshot the locked achievements and hints

## 2. Where streaks, badges and progress appear (S4-T1)

| Where in the app | Feature / words | What it shows |
|---|---|---|
| Home screen, habit card | Flame icon + number | Current streak for that habit |
| Habit menu (tap a card) | "Done Y'day" / "Undo Y'day" | Lets you mark or unmark yesterday only |
| Statistics page | Current / Longest streak | Current and best streak |
| Statistics page | Completions by weekday, Total completions, Completions by month | Progress charts |
| Statistics page | Streak history ("Shows streaks of 2 days or more") | All past streaks |
| Menu → Achievements | Achievements list, Getting Started 3/5 | Earned and locked achievements, with hints |
| Pop-up dialog | "Achievement unlocked!" + icon, title, description | Appears when an achievement is earned |

## 3. Test log

| Test ID | What I did | What I expected | What actually happened | Evidence |
|---|---|---|---|---|
| S4-T1 | Opened the app and clicked every screen and setting | Find where rewards appear | Streak counter on every habit card; statistics page with Current/Longest streak and charts; Achievements page in the menu | S4-T1 screenshots |
| S4-T2 | Created 3 habits with different frequencies | Habits created | Walking (5/day), Read 10 mins (1/day), Drink 2 litres (1/day) created; colour and icon chosen per habit | S4-T2 screenshots |
| S4-T3 | Tried to mark past days; used "Done Y'day", then ticked today | Can mark any past day | Only today and yesterday can be marked. "Done Y'day" marked 15 Nov (streak 1); ticking 16 Nov gave Read a 2-day streak. Archiving and restoring a habit kept its streak | S4-T3 screenshots; `toggleYesterdayStatus.ts` |
| S4-T4 | Earned achievements (archived a habit, wrote a note after midnight, created habits, archived 5 habits, completed all habits) | Neutral, supportive congratulations | "Achievement unlocked!" modal over a dimmed screen, shown once per achievement, closed by clicking outside. Wording is humorous and in places mocks the user (see section 4) | S4-T4 screenshots; `useCheckAchievements.ts` |
| S4-T5 | Missed-day test – in progress (17–19 Nov) | Warning or pause before reset | Expected from code: streak survives one day (yesterday counts), then Current resets to 0 with no message; Longest and history kept | `getStreaks.ts`; screenshots to add |
| S4-T6 | Checked Menu, Appearance and Data Management | Option to turn rewards off | Settings cover theme, language, animations and calendar only. No option to disable streaks, achievements or pop-ups | S4-T6 screenshots |

## 4. Achievement wording (S4-T4b)

| Achievement | Triggered by | Exact wording (as shown in the app) |
|---|---|---|
| Clean Slate | Archiving first habit | "Out of sight, but not forgotten. You have successfully archived your very first habit." |
| The Dark Knight | Writing a note after midnight | "You wrote a note after 00:00. What's keeping you awake? Are you protecting Gotham, or just overthinking again?" |
| Overachiever of the Day! | Creating 3 habits in one day | "Wow, three habits in one day! Who knew you had this much free time? Procrastination looks good on you!" |
| I'll Be Back | Archiving 5 habits | "You've archived 5 habits — because why actually do them when you can just collect?" |
| Perfect Day! | Completing every habit (3 or more) in one day | "You've got 3 or more habits, and you've accomplished every single one!" (neutral and positive) |

**Why it matters:** creating habits is exactly what the app wants users to do, yet the reward calls them a procrastinator. Archiving is a legitimate way to manage goals, yet it is framed as laziness. Relevant to SE Code 4.01 (human values), Kant (respect for users as ends) and Mill (humour for some users, discouragement for others). Perfect Day shows that not every reward mocks the user.

## 5. Missed-day test plan (S4-T5)

| Day | What to do | Screenshot |
|---|---|---|
| 17 Nov | Tick all habits; use "Done Y'day" where still available | Streaks on statistics page |
| 18 Nov | Do **not** tick Walking; tick the others | Walking streak should still show (yesterday counts) |
| 19 Nov | Open the app before ticking anything | Walking: Current = 0, Longest kept, no warning message. Then tick it and screenshot the new streak and streak history |

## 6. Dark-pattern check (Gray et al., 2018) – S4-T7

| Type | Result so far |
|---|---|
| Nagging | Absent – each achievement pop-up appears only once |
| Obstruction | Partly – rewards cannot be turned off at all, but nothing is hidden |
| Sneaking | Unresolved – the streak rule (yesterday counts, then reset) is not explained in the app |
| Interface interference | Partly – mocking wording on some achievements |
| Forced action | Absent – the pop-up dims the screen but closes by clicking outside it |

