#  Refactor Codex: The Code Quality Time Machine

<div align="center">

![Languages](https://img.shields.io/badge/Languages-JS%20%7C%20TS%20%7C%20Python-blue)
![MCP Tools](https://img.shields.io/badge/MCP%20Tools-5-purple)
![License](https://img.shields.io/badge/License-MIT-yellow)
![Status](https://img.shields.io/badge/Status-Production%20Ready-green)

**[ Live Demo](https://codex-refactor-mkjd.vercel.app) | [🔬 Scientific Audit](SCIENTIFIC_AUDIT_REPORT.md)**

*The world's first code quality analyzer with time-travel capabilities. Track how your code evolved across Git commits.*

</div>

---

##  The Problem

Every code quality tool tells you what's wrong with your code **right now**. But they don't answer the most important question:

**"How did my code get this way?"**

**Refactor Codex** is the world's first code analyzer with **time-travel capabilities**. Track quality metrics across Git commit history, identify regressions, and see exactly when technical debt was introduced.

### The Architecture

Built by stitching together incompatible technologies into something **alive**:

```
┌─────────────────────────────────────────────┐
│  React Frontend (Vite + React 19)          │
│  ↓ HTTP/REST                                │
│  Express Backend (Node.js)                  │
│  ├─ JavaScript/TypeScript Analyzer (Babel) │
│  ├─ Python Analyzer (subprocess)            │
│  ├─ GitHub API Integration                  │
│  └─ Gemini AI Integration                   │
│  ↓ stdio                                    │
│  MCP Server (Python)                        │
│                                             │                        │
└─────────────────────────────────────────────┘
```

**Technologies Stitched Together:**
-  **Python** +  **JavaScript/TypeScript** (dual runtime analysis)
-  **AST Analysis** + **AI-Powered Refactoring** (Babel + Gemini)
-  **MCP Protocol** +  **REST API** +  **React** (three architectures, unified)
-  **Historical Analysis** +  **Real-time Metrics** (Git + GitHub API)
---

## Features

###  Time Machine Analysis 
**UNIQUE - No other tool does this.** Track code quality evolution across Git commit history:

- **Historical Timeline** - Quality scores across up to 20 commits
- **Regression Detection** - Pinpoint commits that introduced technical debt
- **Trend Analysis** - Visualize improvement/decline patterns
- **Best/Worst Commits** - Identify quality peaks and valleys
- **Commit-by-Commit Breakdown** - Detailed metrics for each version
- **Developer Journey** - Track coding skill improvement over time

**Real Example:** Analyze `lodash/array.js` over 10 commits:
```
Commit abc123: Quality dropped 15 points (regression detected)
Commit def456: Quality improved 8 points (refactoring success)
Overall trend: Improving (+12 points over 6 months)
```

### 🔬 Multi-Language Code Analysis
**True multi-language support** - JavaScript, TypeScript, AND Python with scientifically accurate metrics:

- **Quality Score (0-100)** - Weighted combination of complexity, smells, and maintainability
- **McCabe Cyclomatic Complexity** - Industry-standard metric (M = decision_points + 1)
- **Toxicity Score (0-100)** - Severity-weighted code smell density
- **Maintainability Index** - Research-based formula: `MI = 0.5×Q + 0.3×(100-T) + 0.2×(100-5C)`
- **Technical Debt** - SQALE method: 15min per smell, severity-weighted
- **Function-Level Analysis** - Detailed breakdown of every function
- **Code Smell Detection** - 12+ smell types with remediation suggestions

### AI-Powered Refactoring (Google Gemini)
**Intelligent refactoring suggestions with context:**

- **Extract Function Refactoring** - Identify code blocks that should be separate functions
- **Before/After Diffs** - Side-by-side comparison with syntax highlighting
- **Risk Assessment** - Safety ratings (Low/Medium/High risk)
- **AI Explanations** - Two AI personalities:
  - **Friendly Assistant** - Encouraging, educational explanations
  - **Mr. Smith** - Direct, technical analysis for serious issues
- **Step-by-Step Implementation** - Detailed guidance for each refactoring
- **Parameter Detection** - Automatic identification of function parameters and return values

###  GitHub Repository Scanner
**Analyze entire codebases with scientific precision:**

- **Batch Analysis** - Scan up to 30 files simultaneously
- **Repository Health Score** - Aggregate quality metrics with statistical analysis
- **Worst Files First** - Prioritized refactoring recommendations
- **Language Detection** - Automatic JS/TS/Python identification
- **Rate Limit Handling** - Smart GitHub API management with caching
- **Smell Density Metrics** - Issues per 1000 lines (industry standard)
- **Technical Debt Estimation** - Total remediation time across codebase

---

Every other tool shows you code quality NOW. **We show you the STORY.**

- See how quality evolved over 10+ commits
- Find the exact commit that introduced tech debt
- Track your improvement as a developer
- Visualize your coding journey

**SonarQube costs $$$$ for this. We do it free.**

```
┌─────────────────────────────────────────────┐
│  React Frontend (JavaScript)                │
│  ↓ HTTP                                     │
│  Express Backend (Node.js)                  │
│  ↓ Child Process                            │
│  Python Analyzer (Python AST)               │
│  ↓ stdio                                    │
│  MCP Server (Python)                        │
│                                             │
└─────────────────────────────────────────────┘
```

### 3. **Production-Ready, Not Just a Demo**
- Multi-language support (JS/TS/Python)
- GitHub API integration with rate limiting
- Error handling at every layer
- Batch processing with async operations
- Extensible architecture

### 4. **Solves Real Problems**
- Developers spend 60% of time reading code, 40% writing
- Technical debt costs $3.61 per line of code
- Code reviews take 4-8 hours per week
- **Refactor Codex automates the analysis and suggests fixes**

---


### Quick Start
```bash
# 1. Setup API Key (REQUIRED for AI features)
cd backend
cp .env.example .env
# Edit .env and add your Gemini API key:
# GEMINI_API_KEY=your_key_here
# Get free key: https://aistudio.google.com/app/apikey

# 2. Start backend
npm install
npm start

# 3. Start frontend (new terminal)
cd frontend
npm install
npm run dev

# 4. Open http://localhost:5173
```

###  API Key Setup (Important!)

The Mr. Smith AI analysis requires a Google Gemini API key:

1. Get your **FREE** API key: https://aistudio.google.com/app/apikey
2. Open `backend/.env` file
3. Add your key: `GEMINI_API_KEY=your_actual_key_here`
4. Restart the backend server





