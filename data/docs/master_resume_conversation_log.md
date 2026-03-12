# Master Resume Conversation Log

## Session Overview
- Workspace: `D:\02.job`
- Goal: build a master resume by collecting raw evidence from prior application materials and source repositories.
- Logging policy: record prior conversation, active plan, execution notes, and future updates in this file.

## Conversation History
### 2026-03-11
- User asked what is needed to write a master resume.
- Response outlined required inputs: basic profile, target roles, experience inventory, quantified outcomes, tech stack, flagship projects, education/certifications, and a unifying narrative.

- User asked to create `data/docs/templete` and save a template, provided GitHub ID `atozwizard`, and agreed that material collection is required.
- Action taken:
  - Created directory `data/docs/templete`.
  - Added [`master_resume_materials_template.md`](/d:/02.job/data/docs/templete/master_resume_materials_template.md).
- Resolution:
  - Template includes profile fields, target roles, branding, tech stack, experience capture, project candidates, quantified outcomes, assets, and next-source checklist.

- User pointed out that `data` does not contain enough repository/project material and suggested that cloning GitHub repositories should be the priority.
- Decision:
  - Agreed. Repository cloning became the priority because resume evidence should be grounded in code, commits, docs, and project structure rather than memory alone.

- User requested:
  - Clone all non-fork repositories for GitHub account `atozwizard`.
  - Clone `https://github.com/Pommit/company_analyzer.git` on branch `dev`.
  - Clone `https://github.com/han0gu/programmers-high-score-kit.git` on branch `main`.
- Action taken:
  - Queried GitHub for non-fork repositories under `atozwizard`.
  - Cloned all returned repositories under `repo/`.
  - Cloned requested external repositories under `repo/`.
- Resolution:
  - Cloned repositories:
    - `atozwizard`
    - `fake_llm_project`
    - `idol_agent_LUMI`
    - `job-analyzer`
    - `manufacturing-ai-coach`
    - `news_chatbot_agent_student`
    - `retry`
    - `sesac_upstage_ai_study`
    - `study_sesac`
    - `trade-onboarding-agent`
    - `upstage-network-lecture`
    - `company_analyzer`
    - `programmers-high-score-kit`
  - Verified target branches by reading `.git/HEAD`:
    - `company_analyzer` -> `dev`
    - `programmers-high-score-kit` -> `main`

### 2026-03-12
- User asked how work would proceed if a project README is missing or weak.
- Decision:
  - Use README as a secondary source only.
  - Fall back to code-first profiling:
    - inspect folder structure
    - read dependency/config files
    - identify entrypoints and core modules
    - inspect commit history and contribution patterns
    - cross-check issues, PRs, and generated artifacts when needed

- User requested two process changes:
  1. Record the full conversation log so far and continue logging future work with plan/progress/resolution summaries.
  2. If a project README is missing or weak, follow a priority order, then create or revise README files before continuing with the broader plan.
- Current response:
  - Creating persistent logs.
  - Starting a repository README audit and remediation queue.

## Active Plan
1. Create persistent logs and record prior conversation plus current status.
2. Audit cloned repositories for README presence and quality.
3. Prioritize repositories with missing or weak documentation.
4. Create or revise README files for highest-priority repositories.
5. Continue repository profiling for master-resume raw data extraction.

## Execution Notes
- Existing file `data/master_resume_guide.txt` displayed as mojibake when read in the terminal, so new UTF-8 markdown documentation was favored over editing that file directly.
- Git branch inspection via standard Git commands hit `dubious ownership` protection; `.git/HEAD` was used as a non-invasive verification fallback.

## Latest Update
### 2026-03-12
- Planned:
  - create persistent work logs
  - audit repository README quality
  - start remediation for repositories with critical documentation gaps
- Attempted:
  - created persistent log files under `data/docs`
  - scanned cloned repositories for README presence, size, and top-level structure
  - inspected weak-documentation repositories directly from code and notebook contents
- Resolved:
  - added conversation log and progress tracker
  - added README audit file
  - replaced weak README files for:
    - `repo/fake_llm_project`
    - `repo/retry`
    - `repo/atozwizard`
- How it was solved:
  - `fake_llm_project`: reconstructed purpose from `main.py`, `agent.py`, `tools.py`, and `workflow.py`
  - `retry`: reconstructed notebook scope from `SeSAC_2강_Tutorial.ipynb` contents
  - `atozwizard`: reconstructed project description from FastAPI routes and MySQL repository code
- Next:
  - review medium-priority repositories with usable but weak documentation
  - continue project profiling for master-resume raw evidence extraction

## Next Update Rule
- After each substantial step, append:
  - what was planned
  - what was attempted
  - what was resolved
  - what remains next
