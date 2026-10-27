# 엄유준

C# MES 개발자로 취업을 준비하고 있습니다. 한국폴리텍대학 부산캠퍼스 소프트웨어융합과에서 개발을 공부하고 있습니다.

LG이노텍과 CJ제일제당에서 생산설비를 운영했습니다. 현장에서 사용했던 작업 화면과 생산정보 처리를 직접 만들어 보고 있습니다.

[PLC 설비 제어](#plc-설비-제어-프로그램) · [비디오 대여](#비디오-대여-관리) · [메모장](#mdi-메모장) · [VIPA](#vipa-영어회화-학습-앱) · [주차장](#부산-공영주차장) · [MindBuilder](#mindbuilder) · [Sadie](#sadie)

## PLC 설비 제어 프로그램

**가장 집중해서 만든 프로젝트입니다.** 화면에서 명령을 보내고 설비 데이터를 다시 받아보는 구조를 연결했습니다.

[![WinForms 설비 제어·생산 현황 화면](https://raw.githubusercontent.com/EddieEom/EddieEom/main/assets/screenshots/mes-hmi.jpg)](https://github.com/EddieEom/MES-System)

| 내가 맡은 일 | 제공·지원받은 부분 |
| --- | --- |
| 요구사항·처리 순서 정리, Gateway·서버·DB·HMI 연동, 코드 검토·동작 확인 | **㈜퍼씨엠의 가상 설비 모델**, AI의 설계·코드 생성 지원 |

MQTT로 생산 데이터를 받고 SignalR·PLC 통신으로 명령을 보냈습니다. 메시지마다 외부 프로그램을 실행해 생긴 지연을 확인하고 프로세스를 재사용하도록 바꿨습니다. PLC 시뮬레이터와 가상 설비에서 확인한 프로젝트입니다.

C# · WinForms · ASP.NET Core · MSSQL · MQTT  
[담당 범위·시행착오·코드 보기](https://github.com/EddieEom/MES-System)

## 비디오 대여 관리

[![고객·비디오·대여 관리 기존 실행 화면](https://raw.githubusercontent.com/EddieEom/EddieEom/main/assets/screenshots/video-rental.jpg)](https://github.com/EddieEom/VideoRentalSystem)

수업에서 시작한 WinForms 프로그램에 비동기 DB 처리를 추가했습니다. 저장 프로시저와 DB 정규화를 공부하며 화면의 입력·DB 저장·목록 갱신을 연결했습니다.

C# · WinForms · ADO.NET · MSSQL  
[구현 범위·개발 과정 보기](https://github.com/EddieEom/VideoRentalSystem)

## MDI 메모장

[![여러 문서를 연 메모장 기존 실행 화면](https://raw.githubusercontent.com/EddieEom/EddieEom/main/assets/screenshots/mdi-notepad.jpg)](https://github.com/EddieEom/csharp-winforms-mdi-notepad)

WinForms 기초를 공부한 수업 프로젝트입니다. 부모·자식 폼과 파일 열기·저장을 구현하며, 메뉴가 현재 선택한 문서에 적용되는 흐름을 익혔습니다.

[폼·이벤트·파일 처리 보기](https://github.com/EddieEom/csharp-winforms-mdi-notepad)

## VIPA 영어회화 학습 앱

<a href="https://github.com/VipaForENG/Vipa_backend"><img src="https://raw.githubusercontent.com/EddieEom/EddieEom/main/assets/screenshots/vipa-test.jpg" alt="팀 앱의 레벨 테스트 기존 실행 화면" width="260"/> <img src="https://raw.githubusercontent.com/EddieEom/EddieEom/main/assets/screenshots/vipa-conversation.jpg" alt="팀 앱의 AI 회화 기존 실행 화면" width="260"/></a>

**팀 프로젝트에서 DB 설계·FastAPI 백엔드를 담당했습니다.** 팀원이 UI·프론트엔드를 구현했고 저는 Flutter 초기 구조에도 참여했습니다. API 요청·응답을 맞추고 AI·Render·Supabase를 연결했습니다.

Hugging Face 기존 모델로 구어체 데이터의 영어 문장을 CEFR 수준별로 분류했습니다.

[백엔드 저장소](https://github.com/VipaForENG/Vipa_backend) · [담당 범위·개발 과정 수정본](docs/VIPA_README.md)

## 부산 공영주차장

[![배포 사이트에서 직접 캡처한 새 주차장 디자인](https://raw.githubusercontent.com/EddieEom/EddieEom/main/assets/screenshots/parking-search.jpg)](https://github.com/EddieEom/Busan_Parking_Website)

AI 코드 생성을 적극 활용한 수업 프로젝트입니다. 요구사항을 전달하고 결과를 확인하며 공공데이터 API·MCP 서버·Cloudflare 배포를 연결했습니다. 지도 검색이 부정확했던 부분을 주소 우선으로 바꾸는 등 실제 사용 결과에 맞춰 수정했습니다.

위 이미지는 2026-10-26 배포 사이트에서 직접 캡처했습니다.  
[배포 사이트](https://busan-parking-website.pages.dev/) · [개발 과정·코드 보기](https://github.com/EddieEom/Busan_Parking_Website)

## MindBuilder

<a href="https://github.com/EddieEom/MindBuilder"><img src="https://raw.githubusercontent.com/EddieEom/MindBuilder/main/frontend/artifacts/previews/hos.png" alt="저장소에 보관된 Human OS 화면 미리보기" width="320"/></a>

AI를 어떻게 활용하면 좋을지 고민하다 '나의 성장을 위한 인간 운영체제'를 앱으로 실험했습니다. 질문·기록·분석·추천을 나눠 구성했습니다.

**이미지는 기존 화면 미리보기입니다.** 실제 서비스의 분석 결과나 이번에 앱을 실행한 캡처와는 구분합니다.

[아이디어·구현 범위·남은 과제 보기](https://github.com/EddieEom/MindBuilder)

## Sadie

LLM 파인튜닝이 궁금해 A100 GPU 2개가 장착된 학교 서버에서 데이터 준비와 학습을 시도했습니다. 뚜렷한 응답 개선은 확인하지 못했습니다. 현재 저장소에는 외부 LLM API로 대화하는 앱 백엔드가 있습니다.

**앱 실행 캡처는 아직 준비되지 않았습니다.** 코드와 처리 구조는 아래 저장소에서 볼 수 있습니다.

[학습 시행착오·백엔드](https://github.com/EddieEom/Sadie-backend) · [Flutter 앱](https://github.com/EddieEom/Sadie_frontend)

---

주로 공부하는 기술: **C# · WinForms · ASP.NET Core · MSSQL**  
팀 프로젝트와 실험: Python · FastAPI · PostgreSQL  
[이메일](mailto:pom159753@gmail.com)
