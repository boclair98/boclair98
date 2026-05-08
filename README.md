# 이희승 (Heeseung Lee)

안녕하세요. Java와 Spring Boot를 중심으로 사용자 흐름과 비즈니스 로직을 함께 고민하는 백엔드 개발자 이희승입니다.

서비스가 실제로 사용되는 과정을 중요하게 생각합니다. 단순히 기능을 구현하는 것에서 끝내지 않고, 사용자가 어떤 입력을 하고 어떤 결과를 받아야 자연스러운지, 백엔드 구조가 그 흐름을 안정적으로 받쳐줄 수 있는지를 함께 고민합니다.

최근에는 Spring Boot, Thymeleaf, JavaScript를 활용해 실제 장소 검색 API와 리뷰 데이터를 연동하는 약속 장소 추천 서비스 `MeetPlace`를 개발하고 있습니다.

---

## Links

| Type | Link |
| --- | --- |
| GitHub | [github.com/boclair98](https://github.com/boclair98) |
| Blog | [boclair98.tistory.com](https://boclair98.tistory.com/) |
| Baekjoon | [solved.ac/profile/boclair98](https://solved.ac/profile/boclair98) |
| Email | boclair98@naver.com |

## Tech Stack

### Backend

![Java](https://img.shields.io/badge/Java-17-007396?style=flat-square&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.x-6DB33F?style=flat-square&logo=springboot&logoColor=white)
![Spring MVC](https://img.shields.io/badge/Spring%20MVC-6DB33F?style=flat-square&logo=spring&logoColor=white)
![Spring Data JPA](https://img.shields.io/badge/Spring%20Data%20JPA-59666C?style=flat-square)
![Querydsl](https://img.shields.io/badge/Querydsl-0769AD?style=flat-square)
![Spring Security](https://img.shields.io/badge/Spring%20Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=flat-square&logo=jsonwebtokens&logoColor=white)
![MyBatis](https://img.shields.io/badge/MyBatis-2F2F2F?style=flat-square)

### Database

![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
![Oracle](https://img.shields.io/badge/Oracle-F80000?style=flat-square&logo=oracle&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-336791?style=flat-square)

### Data / AI

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![Numpy](https://img.shields.io/badge/Numpy-013243?style=flat-square&logo=numpy&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white)
![Scikit--learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)

### Web / Tools

![Thymeleaf](https://img.shields.io/badge/Thymeleaf-005F0F?style=flat-square&logo=thymeleaf&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white)
![IntelliJ IDEA](https://img.shields.io/badge/IntelliJ%20IDEA-000000?style=flat-square&logo=intellijidea&logoColor=white)
![Eclipse IDE](https://img.shields.io/badge/Eclipse%20IDE-2C2255?style=flat-square&logo=eclipseide&logoColor=white)

## Focus

- Java 17, Spring Boot 기반 백엔드 서비스 개발
- Controller, Service, Repository 책임 분리를 고려한 계층형 구조 설계
- JPA 영속성 컨텍스트와 트랜잭션 경계를 고려한 비즈니스 로직 구현
- REST API, 서버 사이드 렌더링, 외부 API 연동
- SQL 기반 데이터 조회, 페이징, 검색 조건, 정렬 처리
- GitHub와 Tistory를 통한 학습 과정과 문제 해결 기록

## Projects

### [MeetPlace](https://github.com/boclair98/MeetPlace)

여러 명이 만날 때 출발지와 원하는 장소 카테고리를 기준으로 실제 약속 장소를 추천하는 Spring Boot 웹 서비스입니다.

- 참가자들의 출발 좌표를 기반으로 중간 좌표 계산
- Kakao Local API로 중간 좌표 주변의 실제 장소 검색
- Google Places API로 평점, 리뷰 수, 대표 리뷰 문구 보강
- 평균 이동거리, 거리 편차, 리뷰 신뢰도를 반영한 추천 점수 계산
- Thymeleaf와 JavaScript 기반 결과 탭, 거리 비교, 공유 문구 생성 UI 구현

### [Question](https://github.com/boclair98/Question)

Spring Boot 기반 직무 맞춤형 면접 시뮬레이션 서비스입니다.

- 직무별 맞춤형 면접 질문 제공 및 40초 응답 타이머 구현
- Spring Security, JWT 기반 인증 체계와 사용자별 직무 정보 저장 기능 구현
- Querydsl 기반 동적 쿼리 최적화와 RESTful API 설계
- 사용자 간 면접 경험 공유를 위한 커뮤니티형 데이터 구조 설계

### Java & Spring Boot E-Commerce Platform

Java 17, Spring Boot, JPA 기반 이커머스 도메인 백엔드 프로젝트입니다.

- MySQL 연동 도메인 모델 설계로 데이터 일관성과 확장성 확보
- Spring Security, JWT 기반 인증/인가 및 등급별 권한 관리 구현
- 페이징 처리 기반 상품 목록 조회 성능 개선
- WebSocket 기반 1:1 실시간 채팅, 계층형 게시판, 문의 시스템 개발

### [haesudamsuhwa_project_streamlit](https://github.com/boclair98/haesudamsuhwa_project_streamlit)

해수 담수화 공정 데이터를 분석하고 전력 사용량을 예측하는 Streamlit 대시보드입니다.

- Python, Numpy, Pandas, Streamlit, Linear Regression 활용
- 수질 기반 실시간 전력 수요 예측 시스템 개발
- 공정 데이터 모니터링 및 시각화 대시보드 구축

## Experience

- [2024.04-2024.07] 알앤비소프트 IT 서비스 본부, SI 개발 및 빌링 개발
  - Oracle, Java 기반 후불 요금제 개발
  - Oracle 기반 할인 적용 로직 개발

## Education

- [2017.03-2023.02] 한신대학교 정보통신학부 졸업
- [2023.01-2023.07] KT AIVLE SCHOOL AI 및 DX 엔지니어 과정 수료
- [2023.03-2023.04] 자바오라클교육센터 Oracle Database 교육
- [2022.03-2023.06] 자바오라클교육센터 WPF 애플리케이션 개발 역량 과정

## Certificates & Awards

- 정보처리기사, 한국산업인력공단 (2024.09)
- SQL개발자(SQLD), 한국데이터베이스진흥센터 (2024.04)
- 데이터분석준전문가(ADsP), 한국데이터베이스진흥원 (2023.03)
- 리눅스마스터 2급 필기합격, 한국정보통신인력개발센터 (2025.02)
- KT AIVLE SCHOOL Practical 빅 프로젝트 수상 (2023.07)
- TOEIC Speaking Test 110 / Intermediate Mid 1 (2024.09)

## Algorithm

[![Solved.ac Profile](http://mazassumnida.wtf/api/v2/generate_badge?boj=boclair98)](https://solved.ac/profile/boclair98)

## GitHub Stats

![GitHub Stats](https://github-readme-stats.vercel.app/api?username=boclair98&show_icons=true&theme=default&hide_border=true)

![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=boclair98&layout=compact&hide_border=true)
