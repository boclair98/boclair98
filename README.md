<div align="center">

<code>BACKEND · PRODUCT · OPERATIONS</code>

<h1>Build · Deploy · Operate</h1>

### 기능을 만드는 데서 멈추지 않고, 실제 배포와 운영까지 연결합니다.

백엔드를 중심으로 **제품 흐름 · 데이터 정합성 · 외부 API · 성능 · 보안 · 장애 대응**을 함께 설계합니다.<br />
금융, 뉴스, 게임, 날씨처럼 서로 다른 도메인의 서비스를 직접 만들고 운영하며 개선하고 있습니다.

<p>
  <a href="#live-services"><img src="https://img.shields.io/badge/LIVE_SERVICES-6-22C55E?style=for-the-badge&labelColor=0B1220" alt="운영 서비스 6개" /></a>
  <a href="https://github.com/boclair98?tab=repositories"><img src="https://img.shields.io/badge/PUBLIC_REPOSITORIES-21-60A5FA?style=for-the-badge&logo=github&logoColor=white&labelColor=0B1220" alt="공개 저장소 21개" /></a>
  <a href="https://boclair98.tistory.com/"><img src="https://img.shields.io/badge/TECH_NOTES-95-F97316?style=for-the-badge&logo=tistory&logoColor=white&labelColor=0B1220" alt="기술 블로그 95개 글" /></a>
</p>

<p>
  <a href="https://stockpilot.coders.kr"><b>StockPilot 체험</b></a>
  &nbsp;·&nbsp;
  <a href="https://morningnews.coders.kr"><b>아침결 읽기</b></a>
  &nbsp;·&nbsp;
  <a href="https://black-midnight.coders.kr"><b>검은 자정 플레이</b></a>
  &nbsp;·&nbsp;
  <a href="https://boclair98.tistory.com/"><b>기술 블로그</b></a>
</p>

</div>

<br />

| Focus | How I work |
| --- | --- |
| **Product** | 문제를 기능 하나로 끝내지 않고 **시작부터 결과 확인까지** 완성된 사용자 흐름으로 만듭니다. |
| **Backend** | 인증, 데이터 격리, 멱등성, **트랜잭션과 정합성**을 서비스의 기본값으로 다룹니다. |
| **Operation** | 캐시, 상태 점검, 모니터링, **배포와 장애 대응**까지 운영 환경을 기준으로 개선합니다. |

<br />

<h2 id="live-services">🚀 Live Services</h2>

현재 접속 가능한 **6개의 서비스를 운영**하고 있습니다. 기능 수보다 실제 사용자 흐름, 안전한 데이터 처리, 배포 이후의 신뢰성을 더 중요하게 봅니다.

### 01. StockPilot — 실제 시세 기반 가상투자 · 학습 플랫폼

> 한국 KRX·NXT 통합 시세와 미국 주식 실제 시세를 바탕으로 **검색 → 분석 → 가상주문 → 복기 → 리그·학습**을 하나의 흐름으로 연결했습니다.

| Focus | Applied |
| --- | --- |
| **Product** | 4가지 주문 방식, 포트폴리오, 투자일지, 시세 리플레이, 1:1 배틀, 12개 학습 코스 |
| **Engineering** | KIS·OpenDART 연동, 비동기 FastAPI, WebSocket 시세, 원화·달러 가상 원장 |
| **Reliability & Safety** | 멱등 요청·DB 유일 제약, append-only 감사 이벤트, 원장 대사, kill switch, readiness/liveness |

- Redis shared cache·single-flight·lease로 외부 시세 API와 다중 replica 작업을 보호합니다.
- 주문 지문과 요청 키로 재시도·중복 클릭에 의한 중복 체결을 서버에서 차단합니다.
- 실거래 어댑터 없이 `SIMULATION` 모드만 허용해 실제 증권계좌 주문과 명확히 분리합니다.
- GitHub Actions에서 백엔드 테스트·정적 분석과 프런트엔드 lint·build를 자동 검증합니다.

<p>
  <img src="https://img.shields.io/badge/Python_3.12-0B1220?style=flat-square&logo=python&logoColor=3776AB" alt="Python 3.12" />
  <img src="https://img.shields.io/badge/FastAPI-0B1220?style=flat-square&logo=fastapi&logoColor=00C7B7" alt="FastAPI" />
  <img src="https://img.shields.io/badge/Next.js_16-0B1220?style=flat-square&logo=nextdotjs&logoColor=white" alt="Next.js 16" />
  <img src="https://img.shields.io/badge/React_19-0B1220?style=flat-square&logo=react&logoColor=61DAFB" alt="React 19" />
  <img src="https://img.shields.io/badge/PostgreSQL-0B1220?style=flat-square&logo=postgresql&logoColor=4169E1" alt="PostgreSQL" />
  <img src="https://img.shields.io/badge/Redis-0B1220?style=flat-square&logo=redis&logoColor=FF4438" alt="Redis" />
  <img src="https://img.shields.io/badge/Docker-0B1220?style=flat-square&logo=docker&logoColor=2496ED" alt="Docker" />
</p>

**[서비스 사용하기 ↗](https://stockpilot.coders.kr)** · [Repository](https://github.com/boclair98/stockpilot)

<br />

### 02. 아침결 — 매일 07:30 뉴스 브리핑

> 네이버 검색, GDELT 해외 보도, 공식기관 RSS를 함께 수집하고 교차 확인해 **읽기 쉬운 하루 뉴스 브리핑**으로 제공합니다.

| Focus | Applied |
| --- | --- |
| **Product** | 관심 분야·분량 설정, PWA Web Push, 지난 브리핑 보관함, 정정·신뢰센터 |
| **Engineering** | Kotlin·Spring Boot API, Next.js PWA, PostgreSQL·Flyway, 다원화 뉴스 수집 |
| **Operation** | 15분 운영 모니터, CI·Playwright E2E·부하 smoke, 암호화 DB 백업, incident runbook |

- 정책·경제·금융·사회·국제·테크·생활·문화·스포츠·e스포츠를 균형 있게 편집합니다.
- 공식 자료와 여러 출처에서 확인되는 사실을 우선하고, 억지로 분야를 채우지 않는 품질 기준을 둡니다.
- 실패 시 발행 중단과 정정 이력을 남길 수 있도록 신뢰·운영 흐름을 서비스 기능으로 설계했습니다.

<p>
  <img src="https://img.shields.io/badge/Kotlin_2.2-0B1220?style=flat-square&logo=kotlin&logoColor=7F52FF" alt="Kotlin 2.2" />
  <img src="https://img.shields.io/badge/Java_21-0B1220?style=flat-square&logo=openjdk&logoColor=ED8B00" alt="Java 21" />
  <img src="https://img.shields.io/badge/Spring_Boot-0B1220?style=flat-square&logo=springboot&logoColor=6DB33F" alt="Spring Boot" />
  <img src="https://img.shields.io/badge/Next.js_16-0B1220?style=flat-square&logo=nextdotjs&logoColor=white" alt="Next.js 16" />
  <img src="https://img.shields.io/badge/PostgreSQL-0B1220?style=flat-square&logo=postgresql&logoColor=4169E1" alt="PostgreSQL" />
  <img src="https://img.shields.io/badge/Playwright-0B1220?style=flat-square&logo=playwright&logoColor=2EAD33" alt="Playwright" />
  <img src="https://img.shields.io/badge/PWA-0B1220?style=flat-square&logo=pwa&logoColor=5A0FC8" alt="PWA" />
</p>

**[오늘의 브리핑 읽기 ↗](https://morningnews.coders.kr)** · [Repository](https://github.com/boclair98/achim-gyeol)

<br />

### 03. 검은 자정 — Web · Android · iOS 실시간 소셜 추리 게임

> 4~12명이 단서, 알리바이, 음성 토론과 공개 투표 기록을 대조하는 모바일 우선 게임입니다. 혼자서도 규칙 기반 AI 7명과 바로 플레이할 수 있습니다.

| Focus | Applied |
| --- | --- |
| **Realtime Game** | WebSocket 상태 동기화, WebRTC P2P 음성, 공개·비밀 채팅, 단계별 타이머 |
| **Server Authority** | 역할·투표·승패 서버 검증, 참가자별 비밀 정보 필터링, 서버 권위 상태 머신 |
| **Multi-platform** | Next.js PWA와 Capacitor 기반 Web·Android·iOS 프로젝트, 반응형 모바일 UI |

- 역할 정답을 클라이언트에 미리 보내지 않고, 각 참가자에게 허용된 정보만 전달합니다.
- 외부 LLM 없이 서버 내부 전략 규칙으로 서로 다른 성향의 AI 플레이어를 동작시킵니다.
- 음성 내용은 게임 서버에 저장하지 않고 WebRTC P2P 연결로 전달합니다.

<p>
  <img src="https://img.shields.io/badge/Python_3.12-0B1220?style=flat-square&logo=python&logoColor=3776AB" alt="Python 3.12" />
  <img src="https://img.shields.io/badge/FastAPI-0B1220?style=flat-square&logo=fastapi&logoColor=00C7B7" alt="FastAPI" />
  <img src="https://img.shields.io/badge/Next.js_16-0B1220?style=flat-square&logo=nextdotjs&logoColor=white" alt="Next.js 16" />
  <img src="https://img.shields.io/badge/TypeScript-0B1220?style=flat-square&logo=typescript&logoColor=3178C6" alt="TypeScript" />
  <img src="https://img.shields.io/badge/WebSocket-0B1220?style=flat-square&logo=socketdotio&logoColor=white" alt="WebSocket" />
  <img src="https://img.shields.io/badge/WebRTC-0B1220?style=flat-square&logo=webrtc&logoColor=333333" alt="WebRTC" />
  <img src="https://img.shields.io/badge/Capacitor-0B1220?style=flat-square&logo=capacitor&logoColor=119EFF" alt="Capacitor" />
</p>

**[게임 시작하기 ↗](https://black-midnight.coders.kr)** · [Repository](https://github.com/boclair98/mafia-game)

<br />

### 04. 날씨한편 — 예보 · 대기질 · 옷차림 메일 구독

> 원하는 지역의 날씨와 외출 준비 정보를 아침·점심·저녁에 받아보는 생활 밀착형 구독 서비스입니다.

| Focus | Applied |
| --- | --- |
| **Product** | 장소 검색·현재 위치, 관측·시간별·3일 예보, 대기질·특보·자외선·꽃가루, 최대 10개 이메일 구독 |
| **Engineering** | Java 17, Spring Boot, JPA, PostgreSQL, Redis·Caffeine, ShedLock, PWA, 반응형 HTML 메일 |
| **Reliability & Security** | timeout·retry·circuit breaker·fallback, bounded executor, Actuator·Prometheus, CSP nonce·HSTS |

- 기상청, 에어코리아, Kakao Local 등 여러 외부 API를 하나의 사용자 흐름으로 연결합니다.
- 분산 스케줄 락으로 중복 메일 발송을 완화하고, 외부 API 장애 시 가능한 데이터로 안전하게 대체합니다.
- readiness/liveness, request ID, fail-closed 관리자 인증과 CI·Dependabot·SBOM을 적용했습니다.

<p>
  <img src="https://img.shields.io/badge/Java_17-0B1220?style=flat-square&logo=openjdk&logoColor=ED8B00" alt="Java 17" />
  <img src="https://img.shields.io/badge/Spring_Boot-0B1220?style=flat-square&logo=springboot&logoColor=6DB33F" alt="Spring Boot" />
  <img src="https://img.shields.io/badge/PostgreSQL-0B1220?style=flat-square&logo=postgresql&logoColor=4169E1" alt="PostgreSQL" />
  <img src="https://img.shields.io/badge/Redis-0B1220?style=flat-square&logo=redis&logoColor=FF4438" alt="Redis" />
  <img src="https://img.shields.io/badge/Prometheus-0B1220?style=flat-square&logo=prometheus&logoColor=E6522C" alt="Prometheus" />
  <img src="https://img.shields.io/badge/PWA-0B1220?style=flat-square&logo=pwa&logoColor=5A0FC8" alt="PWA" />
</p>

**[날씨한편 구독하기 ↗](https://weather.coders.kr)** · [Repository](https://github.com/boclair98/Weather)

<br />

### 05. 살도 · Saldobook — 개인 가계부 · 다계좌 조회

> Google·카카오 로그인부터 월 예산, 거래 기록, 소비 분석과 조회용 다계좌 연결까지 개인의 돈 흐름을 한 화면에 모았습니다.

| Focus | Applied |
| --- | --- |
| **Product** | 월별 수입·지출·예산, 카테고리 분석, 6개월 추이, 검색·필터·CSV, 다계좌 동기화 |
| **Engineering** | Java 21·Spring Boot API, Next.js 16·React 19, JPA·Flyway, PostgreSQL 16 |
| **Data & Security** | 사용자별 데이터 격리, AES-256-GCM 토큰 암호화, 거래 지문 중복 방지, 부분 실패 처리 |

- 계좌별 잔액·거래내역 조회를 독립적으로 처리해 일부 계좌가 실패해도 나머지 동기화를 이어갑니다.
- JDBC session과 HttpOnly·Secure·SameSite 쿠키, CSRF 전용 헤더로 인증 흐름을 보호합니다.
- 실계좌번호와 계좌 비밀번호는 수집하지 않으며 금융결제원 테스트베드와 실제 운영망의 경계를 명시합니다.

<p>
  <img src="https://img.shields.io/badge/Java_21-0B1220?style=flat-square&logo=openjdk&logoColor=ED8B00" alt="Java 21" />
  <img src="https://img.shields.io/badge/Spring_Boot-0B1220?style=flat-square&logo=springboot&logoColor=6DB33F" alt="Spring Boot" />
  <img src="https://img.shields.io/badge/Next.js_16-0B1220?style=flat-square&logo=nextdotjs&logoColor=white" alt="Next.js 16" />
  <img src="https://img.shields.io/badge/React_19-0B1220?style=flat-square&logo=react&logoColor=61DAFB" alt="React 19" />
  <img src="https://img.shields.io/badge/PostgreSQL_16-0B1220?style=flat-square&logo=postgresql&logoColor=4169E1" alt="PostgreSQL 16" />
  <img src="https://img.shields.io/badge/Flyway-0B1220?style=flat-square&logo=flyway&logoColor=CC0200" alt="Flyway" />
</p>

**[살도 사용하기 ↗](https://saldobook.coders.kr)** · [Repository](https://github.com/boclair98/saldobook)

<br />

### 06. TradingStockSysyem — 주식 매매체결 규칙 검증 콘솔

> 국내 주식시장과 대체거래소 환경을 가정해 주문 접수부터 매칭, 체결·감사 이벤트까지 검증하는 브라우저 운영 콘솔입니다.

| Focus | Applied |
| --- | --- |
| **Matching** | 가격·시간 우선, 시장가·지정가, GTC·IOC·FOK, 취소·정정, 미체결 전체 취소 |
| **Market Rules** | 동시호가·uncrossing, 호가단위·가격제한폭, KRX·NXT 세션, 자기체결 방지, 결정론적 SOR |
| **Verification Boundary** | 다중 가상 종목, append-only 체결·감사 이벤트, 매칭엔진·시장 규칙 테스트, Docker 배포 |

- 순수 매칭 코어를 UI와 분리해 주문 규칙과 세션 전환을 반복 검증할 수 있게 구성했습니다.
- 외부 거래소 API와 증권계좌에는 연결하지 않고, 실제 연동 전 검증 범위와 추가 조건을 문서화했습니다.

<p>
  <img src="https://img.shields.io/badge/TypeScript-0B1220?style=flat-square&logo=typescript&logoColor=3178C6" alt="TypeScript" />
  <img src="https://img.shields.io/badge/Next.js_16-0B1220?style=flat-square&logo=nextdotjs&logoColor=white" alt="Next.js 16" />
  <img src="https://img.shields.io/badge/React_19-0B1220?style=flat-square&logo=react&logoColor=61DAFB" alt="React 19" />
  <img src="https://img.shields.io/badge/Matching_Engine-0B1220?style=flat-square&logo=databricks&logoColor=FF3621" alt="Matching Engine" />
  <img src="https://img.shields.io/badge/Docker-0B1220?style=flat-square&logo=docker&logoColor=2496ED" alt="Docker" />
</p>

**[운영 콘솔 열기 ↗](https://tradingstocksysyem.coders.kr)** · [Repository](https://github.com/boclair98/TradingStockSysyem)

<br />

## 🧪 Selected Projects

### MeetPlace

2~8명의 출발지를 바탕으로 평균·최대 이동거리와 편차를 계산하고, Kakao Local·Google Places의 실제 장소를 점수화해 추천합니다.

`Java` · `Spring Boot` · `Thymeleaf` · `Kakao Local API` · `Google Places API`<br />
**[Repository →](https://github.com/boclair98/MeetPlace)**

<br />

### Question

개발자·디자이너·마케팅·영업·반도체 직무별 랜덤 질문, 질문 확인 10초 + 답변 30초 타이머, 세션 로그인과 질문 기록을 구현했습니다.

`Java 17` · `Spring Boot` · `JPA` · `Thymeleaf` · `MySQL` · `H2`<br />
**[Repository →](https://github.com/boclair98/Question)**

<br />

### RO 해수담수화 Dashboard

수질·공정 데이터로 인입압력과 전력 사용량을 예측하고, 공정 상태를 정상·주의·이상으로 시각화했습니다.

`Python` · `Streamlit` · `Pandas` · `NumPy` · `scikit-learn` · `Plotly`<br />
**[Repository →](https://github.com/boclair98/haesudamsuhwa_project_streamlit)**

<br />

## 🧰 Tech Stack

기술 이름만 나열하지 않고, 실제 서비스에서 적용한 맥락과 함께 정리했습니다.

### Backend & API

<p>
  <img src="https://img.shields.io/badge/Java_17%2F21-0B1220?style=flat-square&logo=openjdk&logoColor=ED8B00" alt="Java 17 and 21" />
  <img src="https://img.shields.io/badge/Kotlin-0B1220?style=flat-square&logo=kotlin&logoColor=7F52FF" alt="Kotlin" />
  <img src="https://img.shields.io/badge/Spring_Boot-0B1220?style=flat-square&logo=springboot&logoColor=6DB33F" alt="Spring Boot" />
  <img src="https://img.shields.io/badge/Spring_MVC-0B1220?style=flat-square&logo=spring&logoColor=6DB33F" alt="Spring MVC" />
  <img src="https://img.shields.io/badge/Spring_Data_JPA-0B1220?style=flat-square&logo=spring&logoColor=6DB33F" alt="Spring Data JPA" />
  <img src="https://img.shields.io/badge/Spring_Security-0B1220?style=flat-square&logo=springsecurity&logoColor=6DB33F" alt="Spring Security" />
  <img src="https://img.shields.io/badge/Python_3.12-0B1220?style=flat-square&logo=python&logoColor=3776AB" alt="Python 3.12" />
  <img src="https://img.shields.io/badge/FastAPI-0B1220?style=flat-square&logo=fastapi&logoColor=00C7B7" alt="FastAPI" />
  <img src="https://img.shields.io/badge/SQLAlchemy_Async-0B1220?style=flat-square&logo=sqlalchemy&logoColor=D71F00" alt="SQLAlchemy Async" />
</p>

Spring 기반 금융·뉴스·날씨 서비스와 FastAPI 기반 실시간 투자·게임 서비스를 구현했습니다. REST API, 비동기 I/O, 사용자별 데이터 격리, 세션·OAuth 인증, 서버 권위 상태 처리를 다룹니다.

### Frontend & Mobile

<p>
  <img src="https://img.shields.io/badge/TypeScript-0B1220?style=flat-square&logo=typescript&logoColor=3178C6" alt="TypeScript" />
  <img src="https://img.shields.io/badge/JavaScript-0B1220?style=flat-square&logo=javascript&logoColor=F7DF1E" alt="JavaScript" />
  <img src="https://img.shields.io/badge/Next.js_16-0B1220?style=flat-square&logo=nextdotjs&logoColor=white" alt="Next.js 16" />
  <img src="https://img.shields.io/badge/React_19-0B1220?style=flat-square&logo=react&logoColor=61DAFB" alt="React 19" />
  <img src="https://img.shields.io/badge/Tailwind_CSS-0B1220?style=flat-square&logo=tailwindcss&logoColor=06B6D4" alt="Tailwind CSS" />
  <img src="https://img.shields.io/badge/Thymeleaf-0B1220?style=flat-square&logo=thymeleaf&logoColor=005F0F" alt="Thymeleaf" />
  <img src="https://img.shields.io/badge/PWA-0B1220?style=flat-square&logo=pwa&logoColor=5A0FC8" alt="PWA" />
  <img src="https://img.shields.io/badge/Capacitor-0B1220?style=flat-square&logo=capacitor&logoColor=119EFF" alt="Capacitor" />
</p>

실시간 시장 보드, 개인 금융 대시보드, 모바일 우선 게임, 설치형 PWA와 반응형 HTML 메일까지 사용자 흐름에 맞는 화면을 구현합니다.

### Data · Cache · Migration

<p>
  <img src="https://img.shields.io/badge/PostgreSQL_16-0B1220?style=flat-square&logo=postgresql&logoColor=4169E1" alt="PostgreSQL 16" />
  <img src="https://img.shields.io/badge/MySQL-0B1220?style=flat-square&logo=mysql&logoColor=4479A1" alt="MySQL" />
  <img src="https://img.shields.io/badge/Redis-0B1220?style=flat-square&logo=redis&logoColor=FF4438" alt="Redis" />
  <img src="https://img.shields.io/badge/H2-0B1220?style=flat-square&logo=h2database&logoColor=2C4F7C" alt="H2" />
  <img src="https://img.shields.io/badge/Flyway-0B1220?style=flat-square&logo=flyway&logoColor=CC0200" alt="Flyway" />
  <img src="https://img.shields.io/badge/Alembic-0B1220?style=flat-square&logo=python&logoColor=3776AB" alt="Alembic" />
</p>

거래 원장, 체결 이벤트, 사용자 금융 데이터, 스케줄 상태를 모델링하고 Redis 캐시·분산 lease·중복 방지와 Flyway/Alembic migration을 적용합니다.

### Infra · Delivery · Quality

<p>
  <img src="https://img.shields.io/badge/Docker-0B1220?style=flat-square&logo=docker&logoColor=2496ED" alt="Docker" />
  <img src="https://img.shields.io/badge/Docker_Compose-0B1220?style=flat-square&logo=docker&logoColor=2496ED" alt="Docker Compose" />
  <img src="https://img.shields.io/badge/GitHub_Actions-0B1220?style=flat-square&logo=githubactions&logoColor=2088FF" alt="GitHub Actions" />
  <img src="https://img.shields.io/badge/Playwright-0B1220?style=flat-square&logo=playwright&logoColor=2EAD33" alt="Playwright" />
  <img src="https://img.shields.io/badge/Prometheus-0B1220?style=flat-square&logo=prometheus&logoColor=E6522C" alt="Prometheus" />
  <img src="https://img.shields.io/badge/WebSocket-0B1220?style=flat-square&logo=socketdotio&logoColor=white" alt="WebSocket" />
  <img src="https://img.shields.io/badge/WebRTC-0B1220?style=flat-square&logo=webrtc&logoColor=333333" alt="WebRTC" />
</p>

컨테이너 배포, 자동 테스트·lint·build, liveness/readiness, request ID, 운영 지표, 부하 smoke, 암호화 백업과 장애 대응 runbook을 구성합니다.

### Data · ML · Visualization

<p>
  <img src="https://img.shields.io/badge/Pandas-0B1220?style=flat-square&logo=pandas&logoColor=150458" alt="Pandas" />
  <img src="https://img.shields.io/badge/NumPy-0B1220?style=flat-square&logo=numpy&logoColor=013243" alt="NumPy" />
  <img src="https://img.shields.io/badge/scikit--learn-0B1220?style=flat-square&logo=scikitlearn&logoColor=F7931E" alt="scikit-learn" />
  <img src="https://img.shields.io/badge/Streamlit-0B1220?style=flat-square&logo=streamlit&logoColor=FF4B4B" alt="Streamlit" />
  <img src="https://img.shields.io/badge/Plotly-0B1220?style=flat-square&logo=plotly&logoColor=3F4F75" alt="Plotly" />
</p>

Pandas·NumPy 기반 데이터 전처리, 선형회귀·랜덤포레스트 예측, Streamlit·Plotly 대시보드로 분석 결과를 사용자 화면까지 연결합니다.

### External APIs & Auth

`OAuth 2.0` · `KIS Open API` · `OpenDART` · `금융결제원 오픈뱅킹` · `기상청 API` · `에어코리아` · `Kakao Local API` · `Google Places API` · `GDELT` · `Web Push / FCM`

<br />

## 🛡️ Engineering in Practice

| Focus | Application & Evidence |
| --- | --- |
| **Data Integrity** | 요청 키·주문 지문·DB 유일 제약, append-only 감사 이벤트, 원장 정합성 검사 — [StockPilot](https://github.com/boclair98/stockpilot) |
| **Security & Isolation** | 사용자별 데이터 분리, AES-256-GCM 토큰 암호화, HttpOnly·Secure·SameSite 쿠키, CSRF 헤더 — [Saldobook](https://github.com/boclair98/saldobook) |
| **Resilience** | timeout·retry·circuit breaker·fallback, 일부 외부 API 실패 시 나머지 흐름 지속 — [날씨한편](https://github.com/boclair98/Weather) · [Saldobook](https://github.com/boclair98/saldobook) |
| **Concurrency & Scheduling** | Redis cache·single-flight·lease, ShedLock, bounded executor, 중복 스케줄 실행 완화 — [StockPilot](https://github.com/boclair98/stockpilot) · [날씨한편](https://github.com/boclair98/Weather) |
| **Realtime** | WebSocket 상태 팬아웃, 서버 권위 게임 상태, WebRTC P2P 음성 — [검은 자정](https://github.com/boclair98/mafia-game) |
| **Operations** | CI 품질 게이트, liveness/readiness, 운영 모니터, 암호화 백업, 발행 중단·정정 runbook — [아침결](https://github.com/boclair98/achim-gyeol) · [StockPilot](https://github.com/boclair98/stockpilot) |

<br />

## ✍️ Tech Blog & Problem Solving

### Tech Blog · 95 notes

Java, Spring Boot, 웹 개발, 인프라와 알고리즘을 공부하고 직접 해결한 과정을 기록합니다.

`Spring Boot 15` · `Java 8` · `Algorithm 8` · `Problem Solving 45` · `DX · Infra 12`<br />
**[블로그 전체 글 보기 →](https://boclair98.tistory.com/)**

<br />

### Practice Repositories

풀이와 구현 기록도 코드로 축적합니다.<br />
**[Codetree TIL →](https://github.com/boclair98/codetree-TILs)** · **[전체 저장소 →](https://github.com/boclair98?tab=repositories)**

<br />

<div align="center">

**제품을 만들고 · 배포하고 · 관찰하고 · 다시 개선합니다.**

<sub>Build · Deploy · Operate</sub>

</div>
