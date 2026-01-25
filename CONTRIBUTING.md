# Contributing Guide

## 1. Purpose
This document defines **rules and standards for contributing** to the project.
All members are expected to follow these guidelines to ensure code quality and team efficiency.

---

## 2. General Rules
- Do not push directly to `main` or `develop`
- Every feature or fix must be developed in a separate branch
- All changes must go through Pull Request
- Respect existing code ownership and communicate before major changes

---

## 3. Branch Strategy
- main: stable branch for demo / final submission
- develop: main development branch
- feature/*: feature or task-specific branches

Branch naming:
- feature/login
- feature/rfq-management
- feature/admin-dashboard

---

## 4. Commit Convention

### Commit Message Format
type: short description

### Allowed Types
- feat: new feature
- fix: bug fix
- ui: UI changes
- refactor: code optimization or restructuring
- docs: documentation updates

### Examples
- feat: implement RFQ creation API
- fix: resolve null pointer in order service
- ui: update admin dashboard layout

---

## 5. Pull Request Rules
Each Pull Request must:
- Target `develop` branch
- Have a clear title and description
- Explain:
  - What was implemented
  - Which parts are affected
  - Any important notes for reviewers
- Contain only related changes (no mixed tasks)

Do not merge Pull Requests without permission.

---

## 6. Code Style & Quality
- Write clean, readable, and maintainable code
- Use meaningful variable and method names
- Avoid hard-coded values
- Comment complex or non-obvious logic
- Ensure code builds and runs before committing

---

## 7. Communication & Coordination
- Use GitHub Issues for bugs and feature requests
- Inform the team before making changes that affect multiple modules
- Coordinate through team chat when necessary

---

## 8. Agreement
By contributing to this project, each member agrees to follow the rules defined in this document.
