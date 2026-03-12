# 저장소 README 감사

## 감사 기준
- `good`: project purpose, structure, setup, and usage are mostly understandable.
- `usable but weak`: README exists, but key context is missing or too thin for resume evidence.
- `critical`: missing or effectively empty for practical use.

## 감사 결과
| 저장소 | 상태 | 우선순위 | 메모 |
| --- | --- | --- | --- |
| `company_analyzer` | good | high | Active project, already has substantial README. |
| `trade-onboarding-agent` | good | high | Strong candidate for resume extraction. |
| `job-analyzer` | good | high | Has substantial README and likely direct resume value. |
| `idol_agent_LUMI` | good | high | Sufficient starting documentation. |
| `news_chatbot_agent_student` | good | medium | Large README present. |
| `manufacturing-ai-coach` | good | medium | README is structurally sufficient; terminal rendering issues appear to be encoding-related rather than documentation absence. |
| `upstage-network-lecture` | usable but weak -> fixed | medium | Lecture-note oriented README replaced with project-oriented documentation. |
| `programmers-high-score-kit` | usable but weak | medium | Likely problem archive; resume utility depends on curation. |
| `sesac_upstage_ai_study` | usable but weak | medium | Large study log, but may need project-style framing. |
| `study_sesac` | usable but weak -> fixed | low | Very short README replaced with archive-oriented documentation. |
| `atozwizard` | critical -> fixed | low | Boilerplate profile README replaced with project-specific README. |
| `fake_llm_project` | critical -> fixed | medium | Minimal placeholder README replaced with code-based README. |
| `retry` | critical -> fixed | low | Empty README replaced with notebook-based README. |

## 우선순위 기준
1. Resume relevance
2. Documentation gap
3. Ease of reconstructing the project from code

## 완료된 조치
- Rewrote `repo/fake_llm_project/readme.md`
- Rewrote `repo/retry/README.md`
- Rewrote `repo/atozwizard/README.md`
- Rewrote `repo/study_sesac/README.md`
- Rewrote `repo/upstage-network-lecture/README.md`

## 다음 보강 후보
1. `manufacturing-ai-coach`
2. `programmers-high-score-kit`
3. `sesac_upstage_ai_study`

## 다음 단계
README 보강 이후 고가치 저장소마다 아래 항목을 추출한다.
- project summary
- target problem
- stack
- architecture or flow
- direct contribution clues
- measurable or defensible outcome candidates
