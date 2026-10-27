> VIPA 조직 저장소의 README 교체용 수정본입니다. 현재 GitHub 연결에는 해당 조직 저장소의 쓰기 권한이 없어 이곳에 보관합니다.

# VIPA 영어회화 학습 앱 · 백엔드

**팀원이 만든 앱 화면에 인증·학습 기록·AI 회화 기능을 제공하는 FastAPI 백엔드를 맡았습니다.**

<table><tr><td><img src="https://raw.githubusercontent.com/EddieEom/EddieEom/main/assets/screenshots/vipa-test.jpg" alt="팀이 구현한 레벨 테스트 화면" width="250"/></td><td><img src="https://raw.githubusercontent.com/EddieEom/EddieEom/main/assets/screenshots/vipa-conversation.jpg" alt="팀이 구현한 회화 화면" width="250"/></td></tr></table>

기존 팀 앱 실행 캡처입니다. 화면 UI는 팀원이 구현했으며, 저는 해당 화면의 DB·API·AI 연동을 담당했습니다.

[담당 범위](#담당-범위) · [개발 과정](#개발-과정) · [코드와 확인 범위](#코드와-확인-범위) · [실행 방법](#실행-방법)

## 담당 범위

| 구분 | 담당 |
| --- | --- |
| 내 역할 | DB 설계와 FastAPI 백엔드, 인증·학습 기록·회화 API, AI API 연동 |
| 추가 참여 | Flutter 초기 구조 구성 |
| 팀원 역할 | UI·프론트엔드 구현 |
| 외부 서비스 경험 | Render 배포, Supabase 연동 |
| 데이터 작업 | Hugging Face의 기존 모델을 이용한 영어 문장 CEFR 분류 |

개인 기여율을 임의의 백분율로 계산하지 않고 실제 담당 기능으로 설명합니다.

## 개발 과정

### 화면과 서버의 데이터 형식을 맞추기

화면에서 필요한 값과 서버가 반환할 형식을 맞추면서 API를 연결했습니다. 현재 레벨과 테스트 기록을 나눠 저장하고, 대화는 세션과 턴으로 나눴습니다. 평가 결과가 다음 시나리오와 회화 요청에 쓰이도록 사용자 데이터를 연결했습니다.

### AI의 답변을 저장 가능한 데이터로 바꾸기

자연어 답변만 받으면 화면 표시와 이력 저장에 그대로 쓰기 어려워, 레벨·피드백·교정 문장을 구조화된 응답으로 요청하고 처리했습니다. AI를 호출하는 것과 앱 기능으로 사용하는 것의 차이를 다룬 부분입니다.

### 구어체 데이터를 학습용 자료로 정리하기

기존 CEFR 분류 모델로 영어 문장을 분류하고, 신뢰도 기준을 적용해 DB 적재용 CSV를 구성했습니다. 모델을 새로 학습한 작업이나 분류 정확도 개선 실험과는 구분합니다.

Render와 Supabase를 연결하며 배포 주소·환경변수·DB 연결 설정도 다뤘습니다. 구체적인 오류의 원인과 해결 결과가 기록되지 않은 사례는 해결 성과로 추가하지 않았습니다.

## 코드와 확인 범위

[분류 스크립트](https://github.com/VipaForENG/Vipa_backend/tree/main/scripts/run_cefr_classification.py) · [DB 적재](https://github.com/VipaForENG/Vipa_backend/tree/main/scripts/migrate_vocab.py) · [API](https://github.com/VipaForENG/Vipa_backend/tree/main/app/routes) · [모델](https://github.com/VipaForENG/Vipa_backend/tree/main/app/models) · [프론트엔드 저장소](https://github.com/VipaForENG/Vipa_frontend)

레벨 테스트 → 결과 → 맞춤 시나리오 → 회화 흐름을 팀 앱과 서버를 연결해 확인했습니다. 모델 평가의 정확도나 배포 서비스의 상시 운영을 입증한 결과는 아닙니다.

## 실행 방법

<details>
<summary><b>설치 및 실행</b></summary>

### 1. 저장소와 가상환경 준비

```bash
git clone https://github.com/VipaForENG/Vipa_backend.git
cd Vipa_backend
python -m venv venv
```

Windows:

```powershell
venv\Scripts\activate
```

macOS / Linux:

```bash
source venv/bin/activate
```

```bash
pip install -r requirements.txt
```

### 2. 환경변수 설정

프로젝트 루트에 `.env`를 작성합니다. 기능별로 DB·AI·메일·소셜 로그인·Storage 설정이 필요합니다.

```env
DATABASE_URL=postgresql://USER:PASSWORD@HOST:PORT/DATABASE
SECRET_KEY=YOUR_SECRET_KEY
ALGORITHM=HS256

OPENAI_API_KEY=YOUR_OPENAI_API_KEY
OPENAI_MODEL=gpt-4o-mini
GOOGLE_CLIENT_ID=YOUR_GOOGLE_CLIENT_ID

MAIL_USERNAME=YOUR_EMAIL
MAIL_PASSWORD=YOUR_APP_PASSWORD
MAIL_FROM=YOUR_EMAIL
MAIL_PORT=587
MAIL_SERVER=smtp.gmail.com

SUPABASE_URL=YOUR_SUPABASE_URL
SUPABASE_SERVICE_KEY=YOUR_SUPABASE_SERVICE_KEY
SUPABASE_BUCKET_NAME=profiles
SUPABASE_AUDIO_BUCKET_NAME=audio
```

키와 비밀번호는 실제 환경의 값으로 설정하고 Git에 올리지 않습니다.

### 3. DB 준비와 서버 실행

PostgreSQL에 사용할 DB를 생성하고 `DATABASE_URL`에 연결 정보를 설정합니다.

```bash
alembic upgrade head
uvicorn app.main:app --reload
```

- Swagger: `http://127.0.0.1:8000/docs`
- ReDoc: `http://127.0.0.1:8000/redoc`
- API 기본 경로: `/api/v1`

Android 에뮬레이터에서 로컬 서버에 연결할 때는 일반적으로 `http://10.0.2.2:8000/api/v1`을 사용합니다.

SQLite 로컬 모드는 `VIPA_USE_SQLITE=true`로 설정할 수 있습니다. PostgreSQL을 사용하는 팀 개발 환경과 구분해 사용합니다.

</details>
