# Task Queue v2: GitHub Profile Cleanup (Round 2)

**Last reviewed:** 2026-02-04
**Profile:** [github.com/davidcockson-compliance](https://github.com/davidcockson-compliance)

Run each task as a separate chat session. Copy the **Prompt** into a new Claude Code chat, let it complete, then move to the next. Mark `[x]` when done.

---

## Completed in Round 1

- [x] Profile repo renamed (`davidockson-compliance` -> `davidcockson-compliance`)
- [x] Profile README rewritten (featured projects, tech stack, Mermaid timeline)
- [x] `job-radar-` root README created
- [x] Repo descriptions added to `scarlet-helix` and `job-radar-`
- [x] `policy-generator` and `Compliance-Tools` archived
- [x] `Policy-Update-Tracker` made private
- [x] `digital-transformation-roadmap` restructured (planning/ subdirectory, sublime workspace removed)
- [x] `saasx-soc2-certification` educational disclaimer added
- [x] `digital-transformation-roadmap` .gitignore added
- [x] `davidcockson-compliance` profile repo .gitignore added
- [x] `scarlet-helix` sync.ps1 confirmed clean (public UKGC URLs only)
- [x] `job-radar-` companiesHouse.js confirmed using `process.env`
- [x] `homelab` repo created with README

---

## Still Outstanding

### Task 1: Remove `dev.db` files from `job-radar-` (SECURITY)
**Repo:** `davidcockson-compliance/job-radar-`
**Why:** Two SQLite database files (`backend/dev.db` at 36KB, `backend/prisma/dev.db` at 127KB) are still committed. The `.gitignore` has the `dev.db` exclusion **intentionally commented out** with a note about keeping deployment data. These files may contain personal job search data.
**Prompt:**
```
Clone https://github.com/davidcockson-compliance/job-radar- and do the following:

1. In the root .gitignore, find the commented-out line about dev.db and replace it with an active exclusion. Change:
   # Keeping it un-ignored for now so your deployment has your current zones!
   # backend/prisma/dev.db
   To:
   *.db

2. Remove the database files from git tracking (but keep them locally):
   git rm --cached backend/dev.db backend/prisma/dev.db

3. Commit with message: "fix: remove tracked dev.db files and add *.db to .gitignore"
4. Push to main.
```
- [ ] Completed

---

### Task 2: Add `.gitignore` to `scarlet-helix`
**Repo:** `davidcockson-compliance/scarlet-helix`
**Why:** This repo has no `.gitignore` at all. No safeguard against accidentally committing `.env`, IDE files, or `node_modules/`.
**Prompt:**
```
Clone https://github.com/davidcockson-compliance/scarlet-helix and do the following:

1. Create a .gitignore file with these contents:

# Dependencies
node_modules/

# Environment
.env
.env.local
.env.*.local

# IDE
.vscode/
.idea/
*.sublime-workspace
*.sublime-project
*.swp
*.swo

# OS
.DS_Store
Thumbs.db

# Logs
*.log
npm-debug.log*

# Build
dist/
build/

2. Commit with message: "chore: add .gitignore"
3. Push to main.
```
- [ ] Completed

---

### Task 3: Add `.gitignore` to `homelab`
**Repo:** `davidcockson-compliance/homelab`
**Why:** New repo with no `.gitignore`. As infrastructure configs get added, this needs protection against committing secrets, SSH keys, or `.env` files.
**Prompt:**
```
Clone https://github.com/davidcockson-compliance/homelab and do the following:

1. Create a .gitignore file with these contents:

# Environment and secrets
.env
.env.*
*.pem
*.key
*.crt
id_rsa*
*.tfstate
*.tfstate.backup

# OS
.DS_Store
Thumbs.db

# IDE
.vscode/
.idea/
*.swp

# Docker
docker-compose.override.yml

# Logs
*.log

# Terraform
.terraform/

2. Commit with message: "chore: add .gitignore"
3. Push to main.
```
- [ ] Completed

---

### Task 4: Add MIT LICENSE to 5 repos
**Repos:** `scarlet-helix`, `job-radar-`, `digital-transformation-roadmap`, `davidcockson-compliance`, `homelab`
**Why:** Only `saasx-soc2-certification` has a LICENSE. The rest are public repos with no license, meaning technically no one has permission to use or fork the code.
**Method:** GitHub web UI (fastest — Settings > Add file > Create new file > type "LICENSE" > choose MIT template)
**Instructions:**
```
For each of these 5 repos, go to the GitHub web UI:

1. https://github.com/davidcockson-compliance/scarlet-helix
2. https://github.com/davidcockson-compliance/job-radar-
3. https://github.com/davidcockson-compliance/digital-transformation-roadmap
4. https://github.com/davidcockson-compliance/davidcockson-compliance
5. https://github.com/davidcockson-compliance/homelab

For each:
1. Click "Add file" > "Create new file"
2. Type "LICENSE" as the filename
3. Click "Choose a license template" (appears on the right)
4. Select "MIT License"
5. Set year to 2025 and name to "David Cockson"
6. Click "Review and submit" > Commit to main
```
- [ ] Completed

---

### Task 5: Add topics/tags to all active repos
**Repos:** All 5 active public repos
**Why:** No repos have any topics. Topics improve discoverability and show professionalism.
**Method:** GitHub web UI (click the gear icon next to "About" on each repo page)
**Instructions:**
```
For each repo, click the gear icon next to the description and add topics:

1. scarlet-helix:
   compliance, regtech, ukgc, gambling-commission, docker, javascript, dashboard

2. job-radar-:
   job-search, typescript, react, nodejs, prisma, docker, web-scraping

3. saasx-soc2-certification:
   soc2, compliance, security, python, audit, governance

4. digital-transformation-roadmap:
   digital-transformation, compliance, project-management, regulatory

5. homelab:
   homelab, proxmox, docker, self-hosted, infrastructure
```
- [ ] Completed

---

### Task 6: Rename `job-radar-` to `job-radar`
**Repo:** `davidcockson-compliance/job-radar-`
**Why:** Trailing hyphen in the name looks like a typo/mistake. Clean it up.
**Method:** GitHub web UI
**Instructions:**
```
1. Go to https://github.com/davidcockson-compliance/job-radar-/settings
2. Under "Repository name", change from "job-radar-" to "job-radar"
3. Click "Rename"
4. GitHub will set up a redirect from the old URL automatically.
5. Update the profile README link from job-radar- to job-radar:
   - Edit https://github.com/davidcockson-compliance/davidcockson-compliance/blob/main/README.md
   - Find: job-radar-
   - Replace with: job-radar
   - Commit
```
- [ ] Completed

---

### Task 7: Add screenshot/demo to `scarlet-helix` README
**Repo:** `davidcockson-compliance/scarlet-helix`
**Why:** This is a visual dashboard tool with GitHub Pages enabled. A screenshot in the README would dramatically increase appeal. Currently the README has no visuals.
**Prompt:**
```
Clone https://github.com/davidcockson-compliance/scarlet-helix and do the following:

1. The app is live on GitHub Pages. Take note that the README should reference it.
2. Add a "Live Demo" link at the top of the README pointing to the GitHub Pages URL.
3. Add an "img/" directory and include a screenshot section in the README with a placeholder like:
   > ![Dashboard Screenshot](img/screenshot.png)
   > *Screenshot coming soon — see the [live demo](https://davidcockson-compliance.github.io/scarlet-helix/) to explore the dashboard.*
4. Commit with message: "docs: add live demo link and screenshot placeholder"
5. Push to main.
```
- [ ] Completed

---

### Task 8: Add content to `homelab` repo
**Repo:** `davidcockson-compliance/homelab`
**Why:** Currently contains only a README. The README describes Docker, Portainer, Gitea, Plex, etc. but there's no actual configuration. Adding even basic docker-compose files would make this credible.
**Prompt:**
```
Clone https://github.com/davidcockson-compliance/homelab and do the following:

Based on what the README describes, create a basic project structure:

1. Create docker-compose.yml with service definitions (using placeholder/example values) for:
   - Portainer
   - Uptime Kuma
   - Netdata
   Use official Docker Hub images. Do NOT include any real credentials — use environment variable references.

2. Create a docker-compose.media.yml with:
   - Plex (linuxserver/plex image)
   - Syncthing
   Use environment variable references for paths and credentials.

3. Create a .env.example file documenting all required environment variables.

4. Create a docs/ directory with a brief setup-guide.md explaining how to deploy.

5. Commit with message: "feat: add docker-compose configs and project structure"
6. Push to main.
```
- [ ] Completed

---

### Task 9: Reduce `scarlet-helix` data file bloat
**Repo:** `davidcockson-compliance/scarlet-helix`
**Why:** The `data/` directory has ~8.4MB tracked in git: `current.js` (2.8MB) + `current.json` (2.8MB) are duplicates in different formats, and `history/data_2026-01-24.json` (2.8MB) will keep growing. This makes cloning slow.
**Prompt:**
```
Clone https://github.com/davidcockson-compliance/scarlet-helix and do the following:

1. Check if data/current.js and data/current.json contain the same data in different formats.
2. If they are duplicates, determine which format the app actually uses (check js/app.js and index.html for references).
3. Remove the unused format file and update any references.
4. Add data/history/ to .gitignore (historical snapshots shouldn't be in version control).
5. Run: git rm --cached data/history/
6. Add a note in README.md under a "Data Management" section explaining that:
   - Live data is fetched via sync.ps1
   - Historical snapshots are generated locally and excluded from version control
7. Commit with message: "chore: remove duplicate data format and exclude history from tracking"
8. Push to main.
```
- [ ] Completed

---

### Task 10: Delete old misspelled profile repo (if it still exists)
**Method:** GitHub web UI
**Why:** The old `davidockson-compliance` repo (missing 'c') may still exist alongside the correctly-named `davidcockson-compliance`. Having both is confusing.
**Instructions:**
```
1. Go to https://github.com/davidcockson-compliance/davidockson-compliance
2. If it exists and is separate from the correctly-spelled repo:
   - Go to Settings (bottom of page) > Danger Zone > Delete this repository
   - Confirm deletion
3. If it redirects to davidcockson-compliance, the rename handled it — no action needed.
```
- [ ] Completed

---

### Task 11: Update pinned repos to include `homelab`
**Method:** GitHub web UI
**Why:** The homelab repo is a strong infrastructure showcase. Pin 5 repos instead of 4.
**Instructions:**
```
1. Go to https://github.com/davidcockson-compliance
2. Click "Customize your pins"
3. Select these 5 repositories:
   - scarlet-helix
   - job-radar- (or job-radar if renamed)
   - homelab
   - saasx-soc2-certification
   - digital-transformation-roadmap
4. Save
```
- [ ] Completed

---

### Task 12: Enable branch protection on key repos
**Method:** GitHub web UI
**Why:** No repos have branch protection. For a compliance-focused profile, this is a governance gap.
**Instructions:**
```
For these 3 repos, enable basic branch protection on main:

1. https://github.com/davidcockson-compliance/scarlet-helix/settings/branches
2. https://github.com/davidcockson-compliance/job-radar-/settings/branches  (or job-radar)
3. https://github.com/davidcockson-compliance/saasx-soc2-certification/settings/branches

For each:
1. Click "Add branch ruleset" or "Add rule"
2. Branch name pattern: main
3. Enable: "Require a pull request before merging"
4. Save

Note: This means you'll need to use feature branches and PRs going forward.
This is good practice and demonstrates mature git workflow to recruiters.
```
- [ ] Completed

---

## Order of Execution

| Priority | Task | Type | Method |
|----------|------|------|--------|
| 1 | Task 1 | Security — remove dev.db | Claude Code |
| 2 | Task 2 | Security — scarlet-helix .gitignore | Claude Code |
| 3 | Task 3 | Security — homelab .gitignore | Claude Code |
| 4 | Task 4 | Licensing — MIT on 5 repos | GitHub web UI |
| 5 | Task 5 | Discoverability — add topics | GitHub web UI |
| 6 | Task 6 | Cleanup — rename job-radar- | GitHub web UI |
| 7 | Task 7 | Documentation — scarlet-helix demo link | Claude Code |
| 8 | Task 8 | Content — homelab docker-compose | Claude Code |
| 9 | Task 9 | Optimization — scarlet-helix data files | Claude Code |
| 10 | Task 10 | Cleanup — delete old misspelled repo | GitHub web UI |
| 11 | Task 11 | Profile — update pinned repos | GitHub web UI |
| 12 | Task 12 | Governance — branch protection | GitHub web UI |
