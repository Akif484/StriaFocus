StriaFocus — Prototype Feature Additions

Summary
- Implemented local-only prototype enhancements in `zengrid1.html`.

Key features added
- Assignments: due date field, priority, and urgency badges (Due Today / Due in N days / Overdue).
- Complete/Check-off: mark assignments done with strikethrough and +20 XP reward.
- Daily session logging & summary: tracks today's sessions and minutes; shown in header streak badge.
- Timetable: added Day column (Mon–Fri) for schedule realism.
- Study streak counter: shows consecutive days with sessions completed.
- Quote of the Day: rotating hardcoded motivational quote shown on launch.
- Rank milestone notifications: toast when leveling up.
- Subject color coding: subject badges carry color cues in timetable and assignments.
- Fullscreen focus mode: minimal UI distraction toggle from header.
- Subject notes: per-subject notes modal saved to localStorage.
- Exam countdown: add exams with date; nearest exam shown on launch.
- Flashcard builder: create local decks and cards (saved to localStorage).
- Local auth warning: explicit notice in the auth card that passwords are stored in plain text in localStorage.

Usage
1. Open [zengrid1.html](zengrid1.html) in a browser (double-click or serve via simple HTTP).
2. Create a local profile from the auth panel (demo only). Credentials are stored in localStorage under `stria_focus_auth_db`.
3. Add classes via "Add Class" (you can select day). Add assignments via "File Assignment" and set due date/priority.
4. Complete an assignment by pressing the check button — you'll earn XP and the item will strike through.
5. Use the header controls to toggle theme, enable fullscreen focus, and view your streak badge.
6. Open Flashcard Builder (Add Custom Session → Flashcards) to create decks locally.

Testing & Notes
- Data is persisted to localStorage per-user in `stria_focus_auth_db`.
- This is a prototype: do not store real passwords or sensitive info here.
- To inspect saved state, open DevTools → Application → Local Storage, look for `stria_focus_auth_db`.

Files changed
- [zengrid1.html](zengrid1.html)

Next steps
Next steps
- (Optional) polish UI, add animations, or connect to a real backend for secure auth and persistent storage.

New quick actions added
- Export / Import: from the Account modal, export your `stria_focus_auth_db` as JSON or import a JSON export. Importing can load either a full DB or a single app state into your logged-in profile.
- Backend connect (prototype): test a backend URL from the Account modal. This is a connectivity test only — it will report CORS/network failures.

UI polish
- Toasts now animate on enter/exit. Goal dots have a subtle pulse animation when active.

How to use export/import
1. Open the Account modal after logging in.
2. Click `Export Data` to download your local DB backup.
3. Use `Import` to load a previously exported JSON file. If importing an app state, log in first so the state attaches to your profile.
