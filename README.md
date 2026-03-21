# ActiveFit+ Beta Onboarding Guide

A lightweight, multi-platform tutorial site for beta testers to install and activate the ActiveFit+ beta build. The guide covers both iOS (via Firebase App Distribution) and Android (via Firebase App Tester), with step-by-step instructions, embedded video walkthroughs, and helpful tips for capturing screenshots and recording the screen.

---

## What's Inside

| File | Description |
|------|-------------|
| `index_landing.html` | Main landing page — platform selector (iOS / Android) |
| `ios_firebase_tutorial.html` | Step-by-step iOS installation guide via Firebase |
| `android_tutorial.html` | Step-by-step Android installation guide via Firebase App Tester |
| `index.html` | TestFlight-based iOS beta guide (original tutorial) |
| `icon.png` | App icon displayed across all pages |
| `Videos/` | Folder containing walkthrough MP4 videos per phase |
| `README.md` | This file |

---

## Site Structure

The site is organized around a central landing page that routes testers to the correct guide based on their device.

```
index_landing.html
├── ios_firebase_tutorial.html   (4 phases)
│     Phase 1 — Opening the Invitation Email
│     Phase 2 — Installing Firebase App Distribution
│     Phase 3 — Trust the Profile
│     Phase 4 — Download the App
│
└── android_tutorial.html        (3 phases)
      Phase 1 — Opening the Invitation Email
      Phase 2 — Installing Firebase App Tester
      Phase 3 — Allowing Unknown Sources & Installing

index.html                       (TestFlight guide — 5 phases + Tips)
      Phase 1 — Installing TestFlight
      Phase 2 — Installing ActiveFit+
      Phase 3 — Activating the Beta Request
      Phase 4 — Installing the Beta Build
      Phase 5 — Helpful Tips (screenshots & screen recording)
```

---

## Features

- **Platform selector** — testers choose iOS or Android from the landing page before starting
- **Step-by-step navigation** — each guide is divided into phases with Previous / Main Menu / Next Phase controls
- **Progress indicator** — a fixed top bar shows the current phase and overall progress
- **Embedded video walkthroughs** — each phase includes a video slot for MP4 or iframe content
- **Inline tips and warnings** — contextual notes are placed directly within the relevant step
- **Helpful Tips section** — the TestFlight guide includes a dedicated phase with iPhone screenshot and screen recording tutorials, including YouTube video references
- **Responsive design** — works on desktop and mobile browsers
- **Consistent UI** — all pages share the same design system, color palette, and typography

---

## How to Add Videos

Each phase contains a video slot. To add a video, locate the corresponding comment in the HTML and insert one of the following:

```html
<!-- Local MP4 -->
<video controls>
  <source src="Videos/phase1.mp4" type="video/mp4">
</video>

<!-- Google Drive embed -->
<iframe src="https://drive.google.com/file/d/YOUR_FILE_ID/preview"></iframe>

<!-- YouTube embed -->
<iframe src="https://www.youtube.com/embed/YOUR_VIDEO_ID"></iframe>
```

---

## For Maintainers

- To update step content, edit the relevant phase directly inside the HTML file — each phase is clearly labeled with a comment.
- To add a new phase, duplicate an existing `phase-panel` block and update the `goToPhase()` references and progress dots accordingly.
- The app icon is loaded from `icon.png` in the root directory. Replace this file to update the icon across all pages.
- All pages link back to `index_landing.html` as the main menu — if you rename this file, update the `href` in the back button of both tutorial files.

---

## Hosting

The site is hosted via **GitHub Pages** and is accessible at:

```
https://omargearkus.github.io/HowToAF/
```

To update the site, commit and push changes to the `main` branch. GitHub Pages will redeploy automatically within a few minutes.

---

> This guide is intended for internal beta testers only. Please do not share the link publicly.
