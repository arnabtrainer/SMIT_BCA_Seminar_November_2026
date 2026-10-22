# 🛠️ Module 4 — AI Can Help Me Build
## From an Idea to a Working Application | Complete Presenter Guide & Copy-Ready Prompts

**Programme:** AI in Action — Learn • Create • Build  
**Demonstration project:** My Smart Planner  
**Primary AI environment:** Claude — interactive Artifact / small application  
**Prepared safety net:** `03_My_Smart_Planner_OFFLINE.html` (independent, offline-first sample application)  
**Suitable for:** First-time learners, students, educators and workplace teams.

> **TRAINER-ONLY RESOURCE.** This consolidated guide intentionally includes facilitator scripts, contingencies and optional timing. It is not intended for projection or participant distribution. The separate audience PowerPoint contains no timings, instructions or speaker notes.

---

## 1. The one-sentence idea

**“What if we could turn a plain-language requirement into a useful working app, test it immediately, then improve it through conversation?”**

This module demonstrates **AI-assisted application creation**—not automatic programming expertise, not a guaranteed production application, and not an app that secretly runs an AI model. A basic planner uses deterministic code after AI has helped create it.

### Learner outcomes

Participants will see how to:
- 💡 Turn a practical problem into simple requirements.
- ✍️ Give Claude a clear application-building prompt.
- 🧩 Interact with an AI-generated app instead of stopping at source code.
- 🧪 Verify buttons, calculations, empty states and stored information.
- 🎨 Refine the appearance or add a feature using a follow-up prompt.
- 🔒 Distinguish an **offline demo** from a connected, cloud-backed production service.

---

## 2. The application to build

**My Smart Planner** — a responsive task and progress dashboard for **Study** and **Work** contexts.

| Area | User-visible feature | Success criterion |
|---|---|---|
| Tasks | Add, edit, complete, reopen, delete | Updates appear immediately; user confirmation for destructive actions |
| Information | Name, optional notes, due date, priority, category, estimated minutes | Input is validated; never silently creates empty tasks |
| View | Study / Work mode | Switching modes displays independent task sets |
| Productivity | Search, status filters, sorting | Results are correct and predictable |
| Insight | Total, completed, due today, overdue, progress ring/bar | Values update after mutations; progress = completed / total |
| Suggestions | Next task based on overdue, priority and date | Transparent rule, **not** a fabricated AI recommendation |
| Styling | Responsive desktop/mobile, dark/light mode | Readable on both; no horizontal scrolling on mobile |
| Portability | JSON export/import; CSV export | Data can be backed up and restored |
| Data | Local browser storage where available | No account, server or API key needed for the supplied HTML demo |
| Safety | Confirmation and undo for deletion; safe text display | Entered text is not interpreted as HTML |

### Application's scope (state explicitly if questioned)

- The **provided HTML** is a complete working example, built independently for this workshop. It does **not** connect to Claude, perform LLM inference, send reminders, sync devices, or support collaboration.
- Claude's generated Artifact is a **separate outcome**: the code and features may differ from the prepared HTML. Evaluate what Claude actually creates.
- Saving tasks locally works only if browser storage is permitted. Use **Export JSON** before resetting browser storage, changing devices, or sharing a computer. Private/incognito sessions may discard entries.
- AI-assisted development speeds up prototyping; it does not replace software review, tests, privacy controls or hosting decisions.

---

## 3. Before the seminar — simplest setup

**Have only these two files open during delivery:**
1. `01_PRESENTER_MASTER_WITH_NOTES.pptx`
2. `02_ALL_IN_ONE_DEMO_GUIDE_PRIVATE.md`

Also prepare browser tabs: `https://claude.ai/` and the local HTML application. An internet connection is needed for Claude generation; **the supplied HTML demo itself is offline-first**.

**Account check:** Log into Claude. Anthropic's current guidance says Artifacts can be created in chat, and **Code execution and file creation** may need to be enabled in **Settings → Capabilities**. The UI and account entitlements can change; look for an interactive application/Artifact output rather than a specific button label. Official: https://support.claude.com/en/articles/17153992-what-are-artifacts-and-how-do-i-use-them

Optional: open the supplied offline app in Chrome/Edge/Firefox to demonstrate the completed result immediately. Browser storage permissions vary by device.

---

## 4. Step-by-step live narrative and prompts

### STEP A — Start from a problem

**Example client requirement:**

> “I keep forgetting what to do next. I need a friendly daily planner that works for studying and office tasks. I want to see progress and priorities at a glance.”

Prompt the audience: “What is one thing you would expect a planner to do?” Collect two ideas (e.g., add a deadline, tick a task as complete). Explain that these are **requirements**, not programming syntax.

### STEP B — Prompt 1: Generate the app

Open a new Claude conversation. Copy everything inside this block:

```text
You are an experienced product designer and front-end software engineer.

Build a polished, working, interactive application named "My Smart Planner" as a Claude Artifact that I can use directly in its preview. This is a demonstration for a mixed audience of students, educators and working professionals, so use accessible language and a clean, attractive design.

FUNCTIONAL REQUIREMENTS:
1. Create tasks with a required title, optional notes, optional due date, priority (High/Medium/Low) and category.
2. Edit, mark complete/incomplete and delete tasks. Confirm deletion.
3. Provide "Study" and "Work" modes, each with its own sample tasks and task collection.
4. Search tasks; filter by All/Pending/Completed/Today/Overdue; sort by due date, priority and newest.
5. Show accurate totals: all tasks, completed, due today, overdue, and a progress percentage with an attractive visual progress indicator.
6. Make the app responsive and accessible on laptops and phones. Use a professional blue/teal theme with light/dark mode.
7. Add useful sample data so the app looks complete when first opened.
8. If persistent local storage is supported in this Artifact environment, use it safely; if not, state the limitation clearly. Do not claim persistence unless implemented and tested.

QUALITY REQUIREMENTS:
- All visible buttons must function. Use sensible empty states and basic form validation.
- Keep the initial implementation self-contained; avoid paid APIs, external services, logins, credentials, analytics and collecting personal information.
- Show the WORKING INTERACTIVE APP, not only a code listing or mockup.
- Make clear that task prioritization is a transparent rule, not live AI inference.
- Do not invent a backend or pretend tasks sync across devices.

After creating the app, summarize what works and what still needs testing in five concise bullets.
```

**What to show:** The interactive preview. Add a new task; select high priority; mark completed; inspect the progress value. Do not imply that the first AI output is bug-free.

### STEP C — Prompt 2: Refine the design

```text
Keep all currently working features and existing task data. Improve the interface with a more premium, spacious dashboard layout: readable typography, subtle shadows, strong contrast, better mobile spacing, clear priority badges, and a dark/light theme switch. Do not break the task editor, filters, or progress calculations. Explain any features you had to change.
```

### STEP D — Prompt 3: Test like a developer

```text
Act as a meticulous QA engineer. Review the current My Smart Planner code and test or reason through these cases:
- Add a task with valid fields; reject an empty title.
- Edit title/priority/date and confirm it updates everywhere.
- Complete and reopen tasks; verify the percentage calculation.
- Delete with confirmation; ensure a cancelled deletion leaves data unchanged.
- Switch Study/Work modes; ensure their tasks remain separate.
- Search for a known task; verify pending/completed/today/overdue filters.
- Check deadlines across yesterday, today and tomorrow.
- Check dark mode, empty state and mobile layout.
- Verify whether data survives a page refresh. If not, disclose that limitation.
- Escape user text safely; do not render entered HTML as executable markup.

Fix concrete defects, then provide a short pass/fail table with evidence from tests that actually ran. Clearly label any checks that you could not execute. Do not claim all tests passed without evidence.
```

### STEP E — Prompt 4: Add one live audience feature

```text
Please add a small celebration message when all tasks in the selected Study or Work mode are completed. Preserve all current features. Test that the celebration only appears when there is at least one task and every task in that mode is complete. Keep the UI professional and accessible.
```

### STEP F — Show the prepared offline application

Open `03_My_Smart_Planner_OFFLINE.html` in a modern desktop browser. This ready-to-run demo is **independent from the Claude Artifact** and can be used if the AI generation is delayed. Suggested tour:

1. Study mode → inspect sample tasks and progress.
2. Add a task due today with high priority.
3. Mark it complete; observe totals/progress change.
4. Switch Work mode; confirm different tasks.
5. Search, filter, and toggle dark mode.
6. Download JSON backup; optionally export CSV.
7. Explain that data is stored in the local browser, not a cloud account.

**Offline app shortcut:** Double-click the HTML file. It needs no installation, web server, API key or JavaScript library. Some browser policies may block local storage; the app warns and still works temporarily, but JSON export is then essential.

---

## 5. How the finished planner works (easy to explain)

**Task data → app logic → screen updates.**

- Each task has a unique ID, title, mode, priority, optional due date and a completed flag.
- Completing a task changes its status and the dashboard recomputes the totals.
- Progress is `completed tasks ÷ total tasks × 100` (0% when no tasks exist).
- A task is **overdue** only if unfinished and due before today.
- A due-today task appears in the **Due Today** count only while pending.
- The suggested next task uses a predictable ordering: unfinished tasks first, then overdue tasks, then priority, then date; this is not a learned AI model.
- Study and Work tasks coexist in one dataset but display in their respective modes.

**Quick classroom example:** Four tasks, one completed → progress is 25%. Complete one more → progress becomes 50%.

---

## 6. Test checklist for the supplied offline app

Use this to rehearse. Expected results should match the behavior observed in the app—not merely what a prompt requested.

| Test | Action | Expected result |
|---|---|---|
| Create | Add a task called “Finish report” | New card and total count increment |
| Validation | Submit a blank title | Browser prevents saving |
| Edit | Change title and priority | Card updates correctly |
| Complete | Tick and untick a task | Completed total and progress update |
| Delete | Choose ×, cancel confirmation | No deletion |
| Delete/undo | Confirm deletion, then Undo | Task restored |
| Modes | Switch Study ↔ Work | Two distinct task sets shown |
| Search | Search for “presentation” | Only matching tasks shown |
| Filters | Pending, Completed, Today, Overdue | Relevant set shown |
| Export | Download JSON and CSV | Two downloadable files |
| Restore | Import a valid app JSON backup | Tasks restored after confirmation |
| Invalid import | Import broken JSON | Friendly failure message; previous data retained |
| Theme | Toggle dark/light | Colours change without losing tasks |
| Responsive | Narrow browser to phone width | No horizontal overflow |
| Data continuity | Reload browser | Tasks remain if local storage is permitted |
| HTML safety | Enter text containing `<img...>` | Displays as text rather than an image or script |

---

## 7. Working offline app: precise capabilities and limitations

- The HTML file is a **single-file standalone application**; its CSS and JavaScript are embedded.
- Its browser data model contains a `version: 1` JSON payload and task list. Import checks the schema, task titles, unique IDs, priorities and basic field limits.
- Supports up to **3,000 tasks per imported file** with a 2 MB file-size ceiling; actual browser storage capacity depends on browser policy.
- Exports tasks as JSON (backup/restore) or CSV (analysis in Excel/Sheets).
- Does not provide push reminders, phone notifications, cloud storage, user accounts, server/database sync, concurrent edits, AI inference or integrations.
- Does not guarantee accessibility certification or enterprise security compliance; for production use, formal accessibility, security and cross-browser validation are required.

**Data hygiene:** Use fictional task descriptions for the public demonstration. Avoid uploading real academic records, client data, passwords, confidential deliverables or employee information.

---

## 8. Practical delivery plans — PRIVATE

| Delivery version | Suggested use | Approx. presenter time |
|---|---|---:|
| Short showcase | Earlier modules ran long: demonstrate prebuilt app and one prompt | 5–8 minutes |
| Standard | Generate Claude app, test two interactions, show prepared backup | 15–25 minutes |
| Extended | Improve the UI, test multiple edge cases, compare Claude and offline app | 35–60 minutes |

These numbers **must never appear in audience slides or shared notes**.

### If live generation stalls

1. Never describe a non-functioning preview as successful.
2. Open the standalone HTML sample immediately.
3. Demonstrate task creation, progress and mode switching.
4. Show Prompt 1 to explain how participants can reproduce the exercise.
5. Return to the final takeaway: **Describe → Build → Test → Improve.**

### Presenter speaking outline

- **Opening:** “Today, we’re not learning a programming language. We’re learning how to express a software requirement clearly.”
- **Before generation:** “A good requirement includes what the user can do and how we know the result works.”
- **After generation:** “An attractive screen is only the beginning. Let’s test its behavior.”
- **Before improvement:** “Now we can ask for an enhancement without rewriting our entire specification.”
- **Closing:** “AI gives us a head start. Human judgement and testing make it useful.”

### Strong participant questions

- What should a planner do if there are zero tasks?
- Should an overdue count include tasks that are already finished?
- What happens to saved tasks if someone opens the app on a different laptop?
- Is selecting a high-priority task evidence of AI learning—or just a rule?

---

## 9. Visual identity and presentation use

- 16:9 widescreen; navy, royal blue, cyan/teal and clean white.
- Minimal, large text; real screenshot from the working app.
- Appropriate emoji use: 💡 idea, ✍️ prompt, 🧩 app, 🧪 testing, 🎨 improvement, 🚀 outcome.
- Do not show the time budget, backup plan or speaker instructions on audience slides.
- A trainer edition of the deck contains slide-wise speaker notes; the clean audience edition does not.

---

## 10. Official resource links

- Claude: https://claude.ai/
- Claude help — Artifacts: https://support.claude.com/en/articles/17153992-what-are-artifacts-and-how-do-i-use-them
- Claude help — sharing artifacts: https://support.claude.com/en/articles/9547008-share-artifacts

**Reminder:** Artifacts may use Claude-managed infrastructure and account-specific features. The offline HTML file is a separate implementation designed to run locally without network access. Do not equate the two data-storage models.

**Transition to Module 5:** “We've seen AI help us learn, create and build. Next, let's reflect on the opportunities, test our understanding and share feedback.”
