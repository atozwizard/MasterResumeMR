# Portfolio

## Core Narrative
저는 창업과 운영 현장에서 겪은 문제를 흐름과 구조로 다시 보는 사람입니다. 고객이 왜 멈추는지, 공정이 어디서 막히는지, 서비스가 왜 흔들리는지를 먼저 보고, 그 문제를 입력, 상태, 판단, 출력, 검증 구조로 다시 나눕니다. AI 전환 이후에도 이 방식은 그대로 이어졌습니다.

## What I Actually Work On
- 운영 가능한 AI 구조: 상태, 분기, fallback, tracing, cost tracking
- 설명 가능한 AI: RAG, 단계 분리형 에이전트, 평가 파이프라인
- 제품형 AI: 사용자 흐름, 멀티모달 입력, 실패 시 다음 경로 설계
- 연구형 AI: persona 기반 가드레일 붕괴 테스트, 반복 가능한 보고서 자산화

## Featured Projects

### POMMIT
해커톤 기반 팀 프로젝트 안에서 `company_analyzer`의 `service_agent` 흐름을 맡아, HTML 정리 -> 텍스트 정제 -> 단어 빈도 추출 -> collector 전달 구조를 문서와 코드 기준으로 정리했습니다. HybridRAG는 구현 완료보다 다음 단계 방향으로 검토하고 문서화했습니다.

### LGEA
`LUMI` 서비스 응답을 실제로 반복 실행하고, `runner -> judge -> analysis -> reports` 구조로 결과를 남기는 평가 워크스페이스입니다. 핵심은 일반적인 서비스 테스트가 아니라, persona에 따라 모델의 guardrail이 어느 표면에서 무너지는지 비교하는 실험 구조입니다.

### trade-onboarding-agent
무역 실무 온보딩 미니프로젝트에서 `RAG`와 `riskmanaging agent` 흐름을 중심으로 작업했습니다. 무역 도메인 데이터 ingest, ChromaDB 기반 검색, riskmanaging agent 문서와 백엔드 흐름을 정리했고, 리스크 질문을 RAG 근거와 함께 응답하는 구조를 다뤘습니다.

### poketdogam
`chat`, `scan`, `pokedex` 흐름을 나눠 멀티모달 사용자 경험을 설계한 프로젝트입니다. `입력 수집 -> OCR/후보 확인 -> 문맥 검색 -> 응답 생성 -> trace 저장` 구조와 fallback 방향을 함께 설계했습니다.

### LUMI
청년취업사관학교 교육과정 안에서 구조, 아키텍처, 배포, LLMOps까지 학습하기 위해 진행한 운영형 AI 서비스 본체입니다. FastAPI, LangGraph, checkpointer, token/cost tracking, tracing, RAG, fallback 구조를 함께 다뤘습니다.

프로젝트 상세는 [projects](./projects/README.md)에서 볼 수 있습니다.

## Earlier Experience
- 커피소녀오즈: 생두 매입, 로스팅, QC, 메뉴 기획, 브랜딩, B2B 납품 구조 운영
- 우동오즈: 점심 피크타임 병목과 상권 제약 안에서 공정을 손보고 7분 내 서빙 구조로 개선
- 쿤타치 자가제면: 자가제면 공정과 매장 동선을 함께 보며 운영 효율과 제품 정체성을 조정
- 리틀방콕 중계그린점: 25평 규모 매장에서 HR, 근태, 홀 교육, CS 운영, 주방 교육, 프랜차이즈 구조 경험
- 한솔교육: 3개 지역 150개 수업 운영, 프로모션 매출 달성, 예비팀장 승진 경험

## Closing
저는 문제를 기능으로만 넘기지 않습니다. 어떤 단계로 나눌지, 어디서 분기할지, 무엇을 남겨 다시 검증할지까지 설계합니다. 이 방식으로 현장의 문제를 운영 가능한 AI로 연결해 왔고, 앞으로도 같은 방식으로 기여하겠습니다.