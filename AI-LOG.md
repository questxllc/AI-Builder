# AI Log: Bilang Ride

## Lab 2: Add a Database to Your Site (Nov 2026)

**What I asked Claude:** Use the QuestX Lab 2 instructions and recode my site to use the class database.

**What changed:**
- Added the QuestX class data helper script (`questx-data.js`, `data-site="questxllc"`).
- New **💬 Guestbook & Poll** screen for grown-ups, opened from the home screen:
  - Guestbook: first name (40 characters max) and message (300 max). Shows the 20 newest notes. Saved in the `guestbook` collection.
  - Poll: "Which Bilang Ride game does your child enjoy most?" Saved in the `votes` collection as `{choice}`. Results show totals, a bar and a percentage.
- Visitors' words are shown with `textContent`, never `innerHTML`, so nobody can inject code.
- The helper loads with `defer`, so the counting games still work offline or if the database is down.
- Each browser can vote once (remembered on that device). Someone could still vote again in another browser.

**Peek at the data:**
- https://class-data.questx-classroom.workers.dev/api/questxllc/guestbook
- https://class-data.questx-classroom.workers.dev/api/questxllc/votes?count=choice
