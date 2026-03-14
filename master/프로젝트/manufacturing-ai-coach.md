# 제조 설비 유지보수 AI 코치

## 프로젝트 개요
제조 산업 현장의 신입 엔지니어를 위한 AI 기반 설비 유지보수 온보딩 시스템입니다. LangGraph 기반의 에이전트 워크플로우를 통해 실시간 진단, 정비 추천, 및 안전 가드레일 기능을 제공합니다.

## 주요 기능
- 🤖 **자율 진단 에이전트**: 실시간 센서 데이터 분석 및 이상 원인 진단
- 📚 **RAG 기반 지식 검색**: 제조 매뉴얼, SOP, 과거 장애 이력 검색
- 🛡️ **HITL 안전 가드레일**: 인간 승인 기반의 설비 제어
- 📊 **실시간 모니터링**: 센서 데이터 시각화 및 대시보드
- 🎯 **퀴즈 및 시뮬레이션**: 신입 엔지니어 교육용 훈련 시스템

## 기술 스택
- **Backend**: FastAPI, LangGraph, LangChain
- **LLM**: Llama API
- **Vector DB**: ChromaDB
- **Frontend**: React, Tailwind CSS, Streamlit
- **Monitoring**: LangSmith API

## 설치 및 실행
```bash
# 가상환경 생성
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# 의존성 설치
pip install -r requirements.txt

# 환경변수 설정
cp .env.example .env
# .env 파일에 API 키들 설정

# 백엔드 실행
uvicorn main:app --reload --port 8000

# 프론트엔드 실행
cd frontend
npm install
npm start
```

## 프로젝트 구조
```
제조설비유지ai/
├── backend/
│   ├── agents/          # LangGraph 에이전트
│   ├── api/            # FastAPI 라우트
│   ├── models/         # 데이터 모델
│   ├── services/       # 비즈니스 로직
│   └── utils/          # 유틸리티
├── frontend/           # React 프론트엔드
├── docs/              # 문서
└── tests/             # 테스트
```

## 에이전트 아키텍처
1. **Planner Agent**: 워크플로우 전략 수립
2. **Retriever Agent**: RAG 기반 문서 검색
3. **Diagnosis Agent**: 설비 이상 진단
4. **Recommendation Agent**: 정비 방법 추천
5. **Controller Agent**: 설비 제어 (HITL)

## 라이선스
MIT License