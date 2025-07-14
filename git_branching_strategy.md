# Git Branching Strategy Document

## ✨ 1. When to Create Branches

Branches should be created for:

- 🛠 **Features**: For new features or enhancements.
- 🔎 **Bugfixes**: For fixing bugs.
- 📦 **Releases**: When preparing a production release.
- 🤖 **Hotfixes**: For emergency fixes in production.
- 🔮 **Experiments/Prototypes**: Isolated development and testing.

## 🔖 2. Naming Conventions

| Purpose    | Naming Convention            | Example                    |
| ---------- | ---------------------------- | -------------------------- |
| Feature    | `feature/<short-name>`       | `feature/login-auth`       |
| Bugfix     | `bugfix/<short-description>` | `bugfix/fix-login-null`    |
| Hotfix     | `hotfix/<issue-desc>`        | `hotfix/crash-on-launch`   |
| Release    | `release/<version>`          | `release/1.0.0`            |
| Experiment | `experiment/<idea>`          | `experiment/dark-mode-poc` |

## ♻️ 3. Merge Strategies

| Branch Type    | Merges Into          | Merge Strategy | Notes                                    |
| -------------- | -------------------- | -------------- | ---------------------------------------- |
| `feature/*`    | `develop`            | `--no-ff`      | Keep history of features visible         |
| `bugfix/*`     | `develop` or `main`  | `--no-ff`      | If urgent, go directly into `main`       |
| `hotfix/*`     | `main` & `develop`   | `--no-ff`      | Merge into both for sync                 |
| `release/*`    | `main` and `develop` | `--no-ff`      | Tag release, then sync with develop      |
| `experiment/*` | not merged (usually) | -              | Optional or squash and cherry-pick later |

## 🛏️ 4. Visual Diagram of Branch Structure

![alt text](image-35.png)