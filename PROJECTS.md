# 장지원 | 프로젝트와 기여

**데이터·AI를 동작하는 서비스로 연결합니다.**

추천 모델을 API로 제공하고, 외부 데이터와 생성형 AI를 연결해 사용자가 직접 쓰는 기능을 만듭니다. 모델의 성능뿐 아니라 데이터 누수, 응답 속도, 오류 상황을 함께 확인하며 개발합니다.

서강대학교 컴퓨터공학과 재학 · 관심 분야: **Data & AI / Backend**

## 대표 프로젝트

### 1. [AutoAdvisor — 국내 주식 위험 판단 보조](https://github.com/Capstone-last-dance/AutoAdvisor)
**5인 캡스톤 · 팀장/PM** | Python · scikit-learn · OpenDART · Streamlit

향후 20거래일의 급락 위험과 진입 후보를 공시 근거와 함께 보여주는 팀 프로젝트입니다.

- **급락 위험 모델 탐색** — 같은 주의 급락·비급락 종목을 짝지어 로지스틱 회귀를 학습하고, 직전 검증 연도 데이터로 위험 점수를 보정했습니다. 팀 공식 모델과 별도로 개발한 후보의 2016~2025년 워크포워드 ROC-AUC는 **0.7230**이었습니다. 사전등록 목표는 **0.7275**였으며, 2026년 홀드아웃은 이 실험의 평가 범위 밖입니다.
- **금융 데이터 검증** — OpenDART 공시와 빅카인즈 뉴스에서 피처를 만들고, 신호일 이후의 상호 변경이 과거 뉴스 피처에 반영되는 누수를 수정했습니다.
- **공시 근거와 LLM 검증** — 판단 시점에 확인할 수 있었던 공시 버전만 선택해 원문을 연결하고, 요약 검사에 실패하면 규칙 기반 템플릿으로 대체하도록 구현했습니다.

[팀 원본](https://github.com/Capstone-last-dance/AutoAdvisor) · [개인 모델 재현 코드·결과](https://github.com/Capstone-last-dance/AutoAdvisor/tree/fc27fe884546180b24ab856b1736254019d335f8/reports/20261119_PM_gate_pair32) · [시점 누수 수정](https://github.com/Capstone-last-dance/AutoAdvisor/commit/abccc5a) · [공시 RAG 구현 PR](https://github.com/Capstone-last-dance/AutoAdvisor/pull/71)

### 2. [FitFind — 개인화 패션 추천](https://github.com/oh130/fit-find)
**5인 팀 · 추천 모델 담당** | Python · PyTorch · scikit-learn · FastAPI · Redis

- Two-Tower 후보 생성 → Ranking → Re-ranking·MAB 탐색으로 이어지는 다단계 추천을 구현했습니다.
- 사용자 행동을 반영하는 추천 API와 세션 처리까지 연결했습니다.
- 프로젝트 평가에서 **Recall@300 0.6029, NDCG@50 0.1772**를 기록했습니다.

[프로젝트·시연·평가 결과](https://github.com/oh130/fit-find) · [추천 모델 코드](https://github.com/oh130/fit-find/tree/master/rec_models)

### 3. [LG Aimers — 확률 예측과 검증](https://github.com/jjw712/lg-aimers-portfolio)
**팀 프로젝트 · 개인 모델링, 검증 및 앙상블 설계** | Python · Temporal Validation · OOF Ensemble

- 야구 투구 데이터로 다음 투구의 제구 성공 확률을 예측했습니다.
- 시간순 검증과 OOF 기반 블렌딩을 설계하고, 입력 행의 순서·배치 크기에 따라 예측이 바뀌지 않는지 검사했습니다.
- **팀 최종 165위, 상위 약 15%**. 저장소에서 개인 기여와 팀 성과를 구분하고, 공개용 코드와 합성 데이터 테스트를 제공합니다.

[검증·추론 감사 코드와 실험 기록](https://github.com/jjw712/lg-aimers-portfolio)

### 4. [아이디어 조사 서비스](https://github.com/jjw712/CSE4181-SW-MVP)
**2인 프로젝트 · 핵심 서비스 구현** | Python · FastAPI · Gemini · React

- 앱 아이디어를 입력하면 외부 자료를 수집·정규화하고, Gemini로 요약해 조사 리포트를 생성합니다.
- 요약을 원문 `source_id`와 연결하고 확인되지 않은 정보는 분리했습니다.
- API 키가 없거나 LLM 호출이 실패해도 규칙 기반 결과를 반환하도록 구성했습니다.

[데이터 흐름·지원 소스·실행 방법](https://github.com/jjw712/CSE4181-SW-MVP)

### 5. [다음 휘슬까지 — 축구 감독 시뮬레이션](https://github.com/jjw712/Worldcup_dacon)
**개인 프로젝트 · 기획부터 구현·테스트·배포까지** | TypeScript · React · Cloudflare Workers · Vitest

- 제한된 시간과 행동 포인트 안에서 전술을 선택하는 웹 게임을 개발했습니다.
- 시드 기반 경기 시뮬레이션과 UI를 구현하고, 테스트와 CI를 구성했습니다.
- 웹에서 설치 없이 직접 플레이할 수 있습니다.

**[게임 바로 플레이](https://jammulma-worldcup.andyjjw712.workers.dev)** · [소스 코드·게임 화면](https://github.com/jjw712/Worldcup_dacon)

## 시스템 기초

| 프로젝트 | 구현과 검증 |
| --- | --- |
| [Adaptive Reliable Transfer](https://github.com/jjw712/adaptive-reliable-transfer) | C++로 CRC-32, Stop-and-Wait ARQ, BER 추정 기반 프레임 크기 조절을 구현했습니다. 전송 오류와 재전송 조건을 스트레스 테스트로 검증했습니다. |
| [Pintos OS](https://github.com/jjw712/pintos-os-projects) | C로 사용자 프로그램 실행, 시스템 호출 13개, 프로세스 동기화와 스케줄링을 구현했습니다. **Project 2 테스트 80개 통과** 기록을 정리했습니다. |

## 프로젝트에서 사용한 기술

- **Data & AI:** Python, PyTorch, scikit-learn, Pandas, NumPy, Gemini API
- **Service:** FastAPI, Redis, React, TypeScript, Docker, Cloudflare Workers
- **Systems & Development:** C, C++, Git, GitHub Actions
