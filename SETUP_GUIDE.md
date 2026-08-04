# Salman Khan — GitHub Profile: Design & Setup Guide

This document covers everything outside the README itself: the banner concept, folder structure, badge reference, pinned-repo plan, and step-by-step setup.

---

## 1. Banner Concept

**File:** `assets/banner/banner.svg` — 1600×500, animated SVG (SMIL), renders natively on GitHub.

**Design rationale**
- **Palette:** Black (`#05070d`→`#0a1128`) base with electric-blue (`#00d4ff`) and gold (`#ffd700`) accents — reads as premium/AI without tipping into generic "purple gradient" territory.
- **Left third:** Your SK logo (extracted from the uploaded file, transparent PNG, embedded inline so the SVG is a single portable file).
- **Center-right:** Name in a white→blue→gold gradient with a soft glow filter, role line in electric blue, a monospace tagline (nods to code), and a blinking gold cursor block for a "terminal" feel.
- **Right two-thirds, background:** A generated **neural network** (16 nodes, edges drawn between nodes within a distance threshold, nodes pulse on independent timers) plus **circuit-board traces** at low opacity — reads as "AI + engineering" rather than decoration.
- **Whole canvas:** ~22 floating particles drifting and fading via SMIL `<animate>` — subtle, not distracting, and (unlike a GIF) infinitely loopable at zero file-size cost per frame.
- **Frame:** A thin rounded blue-glow border, consistent with the "holographic panel" look.

**Why SVG over GIF/video:** GitHub renders SVG `<animate>`/SMIL when the SVG is referenced as an image (as it is in the README), so you get smooth infinite animation with a far smaller file than a GIF, crisp at any zoom, and no external hosting dependency.

**If you want a different variant later** (e.g. more circuit-board, less neural net, or a "Matrix rain" version), regenerate `banner.svg` with the same structure — background gradient → circuit paths → neural net → particles → logo → text — and adjust the theme block in `<defs>`.

---

## 2. Complete Folder Structure

Create a repository named exactly **`Salman-Khan751`** (must match your GitHub username) — this is the special "profile README" repo GitHub auto-displays on your profile page.

```
Salman-Khan751/
├── README.md                          # Main profile README (Part 2)
├── SETUP_GUIDE.md                     # This file
├── assets/
│   ├── banner/
│   │   └── banner.svg                 # Animated hero banner (1600×500)
│   ├── logo/
│   │   └── logo.png                   # Extracted SK logo (transparent PNG)
│   └── icons/                         # (optional) any additional custom icons
├── animations/                        # (optional) space for future GIF/Lottie assets
└── .github/
    └── workflows/
        ├── snake.yml                  # Contribution snake generator
        └── metrics.yml                # GitHub metrics / recent activity / auto-update
```

The `output` branch referenced in `snake.yml` is created automatically by the workflow the first time it runs — you don't need to create it manually.

---

## 3. Badge Reference (already used in README, listed here for quick edits)

All badges use [shields.io](https://shields.io) `for-the-badge` / `flat-square` styles for visual consistency.

| Category | Badges included |
|---|---|
| Languages | Python, Java, JavaScript, TypeScript, C++, C# |
| AI / ML | PyTorch, TensorFlow, Scikit-learn, Hugging Face, LangChain, LangGraph, OpenCV, spaCy, NLTK, LLMs, RAG, Agentic AI, Prompt Engineering |
| Web & Backend | React, Next.js, Node.js, Express.js, Flask, FastAPI, Spring Boot, GraphQL, Tailwind CSS |
| Databases | MySQL, MongoDB, PostgreSQL |
| DevOps | Docker, AWS, Git, GitHub, Postman, CI/CD |

To add a badge not listed (e.g. Computer Vision, Generative AI, NLP as standalone tags), use this pattern:

```md
<img src="https://img.shields.io/badge/Computer%20Vision-6E56CF?style=flat-square"/>
<img src="https://img.shields.io/badge/Generative%20AI-6E56CF?style=flat-square"/>
<img src="https://img.shields.io/badge/NLP-6E56CF?style=flat-square"/>
```

---

## 4. Pinned Repository Recommendations

GitHub allows pinning up to **6 repositories**. Recommended order (strongest signal for AI-recruiter scanning first, full-stack breadth second):

| Order | Repository name | One-line description |
|---|---|---|
| 1 | `MediTranscribe` | AI medical transcription platform — Whisper speech-to-text + fine-tuned BERT (95% accuracy) + React/Flask, role-based EHR workflows |
| 2 | `ai-call-intent-emotion-detection` | Real-time telecom call intent & emotion classifier — Whisper + Wav2Vec2.0 + DistilBERT behind a FastAPI service |
| 3 | `toxictrack-hate-speech-detection` | Fine-tuned BERT pipeline for real-time toxic/abusive content moderation |
| 4 | `vehicle-detection-toll-monitoring` | YOLOv5 real-time vehicle detection & classification for toll audit automation |
| 5 | `llama-nlp-chatbot` | Context-aware, multi-turn chatbot fine-tuned on LLaMA, served via FastAPI |
| 6 | `ecommerce-backend-node-mysql` | RBAC-secured REST API for an e-commerce platform — Node.js, Express.js, MySQL, JWT |

**Repo hygiene checklist for each pinned repo:**
- Short, keyword-rich description (shows under the repo name on your profile)
- Topics/tags added (`nlp`, `llm`, `computer-vision`, `fastapi`, `react`, etc.) — this is what recruiters' GitHub topic search picks up
- A project-level README with problem → approach → tech stack → results (the 95% BERT accuracy, latency numbers, etc. belong here, not just on your resume)
- License file (MIT is the safe default for portfolio code)

**GitHub profile organization:**
- Set your bio to one line: `AI Engineer · LLMs, NLP, CV, GenAI/Agentic AI · Full-Stack (MERN)`
- Pin the 6 repos above in that order
- Fill in "Company" (BIIT), "Location," and the LinkedIn link in your profile sidebar so it matches the README

---

## 5. Setup Instructions

1. **Create the special repo:** On GitHub, create a new repository named exactly `Salman-Khan751` (public). GitHub will show a banner offering to add a profile README — accept it, or just push the files below.
2. **Add the files:** Copy `README.md`, `SETUP_GUIDE.md`, `assets/`, and `.github/workflows/` from this delivery into that repo's root, preserving the folder structure above.
3. **Commit & push:**
   ```bash
   git init
   git add .
   git commit -m "Set up profile README, banner, and automation"
   git branch -M main
   git remote add origin https://github.com/Salman-Khan751/Salman-Khan751.git
   git push -u origin main
   ```
4. **Enable the snake workflow:** After the first push, go to the repo's **Actions** tab and confirm `Generate Contribution Snake` runs (or trigger it manually via "Run workflow"). It will create an `output` branch holding the generated SVGs that the README already links to.
5. **Enable the metrics workflow:** Confirm `Update Profile Metrics` runs and commits `metrics.svg` to the repo. If you want it embedded in the README, add:
   ```md
   ![Metrics](metrics.svg)
   ```
   under the GitHub Analytics section.
6. **Update project links:** Replace the placeholder project links in the Featured Projects section once each repo (MediTranscribe, ai-call-intent-emotion-detection, etc.) actually exists at that URL.
7. **Verify rendering:** Open `https://github.com/Salman-Khan751` — the banner, typing animation, badges, stats cards, trophy row, and snake should all render within a minute or two (stats/trophy services can take a few seconds to generate on first load).
8. **Optional polish:** Once the pinned repos exist, add a short GIF or screenshot to each project's own README — profile visitors who click through convert better with a visual than with text alone.
