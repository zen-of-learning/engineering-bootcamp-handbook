# Intern Engineering Handbook

A practical, full-stack engineering onboarding handbook for interns.

Published as a GitHub Pages documentation site at **[https://indapmgr.github.io/docs/](https://indapmgr.github.io/docs/)**.

---

## 📚 Handbook Contents

| Part | Title |
|------|-------|
| [Part 1](docs/part-1-foundations.md) | Foundations |
| [Part 2](docs/part-2-backend-fastapi.md) | Backend: FastAPI |
| [Part 3](docs/part-3-frontend-nextjs.md) | Frontend: Next.js + API Integration |
| [Part 4](docs/part-4-docker.md) | Docker + Docker Compose |
| [Part 5](docs/part-5-postgresql.md) | PostgreSQL + Database Integration |
| [Part 6](docs/part-6-debugging.md) | Debugging |
| [Part 7](docs/part-7-advanced-git.md) | Advanced Git |
| [Part 8](docs/part-8-full-project.md) | Full End-to-End Project |
| [Part 9](docs/part-9-final-evaluation.md) | Final Evaluation, Readiness, and Expectations |

---

## 🚀 Quick Start

### View online

Open the handbook at: [https://indapmgr.github.io/docs/](https://indapmgr.github.io/docs/)

### Run locally with Jekyll

```bash
# Install dependencies
gem install bundler jekyll

# Clone and serve
git clone https://github.com/indapmgr/indap.github.io.git
cd indap.github.io
bundle init
bundle add jekyll minima jekyll-feed jekyll-seo-tag
bundle exec jekyll serve
```

Open [http://localhost:4000/docs/](http://localhost:4000/docs/) in your browser.

---

## 🧠 Core Principle

Being ready does **not** mean finishing tutorials.

Being ready means:

> You can take a task, understand it, break it down, implement it, debug it, and deliver it independently.

---

## Repository Structure

```text
indap.github.io/
├── _config.yml          # Jekyll / GitHub Pages configuration
├── README.md            # This file
├── index.html           # Profile page (https://indapmgr.github.io)
├── styles.css           # Profile page styles
└── docs/
    ├── index.md         # Handbook homepage
    ├── part-1-foundations.md
    ├── part-2-backend-fastapi.md
    ├── part-3-frontend-nextjs.md
    ├── part-4-docker.md
    ├── part-5-postgresql.md
    ├── part-6-debugging.md
    ├── part-7-advanced-git.md
    ├── part-8-full-project.md
    └── part-9-final-evaluation.md
```