# 프로젝트 문제해결 서비스보고서

## 프로젝트명
`poketdogam`

## 한 줄 요약
포켓몬 도감 질의응답과 이미지 스캔을 결합해, 단순 검색이 아니라 `대화형 + 멀티모달` 도감 경험을 만들려는 FastAPI 기반 AI 서비스 스캐폴드.

## 1. problem solve 관점

### 어떤 문제를 풀려 했는가
- 사용자가 포켓몬 정보를 찾을 때 텍스트 검색, 카드 스캔, 상세 도감 조회가 서로 분리되어 있다.
- 이미지 입력은 OCR 정확도, 후보 매핑, 모델 실패 대응까지 같이 고려해야 실제 서비스로 동작할 수 있다.
- 단순 LLM 호출만으로는 도감형 서비스에서 필요한 구조화된 retrieval과 trace 관리가 부족하다.

### 왜 이 방식으로 풀었는가
- `질문 -> 위치/날씨 해석 -> Hybrid GraphRAG -> 응답 생성 -> trace 저장`처럼 노드를 분리해야 각 단계 오류를 설명하고 개선하기 쉽다.
- 스캔은 실패 가능성이 높기 때문에 메인 모델, fallback 모델, 후보 확인 단계를 처음부터 고려하는 편이 맞다.
- 포켓몬 도감은 단순 텍스트 문답이 아니라 엔티티 관계, 폼, 타입, 진화, 지역 정보가 얽혀 있어 GraphRAG 방향이 자연스럽다.

### 어떻게 구현했는가
- FastAPI로 `chat`, `scan`, `pokedex` 라우트를 분리했다.
- `PokedexAgentGraph`에 입력 수집, 위치/날씨 감지, 문맥 검색, 응답 생성, trace 저장 흐름을 배치했다.
- 아키텍처 문서에서 `LiteLLM`, `Upstage OCR`, `Supabase pgvector`, `Graph DB`, `OpenWeatherMap`, `Langfuse` 조합을 고정했다.

### 현재 한계
- 실제 외부 연동은 아직 일부 스텁 상태다.
- `/pokedex/forms/{form_id}`는 현재 스캐폴드 응답이다.
- 스캔 후보도 현재는 예시 후보 반환에 가깝다.

## 2. project service 관점

### 서비스로서 무엇을 제공하는가
- 포켓몬 질의응답 API
- 이미지 업로드 기반 포켓몬 후보 추출 API
- 폼 단위 도감 상세 조회 API

### 사용자 가치
- 검색과 스캔을 분리하지 않고 한 서비스 안에서 연결할 수 있다.
- 향후 위치/날씨/폼 컨텍스트를 반영한 더 풍부한 도감 응답으로 확장 가능하다.
- 추적성과 fallback 구조를 갖춘 설계라 운영형 AI 서비스로 발전시키기 쉽다.

### 서비스 구조가 가진 강점
- 단일 기능 데모가 아니라 `운영 가능한 AI 서비스`를 목표로 한 설계가 문서와 코드에 함께 남아 있다.
- 데이터 계층, 모델 전략, fallback, observability, API 분리를 초기부터 고려했다.
- 향후 음성, OCR, GraphRAG, 개인화 요소를 자연스럽게 붙일 수 있다.

## 3. 리줌에 쓸 수 있는 포인트
- 멀티모달 입력과 도감형 retrieval 문제를 FastAPI + Agent 그래프로 구조화한 프로젝트
- OCR, GraphRAG, fallback, observability를 포함한 운영형 AI 서비스 설계 경험
- 서비스 초기 단계에서 기능 구현뿐 아니라 데이터 정책, 관측성, 아키텍처까지 함께 설계한 경험

## 4. 확인한 근거
- `app/main.py`
- `app/agents/pokedex_agent/graph.py`
- `app/agents/pokedex_agent/state.py`
- `app/api/routes/chat.py`
- `app/api/routes/scan.py`
- `app/api/routes/pokedex.py`
- `docs/specs/구현_아키텍처_확정안.md`
- `pyproject.toml`

## 5. 다음 보강 포인트
- 실제 외부 연동 완료 여부
- OCR 품질과 fallback 동작 검증
- 스캔 후보 정밀도
- 도감 상세 조회의 실데이터 연결
