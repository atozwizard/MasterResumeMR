# 프로젝트 문제해결 서비스보고서

## 프로젝트명
`idol_agent_LUMI` - `feat/lgea/arc`

## 한 줄 요약
기존 `LUMI` 서비스 코드베이스 위에, 모델 API의 guardrail 붕괴 특성을 비교 분석하기 위한 연구 전용 워크스페이스 `LGEA`를 추가한 브랜치.

## 1. problem solve 관점

### 어떤 문제를 풀려 했는가
- 기존 서비스형 챗봇 코드와 별개로, 모델 응답층 자체의 안전성 붕괴를 연구 목적으로 정량 분석할 필요가 있었다.
- 페르소나 주입과 공격 강도에 따라 모델별 가드레일 붕괴율이 어떻게 달라지는지 비교할 수 있는 실행/평가/분석 파이프라인이 필요했다.
- 서비스 코드와 연구 코드를 같은 레포 안에 두더라도, 실험 자산과 운영 자산은 분리돼야 했다.

### 왜 이 방식으로 풀었는가
- `LGEA/` 하위에 runner, judge, analysis, personas, configs, reports를 분리해야 실험 파이프라인과 서비스 코드를 섞지 않을 수 있다.
- 연구 대상이 `RAG 제외, 응답층만 평가`로 명확하기 때문에, 별도 브랜치와 별도 워크스페이스로 범위를 고정하는 편이 맞다.
- dry-run, judge 결과, 분석 요약, 최종 리포트를 단계별 산출물로 남겨야 논문용 근거와 재현성을 확보할 수 있다.

### 어떻게 구현했는가
- `LGEA/runner`, `LGEA/judge`, `LGEA/analysis`, `LGEA/personas`, `LGEA/configs`, `LGEA/reports` 구조를 추가했다.
- 모델별 baseline, persona, attack type, scored result, analysis summary를 파일 기반 산출물로 관리했다.
- 기존 `app/` 서비스 코드는 유지하면서 연구 자산을 브랜치 내부 별도 워크스페이스로 격리했다.

## 2. project service 관점

### 서비스라기보다 무엇인가
- 이 브랜치는 사용자 서비스 제공보다 `LLM guardrail erosion analysis` 연구 프레임워크에 가깝다.
- 공격 생성, 실행, 평가, 분석을 반복 가능한 실험 구조로 제공한다.

### 사용자 가치
- 연구자 또는 실험자 입장에서 모델별 안전성 차이를 반복 실행 가능한 구조로 비교할 수 있다.
- 서비스 개발 코드와 평가 실험 코드를 분리해, 운영 코드 오염 없이 연구를 진행할 수 있다.

### 브랜치 구조의 의미
- 기본 브랜치가 서비스형 챗봇 백엔드라면, `feat/lgea/arc`는 연구형 실험 프레임워크 브랜치다.
- 따라서 README, 리줌 서술, 프로젝트 설명도 `서비스`가 아니라 `연구 파이프라인` 중심으로 읽어야 한다.

## 3. 리줌에 쓸 수 있는 포인트
- LLM guardrail erosion 분석을 위한 runner-judge-analysis 파이프라인 설계
- 서비스 코드와 연구 자산을 한 저장소 안에서 브랜치/워크스페이스 수준으로 분리한 경험
- persona, baseline, scored result, analysis summary까지 재현 가능한 연구 구조 설계

## 4. 확인한 근거
- `README.md`
- `LGEA/README.md`
- `docs/LGEA/LGEA_projectspec.md`
- `LGEA/reports/final_report.md`
- `LGEA/runner/*`
- `LGEA/judge/*`
- `LGEA/analysis/*`
- `LGEA/configs/*`

## 5. 다음 보강 포인트
- live run 기반 실제 scored result 확보
- dry-run이 아닌 실측 비교 결과 정리
- 연구 결과를 서비스 안전성 개선과 어떻게 연결할지 설명 보강
