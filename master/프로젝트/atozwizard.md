# 프로젝트 문제해결 서비스보고서

## 프로젝트명
`atozwizard`

## 한 줄 요약
FastAPI, service, repository 계층을 나눠 MySQL 기반 TODO CRUD를 구현한 소형 백엔드 실습 프로젝트.

## 1. problem solve 관점

### 어떤 문제를 풀려 했는가
- 백엔드 학습 초기에 라우트, 서비스 계층, 저장소 계층이 어떻게 분리되는지 감을 잡기 어렵다.
- 단순 CRUD라도 DB 연동까지 포함해 전체 흐름을 경험할 필요가 있다.

### 왜 이 방식으로 풀었는가
- `main.py`, `service.py`, `repository.py`로 나누면 HTTP 진입점, 비즈니스 로직, DB 접근을 구분해 볼 수 있다.
- TODO 도메인은 단순해서 구조 연습에 적합하다.

### 어떻게 구현했는가
- FastAPI로 TODO 생성/조회/삭제 엔드포인트를 만들었다.
- service 계층에서 흐름을 조율하고, repository 계층에서 MySQL SQL 실행을 담당하도록 분리했다.
- 로컬 MySQL 기반으로 CRUD 흐름을 테스트할 수 있게 구성했다.

## 2. project service 관점

### 서비스로서 무엇을 제공하는가
- TODO 생성
- TODO 목록 조회
- TODO 삭제

### 사용자 가치
- 기능은 단순하지만 백엔드 기본 구조를 보여주는 실습용 서비스로 읽을 수 있다.
- 라우트-서비스-저장소 분리 구조가 명확해 학습 근거로 활용 가능하다.

### 리줌 관점 의미
- FastAPI CRUD 실습
- MySQL 연동 경험
- 계층 분리 구조의 초기 구현 경험

## 3. 확인한 근거
- `README.md`
- `main.py`
- `service.py`
- `repository.py`
