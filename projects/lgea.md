# LGEA

## 한 줄 설명
`LUMI` FastAPI와 내부 service surface를 같은 질문 세트로 반복 실행하고, persona에 따른 모델 가드레일 붕괴를 비교하는 평가 워크스페이스입니다.

## 핵심 내용
- `runner -> judge -> analysis -> reports` 흐름으로 질문 실행, 채점, 분석, 보고서를 분리했습니다.
- FastAPI 응답과 `router`, `response-layer`, `rag`, `tool` surface의 차이를 비교합니다.
- 결과를 JSONL, scored result, 통계 요약, 한국어 보고서로 남깁니다.

## 왜 중요한가
이 프로젝트는 단순 서비스 테스트가 아니라, 어떤 persona와 어떤 표면에서 guardrail erosion이 더 쉽게 나타나는지 반복 가능하게 확인하는 실험 구조라는 점이 핵심입니다.