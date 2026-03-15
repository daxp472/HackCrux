# 🤝 Contributing to NyayaSankalan

First off — **thank you for taking the time to contribute!** 🎉  
Every bug fix, feature, or documentation improvement makes a real difference to India's justice system.

This document explains how to get your changes merged quickly and cleanly.

---

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Ways to Contribute](#ways-to-contribute)
- [Development Setup](#development-setup)
- [Branch Naming Convention](#branch-naming-convention)
- [Commit Message Convention](#commit-message-convention)
- [Pull Request Process](#pull-request-process)
- [Coding Standards](#coding-standards)
- [Testing Guidelines](#testing-guidelines)
- [Reporting Bugs](#reporting-bugs)
- [Requesting Features](#requesting-features)

---

## 📜 Code of Conduct

By participating in this project, you agree to abide by our [Code of Conduct](./CODE_OF_CONDUCT.md).  
Please read it carefully. We enforce it strictly and fairly.

---

## 🌟 Ways to Contribute

You don't have to write code to contribute! Here are all the ways you can help:

| Contribution Type | Description |
|---|---|
| 🐛 Bug Reports | File detailed bug reports via GitHub Issues |
| ✨ Feature Requests | Suggest new features or improvements |
| 💻 Code Contributions | Fix bugs, implement features, refactor code |
| 📖 Documentation | Improve README, wikis, inline comments |
| 🧪 Testing | Write unit, integration, or E2E tests |
| 🎨 UI/UX | Improve the frontend design and accessibility |
| 🌐 Translations | Help localise for regional Indian languages |

---

## 🛠️ Development Setup

### Prerequisites

- **Node.js** `>= 22.0.0`
- **Python** `>= 3.10`
- **PostgreSQL** `>= 14`
- **Git**

### 1. Fork & Clone

```bash
# Fork the repo on GitHub, then clone your fork
git clone https://github.com/<your-username>/HackCrux.git
cd HackCrux

# Add the upstream remote
git remote add upstream https://github.com/daxp472/HackCrux.git
```

### 2. Backend

```bash
cd backend
npm install
cp .env.example .env       # Fill in your DB and Cloudinary credentials
npm run db:migrate
npm run db:seed
npm run dev                # Starts at http://localhost:5000
```

### 3. Frontend

```bash
cd client
npm install
cp .env.example .env       # Set VITE_API_URL=http://localhost:5000/api
npm run dev                # Starts at http://localhost:5173
```

### 4. AI Engine

```bash
cd ai-poc
python -m venv venv
.\venv\Scripts\activate    # Windows | source venv/bin/activate on Linux/macOS
pip install -r requirements.txt
python -m spacy download en_core_web_sm
uvicorn main:app --reload --port 8000
```

---

## 🌿 Branch Naming Convention

Use descriptive branch names following this pattern:

```
<type>/<short-description>
```

| Type | When to Use | Example |
|---|---|---|
| `feature/` | New functionality | `feature/case-search-filter` |
| `fix/` | Bug fixes | `fix/fir-upload-validation` |
| `docs/` | Documentation updates | `docs/update-api-docs` |
| `refactor/` | Code improvement without feature changes | `refactor/auth-middleware` |
| `test/` | Adding or updating tests | `test/case-assignment-service` |
| `chore/` | Build, CI, dependency updates | `chore/upgrade-prisma-v6` |

---

## ✍️ Commit Message Convention

We follow the [Conventional Commits](https://www.conventionalcommits.org/) specification.

```
<type>(<scope>): <short description>

[optional body]

[optional footer]
```

### Examples

```bash
feat(cases): add case reopening API endpoint
fix(auth): resolve JWT expiry refresh loop
docs(readme): update setup instructions for AI engine
test(submission): add court submission edge case tests
refactor(evidence): extract cloudinary upload to service layer
chore(deps): bump express from 4.18 to 4.21
```

### Valid Types

| Type | Description |
|---|---|
| `feat` | A new feature |
| `fix` | A bug fix |
| `docs` | Documentation only changes |
| `refactor` | Code change that neither fixes a bug nor adds a feature |
| `test` | Adding or updating tests |
| `chore` | Build process or auxiliary tool changes |
| `perf` | Performance improvements |
| `style` | Formatting, missing semicolons, etc. |

---

## 📬 Pull Request Process

1. **Sync your fork** before starting work:
   ```bash
   git fetch upstream
   git rebase upstream/main
   ```

2. **Create a branch** from `main`:
   ```bash
   git checkout -b feature/my-amazing-feature
   ```

3. **Make your changes** and commit following the convention above.

4. **Run tests** before pushing:
   ```bash
   # Backend tests
   cd backend && npm test
   
   # Frontend lint
   cd client && npm run lint
   ```

5. **Push your branch**:
   ```bash
   git push origin feature/my-amazing-feature
   ```

6. **Open a Pull Request** on GitHub and fill in the PR template completely.

7. **Address review feedback** — be responsive and open to suggestions.

### PR Requirements for Merge

- [ ] Follows commit message convention
- [ ] No lint errors
- [ ] All existing tests pass
- [ ] New functionality is covered by tests
- [ ] Documentation updated if applicable
- [ ] PR description clearly explains what changed and why

---

## 🧑‍💻 Coding Standards

### TypeScript (Backend & Frontend)

- Use strict TypeScript — no `any` types unless absolutely necessary
- Prefer `interface` over `type` for object shapes
- Use descriptive variable and function names
- Add JSDoc comments for exported functions
- Follow the existing module structure for new features

### Python (AI Engine)

- Follow PEP 8 style guide
- Use type hints for all function signatures
- Write docstrings for all public functions
- Keep functions small and single-purpose

### React (Frontend)

- Prefer functional components with hooks
- Keep components small — extract reusable logic to custom hooks
- Use the existing API layer (`src/api/`) for all HTTP calls
- Follow the existing folder structure under `src/pages/` and `src/components/`

---

## 🧪 Testing Guidelines

### Backend

Tests live in `backend/src/**/*.test.ts`. Run with:
```bash
cd backend && npm test
```

- Write tests for every new API endpoint
- Cover both success and failure cases
- Use `supertest` for HTTP integration tests

### Frontend

- Test critical user flows
- Use React Testing Library for component tests

---

## 🐛 Reporting Bugs

Please use the **Bug Report** issue template and include:

1. **What happened** (actual behaviour)
2. **What should happen** (expected behaviour)
3. **Steps to reproduce** (minimal reproduction steps)
4. **Environment** (OS, Node version, Browser)
5. **Screenshots or logs** if applicable

👉 [Open a Bug Report](https://github.com/daxp472/HackCrux/issues/new?template=bug_report.md)

---

## 💡 Requesting Features

Please use the **Feature Request** issue template and include:

1. **Problem statement** — what problem does this solve?
2. **Proposed solution**
3. **Alternatives considered**
4. **Additional context** (mockups, references)

👉 [Open a Feature Request](https://github.com/daxp472/HackCrux/issues/new?template=feature_request.md)

---

## 🙏 Thank You

Every contribution — big or small — helps bring justice to more people, faster.  
We're grateful for your time and effort. Welcome to the NyayaSankalan community! ⚖️
