# Refactor Codex: Code Quality Time Machine

[Live Demo](https://codex-refactor-mkjd.vercel.app)

Analyze how your code quality evolves across Git commits instead of only evaluating its current state.

---

## Problem

Most code quality tools answer:

"What is wrong with my code right now?"

They do not answer:

"When did it start going wrong?"

---

## Overview

Refactor Codex analyzes code across Git history to:

- track quality changes over time
- identify regression-introducing commits
- understand how technical debt accumulates
- visualize trends in code quality

It provides a timeline view rather than a single snapshot.

---

## Architecture

```
React (Vite)
   ↓ REST
Express API (Node.js)
   ├─ JS/TS Analyzer (Babel AST)
   ├─ Python Analyzer (ast module)
   ├─ GitHub API Integration
   └─ AI Refactoring (Gemini)
   ↓ stdio
Python Analysis Service
```

The system uses language-specific analyzers with a unified scoring layer.

---

## Features

### Time-Travel Analysis

- commit-by-commit quality scores
- regression detection (e.g. sudden drops)
- trend analysis (improving / declining)
- best and worst commits

Example:

```
Commit A → Score: 78  
Commit B → Score: 62 (regression)  
Commit C → Score: 85 (improvement)
```

---

### Multi-Language Code Analysis

Supports JavaScript, TypeScript, and Python.

Metrics include:

- Cyclomatic Complexity (McCabe), computed from control-flow decision points
- Quality Score (0–100), based on weighted heuristics
- Toxicity Score (0–100), based on code smell density
- Maintainability Score (custom, inspired by Maintainability Index)
- Technical Debt (SQALE-inspired remediation estimate)
- Function-level analysis
- Code smell detection (multiple patterns)

Note: Some metrics are heuristic and inspired by industry tools rather than exact implementations.

---

### AI-Assisted Refactoring

- extract-function suggestions
- before/after diffs
- parameter and return detection
- heuristic risk assessment
- natural language explanations

---

### GitHub Repository Scanner

- batch analysis of multiple files
- repository-level quality scoring
- prioritization of problematic files
- rate-limit handling and caching
- smell density metrics (per 1000 LOC)

---

## What Makes It Different

Most tools analyze code at a single point in time.

Refactor Codex analyzes how code evolves.

This enables:

- identifying when technical debt was introduced
- tracking improvement over time
- understanding development patterns

---

## Quick Start

```bash
# Backend
cd backend
cp .env.example .env
# Add: GEMINI_API_KEY=your_key

npm install
npm start

# Frontend
cd frontend
npm install
npm run dev
```

Open http://localhost:5173

---

## Notes

- Designed for JavaScript, TypeScript, and Python codebases
- Uses AST-based static analysis
- Combines deterministic metrics with heuristic scoring
- AI features require a Gemini API key
