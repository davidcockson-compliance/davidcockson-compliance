# Task Queue: GitHub Profile Cleanup

Run each task as a separate chat session. Copy the **Prompt** into a new Claude Code chat, let it complete, then move to the next. Mark `[x]` when done.

Each task is scoped to be small and self-contained to minimize token usage.

---

## Task 1: Audit `job-radar-` for secrets and remove `dev.db` files
**Repo:** `davidcockson-compliance/job-radar-`
**Prompt:**
```
Clone https://github.com/davidcockson-compliance/job-radar- and do the following:
1. Check backend/src/services/companiesHouse.js for any hardcoded API keys or secrets. If found, replace them with process.env references.
2. Uncomment the dev.db line in .gitignore so it reads: dev.db
3. Run: git rm --cached backend/dev.db backend/prisma/dev.db
4. Commit with message: "fix: remove tracked dev.db files and update .gitignore"
5. Push to main.
```
- [ ] Completed

---

## Task 2: Audit `scarlet-helix` sync script for secrets
**Repo:** `davidcockson-compliance/scarlet-helix`
**Prompt:**
```
Clone https://github.com/davidcockson-compliance/scarlet-helix and do the following:
1. Read scripts/sync.ps1 and check for any hardcoded API keys, tokens, or credentials.
2. If any are found, replace them with environment variable references and add a .env.example file documenting required variables.
3. If no secrets are found, report back that the file is clean.
4. Add a .gitignore file appropriate for a JavaScript/Node.js project (use GitHub's template). Include entries for .env, .DS_Store, node_modules/, and *.sublime-workspace.
5. Commit and push to main.
```
- [ ] Completed

---

## Task 3: Add `.gitignore` to remaining repos
**Repos:** Multiple
**Prompt:**
```
For each of these repositories, clone it, add an appropriate .gitignore, commit with message "chore: add .gitignore", and push to main:

1. https://github.com/davidcockson-compliance/Compliance-Tools — use a general .gitignore (Python template from GitHub)
2. https://github.com/davidcockson-compliance/digital-transformation-roadmap — use a general .gitignore. Also include *.sublime-workspace and *.sublime-project entries. Also git rm README.sublime-workspace and commit that removal separately with message "chore: remove IDE artifact"
3. https://github.com/davidcockson-compliance/Policy-Update-Tracker — use Python template
4. https://github.com/davidcockson-compliance/policy-generator — use Python template
5. https://github.com/davidcockson-compliance/davidockson-compliance — use a minimal .gitignore (.env, .DS_Store, *.log)
```
- [ ] Completed

---

## Task 4: Add MIT LICENSE to repos missing one
**Repos:** Multiple
**Prompt:**
```
For each of these repositories, clone it, add a file called LICENSE containing the MIT License text with copyright holder "David Cockson" and year 2025, commit with message "chore: add MIT license", and push to main:

1. https://github.com/davidcockson-compliance/scarlet-helix
2. https://github.com/davidcockson-compliance/job-radar-
3. https://github.com/davidcockson-compliance/Compliance-Tools
4. https://github.com/davidcockson-compliance/digital-transformation-roadmap
5. https://github.com/davidcockson-compliance/Policy-Update-Tracker
6. https://github.com/davidcockson-compliance/policy-generator
7. https://github.com/davidcockson-compliance/davidockson-compliance
```
- [ ] Completed

---

## Task 5: Fix profile README (broken links + tech stack)
**Repo:** `davidcockson-compliance/davidockson-compliance`
**Prompt:**
```
Clone https://github.com/davidcockson-compliance/davidockson-compliance and edit README.md:

1. Replace the Featured Projects section links so they point to actual repos:
   - "[Compliance Automation Framework]" -> link to https://github.com/davidcockson-compliance/scarlet-helix with description "UKGC license intelligence and monitoring dashboard"
   - "[AML Transaction Monitor]" -> link to https://github.com/davidcockson-compliance/saasx-soc2-certification with description "SOC 2 Type II certification project with automated evidence generation"
   - "[Regulatory Reporting Dashboard]" -> link to https://github.com/davidcockson-compliance/digital-transformation-roadmap with description "Digital transformation planning framework for compliance modernization"

2. Update the Technologies & Tools section to reflect actual skills:
   Languages: Python, JavaScript, TypeScript, SQL, PowerShell, HTML/CSS
   Frameworks & Libraries: React, Node.js, Prisma, Vite
   Data & Analytics: Excel, Pandas, Matplotlib
   DevOps & Tools: Docker, Git/GitHub, GitHub Actions
   Collaboration: Jira, Confluence
   Currently Exploring: Ubuntu (Mint), AI tools, advanced Python automation

3. Commit with message "fix: update featured project links and technology stack" and push to main.
```
- [ ] Completed

---

## Task 6: Write root README for `job-radar-`
**Repo:** `davidcockson-compliance/job-radar-`
**Prompt:**
```
Clone https://github.com/davidcockson-compliance/job-radar- and create a root-level README.md based on what actually exists in the codebase. Read the directory structure, package.json files, Dockerfile, docker-compose.yml, and key source files to understand the project, then write a README with:

1. Project title and one-paragraph description
2. Tech stack section (list frontend and backend technologies)
3. Features section (list the job board parsers found in the codebase)
4. Prerequisites (Node.js, Docker)
5. Getting started / setup instructions (based on docker-compose.yml and package.json scripts)
6. Project structure overview (brief tree of key directories)
7. License: MIT

Keep it concise — no more than 100 lines. Commit with message "docs: add project README" and push to main.
```
- [ ] Completed

---

## Task 7: Add GitHub repo descriptions via API
**Note:** This requires `gh` CLI or GitHub web UI. Cannot be done via git alone.
**Prompt (manual or via `gh`):**
```
Using the GitHub web UI or gh CLI, set these repository descriptions:

1. scarlet-helix: "Intelligence tool for tracking and analyzing UK Gambling Commission licenses with real-time monitoring"
2. job-radar-: "Full-stack job discovery and pipeline tracker with multi-source parsing and Docker deployment"

If using gh CLI:
gh repo edit davidcockson-compliance/scarlet-helix --description "Intelligence tool for tracking and analyzing UK Gambling Commission licenses with real-time monitoring"
gh repo edit davidcockson-compliance/job-radar- --description "Full-stack job discovery and pipeline tracker with multi-source parsing and Docker deployment"
```
- [ ] Completed

---

## Task 8: Archive/privatize placeholder repos
**Note:** Requires GitHub web UI or `gh` CLI.
**Prompt (manual or via `gh`):**
```
Using GitHub web UI or gh CLI:

1. Archive: davidcockson-compliance/policy-generator
2. Archive: davidcockson-compliance/Compliance-Tools
3. Make private (or archive): davidcockson-compliance/Policy-Update-Tracker

If using gh CLI:
gh repo archive davidcockson-compliance/policy-generator --yes
gh repo archive davidcockson-compliance/Compliance-Tools --yes
gh repo edit davidcockson-compliance/Policy-Update-Tracker --visibility private
```
- [ ] Completed

---

## Task 9: Pin top repositories on GitHub profile
**Note:** Must be done via GitHub web UI (no API/CLI support for pinning).
**Instructions:**
```
1. Go to https://github.com/davidcockson-compliance
2. Click "Customize your pins"
3. Select these 4 repositories:
   - scarlet-helix
   - job-radar-
   - saasx-soc2-certification
   - digital-transformation-roadmap
4. Save
```
- [ ] Completed

---

## Task 10: Fix profile repo name
**Note:** Requires GitHub web UI.
**Instructions:**
```
1. Go to https://github.com/davidcockson-compliance/davidockson-compliance/settings
2. Under "Repository name", change from "davidockson-compliance" to "davidcockson-compliance"
3. This ensures the profile README renders on your GitHub profile page
4. Note: this will change all git remote URLs — update any local clones
```
- [ ] Completed

---

## Task 11: Restructure `digital-transformation-roadmap`
**Repo:** `davidcockson-compliance/digital-transformation-roadmap`
**Prompt:**
```
Clone https://github.com/davidcockson-compliance/digital-transformation-roadmap and reorganize:

1. Create a planning/ directory
2. Move these files into planning/:
   - business-requirements.md
   - project-charter.md
   - risk-register.md
3. Update any internal markdown links that reference these files
4. Commit with message "refactor: move planning documents into planning/ subdirectory"
5. Push to main.
```
- [ ] Completed

---

## Task 12: Clarify `saasx-soc2-certification` as educational
**Repo:** `davidcockson-compliance/saasx-soc2-certification`
**Prompt:**
```
Clone https://github.com/davidcockson-compliance/saasx-soc2-certification and edit the README.md:

1. Add a clear disclaimer near the top (after the title), such as:
   "> **Note:** This is an educational/demonstration project for a fictional company 'SaaSX'. No real compliance data is contained in this repository."
2. Remove or rephrase any language suggesting access restrictions (e.g., "restricted to authorized team members") since the repo is public with MIT license.
3. Commit with message "docs: clarify project as educational demonstration" and push to main.
```
- [ ] Completed

---

## Order of Execution

**Security-first, then hygiene, then polish:**

| Priority | Tasks | Type |
|----------|-------|------|
| 1 | Task 1, Task 2 | Security audit |
| 2 | Task 3 | .gitignore coverage |
| 3 | Task 10 | Profile repo name fix |
| 4 | Task 4 | Licensing |
| 5 | Task 5 | Profile README fix |
| 6 | Task 6 | Documentation |
| 7 | Task 7 | Repo descriptions |
| 8 | Task 8 | Cleanup/archive |
| 9 | Task 9 | Profile pinning |
| 10 | Task 11 | Restructuring |
| 11 | Task 12 | Clarification |
