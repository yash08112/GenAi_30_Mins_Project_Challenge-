# InterviewCoach AI (30 mins Vibe Coding Project) 

An **open-source AI interview coach** that asks real interview questions, evaluates your answers for accuracy, and provides detailed feedback — perfect for practice sessions and presentations.

![Open Source](https://img.shields.io/badge/Open%20Source-100%25-green)
![Stack](https://img.shields.io/badge/Stack-React%20%2B%20Express-blue)
![AI](https://img.shields.io/badge/AI-Ollama-purple)

## Features

- **AI Question & Answer Flow** — Pick a track (Software Engineering, Data Science, Behavioral, Web Dev) and answer 3 curated interview questions
- **Intelligent Evaluation** — Uses [Ollama](https://ollama.com) (open-source LLM) to judge answer accuracy, with a smart rule-based fallback when Ollama isn't running
- **Detailed Feedback** — Score (0–100), accuracy rating, strengths, and improvement suggestions
- **Voice Input** — Answer questions using your microphone (browser speech recognition)
- **Beautiful UI** — Modern dark theme with animations, score rings, and session summaries

## Quick Start

### Prerequisites

- [Node.js](https://nodejs.org/) 18+ installed
- *(Optional but recommended)* [Ollama](https://ollama.com/download) for AI-powered evaluation

### 1. Install dependencies

```bash
npm install
```

### 2. (Optional) Set up Ollama for AI evaluation

```bash
# Install Ollama from https://ollama.com/download
ollama pull llama3.2
ollama serve
```

Without Ollama, the app still works using a built-in smart scoring engine.

### 3. Run the app

```bash
npm run dev
```

Open **http://localhost:5173** in your browser.

## How It Works

```
┌─────────────┐     ┌──────────────┐     ┌─────────────────┐
│   React UI  │────▶│ Express API  │────▶│ Ollama (LLM)    │
│  (Vite)     │◀────│  Port 3001   │◀────│ or Rule Engine  │
└─────────────┘     └──────────────┘     └─────────────────┘
```

1. User selects an interview category
2. Server serves curated questions from the question bank
3. User submits an answer (typed or via voice)
4. Server evaluates using Ollama AI (or fallback scorer)
5. UI displays score, feedback, strengths, and improvements
6. Session summary shows overall performance

## Tech Stack

| Layer      | Technology                          |
|------------|-------------------------------------|
| Frontend   | React, Vite, Tailwind CSS, Framer Motion |
| Backend    | Node.js, Express                    |
| AI         | Ollama (llama3.2) — open source    |
| Speech     | Web Speech API (browser native)     |

## Project Structure

```
├── src/
│   ├── App.jsx              # Main app with view routing
│   ├── components/          # UI components
│   ├── api.js               # API client
│   └── hooks.js             # Speech recognition, timer hooks
├── server/
│   ├── index.js             # Express API server
│   ├── questions.js         # Question bank
│   └── evaluator.js         # Ollama + fallback evaluation
└── package.json
```
