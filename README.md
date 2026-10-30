# 엄유준

대학 진학전, 제조 현장에서 자동화 설비를 운영한 경험이 있습니다. 대학에서는 **C#으로 조회·입력 화면을 만들고, 서버·DB·PLC 시뮬레이터를 연결하는 프로젝트**를 진행했습니다.

한국폴리텍대학 부산캠퍼스 소프트웨어융합과 · [이메일](mailto:pom159753@gmail.com)

| 기술 | 프로젝트에서 사용한 범위 |
| --- | --- |
| C# · WinForms | 조회·등록·수정·삭제 화면, 비동기 DB·API 호출, 화면 갱신 |
| MSSQL · ADO.NET | 테이블 관계, JOIN·집계, 저장 프로시저 작성·호출, 트랜잭션 처리 |
| ASP.NET Core | 화면과 DB를 연결하는 저장·조회 API |
| MQTT · SignalR · MX Component | 설비 데이터 수신, 제어 명령 전달, PLC 시뮬레이터 디바이스 읽기·쓰기 |

## PLC 설비 제어 · 생산정보 수집 프로그램

**HMI의 조작이 설비 동작으로 이어지고, 제품의 이동·검사 결과가 DB와 화면에 반영되는 흐름을 연결했습니다.**

[![작업지시·생산 수량·설비 상태·알람을 표시하는 WinForms HMI](https://raw.githubusercontent.com/EddieEom/EddieEom/main/assets/screenshots/mes-hmi.jpg)](https://github.com/EddieEom/MES-System)

- **제어:** HMI → 서버 → Gateway → PLC 시뮬레이터로 시작·정지·초기화 명령 전달
- **수집·저장:** MQTT로 제품 이동·검사 결과 수신, 제품·LOT 관련 변경을 트랜잭션으로 처리
- **동작 확인:** 동일 제품의 이동 → FAIL 판정 → 불량 적재 이력 조회, 알람 발생·표시·해제 확인

개인 프로젝트로, ㈜퍼씨엠이 제공한 가상 설비 모델을 사용했습니다. 요구사항과 처리 순서를 정리하고 AI의 설계·코드 생성 도움을 받아 개발했습니다. 실행 중에는 코드·로그·화면을 제공하고 수정안을 적용해 결과를 확인했습니다.

가상 설비가 멈췄을 때는 **STOP에 따른 공급 중단과 통신 지연에 따른 정지를 구분해 전달**했습니다. AI가 제안한 발행 프로세스 재사용 방식을 적용한 뒤 전송 요청 로그를 다시 확인했고, 프로세스 종료 처리도 보완을 요청했습니다. 실물 설비 연동과 장시간 운전은 검증하지 않았습니다.

[통신 구조 · 관련 코드 · 문제 해결 기록](https://github.com/EddieEom/MES-System)

## 비디오 대여 관리 · WinForms와 SQL Server CRUD

[![고객·비디오·대여 정보를 관리하는 WinForms 화면](https://raw.githubusercontent.com/EddieEom/EddieEom/main/assets/screenshots/video-rental.jpg)](https://github.com/EddieEom/VideoRentalSystem)

**입력 → 저장 프로시저 호출 → DB 저장 → 목록 갱신**을 공부한 프로젝트입니다. 고객·비디오·대여 관리 화면에 CRUD, SQL 매개변수 전달, 비동기 DB 처리와 DB 정규화를 적용했습니다.

[실행 화면 · DB 처리 코드 · 학습 과정](https://github.com/EddieEom/VideoRentalSystem)

## VIPA 영어학습 앱 · 팀 백엔드와 API 연동

<a href="https://github.com/VipaForENG/Vipa_backend"><img src="https://raw.githubusercontent.com/EddieEom/EddieEom/main/assets/screenshots/vipa-test.jpg" alt="영어학습 앱의 레벨 테스트 화면" width="230"/> <img src="https://raw.githubusercontent.com/EddieEom/EddieEom/main/assets/screenshots/vipa-conversation.jpg" alt="영어학습 앱의 회화 화면" width="230"/></a>

팀 프로젝트에서 **DB 설계와 FastAPI 백엔드**를 담당했습니다. UI·프론트엔드는 팀원이 구현했고, API 요청·응답 형식을 맞추며 앱과 서버를 연결했습니다.

AI 응답을 문제·회화·학습 기록으로 처리하고, AI Hub 구어체 데이터를 Hugging Face의 기존 CEFR 모델로 분류했습니다. Render 배포와 Supabase 연동도 경험했습니다.

[백엔드 저장소](https://github.com/VipaForENG/Vipa_backend) · [담당 기능과 개발 과정](docs/VIPA_README.md)

## 그 외 학습·실험

<details>
<summary>Java CRUD · WinForms 기초 · 공공데이터·MCP · AI 앱 실험 펼쳐 보기</summary>

### 학생·과정 관리 · Java Spring Boot CRUD

[![학생 검색과 목록 화면](https://raw.githubusercontent.com/EddieEom/Java_Student-Management-System/main/docs/screenshots/student-list.png)](https://github.com/EddieEom/Java_Student-Management-System)

Java·Spring Boot·Maven을 공부하며 웹·REST API CRUD를 구현했습니다. JPA로 SQL Server에 연결하고 검색·정렬·페이징·입력 검증을 적용했습니다.

[실행 화면 · 코드](https://github.com/EddieEom/Java_Student-Management-System)

### MDI 메모장 · WinForms 기초

[![여러 문서를 연 WinForms 메모장](https://raw.githubusercontent.com/EddieEom/EddieEom/main/assets/screenshots/mdi-notepad.jpg)](https://github.com/EddieEom/csharp-winforms-mdi-notepad)

부모·자식 폼, 메뉴 이벤트, 파일 열기·저장을 공부한 작은 실습입니다.

[폼 · 이벤트 · 파일 처리 코드](https://github.com/EddieEom/csharp-winforms-mdi-notepad)

### 부산 공영주차장 · 공공데이터와 MCP 연결

[![부산 공영주차장 실행 화면](https://raw.githubusercontent.com/EddieEom/EddieEom/main/assets/screenshots/parking-search.jpg)](https://github.com/EddieEom/Busan_Parking_Website)

AI 코드 생성을 적극 활용해 공공데이터 API·MCP 서버·Cloudflare 배포를 연결했습니다. 실행 결과를 확인하며 MCP 연결 오류, 지도 검색 주소, PWA 업데이트 흐름의 수정을 요청하고 반영했습니다.

[배포 사이트](https://busan-parking-website.pages.dev/) · [AI 활용 과정 · MCP 구조](https://github.com/EddieEom/Busan_Parking_Website)

### MindBuilder · AI로 생각과 다음 행동을 정리하는 앱 실험

<a href="https://github.com/EddieEom/MindBuilder"><img src="https://raw.githubusercontent.com/EddieEom/MindBuilder/main/frontend/artifacts/previews/hos.png" alt="MindBuilder 화면 미리보기" width="300"/></a>

질문·기록·규칙 기반 분석·LLM 추천을 나누어 구성한 개인 실험입니다. 위 이미지는 저장소의 화면 미리보기입니다.

[아이디어 · 구현 구조 · 진행 상태](https://github.com/EddieEom/MindBuilder)

</details>

[학습 기록: LLM의 원리와 AI에게 맡길 범위에 대한 생각](https://github.com/EddieEom/AI-Study-Notes)
