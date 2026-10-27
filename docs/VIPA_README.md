# VIPA 영어학습 앱 · FastAPI 팀 백엔드

**팀원이 구현한 Flutter 앱에 인증·학습 기록·AI 회화 기능을 제공하는 백엔드를 개발했습니다.**

Python · FastAPI · PostgreSQL · SQLAlchemy · AI API · Hugging Face · Render · Supabase

<table><tr><td><img src="https://raw.githubusercontent.com/EddieEom/EddieEom/main/assets/screenshots/vipa-test.jpg" alt="팀 앱의 레벨 테스트 화면" width="250"/></td><td><img src="https://raw.githubusercontent.com/EddieEom/EddieEom/main/assets/screenshots/vipa-conversation.jpg" alt="팀 앱의 회화 화면" width="250"/></td></tr></table>

## 팀에서 구현한 부분

| 구분 | 내용 |
| --- | --- |
| 담당 기능 | DB 설계, FastAPI 백엔드, 인증·학습 기록·회화 API, AI 연동 |
| 추가 참여 | Flutter 초기 구조 구성 |
| 팀원 구현 | UI·프론트엔드 |
| 외부 서비스 | Render 배포, Supabase 연동 |
| 데이터 준비 | AI Hub 구어체 데이터의 영어 문장을 Hugging Face CEFR 모델로 분류 |

[Flutter 저장소](https://github.com/VipaForENG/Vipa_frontend)

## 개발하면서 고민한 점

### 앱에서 필요한 데이터와 API 응답을 맞추기

팀원이 만든 화면과 서버를 연결하면서 요청·응답 형식을 맞췄습니다. 현재 레벨과 과거 테스트 결과를 구분해 저장하고, 대화는 세션과 턴으로 나눴습니다. 화면 하나에 필요한 데이터가 어떤 테이블과 API를 거치는지 확인하며 전체 흐름을 이해하려고 했습니다.

### AI 답변을 앱 기능으로 사용하기

AI를 호출해 답변을 받는 것만으로는 학습 이력에 바로 저장하기 어려웠습니다. 레벨·피드백·교정 문장을 구조화된 응답으로 요청하고, 처리한 결과를 DB에 저장하도록 구성했습니다.

저장한 사용자 레벨은 다음 시나리오와 회화 요청에 전달했습니다. 테스트·회화·이력 기능이 같은 데이터를 어떻게 사용하는지 연결한 부분입니다.

### 구어체 문장을 수준별 학습 자료로 정리하기

AI Hub 데이터를 불러와 Hugging Face의 `yanou16/cefr-english-classifier`로 영어 문장을 A1~C2 수준으로 분류했습니다. 신뢰도 기준으로 정리한 뒤 DB 적재용 CSV를 만들었습니다.

[분류 코드](https://github.com/VipaForENG/Vipa_backend/blob/main/scripts/run_cefr_classification.py) · [DB 적재 코드](https://github.com/VipaForENG/Vipa_backend/blob/main/scripts/migrate_vocab.py)

기존 모델을 이용한 분류이며 직접 모델을 학습한 작업과는 구분합니다.

## 연결해서 확인한 흐름

레벨 테스트 → 평가 결과 저장 → 맞춤 시나리오 생성 → 회화를 앱과 서버에서 확인했습니다. 팀 프로젝트를 통해 API 구현뿐 아니라 화면·DB·AI 응답이 연결되는 과정과 배포 설정을 경험했습니다.

[API 라우트](https://github.com/VipaForENG/Vipa_backend/tree/main/app/routes) · [DB 모델](https://github.com/VipaForENG/Vipa_backend/tree/main/app/models) · [AI 처리](https://github.com/VipaForENG/Vipa_backend/blob/main/app/services/ai_service.py)

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
