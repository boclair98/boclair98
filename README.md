<div align="center">

<code>BACKEND ENGINEERING · DATA INTEGRITY · OPERATIONS</code>

<h1>Backend Engineering for Reliable Products</h1>

<h3>Java · Kotlin · Spring Boot / Python · FastAPI</h3>

서비스를 직접 설계·배포·운영하며<br />
<strong>트랜잭션 · 데이터 정합성 · 동시성 제어 · 실시간 처리 · 외부 API 장애 격리</strong>를 구현합니다.<br />
PostgreSQL·Redis 기반 데이터 처리부터 Docker·CI, 상태 점검과 운영 관측까지 연결합니다.

<p>
  <a href="https://stockpilot.coders.kr"><img src="https://img.shields.io/badge/FLAGSHIP_01-STOCKPILOT-2563EB?style=for-the-badge&logo=chartdotjs&logoColor=white&labelColor=0B1220" alt="대표 서비스 StockPilot" /></a>
  <a href="https://morningnews.coders.kr"><img src="https://img.shields.io/badge/FLAGSHIP_02-ACHIM_GYEOL-F97316?style=for-the-badge&logo=rss&logoColor=white&labelColor=0B1220" alt="대표 서비스 아침결" /></a>
</p>

<p>
  <img src="https://img.shields.io/badge/Java_%C2%B7_Kotlin-0B1220?style=flat-square&logo=openjdk&logoColor=ED8B00" alt="Java Kotlin" />
  <img src="https://img.shields.io/badge/Spring_Boot-0B1220?style=flat-square&logo=springboot&logoColor=6DB33F" alt="Spring Boot" />
  <img src="https://img.shields.io/badge/Python_%C2%B7_FastAPI-0B1220?style=flat-square&logo=python&logoColor=3776AB" alt="Python FastAPI" />
  <img src="https://img.shields.io/badge/PostgreSQL_%C2%B7_Redis-0B1220?style=flat-square&logo=postgresql&logoColor=4169E1" alt="PostgreSQL Redis" />
  <img src="https://img.shields.io/badge/Next.js_%C2%B7_TypeScript-0B1220?style=flat-square&logo=nextdotjs&logoColor=white" alt="Next.js TypeScript" />
  <img src="https://img.shields.io/badge/Docker_%C2%B7_CI-0B1220?style=flat-square&logo=docker&logoColor=2496ED" alt="Docker CI" />
</p>

<p>
  <code>Transactions</code>
  · <code>Idempotency</code>
  · <code>Concurrency</code>
  · <code>Realtime</code>
  · <code>Resilience</code>
  · <code>Observability</code>
</p>

<p>
  <a href="#flagship-products"><img src="https://img.shields.io/badge/PUBLIC_DEPLOYMENTS-9-22C55E?style=flat-square&labelColor=0B1220" alt="공개 배포 9개" /></a>
  <a href="#engineering"><img src="https://img.shields.io/badge/BUILD_%E2%86%92_DEPLOY_%E2%86%92_OPERATE-END_TO_END-60A5FA?style=flat-square&labelColor=0B1220" alt="Build Deploy Operate" /></a>
  <a href="https://boclair98.tistory.com/"><img src="https://img.shields.io/badge/ENGINEERING-NOTES-F97316?style=flat-square&logo=tistory&logoColor=white&labelColor=0B1220" alt="기술 블로그" /></a>
</p>

<p>
  <a href="#flagship-products"><b>Flagship Systems</b></a>
  &nbsp;·&nbsp;
  <a href="#engineering"><b>Engineering</b></a>
  &nbsp;·&nbsp;
  <a href="#tech-stack"><b>Tech Stack</b></a>
  &nbsp;·&nbsp;
  <a href="#featured-systems"><b>Deployed Systems</b></a>
  &nbsp;·&nbsp;
  <a href="#writing"><b>Writing</b></a>
</p>

</div>

---

<h2 id="flagship-products">01 · Flagship Systems</h2>

두 제품을 중심으로 **데이터 정합성, 외부 API 통합, 자동화된 검증과 배포 이후의 운영 설계**를 보여줍니다.

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

<h2 id="engineering">02 · Backend & Systems Engineering</h2>

기술을 목록으로만 제시하지 않고, 실제 시스템에서 해결한 문제와 함께 보여줍니다.

- **Transactions & Data Integrity** — 멱등 요청, 유일 제약, 가상 원장 대사와 결정론적 재생<br />[StockPilot](https://github.com/boclair98/stockpilot) · [Trading Stock System](https://github.com/boclair98/TradingStockSysyem)
- **Concurrency & Coordination** — 비관적 잠금, 사용자 쌍 유일성, DB 선저장 후 발행, Redis lease와 분산 스케줄 제어<br />[MORROW](https://github.com/boclair98/morrow) · [StockPilot](https://github.com/boclair98/stockpilot) · [날씨한편](https://github.com/boclair98/Weather)
- **External API Resilience** — timeout·retry·circuit breaker·fallback, 캐시와 부분 실패 격리<br />[날씨한편](https://github.com/boclair98/Weather) · [StockPilot](https://github.com/boclair98/stockpilot) · [Saldobook](https://github.com/boclair98/saldobook)
- **Security & Privacy** — OAuth 검증, 해시 세션, 사용자별 데이터 격리, 암호화 토큰과 동의 철회 기반 삭제<br />[MORROW](https://github.com/boclair98/morrow) · [Saldobook](https://github.com/boclair98/saldobook) · [Life Pass](https://github.com/boclair98/hyundai-life-pass)
- **Realtime Systems** — WebSocket 시세·채팅·게임 상태와 WebRTC P2P 음성<br />[StockPilot](https://github.com/boclair98/stockpilot) · [MORROW](https://github.com/boclair98/morrow) · [검은 자정](https://github.com/boclair98/mafia-game)
- **Delivery & Observability** — GitHub Actions, E2E·부하 검증, 상태 점검 엔드포인트, Actuator·Prometheus, 요청 ID, 백업과 운영 런북<br />[아침결](https://github.com/boclair98/achim-gyeol) · [날씨한편](https://github.com/boclair98/Weather) · [StockPilot](https://github.com/boclair98/stockpilot)

---

<h2 id="tech-stack">03 · Tech Stack</h2>

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

### Data · ML · Visualization — Project Experience

<p>
  <img src="https://img.shields.io/badge/MySQL-PROJECT_EXPERIENCE-0B1220?style=flat-square&logo=mysql&logoColor=4479A1" alt="MySQL Project Experience" />
  <img src="https://img.shields.io/badge/Pandas-0B1220?style=flat-square&logo=pandas&logoColor=150458" alt="Pandas" />
  <img src="https://img.shields.io/badge/NumPy-0B1220?style=flat-square&logo=numpy&logoColor=013243" alt="NumPy" />
  <img src="https://img.shields.io/badge/scikit--learn-0B1220?style=flat-square&logo=scikitlearn&logoColor=F7931E" alt="scikit-learn" />
  <img src="https://img.shields.io/badge/Streamlit-0B1220?style=flat-square&logo=streamlit&logoColor=FF4B4B" alt="Streamlit" />
  <img src="https://img.shields.io/badge/Plotly-0B1220?style=flat-square&logo=plotly&logoColor=3F4F75" alt="Plotly" />
</p>

---

<h2 id="featured-systems">04 · Selected Deployed Systems</h2>

### 03. MORROW — 약속까지 이어지는 소셜 디스커버리

> 상호 관심 이후 **MORROW Sync → 실시간 채팅 → 장소·시간 제안 → 안전 확인**까지 이어지는 만 20세 이상 서비스입니다.

- **Architecture** — 추천·상호 매칭, 3라운드 아이스브레이커, 채팅, 약속, 차단·신고·운영 검수와 계정 수명주기를 하나의 도메인 흐름으로 모델링했습니다.
- **Concurrency** — 비관적 잠금과 사용자 쌍 유일 제약으로 중복 매치를 방어하고, 메시지는 DB에 먼저 저장한 뒤 발행하며 `client_id`로 멱등성을 보장합니다.
- **Security** — OAuth `state`·PKCE·nonce, 해시 세션, 사진 파일 시그니처(magic byte)·크기·SHA-256 검증, 검수 전 비공개와 권한 검사를 적용했습니다.
- **Operations** — Redis 분산 요청 제한과 장애 시 인스턴스 로컬 제한, S3-compatible 저장소, Flyway 마이그레이션, 상태 점검과 non-root Docker를 구성했습니다.

`Kotlin 2.3` · `Spring Boot 4` · `Spring Security` · `Spring WebSocket` · `Next.js 16` · `PostgreSQL 16` · `Redis` · `Flyway` · `S3-compatible Storage`

> **Scope:** 공개 포트폴리오 단계이며 성인 확인, 운영 SLA, 백업·복구 알림과 복수 인스턴스 WebSocket fan-out은 정식 출시 전 보강 범위입니다.

**[서비스 사용하기 ↗](https://morrow.coders.kr)** · **[Source Code](https://github.com/boclair98/morrow)**

<br />

### 04. HYUNDAI LIFE PASS — Connected Car Life 파일럿

> 충전소·서비스 거점 탐색과 동의 기반 차량 연동 구조, 차량 여권과 **읽기 전용 OTA Canary Lab**을 구성한 모빌리티 파일럿입니다.

> **Scope:** 현대자동차의 공식 서비스가 아닌 비공식 포트폴리오 콘셉트입니다.

- **Architecture & Integration** — Hyundai Developers, 한국환경공단과 Kakao API를 공급자별 어댑터로 분리하고, 연동 여부와 제공 데이터의 경계를 화면에 명시했습니다.
- **Trust Boundary** — 제공되지 않은 예약·결제·진단·OTA 값을 만들지 않고 출처와 상태를 표시하며, 동의 철회 콜백에서 토큰과 실차 데이터를 삭제합니다.
- **Security & Operations** — PostgreSQL 세션, HttpOnly·Secure·SameSite 쿠키, 요청 제한, request ID·보안 헤더, 서명된 감사 로그와 Actuator 지표를 적용했습니다.
- **Product Flow** — 로그인 전 위치 기반 탐색부터 차량 연결, 7종 경고, 연결 기록과 SDV 배포 보호 규칙까지 사용자·운영 흐름을 분리했습니다.

`Kotlin` · `Spring Boot 3` · `React` · `Vite` · `PostgreSQL` · `Flyway` · `OAuth 2.0` · `Actuator` · `Docker`

**[공개 파일럿 ↗](https://hyundai-life-pass.coders.kr)** · **[Source Code](https://github.com/boclair98/hyundai-life-pass)**

<br />

### 05. YieldScope P&T — 반도체 양산 품질 워크벤치

> Test Program qualification부터 **LOT 격리·판정 → FA/RCA → CAPA 검증 → 교대 인계**까지 재현한 P&T 품질 의사결정 워크벤치입니다.

> **Scope:** 실제 회사 내부 데이터가 아닌 100% 합성 데이터 기반 포트폴리오입니다.

- **Domain Model** — correlation, false reject, guardband, multisite 편차, retest recovery와 test time을 함께 보고 프로그램 release를 판단합니다.
- **Quality Decision** — FPY·DPPM뿐 아니라 UPH·utilization·TAT까지 연결해 수율, 품질과 생산성을 같은 의사결정 흐름에서 확인합니다.
- **Traceability** — 합성 케이스의 LOT HOLD·RELEASE·FA 결정에 사유·담당자·시각을 기록하고, 물리 분석부터 CAPA 재검증까지의 증거 구조를 모델링했습니다.
- **Architecture** — Next.js UI와 FastAPI API, async SQLAlchemy, PostgreSQL/Alembic, 상태 점검 엔드포인트와 Docker/nginx 경계를 구성했습니다.
- **Verification** — 프런트 lint·build, 백엔드 Ruff·pytest, PostgreSQL API 테스트와 health/liveness 스모크를 품질 기준으로 사용합니다.

`Python 3.12` · `FastAPI` · `SQLAlchemy Async` · `Next.js 16` · `React 19` · `PostgreSQL` · `Alembic` · `Docker`

**[공개 데모 ↗](https://yieldscope-pnt.coders.kr)** · **[Source Code](https://github.com/boclair98/yieldscope-pnt)**

---

<h2 id="more-products">05 · More Deployed Systems</h2>

### 06. 검은 자정 — 실시간 소셜 추리 게임

4~12명이 밤 행동, 현장 단서, 음성 토론과 공개 투표 기록을 대조하며 혼자서는 규칙 기반 AI 7명과 플레이하는 모바일 우선 게임입니다.

- **Architecture** — WebSocket 상태 동기화, 참가자별 비밀 정보 필터링과 서버 권위 상태 머신
- **Realtime** — WebRTC P2P 음성, 재접속을 고려한 게임 상태 복구와 공개 투표 기록
- **Delivery** — Next.js PWA와 Capacitor 기반 Web·Android·iOS 프로젝트
- **Stack** — `Python` · `FastAPI` · `Next.js` · `TypeScript` · `WebSocket` · `WebRTC` · `Capacitor`

> **Scope:** 재접속 복구는 동일 인스턴스 범위이며, 현재 방 상태는 인스턴스 메모리에 있어 서버 재시작 시 진행 중인 방이 종료될 수 있습니다.

**[게임 시작하기 ↗](https://black-midnight.coders.kr)** · **[Source Code](https://github.com/boclair98/mafia-game)**

<br />

### 07. 날씨한편 — 맞춤 날씨 · 이메일 브리핑

기상청·에어코리아·Kakao 원천자료를 위치와 활동 목적에 맞는 외출 판단으로 바꾸고 사용자가 지정한 아침·점심·저녁 시각에 이메일로 전달합니다.

- **Resilience** — 여러 외부 API의 timeout·retry·circuit breaker·fallback, Redis/Caffeine cache와 bounded executor
- **Operations** — ShedLock 분산 스케줄, Actuator·Prometheus, readiness/liveness, request ID, CSP nonce·HSTS와 SBOM
- **Verification** — JUnit·Spring Boot Test, GitHub Actions, dependency review와 CycloneDX SBOM 검증
- **Stack** — `Java 17` · `Spring Boot` · `PostgreSQL` · `Redis` · `Caffeine` · `ShedLock` · `Prometheus`

**[날씨한편 열기 ↗](https://weather.coders.kr)** · **[Source Code](https://github.com/boclair98/Weather)**

<br />

### 08. 살도 · Saldobook — 개인 금융 기록 서비스

직접 기록한 수입·지출과 예산을 바탕으로 오늘의 안심 사용액, 월말 예상 지출과 소비 흐름을 보여주는 개인 금융 서비스입니다.

- **Data & Integration** — 사용자별 데이터 격리, 거래 지문 중복 방지와 계좌 단위 부분 실패 처리 구조
- **Security** — JDBC session, HttpOnly·Secure·SameSite 쿠키, 상태 변경 요청의 애플리케이션 전용 헤더 검증과 OAuth 인증 경계
- **Operations & Verification** — 프런트 production build, 백엔드 test·package, Flyway 마이그레이션과 Actuator 상태 점검
- **Current Scope** — 공개 운영본은 수동 입력을 기본으로 하며, AES-256-GCM 토큰 암호화와 계좌 연동은 승인 환경을 위한 선택적 구조로 분리했습니다.
- **Stack** — `Java 21` · `Spring Boot` · `Next.js` · `PostgreSQL` · `Flyway` · `OAuth 2.0` · `Docker`

**[살도 사용하기 ↗](https://saldobook.coders.kr)** · **[Source Code](https://github.com/boclair98/saldobook)**

<br />

### 09. Trading Stock System — 매매체결 · 주문 안전성 검증

국내 주식시장과 대체거래소 환경을 가정해 주문 접수부터 매칭, 체결, 복구와 감사 이벤트까지 검증하는 엔지니어링 콘솔입니다.

- **Architecture** — Venue Matching Lab과 Live Broker Routing 경계를 분리하고, 웹 콘솔과 독립 Java 매칭 코어를 별도 검증 대상으로 구성했습니다.
- **Matching** — 가격·시간 우선, 시장가·지정가, DAY·IOC·FOK, 취소·정정, 동시호가와 결정론적 SOR
- **Reliability** — Java 결정론적 코어, CRC32C WAL, SHA-256 상태 다이제스트 기반 재생 검증, 추가 전용 체결·감사 이벤트와 위험 통제
- **Verification** — 결정론 테스트, 브로커 계약 테스트, CI와 health/readiness 점검
- **Stack** — `Java 21` · `TypeScript` · `Next.js` · `PostgreSQL` · `Drizzle` · `WAL` · `Docker`

> **Scope:** 독립 Java 코어는 현재 웹 실주문 경로와 직접 연결되지 않았고, 3개 브로커 어댑터는 고정 응답 계약 테스트 수준입니다. 실주문은 차단되어 있으며 운영 승인과 sandbox/production E2E는 별도 검증 범위입니다.

**[공개 콘솔 ↗](https://tradingstocksysyem.coders.kr)** · **[Source Code](https://github.com/boclair98/TradingStockSysyem)**

---

<h2 id="selected-projects">06 · Selected Projects</h2>

- **[MeetPlace](https://github.com/boclair98/MeetPlace)** — 2~8명의 출발지에서 평균·최대 이동거리와 편차를 계산하고 Kakao Local·Google Places의 실제 장소를 점수화하는 약속 장소 추천 서비스
- **[Question](https://github.com/boclair98/Question)** — 직무별 랜덤 질문, 질문 확인·답변 타이머, 세션 인증과 질문 기록을 구현한 면접 연습 서비스
- **[RO Desalination Dashboard](https://github.com/boclair98/haesudamsuhwa_project_streamlit)** — 수질·공정 데이터로 인입압력과 전력 사용량을 예측하고 공정 상태를 시각화한 데이터 프로젝트

---

<h2 id="writing">07 · Engineering Notes</h2>

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

<sub>운영 가능한 제품을 만들고, 근거를 남기며, 계속 개선합니다.</sub>

</div>

