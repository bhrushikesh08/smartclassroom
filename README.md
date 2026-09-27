# 📋 Digital Circular System — Smart Classroom Prototype

A real-time, IoT-ready web system that replaces physical, attender-based
circulars in polytechnic colleges with instant digital notices on a
classroom screen — built as a smart-classroom initiative for **SBTET
polytechnic colleges, Andhra Pradesh**.

**🔗 Live demo:** `https://bhrushikesh08.github.io/smartclassroom/` 

---

## The problem

In a typical SBTET polytechnic, when the Principal or a HOD needs to send
out a circular, an attender walks it, on paper, to every classroom in
their department. That means:

- No fixed delivery time — depends entirely on the attender's availability
- No record of which classrooms actually got the notice
- Urgent notices (e.g. "classes suspended from 11 AM") often arrive late
- Paper notices get lost, torn, or never put up at all

This project digitizes that entire flow: a circular published from an
admin console reaches every relevant classroom screen within seconds.

## Features

- **Role-based access** — Principal (publishes to all departments or a
  chosen one) and 4 HODs (CSE / ECE / EEE / MECH, scoped to their own
  department only)
- **Live classroom display** — a full-screen view per department that
  updates the instant a circular is published, no refresh needed
- **Priority levels** — urgent circulars surface as a banner, distinct
  from routine notices
- **Seen tracking** — each display can mark a circular as seen, giving
  the issuer a simple read-count
- **Delete** — Principal can remove any circular; a HOD can remove
  circulars they issued or that targeted their own department
- **Persistent, real-time backend** — powered by Firebase Realtime
  Database (free tier), so it works live across different devices over
  the internet, not just in one browser

## Tech stack

| Layer | Technology |
|---|---|
| Frontend | Plain HTML, CSS, JavaScript (no build step, no framework) |
| Real-time data | Firebase Realtime Database (free tier) |
| Hosting | GitHub Pages / Netlify (free static hosting) |
| Fonts | Source Serif 4, IBM Plex Sans (Google Fonts) |

Everything lives in a single `index.html` file — easy to read, edit, and
deploy with zero setup tooling.



## Project structure

```
├── index.html   # entire app — UI, styling, and logic in one file
└── README.md    # this file
```

## Limitations & what a production rollout would add

- The PIN gate is a demo convenience, not real authentication — a real
  deployment would use the college's SSO/staff login system

- Firebase "test mode" rules are public read/write — fine for a
  controlled demo link, but production would add Firebase
  Authentication + locked-down rules

- This prototype covers the **software layer only**; a classroom rollout
  additionally needs a low-cost always-on screen (existing classroom
  TV/monitor + a Raspberry Pi or Android TV stick running this page in
  kiosk mode) — no new wiring beyond power to the screen

## Future scope

- Companion mobile app / SMS fallback for students off-campus
- Extending the same screens to timetables, exam seating, and substitution alerts
- Analytics dashboard for circular frequency and department-wise seen rates

---

Built By - B. Hrushikesh
— portfolio project.
