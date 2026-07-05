<div align="center">

# 이희승 | Backend Developer

사용자의 흐름을 이해하고, 서비스가 안정적으로 움직이도록 설계하는 백엔드 개발자입니다.

[![GitHub](https://img.shields.io/badge/GitHub-boclair98-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/boclair98)
[![Blog](https://img.shields.io/badge/Blog-boclair98.tistory.com-FF5A4A?style=flat-square&logo=tistory&logoColor=white)](https://boclair98.tistory.com/)
[![Email](https://img.shields.io/badge/Email-boclair98@naver.com-03C75A?style=flat-square&logo=naver&logoColor=white)](mailto:boclair98@naver.com)
[![Solved.ac](https://img.shields.io/badge/Solved.ac-boclair98-0076C0?style=flat-square)](https://solved.ac/profile/boclair98)
[![Portfolio](https://img.shields.io/badge/Portfolio-PDF-0A66C2?style=flat-square&logo=adobeacrobatreader&logoColor=white)](portfolio/LeeHeeSeung_Portfolio.pdf)

</div>

---

## About

Java와 Spring Boot를 중심으로 REST API, 인증/인가, 데이터 조회 흐름, 비즈니스 로직을 구현합니다.

단순히 기능을 완성하는 것보다 사용자가 어떤 맥락에서 서비스를 쓰는지, 데이터가 어떤 상태로 흘러야 안전한지, 이후 변경이 들어왔을 때 구조가 버틸 수 있는지를 함께 봅니다. Controller, Service, Repository의 책임을 나누고 트랜잭션 경계와 데이터 일관성을 고려하는 개발을 지향합니다.

최근에는 약속 장소 추천, 날씨 기반 메일 발송, 면접 시뮬레이션처럼 실제 사용자 흐름이 있는 서비스를 만들며 백엔드 설계와 제품 경험 사이의 연결을 연습하고 있습니다.

## What I Care About

- 사용자가 막히지 않는 자연스러운 서비스 흐름
- 도메인 규칙이 코드 안에서 분명하게 드러나는 구조
- JPA, Querydsl, SQL을 활용한 안정적인 데이터 조회와 변경
- 인증, 권한, 상태 관리처럼 서비스 신뢰도에 직접 연결되는 영역
- 작게 만들고, 원인을 추적하고, 개선 과정을 기록하는 습관

## Tech Stack

**Backend**  
Java 17, Spring Boot, Spring MVC, Spring Data JPA, Querydsl, Spring Security, JWT, MyBatis

**Database**  
MySQL, PostgreSQL, Oracle, SQL

**Data / AI**  
Python, Pandas, Numpy, Scikit-learn, Streamlit

**Web / Tools**  
Thymeleaf, JavaScript, HTML5, Git, GitHub, IntelliJ IDEA

## Product Projects

### [MeetPlace](https://github.com/boclair98/MeetPlace)

여러 명이 만날 때 출발지와 원하는 장소 카테고리를 기준으로 실제 약속 장소를 추천하는 Spring Boot 웹 서비스입니다.

- 참가자 출발 좌표를 기반으로 중간 지점 계산
- Kakao Local API와 Google Places API를 활용한 장소 정보 보강
- 평균 이동거리, 거리 편차, 리뷰 신뢰도를 반영한 추천 점수 설계
- 결과 탭, 거리 비교, 공유 문구 생성 등 사용 흐름 중심의 UI 구현

### [Weather](https://github.com/boclair98/Weather)

지역별 날씨 정보를 기반으로 구독자에게 맞춤형 메일을 발송하는 서비스입니다.

- 날씨 API 연동 및 지역 기반 구독자 관리
- JavaMailSender 기반 메일 발송 기능 구현
- `@Async`를 활용한 비동기 발송 구조 적용
- 구독자 증가를 고려한 Queue, Batch 개선 방향 설계

### [Question](https://github.com/boclair98/Question)

직무 맞춤형 면접 질문과 응답 타이머를 제공하는 Spring Boot 기반 면접 시뮬레이션 서비스입니다.

- 직무별 질문 제공 및 40초 응답 타이머 구현
- Spring Security, JWT 기반 인증 구조 설계
- Querydsl 기반 동적 조회와 REST API 구현
- 면접 경험 공유를 위한 커뮤니티형 데이터 구조 설계

### [haesudamsuhwa_project_streamlit](https://github.com/boclair98/haesudamsuhwa_project_streamlit)

해수 담수화 공정 데이터를 분석하고 전력 사용량을 예측하는 Streamlit 대시보드입니다.

- Pandas, Numpy 기반 데이터 전처리 및 분석
- 선형회귀 기반 전력 수요 예측
- 공정 데이터 모니터링 및 시각화 대시보드 구현

## Experience & Growth

**알앤비소프트 IT 서비스 본부 | SI 개발 및 빌링 개발**  
2024.04 - 2024.07

- Oracle, Java 기반 후불 요금제 개발
- Oracle 기반 할인 적용 로직 개발
- 데이터 중심 비즈니스 로직의 정확성과 예외 흐름 경험

**KT AIVLE SCHOOL AI / DX 엔지니어 과정**  
2023.01 - 2023.07

- 840시간 집중 교육 수료
- AI 모델링, 데이터 분석, DX 서비스 아키텍처 학습
- Practical 빅 프로젝트 수상

## Certificates

- 정보처리기사, 2024.09
- SQLD, 2024.04
- ADsP, 2023.03
- 리눅스마스터 2급, 2026.07
- TOEIC Speaking 110 / Intermediate Mid 1, 2024.09

## Algorithm & Stats

<div align="center">

[![Solved.ac Profile](http://mazassumnida.wtf/api/v2/generate_badge?boj=boclair98)](https://solved.ac/profile/boclair98)

![GitHub Stats](https://github-readme-stats.vercel.app/api?username=boclair98&show_icons=true&theme=default&hide_border=true)

![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=boclair98&layout=compact&hide_border=true)

</div>
