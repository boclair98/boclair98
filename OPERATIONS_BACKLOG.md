# 운영 서비스 개선 작업 원장

이 문서는 실행 기록이다. 후보 서비스나 검증 전 제안을 운영 중인 서비스 또는 확정 장애로 보고하지 않는다.

## 대상 확인

현재 확인은 GitHub 전체 31개 저장소의 관리 이력·README 또는 homepage의 Coders.kr URL·2026-09-10 운영 URL HTTP 응답·Coders 배포 상태를 기준으로 했다.
이번 배치에서는 고정 10개 목록을 제거한 동적 discovery를 실행해 고유 Coders URL 후보 14개를 찾고, 그중 active 13개와 연구용 demo 1개를 판정했다.
active 서비스는 Coders source를 원본 저장소로 확인하고, `coders-kr` 실제 fork parent·기본 브랜치 SHA·브라우저 첫 화면까지 추가 확인했다.
과거 작업 이름과 고정 21개 또는 10개 목록은 편입 근거가 아니다.

## 확인된 운영 서비스

| 저장소 | 운영 URL | 연결 증거 | 확인 커밋 | 확인 시각 | 상태 |
| --- | --- | --- | --- | --- | --- |
| Weather | https://weather.coders.kr | README + HTTP 200 + Coders ready + 브라우저 렌더링 | 56ef0a5f19e96e15f1786e825f5df74e1deeeea7 | 2026-09-10 | active |
| ansimlife | https://ansimlife.coders.kr | homepage/README + HTTP 200 + Coders ready + 브라우저 렌더링 | dc291da937c692653d5285cc8ed4dfa363be1c66 | 2026-09-10 | active |
| hyundai-life-pass | https://hyundai-life-pass.coders.kr | homepage + HTTP 200 + Coders ready + 브라우저 렌더링 | 377593d849eaacd1bef199d02f0839a9dfa4f184 | 2026-09-10 | active |
| yieldscope-pnt | https://yieldscope-pnt.coders.kr | homepage + HTTP 200 + Coders ready + 브라우저 렌더링 | 26a1025df8d91f57bc1e8a38a5e176a3a3f4ae58 | 2026-09-10 | active |
| morrow | https://morrow.coders.kr | homepage + HTTP 200 + Coders ready + 브라우저 렌더링 | 7cdb01a6e3f066b19ff2a5327947bb157615bb9e | 2026-09-10 | active |
| stockpilot | https://stockpilot.coders.kr | homepage + HTTP 200 + Coders ready + 브라우저 렌더링 | 9ac794049104919b9f3d29eac2ca82063289201f | 2026-09-10 | active |
| achim-gyeol | https://morningnews.coders.kr | homepage + HTTP 200 + Coders ready + 브라우저 렌더링 | 5d49911b8eb500e882e3e20eec6f2dc50e67b3df | 2026-09-10 | active |
| mafia-game | https://black-midnight.coders.kr | homepage + HTTP 200 + Coders ready + 브라우저 렌더링 | f78b7fb48d416675382971310ec5e5e02055f420 | 2026-09-10 | active |
| saldobook | https://saldobook.coders.kr | README + HTTP 200 + Coders ready + 브라우저 렌더링 | 12a94e95686eae0d087c3f4c6f396345a3251cd9 | 2026-09-10 | active |
| TradingStockSysyem | https://tradingstocksysyem.coders.kr | README + HTTP 200 + Coders ready + 브라우저 렌더링 | dfc1ed0d52cd5806922a196c449445948c1b0600 | 2026-09-10 | active |
| kkoong | https://segulja-kkung.coders.kr | README + 최근 관리 커밋 + Coders ready + 실제 게임 화면 + 새 fork SHA 일치 | 10ea5f215641d80cc50d148bd6dd78d5d689af9b | 2026-09-10 | active |
| turbo-rush | https://turbo-rush.coders.kr | homepage/README + 최근 관리 커밋 + Coders ready + 실제 게임 화면 + fork SHA 일치 | b0e17914544b7b191946aefd7cfd8a296f4598d2 | 2026-09-10 | active |
| moa-budget | https://moa-budget.coders.kr | README + 로그인 가능한 가계부 화면 + Coders ready + 새 fork SHA 일치 | c6eea9e395dff408ee9f186c2e60cc7aeb9d5baf | 2026-09-10 | active |

## 운영 대상에서 제외한 후보

| 저장소 | 운영 URL | 제외 근거 | 상태 |
| --- | --- | --- | --- |
| haesudamsuhwa_project_streamlit | https://haesudamsuhwa.coders.kr | URL과 화면은 응답하지만 README와 첫 화면이 2021년 기록을 재생하는 읽기 전용 연구용 프로토타입이며 실시간 설비 연동이 아님을 명시 | excluded/demo |

## 누적 개선 항목

| ID | 서비스 | 근거·재현 | 사용자 영향 | 우선순위 | 개선안·완료 조건 | 상태 | PR·배포 증거 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| AL-001 | ansimlife | `/api/programs` 요청이 실패하면 결과 영역에 오류 문구만 남고 즉시 재시도 경로가 없었음. 초기 로딩과 검색 중 상태가 보조기술에 명시되지 않았음. | 일시적인 네트워크·API 오류 뒤 사용자가 검색을 다시 제출해야 하고, 중복 검색을 막는 상태를 이해하기 어려움. | P1 UX/접근성 | 검색 중 `aria-busy`·상태 알림·중복 제출 방지, 실패 시 안전한 `다시 시도` 버튼, 정적 스크립트 캐시 키 갱신. Node 문법 검사와 GitHub Actions Java 21 CI 통과, 운영 브라우저 결과 확인. | done | [boclair98/ansimlife#2](https://github.com/boclair98/ansimlife/pull/2), merged `dc291da937c692653d5285cc8ed4dfa363be1c66`, fork 동일 SHA, Coders `c123eb16-4e81-4f32-b6e8-96514e655394` ready |
| AL-002 | achim-gyeol | `BriefingApp`가 오늘 브리핑 API 실패 때 데모 스토리를 운영 뉴스 목록으로 보여주고, 백엔드 데모 기본값도 `true`였음. | 뉴스 장애가 실제 최신 뉴스처럼 보이면 사용자의 신뢰와 콘텐츠 정확성이 훼손됨. | P0 데이터 신뢰성/UX | 실제 API 실패 시 빈 상태·명확한 오류 안내·`다시 시도`만 보여주고 데모 카드는 예시 미리보기 영역에서만 표시. 운영 `DEMO_DATA_ENABLED` 기본값을 `false`로 고정하고 README에 경계를 기록. 프런트 lint/build/E2E·load smoke, 백엔드 verify, 로컬 오류 상태와 production 정상 브리핑을 확인. | done | [boclair98/achim-gyeol#78](https://github.com/boclair98/achim-gyeol/pull/78), merged `5d49911b8eb500e882e3e20eec6f2dc50e67b3df`, fork 동일 SHA, Coders `81d38e4f-8706-4b27-b3c7-938c94a14952` ready |

## 배치 실행 기록

| 실행 시각 | 범위 | 실제 작업 | 검증 결과 |
| --- | --- | --- | --- |
| 2026-09-10 | active 10개 | 원본 `main` 최신 커밋을 Coders 기존 프로젝트에 재배포하고, `coders-kr` 실제 fork parent·기본 브랜치를 대조 | 10/10 배포 `ready`, 10/10 HTTP 200, 10/10 브라우저 첫 화면 렌더링 |
| 2026-09-10 | ansimlife | 혜택 검색 실패 복구와 로딩 접근성 개선을 구현·검증하고 원본 merge → fork sync → Coders 재배포 | Java 21 CI pass, `dc291da...` 원본·fork SHA 일치, deployment `c123eb16-4e81-4f32-b6e8-96514e655394` ready, 운영 페이지·정상 검색 렌더링 확인 |
| 2026-09-10 | GitHub 전체 동적 discovery | 원본 `main`의 10개 고정 matrix를 제거하고 GitHub 저장소 전체 페이지 조회·Coders URL 후보 추출·서비스별 중복 제거를 구현·실행 | workflow `34439754083` success, 31개 저장소 스캔, 고유 후보 14개, active 13개·demo 제외 1개, 14개 URL HTTP 200 |
| 2026-09-10 | kkoong·moa-budget | 새 active 서비스의 실제 `coders-kr` fork 생성 → canonical SHA 동기화 → Coders 기존 프로젝트 재배포 | `kkoong` SHA `10ea5f2...` 일치·deployment `a3ca507e-8857-4994-924a-ad4ea6ce226a` ready, `moa-budget` SHA `c6eea9e...` 일치·deployment `f108c3a3-53f7-4172-9bc9-3667fd582f6e` ready, 두 URL HTTP 200·브라우저 렌더링 확인 |
| 2026-09-10 18:00 | achim-gyeol | 운영 뉴스 장애 때 데모 데이터가 실제 뉴스처럼 노출되지 않도록 오류 상태·재시도·예시 미리보기 분리를 구현하고 canonical merge → fork sync → Coders 재배포 | GitHub Actions CI `34460704804` success: backend verify, frontend lint/build, Playwright 27 passed, load smoke pass. 로컬 production 정적 화면에서 오류 안내·재시도 확인, production에서 4개 정상 브리핑과 예시 라벨 확인. 정확한 360/390/768/1440 viewport 수치는 이번 실행에서 별도 측정하지 않음 |

이번 실행은 새 서비스 발견과 운영 편입, 동적 모니터링 구조 보완, 새 active 서비스 fork·재배포를 포함한 배치다. 다음 AI 배치부터는 이 원장과 10분 경량 수집 결과를 바탕으로 발견된 active 서비스 전체를 순환 검토하고, 실제 코드 변경이 필요한 서비스만 구현·테스트·merge·fork 동기화·배포한다.

### 2026-09-10 배포 식별자

| 서비스 | Coders 프로젝트 | deployment id | 상태 |
| --- | --- | --- | --- |
| Weather | `weather` | `09c26035-15c9-4acb-b830-a61db739cc18` | ready |
| ansimlife | `ansimlife` | `45f8a7ac-16d0-4b12-bc26-14a69d5cfebd` | ready |
| hyundai-life-pass | `hyundai-life-pass` | `974fffdf-cd89-4eb4-bc97-2cc0cac51185` | ready |
| yieldscope-pnt | `yieldscope-pnt` | `d4de6e02-bb2f-4095-956d-9196ece5ed3e` | ready |
| morrow | `morrow` | `72854902-1b57-4809-b9be-68ac2f2d9807` | ready |
| stockpilot | `stockpilot` | `db3ddce8-1415-4e5d-a14c-1e4398806e18` | ready |
| achim-gyeol | `morningnews` | `81d38e4f-8706-4b27-b3c7-938c94a14952` | ready |
| mafia-game | `black-midnight` | `d7ac0f63-844f-45fe-9e60-ea2153ed4362` | ready |
| saldobook | `saldobook` | `9a432c91-e9c2-4908-9a86-c26b2558d172` | ready |
| TradingStockSysyem | `tradingstocksysyem` | `8cbe217b-dfe8-4005-b41c-fe16d2ecb2e4` | ready |
| kkoong | `segulja-kkung` | `a3ca507e-8857-4994-924a-ad4ea6ce226a` | ready |
| moa-budget | `moa-budget` | `f108c3a3-53f7-4172-9bc9-3667fd582f6e` | ready |

## active 전체 다음 개선 후보

이 표는 장애 확정 목록이 아니라 이번 순환에서 다시 검증할 제품 가설과 완료 기준이다. 실제 구현은 사용자 영향·안전성·외부 승인 여부를 확인한 뒤 선택한다.

| 서비스 | 다음 검토·기획 후보 | 완료 기준 또는 blocker |
| --- | --- | --- |
| Weather | 모바일 메일 카드, 발송 이력·재시도·수신거부, 예보 최신성 표시 | SMTP/도메인 인증과 실제 발송 없이 메일 성공을 주장하지 않음 |
| ansimlife | 공공데이터 최신 시각·출처, 검색·필터·저장 흐름, 인증 회복 | 정부기관 직접 신청은 승인·본인인증·전자서명 없이는 추가하지 않음 |
| hyundai-life-pass | 차량·충전 공급자 오류 격리, 시뮬레이션 경계, 모바일 연결 여정 | Hyundai OAuth·충전사업자 제휴·운영 키 필요 |
| yieldscope-pnt | 합성 데이터 배지 강화, CSV adapter, 역할·승인·감사 흐름 | MES/TMS/Tester/Databook·SSO·보존정책 필요 |
| morrow | 본인·성인 인증, 신고 처리 SLA, 사진·채팅 안전, WebSocket fan-out | 인증 공급자와 실제 운영자 대응 체계 필요 |
| stockpilot | 시세 지연·워커 장애·원장 대사, 모의주문 UX와 위험 고지 | 실주문은 증권사 계약·규제·승인 전 금지 |
| achim-gyeol | 뉴스 장애 시 신뢰 상태, 출처·정정·알림 UX, 브리핑 재시도 | 이번 배치 AL-002 완료; 모바일 실제 viewport 검증은 다음 순환 |
| mafia-game | Redis room coordinator, 재접속·장애 복구, 음성·신고·모더레이션 | TURN/SFU와 다중 인스턴스 부하 검증 필요 |
| saldobook | 탈퇴·개인정보 화면, 거래 중복·백업 복구, 계좌 연결 경계 | 금융결제원 운영 승인·계약·보안 검토 필요 |
| TradingStockSysyem | durable strategy runner, market-data event, p99·HA·재해복구 | 거래소 운영 인가·시장감시·청산결제·이중센터 필요 |
| kkoong | 방 재접속·중복 참가·비정상 입력·신고, 모바일 게임 루프 | 다중 방 부하와 악용 방어의 실제 측정 필요 |
| turbo-rush | 경기 재시작·입력 안정성·모바일 조작·성능/결과 관측 | 랭킹·멀티플레이 기능이 확대될 때 서버 정합성 재검증 |
| moa-budget | 운영 DB·OAuth·거래 중복·백업·삭제/내보내기·모바일 입력 | 금융 데이터 보호와 실제 계좌 연동은 별도 승인 필요 |

## 기록 규칙

- 기존 항목과 증거를 읽고 같은 문제는 갱신한다. 동시 수정 시 다른 실행의 기록을 보존한다.
- 추정 개선안과 실제 재현된 장애를 구분한다.
- 각 배치에서 검토·구현·검증·merge·fork 동기화·배포·운영 확인 단계를 각각 기록한다.
- 운영 서비스의 일시 장애는 대상에서 제외하지 않는다.
- 인증정보와 사용자 개인정보를 기록하지 않는다.
