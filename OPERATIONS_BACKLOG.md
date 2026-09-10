# 운영 서비스 개선 작업 원장

이 문서는 실행 기록이다. 후보 서비스나 검증 전 제안을 운영 중인 서비스 또는 확정 장애로 보고하지 않는다.

## 대상 확인

현재 1차 확인은 GitHub 저장소의 관리 이력·README 또는 homepage의 Coders.kr URL·2026-09-10 운영 URL HTTP 응답을 기준으로 했다.
Coders source/배포 연결과 모든 대표 사용자 흐름은 배치에서 서비스별로 추가 확인한다.
과거 작업 이름과 고정 21개 목록은 편입 근거가 아니다.

## 확인된 운영 서비스

| 저장소 | 운영 URL | 연결 증거 | 확인 커밋 | 확인 시각 | 상태 |
| --- | --- | --- | --- | --- | --- |
| Weather | https://weather.coders.kr | README + HTTP 200 | 배치에서 확인 | 2026-09-10 | active 후보 |
| ansimlife | https://ansimlife.coders.kr | homepage/README + HTTP 200 | 배치에서 확인 | 2026-09-10 | active 후보 |
| hyundai-life-pass | https://hyundai-life-pass.coders.kr | homepage + HTTP 200 | 배치에서 확인 | 2026-09-10 | active 후보 |
| yieldscope-pnt | https://yieldscope-pnt.coders.kr | homepage + HTTP 200 | 배치에서 확인 | 2026-09-10 | active 후보 |
| morrow | https://morrow.coders.kr | homepage + HTTP 200 | 배치에서 확인 | 2026-09-10 | active 후보 |
| stockpilot | https://stockpilot.coders.kr | homepage + HTTP 200 | 배치에서 확인 | 2026-09-10 | active 후보 |
| achim-gyeol | https://morningnews.coders.kr | homepage + HTTP 200 | 배치에서 확인 | 2026-09-10 | active 후보 |
| mafia-game | https://black-midnight.coders.kr | homepage + HTTP 200 | 배치에서 확인 | 2026-09-10 | active 후보 |
| saldobook | https://saldobook.coders.kr | README + HTTP 200 | 배치에서 확인 | 2026-09-10 | active 후보 |
| TradingStockSysyem | https://tradingstocksysyem.coders.kr | README + HTTP 200 | 배치에서 확인 | 2026-09-10 | active 후보 |

## 누적 개선 항목

| ID | 서비스 | 근거·재현 | 사용자 영향 | 우선순위 | 개선안·완료 조건 | 상태 | PR·배포 증거 |
| --- | --- | --- | --- | --- | --- | --- | --- |

## 배치 실행 기록

아직 이 원장 기준으로 자동화가 실제 서비스 코드를 수정·merge·배포한 기록은 없다. 위 목록은 대상 후보의 1차 확인 기록이다.

## 기록 규칙

- 기존 항목과 증거를 읽고 같은 문제는 갱신한다. 동시 수정 시 다른 실행의 기록을 보존한다.
- 추정 개선안과 실제 재현된 장애를 구분한다.
- 각 배치에서 검토·구현·검증·merge·fork 동기화·배포·운영 확인 단계를 각각 기록한다.
- 운영 서비스의 일시 장애는 대상에서 제외하지 않는다.
- 인증정보와 사용자 개인정보를 기록하지 않는다.
