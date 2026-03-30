<div align="center">

# 🏆 GitHub Badge Unlocker

### Automatically unlock all 5 earnable GitHub profile achievement badges with a single click.

[![Unlock Badges](https://img.shields.io/badge/Unlock-All_5_Badges-gold?style=for-the-badge&logo=github&logoColor=white)](../../actions/workflows/unlock-badges.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)](LICENSE)
[![Stars](https://img.shields.io/github/stars/Hunter0Dev/github-badges?style=for-the-badge&color=yellow)](../../stargazers)

<br/>

| Badge | Name | How It's Triggered |
|:-----:|:----:|:------------------:|
| <img src="https://github.githubassets.com/assets/pull-shark-default-498c279a747d.png" width="60"> | **Pull Shark** | Merge 2 Pull Requests |
| <img src="https://github.githubassets.com/assets/yolo-default-be0bbff04951.png" width="60"> | **YOLO** | Merge a PR without code review |
| <img src="https://github.githubassets.com/assets/quickdraw-default-39c6b8ff2ca9.png" width="60"> | **Quickdraw** | Close an issue within 5 minutes |
| <img src="https://github.githubassets.com/assets/pair-extraordinaire-default-d2ce3a4df5f3.png" width="60"> | **Pair Extraordinaire** | Co-author a merged PR |
| <img src="https://github.githubassets.com/assets/galaxy-brain-default-d0d8cf71cb26.png" width="60"> | **Galaxy Brain** | Get 2 discussion answers accepted |

</div>

---

## ⚡ Quick Start (3 Steps)

### Step 1: Create Your Repository

1. Click the green **"Use this template"** button at the top of this page
   - Or [click here to create from template](../../generate)
2. Name it anything you like (e.g. `my-github-badges`)
3. Make sure it's set to **Public**
4. Click **Create repository**

> **Alternative:** Fork this repo instead if you prefer.

### Step 2: Create a Personal Access Token (PAT)

1. Go to **[GitHub Settings → Developer Settings → Personal Access Tokens → Fine-grained tokens](https://github.com/settings/personal-access-tokens/new)**
2. Give it a name like `badge-unlocker`
3. Set expiration to **7 days** (you only need it once)
4. Under **Repository access**, select **"Only select repositories"** and pick your new repo
5. Under **Permissions**, enable these:

   | Permission | Access Level |
   |:----------:|:------------:|
   | **Contents** | Read and Write |
   | **Issues** | Read and Write |
   | **Pull Requests** | Read and Write |
   | **Discussions** | Read and Write |

6. Click **Generate token** and **copy it**

### Step 3: Add the Token & Run the Workflow

1. Go to your new repo → **Settings** → **Secrets and variables** → **Actions**
2. Click **New repository secret**
3. Name: `GH_PAT`
4. Value: Paste the token you copied
5. Click **Add secret**

Now trigger the workflow:

1. Go to the **Actions** tab in your repo
2. Click **"🏆 Unlock All GitHub Badges"** on the left
3. Click **"Run workflow"** → **"Run workflow"**
4. Wait ~2 minutes for it to complete ✅

---

## 🎯 What the Workflow Does

The workflow runs entirely via the GitHub API — no code checkout needed:

```
┌─────────────────────────────────────────────────────┐
│                  🏆 Badge Unlocker                   │
├─────────────────────────────────────────────────────┤
│                                                     │
│  1. 🔧 Enables Discussions on your repo             │
│                                                     │
│  2. 🦈 Pull Shark + 🤠 YOLO                         │
│     → Creates 2 branches with commits               │
│     → Opens 2 Pull Requests                         │
│     → Merges both WITHOUT review                    │
│                                                     │
│  3. ⚡ Quickdraw                                     │
│     → Creates an issue                              │
│     → Closes it instantly (< 5 minutes)             │
│                                                     │
│  4. 🫑 Pair Extraordinaire                           │
│     → Creates a commit with Co-authored-by tag      │
│     → Opens PR and merges it                        │
│                                                     │
│  5. 🧠 Galaxy Brain                                  │
│     → Creates 2 Q&A Discussions (as YOU via PAT)    │
│     → Answers both discussions (as YOU)             │
│     → Marks answers as accepted (as bot)            │
│     → Bot ≠ You = counts for the badge!             │
│                                                     │
│  6. 🎉 Done! Badges appear within a few hours.      │
│                                                     │
└─────────────────────────────────────────────────────┘
```

---

## 🧠 How Galaxy Brain Works

The Galaxy Brain badge requires **2 accepted answers** in GitHub Discussions — and the answer **cannot be self-accepted**. A different user must mark it.

This workflow solves that by using **two different tokens**:

| Action | Token Used | Appears As |
|:------:|:----------:|:----------:|
| Create discussion & answer | `GH_PAT` (your token) | **You** ✅ |
| Mark answer as accepted | `GITHUB_TOKEN` (built-in) | **github-actions[bot]** 🤖 |

Since the bot is a different "user" from you, GitHub counts it as a valid accepted answer!

---

## ⏳ After Running

- Badges can take **a few minutes to several hours** to appear on your profile
- Make sure badges are visible: **Settings** → **Profile** → **Achievements** → Set to **Visible**
- You can safely delete the repo after badges appear — **badges are permanent**

---

## 📋 Badge Tiers

Each badge has multiple tiers based on activity:

| Badge | Default | Bronze | Silver | Gold |
|:-----:|:-------:|:------:|:------:|:----:|
| 🦈 Pull Shark | 2 PRs | 16 PRs | 128 PRs | 1024 PRs |
| 🫑 Pair Extraordinaire | 1 PR | 10 PRs | 24 PRs | 48 PRs |
| 🧠 Galaxy Brain | 2 answers | 8 answers | 16 answers | 32 answers |
| 🤠 YOLO | 1 PR | — | — | — |
| ⚡ Quickdraw | 1 issue | — | — | — |

---

## ❌ Badges NOT Included

These badges exist but **cannot be automated** without violating GitHub's terms:

| Badge | Requirement | Why It Can't Be Automated |
|:-----:|:-----------:|:-------------------------:|
| 🌟 **Starstruck** | 16+ stars on a repo | Needs real community stars |
| 🤝 **Public Sponsor** | Sponsor a developer | Requires real payment |
| 🧙 **Open Sourcerer** | PRs merged in other repos | Needs external contributions |

---

## ⚠️ Disclaimer

This tool is for **educational purposes**. It uses legitimate GitHub API calls to trigger badge criteria on your own repositories. No spam, no external repo manipulation, no terms of service violations.

---

## 📜 License

MIT License — use it however you like.

---

<div align="center">

**If this helped you, consider giving it a ⭐!**

Made with 🖤 by [Hunter0Dev](https://github.com/Hunter0Dev)

</div>
