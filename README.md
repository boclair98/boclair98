<div align="center">

<img src="./assets/profile-header.png" width="100%" alt="이희승 개발자 프로필 헤더" />

# 이희승 | 서비스가 실제로 쓰이도록 만드는 개발자

기능 구현에서 끝나지 않고, **배포·운영·오류 대응까지 연결되는 웹 서비스**를 만들고 있습니다.

<a href="https://stockpilot.coders.kr"><img src="https://img.shields.io/badge/StockPilot-운영_중-2563EB?style=for-the-badge&logo=googlechrome&logoColor=white" alt="StockPilot 운영 사이트" /></a>
<a href="https://saldobook.coders.kr"><img src="https://img.shields.io/badge/Saldobook-운영_중-0F766E?style=for-the-badge&logo=googlechrome&logoColor=white" alt="Saldobook 운영 사이트" /></a>
<a href="https://weather.coders.kr"><img src="https://img.shields.io/badge/날씨한편-운영_중-0284C7?style=for-the-badge&logo=googlechrome&logoColor=white" alt="날씨한편 운영 사이트" /></a>

[![Blog](https://img.shields.io/badge/Study_Blog-22272E?style=flat-square&logo=tistory&logoColor=white)](https://boclair98.tistory.com/)
[![Email](https://img.shields.io/badge/Email-22272E?style=flat-square&logo=naver&logoColor=03C75A)](mailto:boclair98@naver.com)
[![Solved.ac](https://img.shields.io/badge/Solved.ac-22272E?style=flat-square&logo=solveddotac&logoColor=17CE3A)](https://solved.ac/profile/boclair98)

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

## Engineering Focus

- 외부 API, 인증, 데이터, 비동기 작업을 연결한 실제 사용자 흐름 설계
- Java·Spring Boot 기반 REST API와 서비스 계층 중심의 비즈니스 로직 구현
- PostgreSQL·MySQL, JPA, Querydsl, Flyway를 활용한 데이터 신뢰성 관리
- Redis 캐시, 장애 시 대체 흐름, health check 등 운영 안정성 고려
- 사용자에게 이해되는 오류 메시지와 재현 가능한 문제 해결 기록

<p>
  <img src="https://img.shields.io/badge/Java-22272E?style=flat-square&logo=openjdk&logoColor=ED8B00" alt="Java" />
  <img src="https://img.shields.io/badge/Spring_Boot-22272E?style=flat-square&logo=springboot&logoColor=6DB33F" alt="Spring Boot" />
  <img src="https://img.shields.io/badge/PostgreSQL-22272E?style=flat-square&logo=postgresql&logoColor=4169E1" alt="PostgreSQL" />
  <img src="https://img.shields.io/badge/Redis-22272E?style=flat-square&logo=redis&logoColor=DC382D" alt="Redis" />
  <img src="https://img.shields.io/badge/Next.js-22272E?style=flat-square&logo=nextdotjs&logoColor=white" alt="Next.js" />
  <img src="https://img.shields.io/badge/Python-22272E?style=flat-square&logo=python&logoColor=3776AB" alt="Python" />
</p>

---

<div align="center">

<img height="165" src="https://github-readme-stats.vercel.app/api?username=boclair98&show_icons=true&hide_border=true&theme=github_dark_dimmed&rank_icon=github" alt="GitHub 통계" />
<img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=boclair98&layout=compact&hide_border=true&theme=github_dark_dimmed" alt="주요 언어" />

<sub>사용자가 실제로 쓰는 흐름을 만들고, 운영하며, 더 나은 경험으로 고도화합니다.</sub>

</div>
