# 엄유준 | C# MES 개발을 준비하고 있습니다

**C#으로 데이터를 조회·입력하는 화면을 만들고, 서버·DB·PLC 시뮬레이터를 연결해 봤습니다.**

주로 공부하는 기술은 **C# · WinForms · ASP.NET Core · MSSQL**입니다. 제조 현장에서 설비를 운영하고 MES로 공정을 이관했던 경험을 바탕으로, 생산정보를 다루는 프로그램을 만들고 있습니다.

| 기술 | 프로젝트에서 구현한 내용 |
| --- | --- |
| C# · WinForms | 조회·등록·수정·삭제 화면, 비동기 DB·API 호출과 화면 갱신 |
| MSSQL · ADO.NET | 테이블 관계, JOIN·집계, 저장 프로시저 호출, 트랜잭션 처리 |
| ASP.NET Core | 화면과 DB를 연결하는 저장·조회 API |
| MQTT · SignalR · MX Component | 설비 데이터 수신, 제어 명령 전달, PLC 시뮬레이터 디바이스 읽기·쓰기 |
| Python · FastAPI / Java · Spring Boot | 팀 백엔드·AI 연동 / 웹·REST API CRUD 구현 경험 |

한국폴리텍대학 부산캠퍼스 소프트웨어융합과 · [이메일](mailto:pom159753@gmail.com)

## 1. PLC 설비 제어 · 생산정보 수집 프로그램

**화면·서버·DB에서 배운 내용을 설비 통신까지 연결한 대표 프로젝트입니다.**

[![설비 제어와 생산 현황을 표시하는 WinForms 화면](https://raw.githubusercontent.com/EddieEom/EddieEom/main/assets/screenshots/mes-hmi.jpg)](https://github.com/EddieEom/MES-System)

HMI에서 시작·정지·초기화 명령을 보내고, 가상 설비의 제품 이동·검사 결과를 받아 DB에 저장했습니다. 생산 수량·설비 상태·알람을 화면에서 조회하도록 구성했습니다.

㈜퍼씨엠이 제공한 가상 설비 모델을 사용했습니다. 필요한 기능과 처리 순서를 정리하고 AI의 코드 생성 도움을 받아 Gateway·서버·DB·HMI를 연결했으며, 화면·로그·DB로 동작을 확인했습니다.

**보여드릴 경험:** C# 설비 연동, API·DB 연결, 생산 이력 처리. 메시지 전송 지연을 확인하고 발행 프로세스를 재사용하도록 수정한 과정도 정리했습니다.

[구현 내용 · 통신 구조 · 문제 해결 기록](https://github.com/EddieEom/MES-System)

## 2. 비디오 대여 관리 · C# 화면과 DB CRUD

[![비디오·고객·대여 정보를 관리하는 화면](https://raw.githubusercontent.com/EddieEom/EddieEom/main/assets/screenshots/video-rental.jpg)](https://github.com/EddieEom/VideoRentalSystem)

WinForms에서 입력한 값을 SQL Server에 저장하고 다시 조회하는 기본기를 공부했습니다. 고객·비디오·대여 정보를 관리하며 **CRUD, 저장 프로시저, 비동기 DB 처리, DB 정규화**를 적용했습니다.

**보여드릴 경험:** 데이터 관리 화면 구현, SQL 매개변수 전달, 저장 후 목록 갱신. MES의 조회·입력 화면을 공부하는 바탕이 된 프로젝트입니다.

[화면 · DB 처리 코드 · 학습 과정](https://github.com/EddieEom/VideoRentalSystem)

## 3. MDI 메모장 · WinForms 기초

[![여러 문서를 연 WinForms 메모장](https://raw.githubusercontent.com/EddieEom/EddieEom/main/assets/screenshots/mdi-notepad.jpg)](https://github.com/EddieEom/csharp-winforms-mdi-notepad)

부모·자식 폼, 메뉴 이벤트, 파일 열기·저장을 공부한 작은 실습입니다. 현재 선택한 문서를 찾아 편집 기능을 적용하고, UI 스레드로 화면 갱신을 전달하는 흐름을 익혔습니다.

[폼 · 이벤트 · 파일 처리 코드](https://github.com/EddieEom/csharp-winforms-mdi-notepad)

## 4. VIPA 영어학습 앱 · 팀 백엔드와 AI 연동

<a href="https://github.com/VipaForENG/Vipa_backend"><img src="https://raw.githubusercontent.com/EddieEom/EddieEom/main/assets/screenshots/vipa-test.jpg" alt="팀 앱의 레벨 테스트 화면" width="250"/> <img src="https://raw.githubusercontent.com/EddieEom/EddieEom/main/assets/screenshots/vipa-conversation.jpg" alt="팀 앱의 회화 화면" width="250"/></a>

팀 프로젝트에서 DB 설계와 FastAPI 백엔드를 담당했습니다. UI·프론트엔드는 팀원이 구현했고, API 요청·응답 형식을 맞추며 앱을 연결했습니다.

AI 응답을 문제·회화·학습 기록으로 처리했습니다. AI Hub 구어체 데이터는 Hugging Face의 기존 CEFR 모델로 분류해 학습 자료로 정리했습니다. Render 배포와 Supabase 연동도 경험했습니다.

**보여드릴 경험:** 팀원과 API 연결, 앱·서버·DB의 흐름 파악, AI 응답과 외부 데이터 처리.

[백엔드 저장소](https://github.com/VipaForENG/Vipa_backend) · [담당 기능과 개발 과정](docs/VIPA_README.md)

## 5. 학생·과정 관리 · Java Spring Boot CRUD

[![학생 검색과 목록을 표시하는 실행 화면](https://raw.githubusercontent.com/EddieEom/Java_Student-Management-System/main/docs/screenshots/student-list.png)](https://github.com/EddieEom/Java_Student-Management-System)

Java·Spring Boot·Maven을 공부하며 학생·과정 정보를 등록·조회·수정·삭제하는 웹과 REST API를 구현했습니다. JPA로 SQL Server에 연결하고 검색·정렬·페이징과 입력 검증을 적용했습니다.

**보여드릴 경험:** C# 외의 환경에서도 Controller → Service → Repository 흐름으로 기본 데이터 처리 구현.

[실행 화면 · CRUD 코드 · 개발 과정](https://github.com/EddieEom/Java_Student-Management-System)

## 6. 부산 공영주차장 · AI 활용과 MCP 연결

[![부산 공영주차장 배포 화면](https://raw.githubusercontent.com/EddieEom/EddieEom/main/assets/screenshots/parking-search.jpg)](https://github.com/EddieEom/Busan_Parking_Website)

AI 코드 생성을 적극 활용해 공공데이터 API·MCP 서버·Cloudflare 배포를 연결했습니다. 요구사항을 구체화하고 결과를 확인하면서 MCP 연결 오류, 지도 검색 주소, PWA 업데이트 흐름을 수정했습니다.

**보여드릴 경험:** AI를 이용한 구현·수정, MCP 도구 연결과 배포 설정. 캡처는 2026-10-26 배포 사이트 화면입니다.

[배포 사이트](https://busan-parking-website.pages.dev/) · [AI 활용 과정 · MCP 구조](https://github.com/EddieEom/Busan_Parking_Website)

## 개인 실험 · MindBuilder

<a href="https://github.com/EddieEom/MindBuilder"><img src="https://raw.githubusercontent.com/EddieEom/MindBuilder/main/frontend/artifacts/previews/hos.png" alt="MindBuilder의 Human OS 기존 화면 미리보기" width="300"/></a>

'AI로 생각과 다음 행동을 정리할 수 있을까?'라는 아이디어를 앱으로 옮긴 실험입니다. 질문·기록·규칙 기반 분석·LLM 추천을 나눠 구성했습니다. 위 이미지는 저장소의 화면 미리보기입니다.

[아이디어 · 구현 구조 · 진행 상태](https://github.com/EddieEom/MindBuilder)
