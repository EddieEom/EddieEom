# 엄유준 · C# MES 개발을 준비하는 신입

제조 현장 경험을 바탕으로 **설비 제어·생산 데이터 처리·업무 화면**을 구현하고 있습니다.  
한국폴리텍대학 부산캠퍼스 소프트웨어융합과 · 전문학사 졸업예정

**주요 기술** C# · WinForms · ASP.NET Core · MSSQL  
**백엔드 개발 경험** Python · FastAPI · PostgreSQL

[대표 프로젝트](https://github.com/EddieEom/MES-System) · [이메일](mailto:pom159753@gmail.com)

## 대표 프로젝트 · 디지털 트윈 기반 PLC 설비 제어 프로그램

**HMI에서 제어 명령을 전달하고, 가상 설비의 생산 데이터를 저장·조회하는 프로그램입니다.**

작업지시·LOT·제품 이력 관리 등 MES 관련 기능을 함께 구현했습니다.

<img src="https://raw.githubusercontent.com/EddieEom/EddieEom/main/assets/screenshots/mes-hmi.jpg" alt="작업지시·LOT·생산수량·설비 상태·알람을 표시하는 WinForms HMI" width="100%"/>

| 구분 | 내용 |
| :--- | :--- |
| 개발 형태 | 개인 프로젝트 |
| 제공받은 부분 | MELSOFT Gemini 가상 생산설비 모델 (주)퍼씨엠 제공 |
| 직접 개발한 범위 | C# Gateway · ASP.NET Core 서버 · MSSQL DB · WinForms HMI |
| 확인 환경 | GX Simulator2 · MELSOFT Gemini |

- **설비 제어:** HMI의 START·STOP·RESET 요청을 서버와 Gateway를 거쳐 PLC 시뮬레이터에 전달했습니다.
- **데이터 처리:** MQTT로 제품 이동·검사 결과를 수신해 DB에 저장하고, 관련 품질·LOT 처리를 트랜잭션으로 구성했습니다.
- **화면과 이력:** 생산수량·설비 상태·알람을 표시하고, 동일 제품의 이동 이력과 검사 결과를 DB에서 조회했습니다.

시뮬레이터 환경에서 제어 명령에 따른 동작, 제품 이력 저장, 알람 발생·표시·해제를 확인했습니다.

**[구조·코드·동작 확인 내용 보기 →](https://github.com/EddieEom/MES-System)**

<details>
<summary>연동한 가상 설비 화면</summary>

<img src="https://raw.githubusercontent.com/EddieEom/EddieEom/main/assets/screenshots/mes-digital-twin.jpg" alt="제공받아 연동에 활용한 MELSOFT Gemini 가상 생산설비 모델" width="100%"/>

</details>

## 함께 진행한 프로젝트

| 프로젝트 | 담당 범위와 구현 경험 |
| :--- | :--- |
| **[C# 비디오 대여 관리](https://github.com/EddieEom/VideoRentalSystem)**<br>수업 프로젝트 확장 | WinForms · ADO.NET · MSSQL 기반 고객·비디오·대여 관리. 조회·등록·수정·삭제, Excel 출력 구현 |
| **[VIPA 영어학습 앱](https://github.com/VipaForENG/Vipa_backend)**<br>팀 프로젝트 | FastAPI · PostgreSQL 기반 DB 설계·백엔드 담당. JWT 인증, 레벨 테스트, 회화·학습 이력 API와 외부 AI API 연동 |

VIPA에서는 프론트엔드 초기 구조 구성에도 참여했으며, 화면 UI와 프론트엔드 구현은 팀원이 담당했습니다.  
[VIPA 프론트엔드 저장소](https://github.com/VipaForENG/Vipa_frontend)

<details>
<summary>기타 프로젝트·학습 기록</summary>

| 프로젝트 | 내용 |
| :--- | :--- |
| [Sadie](https://github.com/EddieEom/Sadie-backend) | AI Hub 데이터 전처리 · LLaMA 학습 실험 · 대화 앱 연동 |
| [MindBuilder](https://github.com/EddieEom/MindBuilder) | FastAPI · PostgreSQL · Flutter 기반 개인 프로토타입 |
| [MDI 메모장](https://github.com/EddieEom/csharp-winforms-mdi-notepad) | 다중 문서 · 파일 입출력 · 이벤트 처리 |
| [부산 공영주차장](https://github.com/EddieEom/Busan_Parking_Website) | 생성형 AI 활용 웹 제작 수업 · Cloudflare 배포 · 기능 확인 |

</details>
