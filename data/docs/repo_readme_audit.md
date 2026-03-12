# Repository README Audit

## Audit Rule
- `good`: project purpose, structure, setup, and usage are mostly understandable.
- `usable but weak`: README exists, but key context is missing or too thin for resume evidence.
- `critical`: missing or effectively empty for practical use.

## Audit Snapshot
| Repository | Status | Priority | Notes |
| --- | --- | --- | --- |
| `company_analyzer` | good | high | Active project, already has substantial README. |
| `trade-onboarding-agent` | good | high | Strong candidate for resume extraction. |
| `job-analyzer` | good | high | Has substantial README and likely direct resume value. |
| `idol_agent_LUMI` | good | high | Sufficient starting documentation. |
| `news_chatbot_agent_student` | good | medium | Large README present. |
| `manufacturing-ai-coach` | usable but weak | medium | README exists, but needs closer review for completeness. |
| `upstage-network-lecture` | usable but weak | medium | README exists, but may be lecture-note oriented. |
| `programmers-high-score-kit` | usable but weak | medium | Likely problem archive; resume utility depends on curation. |
| `sesac_upstage_ai_study` | usable but weak | medium | Large study log, but may need project-style framing. |
| `study_sesac` | usable but weak | low | Very short README for a broad study archive. |
| `atozwizard` | critical -> fixed | low | Boilerplate profile README replaced with project-specific README. |
| `fake_llm_project` | critical -> fixed | medium | Minimal placeholder README replaced with code-based README. |
| `retry` | critical -> fixed | low | Empty README replaced with notebook-based README. |

## Priority Logic
1. Resume relevance
2. Documentation gap
3. Ease of reconstructing the project from code

## Actions Completed
- Rewrote `repo/fake_llm_project/readme.md`
- Rewrote `repo/retry/README.md`
- Rewrote `repo/atozwizard/README.md`

## Next Remediation Candidates
1. `manufacturing-ai-coach`
2. `upstage-network-lecture`
3. `study_sesac`

## Downstream Plan
After README remediation, extract for each high-value repository:
- project summary
- target problem
- stack
- architecture or flow
- direct contribution clues
- measurable or defensible outcome candidates
