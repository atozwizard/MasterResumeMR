# 프로젝트 문제해결 서비스보고서

## 프로젝트명
`idol_agent_LUMI`

## 한 줄 요약
가상 아이돌 캐릭터와의 대화를 `서비스로 운영 가능한 수준`으로 만들기 위해, LangGraph 기반 대화 구조와 LLMOps 요소를 결합한 AI 백엔드 프로젝트.

## 1. problem solve 관점

### 어떤 문제를 풀려 했는가
- 캐릭터형 챗봇은 단순히 답을 생성하는 것만으로는 부족하고, 세계관 일관성, 세션 유지, 장애 대응, 비용 통제, 관측 가능성이 함께 필요하다.
- 여러 데이터 소스(RAG 문서, 일정, 팬레터, 대화 이력)를 연결하지 않으면 캐릭터 응답 품질이 쉽게 흔들린다.
- 스트리밍과 상태 저장이 없으면 사용자 체감 품질과 운영 디버깅이 모두 약해진다.

### 왜 이 방식으로 풀었는가
- 대화 흐름을 노드와 엣지로 나눠야 의도 분류, 검색, tool 실행, 응답 생성의 책임을 분리할 수 있다.
- 캐릭터 서비스는 일반 챗봇보다 재방문과 세션 지속성이 중요하므로 checkpointer와 conversation 저장이 필요하다.
- 운영 중 장애와 비용 문제를 추적하려면 LiteLLM fallback, token counter, cost tracker, Langfuse tracing이 먼저 붙어야 한다.

### 어떻게 구현했는가
- FastAPI와 UI를 함께 두고 API/서비스 레이어를 분리했다.
- LangGraph `state`, `nodes`, `edges`, `graph` 구조로 대화 흐름을 구현했다.
- repository 계층에 RAG 검색, 일정 조회, 팬레터 저장, 대화 저장을 분리했다.
- `core/llm.py`, `checkpointer.py`, `token_counter.py`, `cost_tracker.py`, `tracing.py`로 운영형 기능을 분리했다.

## 2. project service 관점

### 서비스로서 무엇을 제공하는가
- 가상 아이돌 `LUMI`와 대화하는 API
- 스트리밍 응답 경험
- 세계관 기반 응답 생성
- 일정 조회와 팬레터 저장 같은 캐릭터 서비스 기능

### 사용자 가치
- 단순 정보봇이 아니라 캐릭터성과 지속성을 가진 대화 경험을 제공할 수 있다.
- 팬 입장에서는 일회성 답변보다 `계속 대화할 수 있는 경험`이 중요하며, 이 프로젝트는 그 구조를 먼저 설계했다.

### 서비스 구조의 의미
- `fallback`, `checkpoint`, `cost tracking`, `tracing`을 갖춘 구조는 실제 서비스 운영을 전제한 설계다.
- 반복 사용되는 캐릭터형 AI에서는 이 요소들이 사용성보다 먼저 신뢰와 운영 가능성을 만든다.

## 3. 리줌에 쓸 수 있는 포인트
- LiteLLM fallback, checkpointer, cost tracker, Langfuse tracing을 포함한 운영형 AI 서비스 구조 구현
- RAG, 일정, 팬레터 저장을 연결한 캐릭터형 챗봇 백엔드 구축
- 스트리밍 응답과 상태 저장을 포함한 서비스형 대화 경험 설계

## 4. 확인한 근거
- `README.md`
- `app/main.py`
- `app/ui.py`
- `app/core/llm.py`
- `app/core/checkpointer.py`
- `app/core/cost_tracker.py`
- `app/core/tracing.py`
- `app/graph/state.py`
- `app/graph/nodes.py`
- `app/graph/edges.py`
- `app/graph/graph.py`
- `app/repositories/rag.py`
- `app/repositories/schedule.py`
- `app/repositories/fan_letter.py`
- `app/repositories/conversation.py`
- `app/api/routes/chat.py`

## 5. 다음 보강 포인트
- 실제 배포/운영 결과
- 비용 추적과 fallback의 정량 지표
- 캐릭터 응답 품질 평가 지표
