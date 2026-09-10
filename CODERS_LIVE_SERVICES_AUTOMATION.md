# Coders.kr 운영 서비스 자동 고도화 실행 지침

버전: 2026-09-10
시간대: Asia/Seoul
문서 용도: GitHub 관리·Coders.kr 운영 서비스의 지속적인 기능 고도화, 장애 대응, UI 개선, 안전한 배포

## 1. 임무

지정된 GitHub 소유자의 저장소 중 사용자가 실제로 관리하고, Coders.kr에서 현재 운영 중인 서비스만 자동화 대상으로 편입한다.
자동화는 URL 감시로 끝나지 않는다. 누적된 운영 신호를 바탕으로 기능 수정, 유용한 신규 기능, UI·UX 개선, 접근성, 성능, 장애 예방, 테스트, 문서 개선을 실제로 수행한다.
검증된 변경은 canonical GitHub 저장소에 먼저 반영하고, 실제 GitHub fork를 동기화한 뒤 Coders.kr에 배포하고 운영 흐름을 확인한다.
대상 수는 고정하지 않는다. 과거 작업 목록, 공개 Coders 프로젝트 전체, 예전에 확인한 숫자를 현재 대상의 근거로 사용하지 않는다.

## 2. 실행 환경

다음 값은 자동화 실행 시 주입한다.

- SOURCE_OWNER: 사용자가 지정한 원본 GitHub 소유자
- FORK_OWNER: 배포용 GitHub 조직 또는 포크 소유자
- STATE_FILE: 운영 원장 경로
- CODERS_TOKEN: 승인된 비밀 저장소에서만 읽는 Coders 인증정보
- GITHUB_TOKEN: 승인된 GitHub 인증정보

토큰, 쿠키, 개인정보, 사용자 입력, 운영 데이터는 문서·로그·PR·보고서에 기록하지 않는다.
저장소의 실제 기본 브랜치를 API로 확인한다.
원본과 fork의 관계를 파일 복사로 추측하지 말고 GitHub의 parent 정보를 확인한다.

## 3. 운영 대상 편입 조건

아래 조건을 모두 확인한 서비스만 active 대상으로 편입한다.

1. SOURCE_OWNER의 GitHub 저장소이고 사용자의 커밋 또는 지속적인 관리 이력이 확인된다.
2. 저장소가 archived가 아니며 실제 소스, 빌드 또는 실행 구성이 있다.
3. README, 관련 Markdown, 저장소 homepage, 배포 설정 중 하나에 그 저장소 자신의 Coders.kr production URL이 연결되어 있다.
4. Coders.kr의 source repository, 배포 이력, 자동 배포 설정 중 하나가 해당 GitHub 저장소와 대응한다.
5. 현재 운영 URL에 실제 화면 또는 대표 진입 경로가 응답한다.
6. 서비스가 현재 운영 중이라는 근거가 있다.

관리 여부가 불명확한 저장소, 예제·과제·테스트 저장소, 단순 외부 링크, 미배포 프로젝트, 운영 종료 프로젝트, source 연결 없는 upload-only 프로젝트는 우선 제외한다.
일시적인 5xx, timeout, 배포 실패, API 장애는 운영 종료가 아니라 incident로 기록하고 복구 대상으로 유지한다.
조회 권한 부족, 플랫폼 오류, 네트워크 차단은 운영 종료로 해석하지 않는다.
이미 active로 확인된 서비스의 소스 연결이 사라지면 자동 제외하지 말고 source_missing blocker로 기록한다.
운영 대상의 개수는 매번 발견 결과로 계산한다.

## 4. 대상 발견 절차

매 배치 시작 시 GitHub 저장소 목록을 모든 페이지까지 읽는다.

- 각 저장소의 기본 브랜치와 최근 관리 커밋을 확인한다.
- README, README 변형, docs Markdown, 배포 workflow, coders 관련 설정을 찾는다.
- coders.kr URL을 수집하고 예제·외부 링크와 production URL을 구분한다.
- Coders.kr 배포 source와 GitHub 저장소를 대조한다.
- URL이 살아 있는지 확인하고 대표 진입 경로를 기록한다.
- 저장소와 URL의 연결 증거, 확인 커밋, 확인 시각을 원장에 남긴다.
- 후보와 active, incident, source_missing, excluded를 분리한다.
- 전체 조회에 실패하면 이전 정상 inventory를 유지하고 inventory_incomplete로 기록한다.
- 새 서비스는 모든 편입 조건을 통과한 뒤에만 자동화 대상에 추가한다.
- 과거 목록은 후보 참고 자료로만 사용하고 자동 편입하지 않는다.

## 5. 10분 경량 수집

10분마다 GitHub Actions가 AI 없이 아래 신호만 수집한다.

- 운영 URL HTTP 상태
- 제한된 재시도 후 최종 상태
- 응답 시간
- 알려진 health endpoint가 있을 때의 상태
- CI 실패 또는 배포 실패 여부
- 점검 시각과 서비스 식별자

10분 수집은 AI 기획, 코드 리뷰, UI 판단, 전체 기능 테스트가 아니다.
무제한 로그나 사용자 데이터를 수집하지 않는다.
실패 시 재시도하되 timeout과 요청량을 제한한다.
429 응답은 Retry-After를 존중한다.
수집 결과는 GitHub Actions summary와 artifact 또는 승인된 원장에 보관한다.
같은 원인의 반복 실패는 새 항목을 계속 만들지 말고 기존 finding을 갱신한다.
경량 수집은 Codex 토큰을 사용하지 않는 GitHub Actions 단계로 유지한다.

## 6. 하루 5회 AI 배치

모든 시간은 한국 시간이다.

- 00:00: 누적 장애, 야간 변경, 배포 안전성, 복구 작업
- 08:00: 아침 사용자 흐름, 뉴스·날씨·메일 데이터 최신성, 야간 결과
- 12:00: 기능 고도화, 신규 기능, 회귀 수정
- 18:00: UI·UX, 접근성, 모바일, 성능 개선
- 21:00: 남은 검증 완료 항목, 운영 안정성, README와 릴리스 정리

각 배치에서는 먼저 운영 원장, 마지막 검토 SHA, 새 커밋, 새 CI 결과, 실패한 배포를 읽는다.
변경·장애·사용자 영향이 큰 서비스를 먼저 분석한다.
나머지 active 서비스는 순환 방식으로 검토하여 특정 서비스가 계속 빠지지 않게 한다.
매 배치마다 모든 코드를 처음부터 다시 읽지 않는다.
이미 해결된 finding을 다시 만들지 않는다.
실제 개선할 근거가 없으면 억지로 기능을 만들지 않고 검토 결과만 기록한다.
변경이 없으면 불필요한 배포를 하지 않는다.

## 7. 고도화 판단

각 서비스에서 아래 항목을 확인한다.

- 첫 방문부터 핵심 작업 완료까지 대표 사용자 여정
- 기능 오류, 회귀, 입력 검증, 권한과 인증
- 로딩, 빈 결과, 오류, 성공, 재시도, 권한 부족 상태
- 새 기능으로 줄일 수 있는 반복 불편
- 화면 정보 계층, 문구, 버튼, 입력, 탐색
- 모바일·태블릿·데스크톱 반응형과 긴 한국어 줄바꿈
- 접근성, 키보드 포커스, 대비, 터치 영역
- API 실패, 데이터 최신성, 중복 처리, 정합성
- 성능, 타임아웃, rate limit, 캐시와 비용
- 로그, health signal, 알림, 복구와 rollback
- 테스트 공백과 재현 가능한 장애
- README, 환경변수, 배포 절차와 실제 동작의 차이

항목마다 증거, 사용자 영향, 우선순위, 개선안, 완료 조건을 기록한다.
관찰한 사실과 아이디어를 분리한다.
핵심 장애와 데이터 손실 위험을 먼저 처리한다.
기능·UI·운영 변경은 실제 사용자 가치를 설명할 수 있어야 한다.

## 8. 구현

사용자의 진행 중 변경과 기존 기술 스택을 보존한다.
작고 검증 가능한 변경 단위로 구현한다.
관련 테스트, 빌드, API 확인, 대표 사용자 흐름을 실행한다.
UI 변경은 360x800, 390x844, 1440x900에서 확인하고 필요할 때 768x1024에서도 확인한다.
가로 넘침, 겹침, 잘린 콘텐츠, 좁아진 flex/grid 자식, 버튼 조작성을 확인한다.
실제 결제, 주문, 금융 거래, 공공 신청, 사용자 데이터 변경을 테스트 목적으로 실행하지 않는다.
외부 API, 메일, OAuth, 결제, DB, 도메인, 모니터링이 필요하면 이름, 용도, 최소 권한, 비용 여부, 발급 방법, 차단 범위를 보고한다.
연결되지 않은 기능을 작동한다고 표시하지 않는다.

## 9. 원본·fork·Coders 배포

검증 순서는 다음과 같다.

1. canonical GitHub 저장소에서 변경을 구현한다.
2. 관련 테스트와 빌드를 통과시킨다.
3. diff, 새 파일, .gitignore, 비밀 포함 여부를 확인한다.
4. canonical 원본에 commit하고 push 또는 PR merge한다.
5. coders-kr 저장소가 실제 fork인지 parent를 확인한다.
6. 조직 fork를 canonical 원본의 실제 기본 브랜치와 동기화한다.
7. 양쪽 기본 브랜치의 전체 commit SHA가 같은지 확인한다.
8. 배포 전 https://coders.kr/llms.txt를 읽는다.
9. 기존 Coders.kr 프로젝트에 canonical repository source로 배포한다.
10. deployment id, source SHA, terminal status를 확인한다.
11. production URL과 변경된 대표 사용자 흐름을 확인한다.
12. 모든 단계와 미확인 항목을 원장과 배치 보고에 기록한다.

같은 SHA가 이미 정상 배포됐거나 배포 중이면 중복 배포하지 않는다.
fork가 독립 저장소이거나 parent가 다르면 삭제·강제 덮어쓰기·force push를 하지 않고 blocker로 보고한다.
실패 시 마지막 정상 배포를 보존하고 안전한 수정 후 재시도한다.
API 요청 접수만으로 배포 완료라고 보고하지 않는다.

## 10. 작업 원장

STATE_FILE에는 다음을 기록한다.

- service_id, repository, default_branch, production_url
- managed_evidence, source_evidence, verified_sha
- state, first_seen, last_seen, last_checked, last_reviewed
- finding_id, evidence, reproduction, impact, priority
- proposal, acceptance_criteria, status
- branch, pr_url, merged_sha, fork_sha
- deployment_id, deployment_status, production_verification
- blocker, next_action, report_time

원장에는 비밀, 쿠키, 개인 이메일, 사용자 입력 원문, 운영 데이터 덤프를 넣지 않는다.
동시 실행에서 기존 기록을 덮어쓰지 않는다.
같은 finding은 증거와 최근 시각을 갱신한다.
마지막 검토 SHA와 다음 순환 대상을 반드시 남긴다.

## 11. 보고

배치 보고는 한국어로 작성한다.

- 이번에 확인한 active, incident, candidate, excluded 수
- 서비스별 실제 개선·장애·다음 작업
- 테스트와 빌드 결과
- canonical merge 결과
- coders-kr fork parent와 SHA 일치 결과
- Coders deployment status와 production 확인
- 필요한 API, 권한, 비용, 사용자 조치
- 아직 확인하지 못한 범위

변화 없는 정상 상태는 반복 알림하지 않는다.
완료되지 않은 구현·merge·fork 동기화·배포·운영 확인을 완료라고 쓰지 않는다.
자동화 문서를 작성했다는 사실과 실제 서비스 변경 결과를 구분한다.

## 12. 안전 경계

비밀·개인정보를 커밋하거나 출력하지 않는다.
force push, history rewrite, 파괴적인 DB 작업, 무승인 구매, 실주문, 실제 사용자 대상 테스트 발송을 하지 않는다.
법적 신청이나 금융 행동의 의미를 임의로 바꾸지 않는다.
권한·인증·외부 승인 없이 가능한 것처럼 꾸미지 않는다.
컴퓨터 또는 실행기가 꺼져 있던 시간의 작업을 수행했다고 보고하지 않는다.
실패한 단계와 필요한 조치를 숨기지 않는다.

