<div align="center">

<img src="./assets/profile-header.png" width="100%" alt="서비스 운영 포트폴리오 헤더" />

# Build · Deploy · Operate

**실제 사용 흐름을 만들고, 배포 후에도 안정적으로 운영하는 서비스 포트폴리오**입니다.

<a href="https://stockpilot.coders.kr"><img src="https://img.shields.io/badge/StockPilot-운영_중-2563EB?style=for-the-badge&logo=googlechrome&logoColor=white" alt="StockPilot 운영 사이트" /></a>
<a href="https://saldobook.coders.kr"><img src="https://img.shields.io/badge/Saldobook-운영_중-0F766E?style=for-the-badge&logo=googlechrome&logoColor=white" alt="Saldobook 운영 사이트" /></a>
<a href="https://weather.coders.kr"><img src="https://img.shields.io/badge/날씨한편-운영_중-0284C7?style=for-the-badge&logo=googlechrome&logoColor=white" alt="날씨한편 운영 사이트" /></a>

</div>

---

## 운영 서비스

| 서비스 | 한 줄 소개 | 바로가기 |
| --- | --- | --- |
| **StockPilot** | 실제 시세를 바탕으로 시장 확인부터 가상 주문·리그까지 경험하는 주식 투자 연습 서비스 | [운영 사이트](https://stockpilot.coders.kr) · [GitHub](https://github.com/boclair98/stockpilot) |
| **살도 (Saldobook)** | Google·카카오 로그인, 예산·소비 분석, 여러 계좌 연결을 지원하는 개인 가계부 | [운영 사이트](https://saldobook.coders.kr) · [GitHub](https://github.com/boclair98/saldobook) |
| **날씨한편** | 지역별 예보와 동적 옷차림 추천을 메일로 보내는 날씨 구독 서비스 | [운영 사이트](https://weather.coders.kr) · [GitHub](https://github.com/boclair98/Weather) |
| **Question** | 직무·면접 유형별 랜덤 질문과 40초 타이머를 제공하는 면접 시뮬레이터 | [GitHub](https://github.com/boclair98/Question) |
| **RO 해수담수화 대시보드** | 수질·공정 데이터를 바탕으로 압력과 전력 사용량을 예측하는 운영 대시보드 | [GitHub](https://github.com/boclair98/haesudamsuhwa_project_streamlit) |

> 운영 URL이 있는 서비스는 실제 사용 흐름과 배포 환경을 기준으로 계속 개선하고 있습니다.

---

## 01. StockPilot — 가상 주식 투자 연습

<a href="https://stockpilot.coders.kr">
  <img src="https://raw.githubusercontent.com/boclair98/stockpilot/main/docs/images/stockpilot-kospi-live.png" width="720" alt="StockPilot 운영 화면" />
</a>

한국 KRX·NXT 통합 시세와 미국 주식 시세를 확인하고, 가상 자산으로 분석·주문·성과 확인을 연습할 수 있는 서비스입니다.

- KIS Open API 기반 한국·미국 시세, OpenDART 기업·공시 데이터 연동
- 시장가·지정가·손절·조건부 지정가 가상 주문과 예수금·보유 수량 검증
- 포트폴리오, 투자 리포트, 목표가 알림, 시세 리플레이, 수익률 리그
- 실제 증권계좌 주문 없이 서비스 내부 가상 원장만 사용

**[StockPilot 시작하기 →](https://stockpilot.coders.kr)**

---

## 02. 살도 (Saldobook) — 내 돈의 흐름을 한눈에

<a href="https://saldobook.coders.kr">
  <img src="https://raw.githubusercontent.com/boclair98/saldobook/main/docs/images/dashboard.png" width="720" alt="살도 개인 대시보드" />
</a>

월별 수입·지출과 예산을 관리하고, 소비 흐름을 분석하는 사용자별 가계부입니다.

- Google·카카오 OAuth 로그인과 사용자별 데이터 분리
- 수입·지출 기록, 검색·필터, CSV 내보내기, 카테고리 소비 분석
- 월 예산 사용률과 최근 6개월 수입·지출 추이
- 금융결제원 오픈뱅킹 **테스트베드** 기반 다계좌 연결·동기화
- 접근 토큰 AES-256-GCM 암호화 및 외부 거래 중복 방지

**[살도 시작하기 →](https://saldobook.coders.kr)**

---

## 03. 날씨한편 — 날씨를 메일로 받아보는 일상 서비스

<a href="https://weather.coders.kr">
  <img src="https://raw.githubusercontent.com/boclair98/Weather/main/docs/images/weather-subscription-form.svg" width="720" alt="날씨한편 구독 화면" />
</a>

선택한 지역의 예보와 외출 조언, 날씨에 맞는 스타일링 추천을 아침·점심·저녁 메일로 제공합니다.

- 카카오 장소·주소 검색, 브라우저 현재 위치, 기상청 예보 연동
- 최대 10개 이메일 동시 구독 및 이메일 기반 구독 정보 갱신
- 날씨·기온·강수·바람·대기질·연령대 조합의 동적 스타일링 추천
- Gmail·네이버 메일에 맞춘 반응형 HTML 메일과 안전한 수신 거부
- PostgreSQL·Redis, 분산 스케줄 락, health probe, graceful shutdown 적용

**[날씨한편 시작하기 →](https://weather.coders.kr)**

---

## 04. Question — 직무 맞춤 면접 시뮬레이션

<img src="https://raw.githubusercontent.com/boclair98/Question/main/docs/images/question.png" width="720" alt="Question 면접 질문 화면" />

개발자·디자이너·마케팅·영업·반도체 엔지니어 직무의 인성/직무 면접을 제한 시간 안에 연습하는 서비스입니다.

- 직무와 면접 유형에 따른 랜덤 질문 제공
- 질문 확인 10초 + 답변 30초의 40초 타이머
- 세션 기반 로그인, 질문 기록, 로그인 사용자의 질문 추가
- Spring Boot·JPA·Thymeleaf 기반 구현, H2 demo 프로필 제공

[프로젝트 자세히 보기 →](https://github.com/boclair98/Question)

---

## 05. RO 해수담수화 공정 예측 대시보드

<img src="https://raw.githubusercontent.com/boclair98/haesudamsuhwa_project_streamlit/main/docs/images/dashboard.png" width="720" alt="RO 해수담수화 공정 대시보드" />

수질과 RO 공정 데이터를 연결해 인입압력·전력 사용량을 예측하고, 공정 상태를 직관적으로 보여주는 데이터 대시보드입니다.

- 수온·pH·탁도·COD 등 수질 데이터 분석
- 선형회귀·랜덤포레스트 기반 인입압력 및 전력량 예측
- 정상·주의·이상 상태와 주요 지표 변화 시각화
- Streamlit, Pandas, NumPy, scikit-learn, Plotly 활용

[프로젝트 자세히 보기 →](https://github.com/boclair98/haesudamsuhwa_project_streamlit)

---

## Tech Stack

| 영역 | 사용 기술 |
| --- | --- |
| **Backend** | Java 17/21, Spring Boot, Spring MVC, Spring Data JPA, Spring Security, JWT, Querydsl, Gradle |
| **Frontend** | TypeScript, JavaScript, Next.js, React, Thymeleaf, HTML, CSS |
| **Data** | PostgreSQL, MySQL, H2, Redis, Flyway, JPA, SQL |
| **External & Auth** | OAuth 2.0, Kakao Local API, KIS Open API, OpenDART, 기상청 API, 금융결제원 오픈뱅킹 |
| **Infra & Operation** | Docker, GitHub Actions, health check, graceful shutdown, cache, distributed scheduler lock |
| **Data/AI** | Python, Pandas, NumPy, scikit-learn, Streamlit, Plotly |

<p>
  <img src="https://img.shields.io/badge/Java-22272E?style=flat-square&logo=openjdk&logoColor=ED8B00" alt="Java" />
  <img src="https://img.shields.io/badge/Spring_Boot-22272E?style=flat-square&logo=springboot&logoColor=6DB33F" alt="Spring Boot" />
  <img src="https://img.shields.io/badge/Next.js-22272E?style=flat-square&logo=nextdotjs&logoColor=white" alt="Next.js" />
  <img src="https://img.shields.io/badge/PostgreSQL-22272E?style=flat-square&logo=postgresql&logoColor=4169E1" alt="PostgreSQL" />
  <img src="https://img.shields.io/badge/MySQL-22272E?style=flat-square&logo=mysql&logoColor=4479A1" alt="MySQL" />
  <img src="https://img.shields.io/badge/Redis-22272E?style=flat-square&logo=redis&logoColor=DC382D" alt="Redis" />
  <img src="https://img.shields.io/badge/Docker-22272E?style=flat-square&logo=docker&logoColor=2496ED" alt="Docker" />
  <img src="https://img.shields.io/badge/Python-22272E?style=flat-square&logo=python&logoColor=3776AB" alt="Python" />
</p>

---

<div align="center">

<sub>Build · Deploy · Operate</sub>

</div>
