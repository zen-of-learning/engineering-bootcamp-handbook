# Engineering Bootcamp Handbook

A practical multi-course engineering handbook for backend and JavaScript/frontend bootcamp students.

Published as a GitHub Pages documentation site at **[https://indapmgr.github.io/engineering-bootcamp-handbook/](https://indapmgr.github.io/engineering-bootcamp-handbook/)**.

---

## 📚 Course Paths

| Course | Start Here | Focus |
|--------|------------|-------|
| Backend Engineering Handbook | [Part 1](part-1-development-environment.md) | Development setup, FastAPI, virtual environments, API testing, PostgreSQL, Docker, debugging, Git, and backend capstone work |
| JavaScript Frontend Bootcamp | [JavaScript Overview](javascript/index.md) | ES6+ basics, arrays, objects, DOM, events, forms, async JavaScript, `fetch`, API-driven UI, and a final frontend project |

---

## Backend Handbook Contents

| Part | Title |
|------|-------|
| [Part 1](part-1-development-environment.md) | Development Environment & Foundations |
| [Part 2](part-2-backend-fastapi.md) | Backend: FastAPI |
| [Part 3](part-3-virtualenv-api-testing.md) | Virtualenv & API Testing |
| [Part 4](part-4-docker.md) | Docker + Docker Compose |
| [Part 5](part-5-postgresql.md) | PostgreSQL + Database Integration |
| [Part 6](part-6-debugging.md) | Debugging |
| [Part 7](part-7-advanced-git.md) | Advanced Git |
| [Part 8](part-8-full-project.md) | Backend Capstone Project |
| [Part 9](part-9-final-evaluation.md) | Final Evaluation, Readiness, and Expectations |

---

## JavaScript Frontend Bootcamp Contents

| Day | Topic |
|-----|-------|
| [Day 1](javascript/day-1.md) | JavaScript Basics: variables and simple data |
| [Day 2](javascript/day-2.md) | JavaScript Basics: arrays and objects |
| [Day 3](javascript/day-3.md) | Control Flow + Functions |
| [Day 4](javascript/day-4.md) | Arrays |
| [Day 5](javascript/day-5.md) | Objects |
| [Day 6](javascript/day-6.md) | DOM Basics |
| [Day 7](javascript/day-7.md) | DOM Manipulation |
| [Day 8](javascript/day-8.md) | Events |
| [Day 9](javascript/day-9.md) | Forms |
| [Day 10](javascript/day-10.md) | Async JavaScript |
| [Day 11](javascript/day-11.md) | API + UI |
| [Day 12](javascript/day-12.md) | Clean Code + Structure |
| [Day 13–14](javascript/day-13-14.md) | Final Project |

---

## 🚀 Quick Start

### View online

Open the handbook at: [https://indapmgr.github.io/engineering-bootcamp-handbook/](https://indapmgr.github.io/engineering-bootcamp-handbook/)

### Run locally with Jekyll

```bash
# Install dependencies
gem install bundler jekyll

# Clone and serve
git clone https://github.com/indapmgr/engineering-bootcamp-handbook.git
cd engineering-bootcamp-handbook
bundle init
bundle add jekyll minima jekyll-feed jekyll-seo-tag
bundle exec jekyll serve
```

Open [http://localhost:4000/engineering-bootcamp-handbook/](http://localhost:4000/engineering-bootcamp-handbook/) in your browser.

---

## 🧠 Core Principle

Being ready does **not** mean finishing tutorials.

Being ready means:

> You can take a task, understand it, break it down, implement it, debug it, and deliver it independently.

For this bootcamp, "deliver" means producing working software, verifying it from a clean environment, and sharing it clearly for review.

---

## Repository Structure

```text
engineering-bootcamp-handbook/
├── _config.yml                         # Jekyll / GitHub Pages configuration
├── README.md                           # This file
├── index.md                            # Course selection homepage
├── javascript/                         # 2-week JavaScript frontend bootcamp
│   ├── index.md
│   ├── day-1.md
│   ├── day-2.md
│   ├── day-3.md
│   ├── day-4.md
│   ├── day-5.md
│   ├── day-6.md
│   ├── day-7.md
│   ├── day-8.md
│   ├── day-9.md
│   ├── day-10.md
│   ├── day-11.md
│   ├── day-12.md
│   └── day-13-14.md
├── part-1-development-environment.md
├── part-2-backend-fastapi.md
├── part-3-virtualenv-api-testing.md
├── part-4-docker.md
├── part-5-postgresql.md
├── part-6-debugging.md
├── part-7-advanced-git.md
├── part-8-full-project.md
└── part-9-final-evaluation.md
```
