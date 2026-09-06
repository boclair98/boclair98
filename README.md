<div align="center">

<code>BOCLAIR98 / BACKEND & SERVICE ENGINEERING</code>

<h1>코드에서 서비스까지.</h1>

<p><strong>직접 만드는 서비스, 코드로 풀어낸 문제, 함께 나누는 개발 기록.</strong></p>

<p>
Java · Kotlin · Spring Boot &nbsp;/&nbsp; Python · FastAPI<br />
PostgreSQL · Redis · WebSocket · Docker · GitHub Actions
</p>

<p>
  <code>Data Integrity</code> · <code>Concurrency</code> · <code>Realtime</code><br />
  <code>API Resilience</code> · <code>Observability</code> · <code>Recovery</code>
</p>

<p>
  <a href="#flagship-products"><b>대표 서비스</b></a> &nbsp; / &nbsp;
  <a href="#service-directory"><b>운영 서비스</b></a> &nbsp; / &nbsp;
  <a href="#engineering"><b>코드 탐색</b></a> &nbsp; / &nbsp;
  <a href="#operations"><b>운영 문서</b></a> &nbsp; / &nbsp;
  <a href="#tech-stack"><b>기술 스택</b></a> &nbsp; / &nbsp;
  <a href="https://boclair98.tistory.com/"><b>기술 블로그 ↗</b></a>
</p>

</div>

<table align="center">
<tr>
<td width="440" valign="top">
<sub>01 / FINTECH · PAPER TRADING</sub>
<h3>StockPilot</h3>
<p><strong>실제 시세로 배우는 모의투자</strong></p>
<p>주문 멱등성 · 가상 원장 대사<br />실시간 시세 · 분산 캐시</p>
<p><code>FastAPI</code> <code>PostgreSQL</code> <code>Redis</code></p>
<p><a href="https://stockpilot.coders.kr"><strong>서비스 열기 ↗</strong></a> &nbsp;·&nbsp; <a href="https://github.com/boclair98/stockpilot">코드</a></p>
</td>
<td width="440" valign="top">
<sub>02 / NEWS · DAILY BRIEFING</sub>
<h3>아침결</h3>
<p><strong>매일 07:30, 오늘의 뉴스 브리핑</strong></p>
<p>뉴스 수집·품질 검증·발행<br />PWA 알림 · 정정·백업·복구</p>
<p><code>Kotlin</code> <code>Spring Boot</code> <code>PostgreSQL</code></p>
<p><a href="https://morningnews.coders.kr"><strong>브리핑 읽기 ↗</strong></a> &nbsp;·&nbsp; <a href="https://github.com/boclair98/achim-gyeol">코드</a></p>
</td>
</tr>
</table>

<p align="center"><sub>API와 데이터 모델부터 검증·배포·장애 대응까지, 제품을 구성하는 기술을 직접 연결합니다.</sub></p>

---

<h2 id="service-directory">01 / 직접 운영하는 서비스 · Services</h2>

직접 만들고 배포하며 개선하는 서비스들입니다. **어떤 서비스인지 먼저 살펴보고, 링크를 눌러 이용해 보세요.** 공개 파일럿·데모는 별도로 표시했습니다.

| 서비스 | 어떤 서비스인가요? | 바로가기 |
| :--- | :--- | :--- |
| **StockPilot** | 실제 한·미 주식 시세로 가상투자하고, 투자일지와 리그로 학습하는 모의투자 서비스 | [모의투자 ↗](https://stockpilot.coders.kr) |
| **아침결** | 매일 오전 7시 30분, 핵심 뉴스의 배경과 출처까지 정리해 전하는 뉴스 브리핑 | [오늘의 뉴스 ↗](https://morningnews.coders.kr) |
| **MORROW** | 서로의 관심에서 매칭·실시간 대화·약속으로 이어지는 소셜 디스커버리 · 공개 포트폴리오 | [둘러보기 ↗](https://morrow.coders.kr) |
| **날씨한편** | 위치와 활동에 맞는 날씨·대기질 정보를 확인하고, 원하는 시간에 이메일로 받는 날씨 브리핑 | [날씨 확인 ↗](https://weather.coders.kr) |
| **살도 · Saldobook** | 수입·지출과 예산을 기록하고, 오늘 쓸 수 있는 금액과 월말 예상 지출을 확인하는 금융 기록장 | [가계부 열기 ↗](https://saldobook.coders.kr) |
| **검은 자정** | 단서·음성 토론·투표로 진실을 추리하는 실시간 소셜 게임. 혼자서도 AI와 플레이 | [게임 시작 ↗](https://black-midnight.coders.kr) |
| **HYUNDAI LIFE PASS** | 충전소·서비스 거점 탐색과 차량 관리 흐름을 연결한 커넥티드카 서비스 · 비공식 파일럿 | [파일럿 보기 ↗](https://hyundai-life-pass.coders.kr) |
| **YieldScope P&T** | 반도체 LOT 판정부터 원인 분석·개선 조치·교대 인계까지 체험하는 품질 워크벤치 · 합성 데이터 데모 | [데모 보기 ↗](https://yieldscope-pnt.coders.kr) |
| **Trading Stock System** | 주문 접수·매칭·체결·복구 과정을 살펴보는 매매체결 검증 콘솔 · 실주문 차단 | [콘솔 열기 ↗](https://tradingstocksysyem.coders.kr) |

<sub>소스 코드와 상세 설계는 아래 대표 서비스 및 서비스별 설계에서 확인할 수 있습니다.</sub>

---

<h2 id="flagship-products">02 / 대표 서비스 · Flagship Systems</h2>

가장 깊게 다듬고 있는 두 서비스입니다. **어떤 제품을 만들었는지, 내부에서 어떤 문제가 생기고 어떻게 풀었는지**를 함께 정리했습니다.

### 01. StockPilot — 실제 시세 기반 가상투자 · 학습 플랫폼

> KRX·NXT와 미국 주식 시세를 **검색 → 분석 → 가상주문 → 복기 → 리그·학습**으로 연결한 투자 학습 제품입니다.

```text
KIS · OpenDART · SEC EDGAR
             ↓
Async API → Order Guard → Ledger · Audit
      └──── WebSocket ────→ Client
```

- **Architecture & Integration** — 비동기 FastAPI에서 KIS Open API, OpenDART와 SEC EDGAR를 통합하고 WebSocket 시세와 PostgreSQL 가상 원장을 분리했습니다.
- **Data Integrity** — 요청 키·주문 지문·DB 유일 제약으로 중복 체결을 막고, 추가 전용 감사 이벤트와 원장 대사로 잔액 정합성을 검증합니다.
- **Distributed Operations** — Redis 공유 캐시·single-flight·lease로 외부 시세 API와 복수 인스턴스의 중복 작업을 제어합니다.
- **Delivery & Safety** — readiness/liveness, CI 품질 게이트와 kill switch를 구성하고 실제 증권계좌 주문은 구조적으로 차단했습니다.
- **Product** — 4가지 주문 방식, 원화·달러 포트폴리오, 투자일지, 시세 리플레이, 리그와 4단계 12개 위험관리 미션을 구현했습니다.

`Python 3.12` · `FastAPI` · `Next.js 16` · `React 19` · `TypeScript` · `PostgreSQL 16` · `Alembic` · `Redis` · `Docker`

> **Scope:** 실제 증권계좌 주문과 연결하지 않는 100% 가상투자 서비스입니다.

**[서비스 사용하기 ↗](https://stockpilot.coders.kr)** · **[Source Code](https://github.com/boclair98/stockpilot)**

<br />

### 02. 아침결 — 매일 07:30 뉴스 브리핑

> 네이버 검색, GDELT와 공식기관 RSS를 함께 수집해 전날의 핵심 뉴스를 **한 줄 결론 → 배경 → 출처 → 다음 확인 포인트**로 전달합니다.

```text
Search · GDELT · Official RSS
               ↓
Ingestion → Quality Gate → Briefing API
                              └→ PWA · Web Push
```

- **Collection Pipeline** — Kotlin·Spring Boot API에서 네이버 검색, GDELT와 공식기관 RSS를 수집하고 PostgreSQL/Flyway 기반으로 브리핑과 출처를 관리합니다.
- **Publishing Quality** — 공식 자료와 복수 출처를 우선하며, 기준 미달 콘텐츠는 발행 대상에서 제외하도록 수집·검증·발행 단계를 분리했습니다.
- **Operations** — 발행 전 검증, 운영 모니터, 실패 시 발행 중단, 정정 이력과 암호화 백업·복구 절차를 구성했습니다.
- **Verification** — Playwright E2E, 부하 스모크 테스트, 프런트 lint·build와 백엔드 검증을 배포 기준으로 사용합니다.
- **Product** — 관심 분야·분량 설정, 지난 브리핑 보관함, 신뢰센터와 PWA Web Push를 하나의 구독 흐름으로 연결했습니다.

`Kotlin` · `Java 21` · `Spring Boot` · `Next.js 16` · `React 19` · `PostgreSQL` · `Flyway` · `PWA` · `Playwright`

**[오늘의 브리핑 읽기 ↗](https://morningnews.coders.kr)** · **[Source Code](https://github.com/boclair98/achim-gyeol)**

---

<h2 id="tech-stack">03 / Technical Stack</h2>

### Core Backend & API

Spring 기반 금융·뉴스·모빌리티 서비스와 FastAPI 기반 투자·게임·품질 시스템의 API와 백그라운드 작업을 구현했습니다.

<p>
  <img src="https://img.shields.io/badge/Java-17_%C2%B7_21-0B1220?style=flat-square&logo=openjdk&logoColor=ED8B00" alt="Java" />
  <img src="https://img.shields.io/badge/Kotlin-2.x-0B1220?style=flat-square&logo=kotlin&logoColor=7F52FF" alt="Kotlin" />
  <img src="https://img.shields.io/badge/Spring_Boot-3_%C2%B7_4-0B1220?style=flat-square&logo=springboot&logoColor=6DB33F" alt="Spring Boot" />
  <img src="https://img.shields.io/badge/Spring_Security-0B1220?style=flat-square&logo=springsecurity&logoColor=6DB33F" alt="Spring Security" />
  <img src="https://img.shields.io/badge/Python-3.12-0B1220?style=flat-square&logo=python&logoColor=3776AB" alt="Python" />
  <img src="https://img.shields.io/badge/FastAPI-0B1220?style=flat-square&logo=fastapi&logoColor=00C7B7" alt="FastAPI" />
  <img src="https://img.shields.io/badge/Gradle-0B1220?style=flat-square&logo=gradle&logoColor=02303A" alt="Gradle" />
</p>

`REST API` · `Layered Architecture` · `Transaction Boundary` · `Validation` · `Pydantic` · `OAuth 2.0` · `Background Jobs`

### Data · Consistency · Cache

PostgreSQL 제약·잠금·감사 로그와 Redis 캐시·lease를 사용해 중복 처리와 데이터 불일치를 제어합니다.

<p>
  <img src="https://img.shields.io/badge/PostgreSQL-0B1220?style=flat-square&logo=postgresql&logoColor=4169E1" alt="PostgreSQL" />
  <img src="https://img.shields.io/badge/Redis-0B1220?style=flat-square&logo=redis&logoColor=FF4438" alt="Redis" />
  <img src="https://img.shields.io/badge/JPA_%C2%B7_Hibernate-0B1220?style=flat-square&logo=hibernate&logoColor=59666C" alt="JPA Hibernate" />
  <img src="https://img.shields.io/badge/SQLAlchemy-0B1220?style=flat-square&logo=sqlalchemy&logoColor=D71F00" alt="SQLAlchemy" />
  <img src="https://img.shields.io/badge/Flyway-0B1220?style=flat-square&logo=flyway&logoColor=CC0200" alt="Flyway" />
  <img src="https://img.shields.io/badge/Alembic-0B1220?style=flat-square&logo=python&logoColor=3776AB" alt="Alembic" />
</p>

`Idempotency` · `Pessimistic Lock` · `Unique Constraint` · `Audit Log` · `WAL / Replay` · `Caffeine` · `Drizzle` · `S3-compatible Storage`

### Delivery · Operations · Observability

Docker 배포, CI 품질 게이트, 상태 점검, 운영 지표와 복구 절차를 서비스 단위로 구성합니다.

<p>
  <img src="https://img.shields.io/badge/Docker-0B1220?style=flat-square&logo=docker&logoColor=2496ED" alt="Docker" />
  <img src="https://img.shields.io/badge/nginx-0B1220?style=flat-square&logo=nginx&logoColor=009639" alt="nginx" />
  <img src="https://img.shields.io/badge/GitHub_Actions-0B1220?style=flat-square&logo=githubactions&logoColor=2088FF" alt="GitHub Actions" />
  <img src="https://img.shields.io/badge/Playwright-0B1220?style=flat-square&logo=playwright&logoColor=2EAD33" alt="Playwright" />
  <img src="https://img.shields.io/badge/Prometheus-0B1220?style=flat-square&logo=prometheus&logoColor=E6522C" alt="Prometheus" />
  <img src="https://img.shields.io/badge/Spring_Actuator-0B1220?style=flat-square&logo=springboot&logoColor=6DB33F" alt="Spring Actuator" />
  <img src="https://img.shields.io/badge/JUnit-0B1220?style=flat-square&logo=junit5&logoColor=25A162" alt="JUnit" />
</p>

`Docker Compose` · `ShedLock` · `CI Quality Gate` · `Health Probe` · `Request ID` · `Rate Limit` · `Circuit Breaker` · `Runbook` · `Backup`

### Frontend · Realtime · Mobile

<p>
  <img src="https://img.shields.io/badge/TypeScript-0B1220?style=flat-square&logo=typescript&logoColor=3178C6" alt="TypeScript" />
  <img src="https://img.shields.io/badge/Next.js-16-0B1220?style=flat-square&logo=nextdotjs&logoColor=white" alt="Next.js" />
  <img src="https://img.shields.io/badge/React-19-0B1220?style=flat-square&logo=react&logoColor=61DAFB" alt="React" />
  <img src="https://img.shields.io/badge/Tailwind_CSS-4-0B1220?style=flat-square&logo=tailwindcss&logoColor=06B6D4" alt="Tailwind CSS" />
  <img src="https://img.shields.io/badge/WebSocket-0B1220?style=flat-square&logo=socketdotio&logoColor=white" alt="WebSocket" />
  <img src="https://img.shields.io/badge/WebRTC-0B1220?style=flat-square&logo=webrtc&logoColor=white" alt="WebRTC" />
  <img src="https://img.shields.io/badge/PWA_%C2%B7_Capacitor-0B1220?style=flat-square&logo=pwa&logoColor=5A0FC8" alt="PWA Capacitor" />
</p>

`Vite` · `Thymeleaf` · `Responsive UI` · `Static Export` · `Server-rendered View`

### External APIs · Identity

`Kakao · Naver · Google OAuth` · `KIS Open API` · `OpenDART` · `SEC EDGAR` · `금융결제원 테스트베드` · `Hyundai Developers` · `기상청` · `에어코리아` · `Kakao Local/Maps` · `Google Places` · `GDELT` · `Web Push / FCM`

### Data Tools · ML · Visualization — Project Experience

<p>
  <img src="https://img.shields.io/badge/MySQL-PROJECT_EXPERIENCE-0B1220?style=flat-square&logo=mysql&logoColor=4479A1" alt="MySQL Project Experience" />
  <img src="https://img.shields.io/badge/Pandas-0B1220?style=flat-square&logo=pandas&logoColor=150458" alt="Pandas" />
  <img src="https://img.shields.io/badge/NumPy-0B1220?style=flat-square&logo=numpy&logoColor=013243" alt="NumPy" />
  <img src="https://img.shields.io/badge/scikit--learn-0B1220?style=flat-square&logo=scikitlearn&logoColor=F7931E" alt="scikit-learn" />
  <img src="https://img.shields.io/badge/Streamlit-0B1220?style=flat-square&logo=streamlit&logoColor=FF4B4B" alt="Streamlit" />
  <img src="https://img.shields.io/badge/Plotly-0B1220?style=flat-square&logo=plotly&logoColor=3F4F75" alt="Plotly" />
</p>

---

<h2 id="engineering">04 / Explore the Code · 궁금한 문제부터</h2>

처음 오셨다면 아래 질문에서 시작해 보세요. **개념을 정리한 글 → 서비스 구현 → 운영 문서**로 이어서 읽을 수 있습니다.

| 궁금한 문제 | 살펴볼 구현 | 함께 읽기 |
| :--- | :--- | :--- |
| 같은 주문이 두 번 들어오면? | [StockPilot](https://github.com/boclair98/stockpilot)의 멱등 키·유일 제약·원장 대사 | [HTTP 멱등성](https://boclair98.tistory.com/113) |
| 두 요청이 동시에 상태를 바꾸면? | [MORROW](https://github.com/boclair98/morrow)의 잠금·사용자 쌍 유일성·DB 저장 후 발행 | [트랜잭션 AOP](https://boclair98.tistory.com/132) |
| 외부 API가 느리거나 멈추면? | [날씨한편](https://github.com/boclair98/Weather)의 timeout·circuit breaker·캐시·부분 실패 격리 | [운영 런북](https://github.com/boclair98/Weather/blob/main/docs/OPERATIONS.md) |
| 실시간 정보는 누구에게까지 보여줄까? | [검은 자정](https://github.com/boclair98/mafia-game)의 서버 권위 상태·참가자별 정보 필터링·WebRTC | [StockPilot 시세 처리](https://github.com/boclair98/stockpilot) |
| 실패한 배포·발행은 어떻게 수습할까? | [아침결](https://github.com/boclair98/achim-gyeol)의 품질 게이트·발행 중단·정정·복구 | [사고 대응 절차](https://github.com/boclair98/achim-gyeol/blob/main/docs/INCIDENT_RESPONSE.md) |
| 같은 이벤트로 같은 결과를 복원할 수 있을까? | [Trading Stock System](https://github.com/boclair98/TradingStockSysyem)의 결정론적 코어·WAL·재생 검증 | [코어와 검증 범위](https://github.com/boclair98/TradingStockSysyem#readme) |

<sub>링크는 각 저장소의 진입점과 관련 글입니다. 구현 범위와 제약도 각 프로젝트 설명에 함께 남겼습니다.</sub>

---

<h2 id="operations">05 / 운영을 코드와 문서로 남깁니다</h2>

배포 이후에는 **실패를 감지하는 방법, 안전하게 멈추는 기준, 복구 후 확인할 항목**까지 다룹니다.

### Protect / 정합성과 안전 경계

StockPilot의 중복 주문 방지, 오래된 시세 차단, 주문 한도, 킬 스위치와 원장 대사 기준을 문서화했습니다.

[주문 통제·도입 준비 기준 ↗](https://github.com/boclair98/stockpilot/blob/main/docs/BROKERAGE_READINESS.md)

### Observe / 상태와 장애 원인 확인

날씨한편은 liveness·readiness, 외부 API 지표와 원천자료의 시각을 구분하고, 마지막 정상자료 사용과 실패 응답의 기준을 운영 런북에 정리했습니다.

[상태 점검·장애 대응·배포와 롤백 ↗](https://github.com/boclair98/Weather/blob/main/docs/OPERATIONS.md)

### Recover / 중단·정정·복구

아침결은 발행 중단과 정정 절차, 실패한 발송 재시도, 암호화 백업과 격리된 DB에서의 복구 검증 절차를 갖췄습니다.

[사고 대응·정정 발행 ↗](https://github.com/boclair98/achim-gyeol/blob/main/docs/INCIDENT_RESPONSE.md) · [백업·복구 절차 ↗](https://github.com/boclair98/achim-gyeol/blob/main/docs/BACKUP_AND_RESTORE.md)

---

<h2 id="featured-systems">06 / 서비스별 설계 · Selected Systems</h2>

서비스 이름을 펼치면 설계·기술 스택·구현 범위를 읽을 수 있습니다.

<details>
<summary><strong>03. MORROW — 약속까지 이어지는 소셜 디스커버리</strong></summary>

> 상호 관심 이후 **MORROW Sync → 실시간 채팅 → 장소·시간 제안 → 안전 확인**까지 이어지는 만 20세 이상 서비스입니다.

- **Architecture** — 추천·상호 매칭, 3라운드 아이스브레이커, 채팅, 약속, 차단·신고·운영 검수와 계정 수명주기를 하나의 도메인 흐름으로 모델링했습니다.
- **Concurrency** — 비관적 잠금과 사용자 쌍 유일 제약으로 중복 매치를 방어하고, 메시지는 DB에 먼저 저장한 뒤 발행하며 `client_id`로 멱등성을 보장합니다.
- **Security** — OAuth `state`·PKCE·nonce, 해시 세션, 사진 파일 시그니처(magic byte)·크기·SHA-256 검증, 검수 전 비공개와 권한 검사를 적용했습니다.
- **Operations** — Redis 분산 요청 제한과 장애 시 인스턴스 로컬 제한, S3-compatible 저장소, Flyway 마이그레이션, 상태 점검과 non-root Docker를 구성했습니다.

`Kotlin 2.3` · `Spring Boot 4` · `Spring Security` · `Spring WebSocket` · `Next.js 16` · `PostgreSQL 16` · `Redis` · `Flyway` · `S3-compatible Storage`

> **Scope:** 공개 포트폴리오 단계이며 성인 확인, 운영 SLA, 백업·복구 알림과 복수 인스턴스 WebSocket fan-out은 정식 출시 전 보강 범위입니다.

**[서비스 사용하기 ↗](https://morrow.coders.kr)** · **[Source Code](https://github.com/boclair98/morrow)**

</details>


<details>
<summary><strong>04. HYUNDAI LIFE PASS — Connected Car Life 파일럿</strong></summary>

> 충전소·서비스 거점 탐색과 동의 기반 차량 연동 구조, 차량 여권과 **읽기 전용 OTA Canary Lab**을 구성한 모빌리티 파일럿입니다.

> **Scope:** 현대자동차의 공식 서비스가 아닌 비공식 포트폴리오 콘셉트입니다.

- **Architecture & Integration** — Hyundai Developers, 한국환경공단과 Kakao API를 공급자별 어댑터로 분리하고, 연동 여부와 제공 데이터의 경계를 화면에 명시했습니다.
- **Trust Boundary** — 제공되지 않은 예약·결제·진단·OTA 값을 만들지 않고 출처와 상태를 표시하며, 동의 철회 콜백에서 토큰과 실차 데이터를 삭제합니다.
- **Security & Operations** — PostgreSQL 세션, HttpOnly·Secure·SameSite 쿠키, 요청 제한, request ID·보안 헤더, 서명된 감사 로그와 Actuator 지표를 적용했습니다.
- **Product Flow** — 로그인 전 위치 기반 탐색부터 차량 연결, 7종 경고, 연결 기록과 SDV 배포 보호 규칙까지 사용자·운영 흐름을 분리했습니다.

`Kotlin` · `Spring Boot 3` · `React` · `Vite` · `PostgreSQL` · `Flyway` · `OAuth 2.0` · `Actuator` · `Docker`

**[공개 파일럿 ↗](https://hyundai-life-pass.coders.kr)** · **[Source Code](https://github.com/boclair98/hyundai-life-pass)**

</details>


<details>
<summary><strong>05. YieldScope P&T — 반도체 양산 품질 워크벤치</strong></summary>

> Test Program qualification부터 **LOT 격리·판정 → FA/RCA → CAPA 검증 → 교대 인계**까지 재현한 P&T 품질 의사결정 워크벤치입니다.

> **Scope:** 실제 회사 내부 데이터가 아닌 100% 합성 데이터 기반 포트폴리오입니다.

- **Domain Model** — correlation, false reject, guardband, multisite 편차, retest recovery와 test time을 함께 보고 프로그램 release를 판단합니다.
- **Quality Decision** — FPY·DPPM뿐 아니라 UPH·utilization·TAT까지 연결해 수율, 품질과 생산성을 같은 의사결정 흐름에서 확인합니다.
- **Traceability** — 합성 케이스의 LOT HOLD·RELEASE·FA 결정에 사유·담당자·시각을 기록하고, 물리 분석부터 CAPA 재검증까지의 증거 구조를 모델링했습니다.
- **Architecture** — Next.js UI와 FastAPI API, async SQLAlchemy, PostgreSQL/Alembic, 상태 점검 엔드포인트와 Docker/nginx 경계를 구성했습니다.
- **Verification** — 프런트 lint·build, 백엔드 Ruff·pytest, PostgreSQL API 테스트와 health/liveness 스모크를 품질 기준으로 사용합니다.

`Python 3.12` · `FastAPI` · `SQLAlchemy Async` · `Next.js 16` · `React 19` · `PostgreSQL` · `Alembic` · `Docker`

**[공개 데모 ↗](https://yieldscope-pnt.coders.kr)** · **[Source Code](https://github.com/boclair98/yieldscope-pnt)**

</details>


---

<h2 id="more-products">07 / More Deployed Systems</h2>

서비스 이름을 펼치면 설계·기술 스택·구현 범위를 읽을 수 있습니다.

<details>
<summary><strong>06. 검은 자정 — 실시간 소셜 추리 게임</strong></summary>

4~12명이 밤 행동, 현장 단서, 음성 토론과 공개 투표 기록을 대조하며 혼자서는 규칙 기반 AI 7명과 플레이하는 모바일 우선 게임입니다.

- **Architecture** — WebSocket 상태 동기화, 참가자별 비밀 정보 필터링과 서버 권위 상태 머신
- **Realtime** — WebRTC P2P 음성, 재접속을 고려한 게임 상태 복구와 공개 투표 기록
- **Delivery** — Next.js PWA와 Capacitor 기반 Web·Android·iOS 프로젝트
- **Stack** — `Python` · `FastAPI` · `Next.js` · `TypeScript` · `WebSocket` · `WebRTC` · `Capacitor`

> **Scope:** 재접속 복구는 동일 인스턴스 범위이며, 현재 방 상태는 인스턴스 메모리에 있어 서버 재시작 시 진행 중인 방이 종료될 수 있습니다.

**[게임 시작하기 ↗](https://black-midnight.coders.kr)** · **[Source Code](https://github.com/boclair98/mafia-game)**

</details>


<details>
<summary><strong>07. 날씨한편 — 맞춤 날씨 · 이메일 브리핑</strong></summary>

기상청·에어코리아·Kakao 원천자료를 위치와 활동 목적에 맞는 외출 판단으로 바꾸고 사용자가 지정한 아침·점심·저녁 시각에 이메일로 전달합니다.

- **Resilience** — 여러 외부 API의 timeout·retry·circuit breaker·fallback, Redis/Caffeine cache와 bounded executor
- **Operations** — ShedLock 분산 스케줄, Actuator·Prometheus, readiness/liveness, request ID, CSP nonce·HSTS와 SBOM
- **Verification** — JUnit·Spring Boot Test, GitHub Actions, dependency review와 CycloneDX SBOM 검증
- **Stack** — `Java 17` · `Spring Boot` · `PostgreSQL` · `Redis` · `Caffeine` · `ShedLock` · `Prometheus`

**[날씨한편 열기 ↗](https://weather.coders.kr)** · **[Source Code](https://github.com/boclair98/Weather)**

</details>


<details>
<summary><strong>08. 살도 · Saldobook — 개인 금융 기록 서비스</strong></summary>

직접 기록한 수입·지출과 예산을 바탕으로 오늘의 안심 사용액, 월말 예상 지출과 소비 흐름을 보여주는 개인 금융 서비스입니다.

- **Data & Integration** — 사용자별 데이터 격리, 거래 지문 중복 방지와 계좌 단위 부분 실패 처리 구조
- **Security** — JDBC session, HttpOnly·Secure·SameSite 쿠키, 상태 변경 요청의 애플리케이션 전용 헤더 검증과 OAuth 인증 경계
- **Operations & Verification** — 프런트 production build, 백엔드 test·package, Flyway 마이그레이션과 Actuator 상태 점검
- **Current Scope** — 공개 운영본은 수동 입력을 기본으로 하며, AES-256-GCM 토큰 암호화와 계좌 연동은 승인 환경을 위한 선택적 구조로 분리했습니다.
- **Stack** — `Java 21` · `Spring Boot` · `Next.js` · `PostgreSQL` · `Flyway` · `OAuth 2.0` · `Docker`

**[살도 사용하기 ↗](https://saldobook.coders.kr)** · **[Source Code](https://github.com/boclair98/saldobook)**

</details>


<details>
<summary><strong>09. Trading Stock System — 매매체결 · 주문 안전성 검증</strong></summary>

국내 주식시장과 대체거래소 환경을 가정해 주문 접수부터 매칭, 체결, 복구와 감사 이벤트까지 검증하는 엔지니어링 콘솔입니다.

- **Architecture** — Venue Matching Lab과 Live Broker Routing 경계를 분리하고, 웹 콘솔과 독립 Java 매칭 코어를 별도 검증 대상으로 구성했습니다.
- **Matching** — 가격·시간 우선, 시장가·지정가, DAY·IOC·FOK, 취소·정정, 동시호가와 결정론적 SOR
- **Reliability** — Java 결정론적 코어, CRC32C WAL, SHA-256 상태 다이제스트 기반 재생 검증, 추가 전용 체결·감사 이벤트와 위험 통제
- **Verification** — 결정론 테스트, 브로커 계약 테스트, CI와 health/readiness 점검
- **Stack** — `Java 21` · `TypeScript` · `Next.js` · `PostgreSQL` · `Drizzle` · `WAL` · `Docker`

> **Scope:** 독립 Java 코어는 현재 웹 실주문 경로와 직접 연결되지 않았고, 3개 브로커 어댑터는 고정 응답 계약 테스트 수준입니다. 실주문은 차단되어 있으며 운영 승인과 sandbox/production E2E는 별도 검증 범위입니다.

**[공개 콘솔 ↗](https://tradingstocksysyem.coders.kr)** · **[Source Code](https://github.com/boclair98/TradingStockSysyem)**

</details>


---

<h2 id="selected-projects">08 / Engineering Projects</h2>

- **[MeetPlace](https://github.com/boclair98/MeetPlace)** — 2~8명의 출발지에서 평균·최대 이동거리와 편차를 계산하고 Kakao Local·Google Places의 실제 장소를 점수화하는 약속 장소 추천 서비스
- **[Question](https://github.com/boclair98/Question)** — 직무별 랜덤 질문, 질문 확인·답변 타이머, 세션 인증과 질문 기록을 구현한 면접 연습 서비스
- **[RO Desalination Dashboard](https://github.com/boclair98/haesudamsuhwa_project_streamlit)** — 수질·공정 데이터로 인입압력과 전력 사용량을 예측하고 공정 상태를 시각화한 데이터 프로젝트

---

<h2 id="writing">09 / Engineering Notes</h2>

구현 결과만 남기지 않고 Java, Spring Boot, 데이터베이스, 인프라와 문제 해결 과정을 글과 코드로 기록합니다.

- **[트랜잭션 AOP 주의 사항 ↗](https://boclair98.tistory.com/132)** — `@Transactional` proxy와 self-invocation 함정을 테스트로 확인
- **[커넥션 풀 ↗](https://boclair98.tistory.com/128)** — 연결 비용과 서버·DB 자원에 맞춘 pool sizing 관점
- **[HTTP 메서드에서 멱등성이란 무엇일까요? ↗](https://boclair98.tistory.com/113)** — 재시도와 중복 요청을 안전하게 다루는 기준
- **[HTTP 헤더 캐시와 조건부 요청 ↗](https://boclair98.tistory.com/126)** — validation header와 `304 Not Modified`를 활용한 전송 최적화
- **[JPA - 영속성 컨텍스트 ↗](https://boclair98.tistory.com/135)** — 1차 캐시, 동일성, 쓰기 지연과 dirty checking 정리

**[기술 블로그 전체 글 보기](https://boclair98.tistory.com/)** · **[Codetree TIL](https://github.com/boclair98/codetree-TILs)** · **[Algorithm](https://github.com/boclair98/Algorithm)** · **[전체 저장소](https://github.com/boclair98?tab=repositories)**

---

<div align="center">

<strong>Design · Build · Verify · Deploy · Observe · Improve</strong>

<sub>만들고, 검증하고, 기록합니다. 다음 구현에 도움이 되는 코드가 남도록.</sub>

</div>
