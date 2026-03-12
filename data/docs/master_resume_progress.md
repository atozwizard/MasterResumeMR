# Master Resume Progress Tracker

## Objective
Build a reusable master resume backed by verifiable raw evidence from repositories, resumes, portfolios, and application materials.

## Status Summary
- Material collection template: completed
- GitHub repository acquisition: completed
- README audit across cloned repositories: in progress
- README remediation for weak/missing docs: in progress
- Repository raw-note extraction for resume evidence: pending

## Decisions
- Source of truth should be repositories and artifacts, not memory.
- Clone all non-fork repositories from `atozwizard`.
- Include active external projects:
  - `Pommit/company_analyzer` on `dev`
  - `han0gu/programmers-high-score-kit` on `main`
- If README quality is poor, document the repository using code-first inspection and then improve the README before downstream analysis.

## Completed
### Template and Workspace Prep
- Created [`data/docs/templete/master_resume_materials_template.md`](/d:/02.job/data/docs/templete/master_resume_materials_template.md)

### Repository Collection
- Cloned repositories into `repo/`
- Confirmed requested branches for externally specified repositories

## In Progress
### README Audit
- Goal: classify each repository into:
  - `good`
  - `usable but weak`
  - `missing`
- Output target: remediation queue ordered by likely resume value and documentation gap.

### README Remediation
- Completed:
  - `repo/fake_llm_project/readme.md`
  - `repo/retry/README.md`
  - `repo/atozwizard/README.md`
- Tracking file:
  - [`data/docs/repo_readme_audit.md`](/d:/02.job/data/docs/repo_readme_audit.md)

## Planned Resolution Method
### If README is good
- Use it as a shortcut, then verify against code.

### If README is weak
- Rewrite key sections:
  - project purpose
  - stack
  - architecture or main flow
  - setup/run instructions
  - notable features
  - result or status

### If README is missing
- Create one from repository inspection:
  - file structure
  - dependencies
  - entrypoints
  - execution flow
  - outputs and artifacts

## Next Actions
1. Scan all cloned repositories for README files.
2. Sample each repository's top-level structure and dependency files.
3. Rank documentation remediation priority by resume relevance.
4. Start with the highest-signal repository lacking usable documentation.
