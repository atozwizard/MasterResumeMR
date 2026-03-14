# 프로젝트 문제해결 서비스보고서

## 프로젝트명
`upstage-network-lecture`

## 한 줄 요약
FastAPI, MySQL, SQLAlchemy, 예외 처리, Upstage Solar 요약 기능을 함께 연습한 백엔드 실습 프로젝트.

## 1. problem solve 관점

### 어떤 문제를 풀려 했는가
- 백엔드 학습 초기에는 라우트, 서비스 계층, 저장소 계층, 예외 처리, 외부 AI API 연동을 따로 배우면 전체 흐름이 잘 보이지 않는다.
- 단순 CRUD 예제만으로는 실제 서비스 구조를 이해하기 어렵다.
- 사용자 관리와 TODO 관리, AI 요약 기능을 한 프로젝트 안에서 다뤄보는 연습이 필요했다.

### 왜 이 방식으로 풀었는가
- FastAPI 앱 안에 사용자 API, TODO API, 예외 처리, AI 요약 기능을 같이 넣으면 백엔드 기본 구조를 한 번에 볼 수 있다.
- 메모리 기반 TODO와 DB 기반 사용자 경로를 함께 두면 실습 난이도를 나눠서 이해하기 좋다.
- Upstage Solar 요약 기능을 넣으면 단순 백엔드 실습을 넘어 AI API 연동 흐름까지 확인할 수 있다.

### 어떻게 구현했는가
- `main.py`에 FastAPI 진입점, TODO 라우트, 예외 핸들러를 구성했다.
- `app/service/`와 `app/repository/`로 계층을 나눴다.
- `app/core/db.py`에서 MySQL + SQLAlchemy 세션을 설정했다.
- `services/ai_agent.py`를 통해 Upstage Solar 요약 기능을 연결했다.

## 2. project service 관점

### 서비스로서 무엇을 제공하는가
- 사용자 관리 API
- TODO 생성/조회/삭제 API
- TODO 목록 AI 요약 기능

### 사용자 가치
- 백엔드 관점에서는 기본 CRUD, 계층 분리, 예외 처리, AI API 연동을 한 프로젝트 안에서 보여준다.
- 기능은 단순하지만 `실제 서비스 구조의 축소판`처럼 읽을 수 있다.

### 리줌 관점 의미
- FastAPI 백엔드 기본기
- DB 접근 계층 이해
- AI API 연동 경험
- 예외 처리와 라우팅 구조 연습

## 3. 리줌에 쓸 수 있는 포인트
- FastAPI + SQLAlchemy + MySQL 기반 백엔드 실습 프로젝트 구현
- 사용자 API와 TODO API를 계층형 구조로 분리
- Upstage Solar를 활용한 TODO 요약 기능 연동

## 4. 확인한 근거
- `README.md`
- `main.py`
- `app/api/route/user_routers.py`
- `app/service/`
- `app/repository/`
- `app/core/db.py`
- `services/ai_agent.py`

## 5. 다음 보강 포인트
- TODO도 DB 기반으로 통합
- 요청/응답 예시 문서 추가
- 테스트와 스키마 초기화 가이드 보강
