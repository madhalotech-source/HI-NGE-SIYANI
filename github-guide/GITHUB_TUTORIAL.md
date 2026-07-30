# GitHub Tutorial — HI NGE SIYANI

You already know Delphi. This teaches you GitHub, from zero, using this exact project as the example.

## 1. Create a GitHub Account & Repository

1. Go to [github.com](https://github.com) and sign up (or sign in).
2. Click the **+** icon (top right) → **New repository**.
3. Repository name: `HI-NGE-SIYANI`
4. Description: "Multilingual AI-powered digital ecosystem for South Africa — hackathon MVP."
5. Choose **Public** (so judges can view it) or **Private** with judges added as collaborators, per your hackathon's rules.
6. Check **Add a README file**.
7. Click **Create repository**.

## 2. Install Git Locally

- Windows: download from [git-scm.com](https://git-scm.com), install with default options.
- Verify install: open a terminal/command prompt and run:
  ```
  git --version
  ```

## 3. Configure Git (once, on any new machine)

```
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

## 4. Clone the Repository to Your Computer

```
git clone https://github.com/<your-username>/HI-NGE-SIYANI.git
cd HI-NGE-SIYANI
```

## 5. Create Folders

You can create folders directly on your file system (Windows Explorer, or your Delphi IDE's project structure) inside the cloned `HI-NGE-SIYANI` folder. Git tracks files, not empty folders — a folder only appears in GitHub once it contains at least one file. Suggested structure:

```
HI-NGE-SIYANI/
├── docs/
├── github-guide/
├── src/
│   ├── android/
│   └── backend/
└── assets/
```

## 6. Upload (Add) Documentation Files

Copy your `.md` documentation files into the `docs/` folder, then from the terminal:

```
git add docs/
git status        # shows what will be committed — review before committing
```

## 7. Commit Changes

A commit is a saved checkpoint with a message explaining *why* the change was made.

```
git commit -m "Add project vision, mission, and executive summary docs"
```

### Writing Good Commit Messages

- Use the imperative mood: "Add", "Fix", "Update" — not "Added" or "Adding".
- Be specific: `Fix language selection crash on Android 12` beats `fix bug`.
- One logical change per commit where practical — don't bundle unrelated changes.
- Reference issues when relevant: `Fix onboarding validation (Closes #7)`.

## 8. Push Updates to GitHub

```
git push origin main
```

This uploads your committed changes to GitHub, where judges and collaborators can see them.

## 9. Using Branches

Branches let you work on a feature without disturbing your stable `main` branch.

```
git checkout -b feature/language-selection-screen
```

Work, commit as usual on this branch, then push it:

```
git push origin feature/language-selection-screen
```

On GitHub, open a **Pull Request** to merge `feature/language-selection-screen` into `main` once it's working. This creates a visible, timestamped record of each feature's development — valuable for judges reviewing your process.

**Suggested branch naming:** `feature/...`, `fix/...`, `docs/...`

## 10. Creating Releases

Once your MVP is demo-ready:

1. On GitHub, go to your repository → **Releases** (right sidebar) → **Draft a new release**.
2. Create a tag, e.g. `v0.1.0-hackathon`.
3. Title: "Hackathon Submission — HI NGE SIYANI MVP"
4. Description: summarise what's working (link to your [Product Roadmap](../docs/05-product-roadmap.md)).
5. Click **Publish release**.

Judges can view this as a clear, official snapshot of your submission state.

## 11. Preparing Your Repository for Judges

- Keep `README.md` current — it's the first thing judges see.
- Commit early and often, even small progress — a history of 30 small commits over 3 days looks more credible than one giant commit the night before.
- Use clear commit messages (see above) — judges may skim your commit log as evidence of real, iterative work.
- Open GitHub Issues for known bugs/TODOs rather than hiding them — it demonstrates process maturity.
- Tag a release before the judging deadline so there's an unambiguous "this is our submission" point.

## 12. Everyday Workflow Cheat Sheet

```
git pull origin main          # get latest changes before starting work
git checkout -b feature/xyz    # start a new branch for a task
# ... make changes ...
git add .
git commit -m "Clear, specific message"
git push origin feature/xyz
# open a Pull Request on GitHub, review, merge into main
```

## Common Beginner Mistakes to Avoid

- Committing directly to `main` for risky changes — use a branch.
- Vague commit messages like `update` or `fix stuff`.
- Committing secrets (API keys, `.env` files) — add them to `.gitignore` instead.
- Forgetting `git pull` before starting new work, causing avoidable merge conflicts.
