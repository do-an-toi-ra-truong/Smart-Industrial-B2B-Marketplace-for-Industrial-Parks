# Git Checklist – Team Workflow

## Scope
This checklist defines **daily Git operations** for all team members.
Follow it step by step to avoid conflicts and broken history.

---

## Goal
- Keep repository clean
- Prevent code overwriting
- Maintain clear commit history

---

## 1. One-time Setup (Local)

- Clone repository
- Checkout develop branch

git clone <repository-url>  
git checkout develop  

---

## 2. Before Starting Work (Daily – Local)

- Verify current branch

git branch

- Pull latest code

git pull origin develop

- Create new feature branch

git checkout -b feature/<short-name>

Do not work directly on `main` or `develop`.

---

## 3. During Development (Local)

- Code and test locally
- Commit small and focused changes

git add .  
git commit -m "feat: short description"

- Push branch to GitHub

git push -u origin feature/<short-name>

---

## 4. Pull Request (GitHub Web)

- Create Pull Request:
  - From: feature/<short-name>
  - To: develop
- Provide clear description:
  - What was done
  - Affected components
  - Notes for reviewer

Do not merge without authorization.

---

## 5. When Pull Request Requires Changes

### Local
- Checkout the same feature branch
- Update code as requested
- Commit and push again

git add .  
git commit -m "fix: update based on review"  
git push  

### GitHub
- Pull Request updates automatically
- Do not create a new Pull Request

---

## 6. After Pull Request Is Merged

### Cleanup (Local)
- Delete local branch

git branch -d feature/<name>

- Delete remote branch

git push origin --delete feature/<name>

### Sync Develop
- Switch back to develop

git checkout develop  
git pull  

---

## 7. Strictly Prohibited
- Direct push to `main`
- Force push
- Multiple tasks in one branch
- Committing code that does not build or run

---

## Core Rule
One person.  
One branch.  
One task.

Clean repository.  
Clear history.  
Team survives until deadline.
