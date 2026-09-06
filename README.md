<div align="center">

<code>BOCLAIR98 / BACKEND & SYSTEMS ENGINEERING</code>

<h1>코드에서 서비스까지.</h1>

<p><strong>데이터 정합성, 동시성 제어, 실패 복구를 다루는 백엔드 개발.</strong><br />
직접 배포한 서비스와 구현·검증 과정을 기록합니다.</p>

<p>
  <a href="#service-directory"><b>Services</b></a> &nbsp; / &nbsp;
  <a href="#engineering"><b>Engineering</b></a> &nbsp; / &nbsp;
  <a href="#tech-stack"><b>Stack</b></a> &nbsp; / &nbsp;
  <a href="#operations"><b>Runbooks</b></a> &nbsp; / &nbsp;
  <a href="#writing"><b>Writing</b></a>
</p>

</div>

---

<h2 id="service-directory">01 / Services · 직접 만들고 운영하는 서비스</h2>

<a id="flagship-products"></a>

<table align="center">
<tr>
<td width="440" valign="top">
<sub>FLAGSHIP / FINTECH</sub>
<h3>StockPilot</h3>
<p><strong>실제 한·미 주식 시세 기반 모의투자</strong><br />
가상주문·포트폴리오·투자일지·리그를 연결한 투자 학습 서비스.</p>
<p><code>Python · FastAPI</code><br /><code>PostgreSQL · Redis · Next.js</code></p>
<ul>
<li><strong>Integrity</strong> — 요청 키·주문 지문·DB 유일 제약으로 중복 체결 방어</li>
<li><strong>Coordination</strong> — 공유 캐시·single-flight·lease로 외부 API 호출과 중복 작업 제어</li>
<li><strong>Audit</strong> — 추가 전용 감사 이벤트와 가상 원장 대사로 잔액 검증</li>
</ul>
<p><a href="https://stockpilot.coders.kr"><strong>모의투자 열기 ↗</strong></a> &nbsp;·&nbsp; <a href="https://github.com/boclair98/stockpilot">Source</a></p>
<p><sub>100% 가상투자. 실제 증권계좌 주문은 차단합니다.</sub></p>
</td>
<td width="440" valign="top">
<sub>FLAGSHIP / NEWS PIPELINE</sub>
<h3>아침결</h3>
<p><strong>매일 오전 07:30 뉴스 브리핑</strong><br />
핵심 뉴스의 결론·배경·출처를 정리하고 PWA 알림으로 전달하는 서비스.</p>
<p><code>Kotlin · Spring Boot</code><br /><code>PostgreSQL · Flyway · Next.js</code></p>
<ul>
<li><strong>Ingestion</strong> — 네이버 검색·GDELT·공식기관 RSS 수집과 출처 관리</li>
<li><strong>Quality Gate</strong> — 수집·검증·발행 분리, 기준 미달 콘텐츠 발행 제외</li>
<li><strong>Verification</strong> — Playwright E2E·부하 스모크·백엔드 검증을 배포 기준에 포함</li>
</ul>
<p><a href="https://morningnews.coders.kr"><strong>오늘의 브리핑 ↗</strong></a> &nbsp;·&nbsp; <a href="https://github.com/boclair98/achim-gyeol">Source</a></p>
<p><sub>관심 분야·분량 설정, 보관함과 신뢰센터를 제공합니다.</sub></p>
</td>
</tr>
</table>

<br />

### More Services

| 서비스 | 한 줄 소개 | 링크 |
| :--- | :--- | :--- |
| **MORROW** | 매칭·실시간 대화·약속으로 이어지는 소셜 디스커버리 · 공개 포트폴리오 | [서비스 ↗](https://morrow.coders.kr) · [Source](https://github.com/boclair98/morrow) |
| **날씨한편** | 위치·활동별 날씨와 대기질을 확인하고 지정 시간에 이메일로 받는 브리핑 | [서비스 ↗](https://weather.coders.kr) · [Source](https://github.com/boclair98/Weather) |
| **살도 · Saldobook** | 수입·지출·예산을 기록하고 오늘의 안심 사용액과 월말 예상 지출을 확인하는 가계부 | [서비스 ↗](https://saldobook.coders.kr) · [Source](https://github.com/boclair98/saldobook) |
| **검은 자정** | 단서·음성 토론·투표로 추리하는 실시간 게임. 혼자서도 AI와 플레이 | [게임 ↗](https://black-midnight.coders.kr) · [Source](https://github.com/boclair98/mafia-game) |
| **HYUNDAI LIFE PASS** | 충전소·서비스 거점 탐색과 차량 관리 흐름을 연결한 비공식 커넥티드카 파일럿 | [파일럿 ↗](https://hyundai-life-pass.coders.kr) · [Source](https://github.com/boclair98/hyundai-life-pass) |
| **YieldScope P&T** | LOT 판정·원인 분석·개선 조치·교대 인계를 체험하는 반도체 품질 워크벤치 · 합성 데이터 데모 | [데모 ↗](https://yieldscope-pnt.coders.kr) · [Source](https://github.com/boclair98/yieldscope-pnt) |
| **Trading Stock System** | 주문 매칭·체결·재생 복구를 검증하는 엔지니어링 콘솔 · 실주문 차단 | [콘솔 ↗](https://tradingstocksysyem.coders.kr) · [Source](https://github.com/boclair98/TradingStockSysyem) |

<details>
<summary>구현 범위와 운영 제약</summary>

- **MORROW** — 성인 확인, 운영 SLA, 백업·복구 알림과 복수 인스턴스 WebSocket fan-out은 정식 출시 전 보강 범위입니다.
- **살도** — 공개 운영본은 수동 입력이 기본입니다. 계좌 연동과 토큰 암호화는 승인 환경용 선택적 구조입니다.
- **검은 자정** — 방 상태는 인스턴스 메모리에 저장합니다. 재접속 복구는 동일 인스턴스 범위이며 서버 재시작 시 진행 중인 방이 종료될 수 있습니다.
- **HYUNDAI LIFE PASS** — 현대자동차 공식 서비스가 아닌 포트폴리오입니다. OTA Canary는 읽기 전용이며 실제 예약·결제·진단·OTA 기능을 제공한다고 주장하지 않습니다.
- **YieldScope P&T** — 실제 회사 내부 자료가 아닌 100% 합성 데이터를 사용합니다.
- **Trading Stock System** — 독립 Java 코어는 웹 실주문 경로와 연결되지 않았습니다. 브로커 어댑터는 고정 응답 계약 테스트 수준이며 운영 승인과 sandbox/production E2E는 별도 검증 범위입니다.

</details>

---

<h2 id="engineering">02 / Engineering · 문제와 구현</h2>

다른 프로젝트에서 다룬 설계 사례입니다. 위 서비스 표의 **Source**에서 각 구현을 탐색할 수 있습니다.

| 주제 · 프로젝트 | 문제 | 구현 접근 |
| :--- | :--- | :--- |
| **Concurrency** · MORROW | 동시 요청으로 인한 중복 매치·메시지 | 비관적 잠금·사용자 쌍 유일 제약, DB 저장 후 발행, `client_id` 멱등 처리 |
| **Resilience** · 날씨한편 | 외부 API 지연·실패의 전파 | timeout·retry·circuit breaker·fallback, bounded executor와 Redis/Caffeine 캐시 |
| **Isolation** · 살도 | 사용자 데이터 혼재·거래 중복 | 사용자별 데이터 격리, 거래 지문 중복 방지, 계좌 단위 부분 실패 처리 |
| **Realtime** · 검은 자정 | 참가자별 공개 정보와 실시간 상태의 일관성 | 서버 권위 상태 머신, 비밀 정보 필터링, WebSocket 동기화·WebRTC 음성 |
| **Trust Boundary** · LIFE PASS | 공급자별 데이터 차이와 동의 철회 | 공급자 어댑터 분리, 출처·상태 표시, 철회 콜백에서 토큰·실차 데이터 삭제 |
| **Traceability** · YieldScope | 품질 판정의 근거와 후속 조치 추적 | LOT HOLD·RELEASE·FA에 사유·담당자·시각 기록, RCA·CAPA 재검증 흐름 모델링 |
| **Determinism** · Trading System | 장애 후 처리 결과의 재현성 | Java 코어, CRC32C WAL, SHA-256 상태 다이제스트 기반 재생 검증 |

---

<h2 id="tech-stack">03 / Technical Stack</h2>

### Core Backend & API

<p>
  <img src="https://img.shields.io/badge/Java-17_%C2%B7_21-0B1220?style=flat-square&logo=openjdk&logoColor=ED8B00" alt="Java" />
  <img src="https://img.shields.io/badge/Kotlin-2.x-0B1220?style=flat-square&logo=kotlin&logoColor=7F52FF" alt="Kotlin" />
  <img src="https://img.shields.io/badge/Spring_Boot-3_%C2%B7_4-0B1220?style=flat-square&logo=springboot&logoColor=6DB33F" alt="Spring Boot" />
  <img src="https://img.shields.io/badge/Spring_Security-0B1220?style=flat-square&logo=springsecurity&logoColor=6DB33F" alt="Spring Security" />
  <img src="https://img.shields.io/badge/Python-3.12-0B1220?style=flat-square&logo=python&logoColor=3776AB" alt="Python" />
  <img src="https://img.shields.io/badge/FastAPI-0B1220?style=flat-square&logo=fastapi&logoColor=00C7B7" alt="FastAPI" />
  <img src="https://img.shields.io/badge/Gradle-0B1220?style=flat-square&logo=gradle&logoColor=02303A" alt="Gradle" />
</p>

### Data · Consistency · Cache

<p>
  <img src="https://img.shields.io/badge/PostgreSQL-0B1220?style=flat-square&logo=postgresql&logoColor=4169E1" alt="PostgreSQL" />
  <img src="https://img.shields.io/badge/Redis-0B1220?style=flat-square&logo=redis&logoColor=FF4438" alt="Redis" />
  <img src="https://img.shields.io/badge/JPA_%C2%B7_Hibernate-0B1220?style=flat-square&logo=hibernate&logoColor=59666C" alt="JPA Hibernate" />
  <img src="https://img.shields.io/badge/SQLAlchemy-0B1220?style=flat-square&logo=sqlalchemy&logoColor=D71F00" alt="SQLAlchemy" />
  <img src="https://img.shields.io/badge/Flyway-0B1220?style=flat-square&logo=flyway&logoColor=CC0200" alt="Flyway" />
  <img src="https://img.shields.io/badge/Alembic-0B1220?style=flat-square&logo=python&logoColor=3776AB" alt="Alembic" />
</p>

`Caffeine` · `Drizzle` · `S3-compatible Storage`

### Delivery · Operations · Observability

<p>
  <img src="https://img.shields.io/badge/Docker-0B1220?style=flat-square&logo=docker&logoColor=2496ED" alt="Docker" />
  <img src="https://img.shields.io/badge/nginx-0B1220?style=flat-square&logo=nginx&logoColor=009639" alt="nginx" />
  <img src="https://img.shields.io/badge/GitHub_Actions-0B1220?style=flat-square&logo=githubactions&logoColor=2088FF" alt="GitHub Actions" />
  <img src="https://img.shields.io/badge/Playwright-0B1220?style=flat-square&logo=playwright&logoColor=2EAD33" alt="Playwright" />
  <img src="https://img.shields.io/badge/Prometheus-0B1220?style=flat-square&logo=prometheus&logoColor=E6522C" alt="Prometheus" />
  <img src="https://img.shields.io/badge/Spring_Actuator-0B1220?style=flat-square&logo=springboot&logoColor=6DB33F" alt="Spring Actuator" />
  <img src="https://img.shields.io/badge/JUnit-0B1220?style=flat-square&logo=junit5&logoColor=25A162" alt="JUnit" />
</p>

`Docker Compose` · `ShedLock` · `Ruff` · `pytest` · `SBOM`

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

`Vite` · `Thymeleaf`

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

<h2 id="operations">04 / Runbooks · 배포 이후의 기준</h2>

운영 판단과 복구 절차는 문서로 남깁니다. 아래 링크에서 점검 항목과 대응 순서를 확인할 수 있습니다.

| 문서 | 확인할 내용 |
| :--- | :--- |
| [StockPilot · 주문 통제 기준](https://github.com/boclair98/stockpilot/blob/main/docs/BROKERAGE_READINESS.md) | 오래된 시세 차단, 주문 한도, kill switch와 도입 전 검증 기준 |
| [날씨한편 · 운영 런북](https://github.com/boclair98/Weather/blob/main/docs/OPERATIONS.md) | liveness/readiness, 외부 API 지표, 마지막 정상자료 사용, 배포·롤백 |
| [아침결 · 사고 대응](https://github.com/boclair98/achim-gyeol/blob/main/docs/INCIDENT_RESPONSE.md) | 발행 중단, 정정 이력과 실패한 발송 재시도 |
| [아침결 · 백업과 복구](https://github.com/boclair98/achim-gyeol/blob/main/docs/BACKUP_AND_RESTORE.md) | 암호화 백업, 격리된 DB에서의 복구와 검증 절차 |

---

<h2 id="writing">05 / Engineering Notes</h2>

구현에서 만난 개념과 주의점을 정리한 글입니다.

- **[트랜잭션 AOP 주의 사항 ↗](https://boclair98.tistory.com/132)** — `@Transactional` proxy와 self-invocation 함정을 테스트로 확인
- **[커넥션 풀 ↗](https://boclair98.tistory.com/128)** — 연결 비용과 서버·DB 자원에 맞춘 pool sizing 관점
- **[HTTP 메서드에서 멱등성이란 무엇일까요? ↗](https://boclair98.tistory.com/113)** — 재시도와 중복 요청을 안전하게 다루는 기준
- **[HTTP 헤더 캐시와 조건부 요청 ↗](https://boclair98.tistory.com/126)** — validation header와 `304 Not Modified`를 활용한 전송 최적화
- **[JPA - 영속성 컨텍스트 ↗](https://boclair98.tistory.com/135)** — 1차 캐시, 동일성, 쓰기 지연과 dirty checking 정리

**[기술 블로그 전체 글 보기](https://boclair98.tistory.com/)** · **[Codetree TIL](https://github.com/boclair98/codetree-TILs)** · **[Algorithm](https://github.com/boclair98/Algorithm)** · **[전체 저장소](https://github.com/boclair98?tab=repositories)**


---

<h2 id="selected-projects">06 / More Projects</h2>

- **[MeetPlace](https://github.com/boclair98/MeetPlace)** — 2~8명의 출발지에서 평균·최대 이동거리와 편차를 계산하고 Kakao Local·Google Places의 실제 장소를 점수화하는 약속 장소 추천 서비스
- **[Question](https://github.com/boclair98/Question)** — 직무별 랜덤 질문, 질문 확인·답변 타이머, 세션 인증과 질문 기록을 구현한 면접 연습 서비스
- **[RO Desalination Dashboard](https://github.com/boclair98/haesudamsuhwa_project_streamlit)** — 수질·공정 데이터로 인입압력과 전력 사용량을 예측하고 공정 상태를 시각화한 데이터 프로젝트

---

<div align="center">

<code>BUILD → VERIFY → DEPLOY → OBSERVE → IMPROVE</code>

</div>
