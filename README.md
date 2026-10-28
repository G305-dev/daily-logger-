# ShipLog — Starfetch Web Portal (minimal)

> 🌐 **Open access:** anyone can view this site — no login, no roles, no menus.

The site has **3 pages** (tabs at the top) plus 2 actions:

1. 🚀 **Project page** — the **Project Title**, the project's **Main Goal**, and one general **Project Timeline** for the whole project. It opens first by default (`#Project` in the URL). Click **✏️ Edit title, goal & timeline** to select the overall **Project Start Date** and **Project Finish Date** with date pickers. There is no milestone form; Finish must simply be on or after Start. Existing milestone timelines from the previous version are automatically converted using the earliest start date and latest finish date.
2. 👨‍💻 **One page per developer** — Emmanuel (Frontend Development) and David (Backend Development) each have their **own page** (tabs at the top; anyone can view either, and `#Emmanuel` / `#David` in the URL open that page directly). A developer's page shows only **his** **Goal**, numbered **Tasks**, numbered **Expected Deliverable**, and **Logged Work / Proof** — newest day first, with previous days underneath.
3. ＋ **Add New Task** — a form with only 3 fields: **Goal**, **Tasks** (one per line, auto-numbered), and **Expected Deliverable** (one deliverable per line, auto-numbered). Use the button on a developer's page (or the header button, which acts on the open/last developer page) so it is saved under that developer.
4. ✍️ **Log Today's Work — a checklist, locked to one developer.** Opened from Emmanuel's page it is **Emmanuel's checklist only** (his Goal, Tasks and Expected Deliverable); opened from David's page it is **David's only**. The other developer's tasks are **not shown and cannot be ticked or logged** in that form — Emmanuel cannot log David's work and David cannot log Emmanuel's. **Tick the tasks that were done today** (optionally add a per-task note + hours, and shared proof — screenshot, live/demo link, GitHub link), then **Save checklist**: every newly ticked task is marked **Done** and logged under that developer's **Logged Work / Proof**. Tasks already Done appear ticked and locked, so re-opening the checklist never duplicates entries.

Everything else (stats dashboard, task board, daily log page, gallery, task table, banners, search, print/export toolbars) has been **removed by design**.

## Run it locally

Unzip, then either double-click `index.html`, or serve the folder:

```bash
cd dev-tracker
python3 -m http.server 5173        # Mac/Linux
py -m http.server 5173             # Windows
# open http://localhost:5173
```

> Data saves automatically in your browser's localStorage (key `shiplog_v2`) — the same key as previous versions, so existing goals/tasks/proof appear under the developers when you replace `index.html`. Always open it the same way in the same browser.

## Daily use

- **Morning:** each developer opens **his own page** (Emmanuel / David tab) and clicks **＋ Add New Task** → Goal / Tasks / Expected Deliverable.
- **During & end of day:** on **your own page**, open **✍️ Log Today's Work** and **tick off your tasks completed today**, then Save — ticked tasks become Done and the work/proof shows on your page. (You cannot tick or log the other developer's tasks from your checklist.)
- **Anyone checking progress:** open Emmanuel's page to see his Goal/Tasks/Expected Deliverable + Logged Work / Proof, then David's page for his — no login needed.
