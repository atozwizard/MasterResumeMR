# POMMIT

## 한 줄 설명
해커톤 기반 팀 프로젝트 안에서 `company_analyzer`의 `service_agent` 흐름을 맡아, NLP 전처리의 시작점과 HybridRAG 확장 방향을 검토한 프로젝트입니다.

## 핵심 내용
- HTML 정리 -> 텍스트 정제 -> 단어 빈도 추출 -> collector 전달 구조를 문서와 코드 기준으로 정리했습니다.
- `cleaned_documents`, `service_word_frequencies` 같은 상태 필드를 기준으로 최소기능을 세웠습니다.
- HybridRAG와 NLP 전처리 강화 방향은 연구 메모와 설계 문서 수준에서 검토하고 문서화했습니다.

## 왜 중요한가
이 프로젝트는 복잡한 에이전트 협업 안에서 구조를 먼저 세우고, 다음 실험 방향까지 정리하는 방식으로 일한다는 점을 보여줍니다.