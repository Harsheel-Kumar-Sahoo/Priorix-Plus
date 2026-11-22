<div align="center">

<img src="icons/icon.svg" width="96" height="96" alt="Priorix logo">

# Priorix

**A minimal, installable task manager that tells you what to do next.**

<a href="https://priorix-plus.vercel.app"><b>Open the live app &rarr; priorix-plus.vercel.app</b></a>

<a href="https://priorix-plus.vercel.app"><img src="https://img.shields.io/badge/live-priorix--plus.vercel.app-000000?style=flat-square&logo=vercel&logoColor=white" alt="Live demo"></a>
<img src="https://img.shields.io/badge/PWA-installable-4f46e5?style=flat-square" alt="PWA">
<img src="https://img.shields.io/badge/offline-ready-0ea5e9?style=flat-square" alt="Offline ready">
<img src="https://img.shields.io/badge/dependencies-none-10b981?style=flat-square" alt="No dependencies">
<img src="https://img.shields.io/badge/stack-HTML%20%7C%20CSS%20%7C%20JS-64748b?style=flat-square" alt="Stack">

</div>

---

Bored, overwhelmed or just stuck? Add your tasks with deadlines and priorities, tap **What to do**, and Priorix ranks everything for you. It's a single-page app with no build step, no framework and no account.

## <img src="https://api.iconify.design/lucide/rocket.svg?color=%236366f1" width="24" height="24" align="absmiddle" alt="">&nbsp; Features

| | Feature | Details |
|:-:|---|---|
| <img src="https://api.iconify.design/lucide/wand-sparkles.svg?color=%236366f1" width="20" height="20" align="absmiddle" alt=""> | **What to do** | Ranks open tasks by priority and deadline urgency, and explains each pick |
| <img src="https://api.iconify.design/lucide/flag.svg?color=%236366f1" width="20" height="20" align="absmiddle" alt=""> | **Priority levels** | Low, medium and high, colour-coded on every card |
| <img src="https://api.iconify.design/lucide/calendar.svg?color=%236366f1" width="20" height="20" align="absmiddle" alt=""> | **Deadline date** | Overdue and due-soon tasks are highlighted automatically |
| <img src="https://api.iconify.design/lucide/clock.svg?color=%236366f1" width="20" height="20" align="absmiddle" alt=""> | **Deadline time** | Optional exact time for same-day planning |
| <img src="https://api.iconify.design/lucide/link.svg?color=%236366f1" width="20" height="20" align="absmiddle" alt=""> | **Links** | Attach several links per task and open them in one tap |
| <img src="https://api.iconify.design/lucide/search.svg?color=%236366f1" width="20" height="20" align="absmiddle" alt=""> | **Search and sort** | Smart order, deadline, priority or newest; Active, Done and All tabs |
| <img src="https://api.iconify.design/lucide/trending-up.svg?color=%236366f1" width="20" height="20" align="absmiddle" alt=""> | **Progress stats** | Active, overdue and completion percentage at a glance |
| <img src="https://api.iconify.design/lucide/smartphone.svg?color=%236366f1" width="20" height="20" align="absmiddle" alt=""> | **Mobile first** | Responsive layout with a floating add button |
| <img src="https://api.iconify.design/lucide/zap.svg?color=%236366f1" width="20" height="20" align="absmiddle" alt=""> | **Works offline** | Service worker caches the app after the first visit |
| <img src="https://api.iconify.design/lucide/lock.svg?color=%236366f1" width="20" height="20" align="absmiddle" alt=""> | **Private** | Data lives in your browser's local storage and never leaves your device |

## <img src="https://api.iconify.design/lucide/target.svg?color=%236366f1" width="24" height="24" align="absmiddle" alt="">&nbsp; How "What to do" works

Every open task gets a score. The highest score comes first.

> **score = priority weight + urgency bonus**

| Priority | Weight | | Deadline | Bonus |
|---|:-:|---|---|:-:|
| High | 36 | | Overdue | 50 |
| Medium | 24 | | Under 3 hours | 40 |
| Low | 12 | | Under 24 hours | 30 |
| | | | Under 3 days | 20 |
| | | | Under 7 days | 10 |
| | | | Later | 3 |
| | | | No deadline | 0 |

So an overdue low-priority task (62) outranks a high-priority task due next week (46), while a high-priority task due today (66) beats both.

## <img src="https://api.iconify.design/lucide/download.svg?color=%236366f1" width="24" height="24" align="absmiddle" alt="">&nbsp; Install

Open **[priorix-plus.vercel.app](https://priorix-plus.vercel.app)** on your phone or computer to install it right away. Priorix needs to be served over **HTTPS** to be installable. Hosting is free on Netlify Drop, GitHub Pages or Cloudflare Pages.

| Platform | Steps |
|---|---|
| **Android (Chrome)** | Tap **Install** in the app header, or menu, then *Install app* |
| **iPhone (Safari)** | Tap **Share**, then *Add to Home Screen* |
| **Desktop (Chrome / Edge)** | Click the install icon in the address bar |

## <img src="https://api.iconify.design/lucide/code.svg?color=%236366f1" width="24" height="24" align="absmiddle" alt="">&nbsp; Run locally

No build tools are needed. Serve the folder with any static server:

```bash
# Python
python3 -m http.server 8080

# or Node
npx serve .
```

Then open `http://localhost:8080`. Service workers work on `localhost` even without HTTPS.

## <img src="https://api.iconify.design/lucide/folder.svg?color=%236366f1" width="24" height="24" align="absmiddle" alt="">&nbsp; Project structure

```
priorix/
├── index.html              # App: markup, styles and logic
├── manifest.webmanifest    # PWA metadata
├── sw.js                   # Service worker (offline cache)
├── icons/
│   ├── icon.svg
│   ├── icon-192.png
│   ├── icon-512.png
│   └── icon-maskable-512.png
└── README.md
```

## <img src="https://api.iconify.design/lucide/palette.svg?color=%236366f1" width="24" height="24" align="absmiddle" alt="">&nbsp; Customise

- **Colours:** edit the CSS variables at the top of `index.html` (`--accent`, `--accent2`, `--bg` and so on).
- **Ranking:** change the `W` weights and the `urgency()` function in the script.
- **Updates:** after changing any file, bump `CACHE='priorix-v1'` in `sw.js` so installed copies refresh.

## <img src="https://api.iconify.design/lucide/lock.svg?color=%236366f1" width="24" height="24" align="absmiddle" alt="">&nbsp; Data and privacy

Tasks are saved to `localStorage` under the key `priorix`. Nothing is sent to a server. Clearing your browser data removes your tasks, and data is not shared between devices.

## <img src="https://api.iconify.design/lucide/map.svg?color=%236366f1" width="24" height="24" align="absmiddle" alt="">&nbsp; Roadmap ideas

- [ ] Export and import as JSON
- [ ] Recurring tasks
- [ ] Reminders and notifications
- [ ] Dark mode
- [ ] Subtasks

---

<div align="center">

<sub>Built to answer one question: <b>what should I do next?</b></sub>

</div>
