# GitHub Profile Review: davidcockson-compliance

**Review Date:** 2026-02-04
**Profile:** [github.com/davidcockson-compliance](https://github.com/davidcockson-compliance)
**Repositories Analyzed:** 8 public repos

---

## Executive Summary

David Cockson's GitHub profile tells the story of a compliance professional actively building technical skills. The profile has a strong foundation -- a well-written bio, clear domain expertise, and two standout projects (`scarlet-helix` and `job-radar-`). However, several repositories are stubs or placeholders that dilute the portfolio's impact, and there are gaps in licensing, `.gitignore` coverage, and documentation consistency that should be addressed.

---

## 1. Critical Actions (Security & Functionality)

### 1.1 Committed SQLite Databases in `job-radar-`
**Severity: Medium-High**

Two `dev.db` SQLite database files are committed to the repository:
- `backend/dev.db`
- `backend/prisma/dev.db`

The `.gitignore` has the `dev.db` exclusion rule **intentionally commented out** with a note about keeping deployment data. These database files may contain personal job search data, saved listings, or configuration tied to personal accounts.

**Action:** Uncomment the `dev.db` line in `.gitignore`, remove the files from tracking (`git rm --cached`), and consider whether the history needs cleaning with `git filter-branch` or BFG Repo-Cleaner.

### 1.2 Potential API Key Exposure in `job-radar-`
**Severity: Medium**

`backend/src/services/companiesHouse.js` likely interacts with the Companies House API, which requires an API key. Without inspecting the file contents, it's unclear whether the key is loaded from an environment variable or hardcoded.

**Action:** Audit `companiesHouse.js` to confirm the API key is sourced from environment variables (e.g., `process.env.COMPANIES_HOUSE_API_KEY`), not hardcoded. Also run `git log -p -- backend/src/services/companiesHouse.js` to check if keys were ever committed in earlier versions.

### 1.3 Potential API Key in `scarlet-helix` sync script
**Severity: Medium**

`scripts/sync.ps1` (5,866 bytes) fetches data from the UK Gambling Commission regulatory register. This script could contain hardcoded credentials or API endpoints with authentication tokens.

**Action:** Audit `sync.ps1` for any hardcoded credentials. If the script fetches from a public API, document that clearly in a comment.

### 1.4 Missing `.gitignore` Files (Multiple Repos)
**Severity: Medium**

The following repositories have **no `.gitignore`** at all:
- `scarlet-helix`
- `Compliance-Tools`
- `digital-transformation-roadmap`
- `Policy-Update-Tracker`
- `policy-generator`
- `davidockson-compliance` (profile repo)

Without a `.gitignore`, there is no safeguard against accidentally committing `.env` files, IDE configurations, OS artifacts (`.DS_Store`), or other sensitive content.

**Action:** Add appropriate `.gitignore` files to all repositories. Use GitHub's templates (e.g., Node.js for JS projects, Python for Python projects).

### 1.5 No Branch Protection on Any Repository
**Severity: Low-Medium**

No repository has branch protection enabled on `main`. For the compliance-focused repos (`saasx-soc2-certification` in particular), this is a governance gap -- anyone with write access can push directly to `main` without review.

**Action:** Enable branch protection rules on `main` for at least `saasx-soc2-certification` and `scarlet-helix` (require PR reviews, status checks).

---

## 2. Quick Wins (Cleanup & Basic Hygiene)

### 2.1 Missing LICENSE Files (6 of 8 repos)

| Repository | LICENSE Status |
|---|---|
| scarlet-helix | **Missing** |
| job-radar- | **Missing** (MIT declared in package.json but no file) |
| saasx-soc2-certification | MIT License present |
| davidockson-compliance | **Missing** |
| Compliance-Tools | **Missing** |
| digital-transformation-roadmap | **Missing** |
| Policy-Update-Tracker | **Missing** (MIT mentioned in README) |
| policy-generator | **Missing** |

**Action:** Add MIT `LICENSE` files to all repositories. Takes 2 minutes per repo via GitHub's "Add file" UI.

### 2.2 Repository Naming Issues

| Issue | Repository | Recommendation |
|---|---|---|
| Trailing hyphen | `job-radar-` | Rename to `job-radar` |
| Typo in profile repo | `davidockson-compliance` (missing 'c') | Should be `davidcockson-compliance` to match the username for the special profile README feature |
| Inconsistent casing | `Compliance-Tools` vs `policy-generator` | Standardize to lowercase-with-hyphens |
| Inconsistent casing | `Policy-Update-Tracker` | Rename to `policy-update-tracker` |

**Note on profile repo:** The repo is named `davidockson-compliance` but the GitHub username is `davidcockson-compliance`. For the profile README to render on the profile page, the repo name **must exactly match** the username. This appears to be a typo that may prevent the README from displaying.

### 2.3 Remove IDE Artifact

`digital-transformation-roadmap` contains a `README.sublime-workspace` file committed to the root. This is an IDE configuration file that should not be in version control.

**Action:** Remove the file and add `*.sublime-workspace` and `*.sublime-project` to `.gitignore`.

### 2.4 Large Data Files in `scarlet-helix`

The `data/` directory contains ~8.4 MB of JSON/JS files tracked in Git:
- `data/current.js` (2.8 MB) + `data/current.json` (2.8 MB) -- duplicate formats
- `data/history/data_2026-01-24.json` (2.8 MB)

As the history directory grows with more snapshots, this repo will become increasingly heavy.

**Action:** Consider Git LFS for the data files, or host the data externally (e.g., GitHub Releases, a CDN, or a separate data repo). At minimum, eliminate the JS/JSON duplication.

### 2.5 Add Repository Descriptions

| Repository | Current Description |
|---|---|
| scarlet-helix | **None** |
| job-radar- | **None** |
| saasx-soc2-certification | "SOC 2 Type II Certification Project" |
| davidockson-compliance | "about me" |
| Compliance-Tools | "Looking at ways to explore in a more structured way" |
| digital-transformation-roadmap | Has description |
| Policy-Update-Tracker | Has description |
| policy-generator | "Project to create a Policy Generator" |

**Action:** Add clear, professional one-line descriptions to `scarlet-helix` and `job-radar-`. These are the two strongest projects and currently have no descriptions at all.

Suggested descriptions:
- **scarlet-helix:** "Intelligence tool for tracking and analyzing UK Gambling Commission licenses with real-time monitoring"
- **job-radar-:** "Full-stack job discovery and pipeline tracker with multi-source parsing and Docker deployment"

---

## 3. Deep Work (Documentation & Project Refinement)

### 3.1 README Quality Assessment

| Repository | Has README | Title | Description | Setup | Usage | Screenshots | Grade |
|---|---|---|---|---|---|---|---|
| scarlet-helix | Yes | Yes | Yes | Yes (Docker + local) | Yes | No | **B+** |
| job-radar- | **Root: No** | - | - | - | - | - | **F** |
| saasx-soc2-certification | Yes | Yes | Yes | Partial | Yes | No | **B** |
| davidockson-compliance | Yes | Yes | Yes | N/A | N/A | No | **B** (profile) |
| Compliance-Tools | Yes | Yes | Minimal | No | No | No | **D** |
| digital-transformation-roadmap | Yes | Yes | Yes | Partial | Yes | No | **B-** |
| Policy-Update-Tracker | Yes | Yes | Yes | Yes | Yes | No | **B** (but no code exists) |
| policy-generator | Yes | Barely | One sentence | No | No | No | **F** |

**Priority actions:**
1. **`job-radar-`**: Needs a root-level README urgently. This is a full-stack application with Docker, Prisma, React, multiple job board parsers -- it deserves comprehensive documentation with setup instructions, architecture overview, and screenshots.
2. **`scarlet-helix`**: Add a screenshot or demo GIF. This is a visual dashboard tool -- showing it in action would dramatically increase appeal.
3. **`Compliance-Tools`**: Flesh out the README or consider merging this into the profile README. Currently it reads like a personal scratchpad.

### 3.2 Repository Structure Audit

**Well-structured:**
- `saasx-soc2-certification` -- Excellent phase-aligned directory layout with `docs/`, `evidence/`, `scripts/`, `templates/`
- `job-radar-` -- Clean monorepo with `backend/` and `frontend/` separation, Docker support, Prisma migrations
- `scarlet-helix` -- Logical separation of `css/`, `js/`, `data/`, `scripts/`

**Needs work:**
- `digital-transformation-roadmap` -- Root-level clutter (business-requirements.md, project-charter.md, risk-register.md, IDE workspace file). These planning docs should be in a `docs/` or `planning/` subdirectory.
- `Compliance-Tools` -- Files with spaces in names (`docs/100 ai use cases by gemini`). Use hyphens or underscores instead.

### 3.3 `saasx-soc2-certification` -- License vs. Access Contradiction

The README states the repository contains "sensitive compliance documentation restricted to authorized team members" but the repo is **public** with an **MIT license**. This is contradictory.

**Action:** Either make the repo private (if it contains real compliance data) or update the README to clarify this is a demonstrative/educational project for a fictional "SaaSX" company.

---

## 4. Portfolio Strategy

### 4.1 Highlight Candidates (Top Projects)

**Tier 1 -- Pin These:**

1. **`scarlet-helix`** -- The strongest portfolio piece. A real-world compliance intelligence tool with Docker support, technical documentation, and clear domain relevance. Demonstrates: frontend development, data processing, containerization, regulatory expertise.

2. **`job-radar-`** -- Impressive full-stack application. Backend (Node.js + Prisma + SQLite) with parsers for 7 job boards (Ashby, Greenhouse, Indeed, Lever, LinkedIn, Otta, Rippling). Frontend (React + TypeScript + Vite). Docker + nginx. Demonstrates: full-stack development, API integration, database design, TypeScript.

3. **`saasx-soc2-certification`** -- Showcases deep compliance knowledge. Well-organized project structure, Python scripts for synthetic evidence generation and GitHub issue automation. Demonstrates: compliance expertise, Python, project management methodology.

**Tier 2 -- Improve Then Pin:**

4. **`digital-transformation-roadmap`** -- Good content but needs structural cleanup. Demonstrates strategic thinking and business-to-technical translation skills.

**Tier 3 -- Archive or Make Private:**

5. **`Compliance-Tools`** -- An organizational index with no code. Better served as a section in the profile README.
6. **`Policy-Update-Tracker`** -- Ambitious README describing features that don't exist. Until code is added, this creates a credibility gap.
7. **`policy-generator`** -- A 56-byte README stub. Adds no value to the public portfolio.

### 4.2 Pinning Recommendations

Pin these 4 repositories on the GitHub profile:
1. `scarlet-helix`
2. `job-radar-`
3. `saasx-soc2-certification`
4. `digital-transformation-roadmap`

### 4.3 Archive Candidates

| Repository | Action | Reason |
|---|---|---|
| `policy-generator` | Archive or make private | Empty stub (56-byte README only) |
| `Compliance-Tools` | Archive or make private | No code; just a planning index |
| `Policy-Update-Tracker` | Make private until implemented | README promises features with no backing code |

### 4.4 Profile README Improvements

The profile README is well-written but has some issues:

1. **Featured Projects links are broken** -- The "Featured Projects" section references `[Compliance Automation Framework]`, `[AML Transaction Monitor]`, and `[Regulatory Reporting Dashboard]`, but none of these repositories exist. These should link to actual repos (`scarlet-helix`, `job-radar-`, `saasx-soc2-certification`).

2. **Technologies section is thin** -- Lists only "Python" and "Excel." Based on the actual repos, you should add: JavaScript, TypeScript, React, Node.js, SQL/Prisma, Docker, HTML/CSS, PowerShell, Git/GitHub Actions.

3. **Personal email is exposed** -- `DavidCockson@gmail.com` is publicly visible. Consider whether this is intentional or if a contact form / LinkedIn message would be preferable.

4. **Profile repo name typo** -- As noted, `davidockson-compliance` is missing a 'c'. If this is the special profile repo, it won't render unless the name matches the username exactly.

---

## 5. Portfolio Narrative

### What Story Does This GitHub Tell?

**Current narrative:** A compliance professional in early stages of building a technical portfolio, with a mix of genuine working projects and aspirational placeholders.

**Strengths:**
- Clear domain expertise in gambling/regulatory compliance (UKGC, MGA, AML)
- Two genuinely impressive projects (`scarlet-helix`, `job-radar-`) that demonstrate real engineering capability
- The SOC 2 project shows structured thinking and knowledge of compliance frameworks
- Active contribution pattern (repos from Sept 2025 to Feb 2026)

**Weaknesses:**
- The placeholder repos (policy-generator, Policy-Update-Tracker without code) undermine credibility -- they suggest projects were announced but not followed through
- Broken links in the profile README create a "vaporware" impression
- Missing documentation on the two best projects is a significant missed opportunity
- Inconsistent naming and missing licenses suggest the portfolio hasn't been curated

**Recommended narrative (after cleanup):**
> "A compliance technology professional who builds real tools that solve regulatory problems. The portfolio demonstrates full-stack capability (scarlet-helix, job-radar-), compliance domain expertise (SOC 2 certification project), and strategic thinking (digital transformation roadmap). Each project connects domain knowledge with practical engineering."

---

## Summary Action Items

### Immediate (This Week)
- [ ] Audit `companiesHouse.js` and `sync.ps1` for hardcoded secrets
- [ ] Remove committed `dev.db` files from `job-radar-` and update `.gitignore`
- [ ] Fix profile repo name typo (`davidockson-compliance` -> `davidcockson-compliance`)
- [ ] Add `.gitignore` files to all repositories missing them
- [ ] Archive or make private: `policy-generator`, `Compliance-Tools`

### Short-Term (This Month)
- [ ] Write a comprehensive root README for `job-radar-`
- [ ] Add MIT LICENSE files to all repos
- [ ] Add descriptions to `scarlet-helix` and `job-radar-`
- [ ] Fix broken Featured Projects links in profile README
- [ ] Update Technologies section in profile README
- [ ] Add screenshot/demo to `scarlet-helix` README
- [ ] Remove `README.sublime-workspace` from `digital-transformation-roadmap`
- [ ] Pin top 4 repositories on GitHub profile

### Medium-Term (Next Quarter)
- [ ] Implement code for `Policy-Update-Tracker` (or keep it private until ready)
- [ ] Move `digital-transformation-roadmap` planning docs into subdirectories
- [ ] Set up Git LFS or external hosting for `scarlet-helix` data files
- [ ] Enable branch protection on key repositories
- [ ] Clarify `saasx-soc2-certification` as educational/fictional to resolve license contradiction
- [ ] Add GitHub Actions CI/CD to `scarlet-helix` and `job-radar-`
