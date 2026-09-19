# 서비스 기준선

## 정체성

ITADAKI는 한국어 여행자가 도쿄 식당을 발견하고 공식 출처를 비교해 방문 결정을 내리도록 돕는 정적 웹/PWA다. 예약 대행·전화 발신·결제는 제품 범위 밖이다.

## 근거 기반 현재 상태

| 항목 | 상태 | 근거 |
|---|---|---|
| 최신 제품판 | `v5.4.20260904.1` | `04_코드/apps/web/progress.json` |
| 공개 URL | Pages 개발판 | `https://hanksleekorea-boop.github.io/itadaki/` HTTP 200 기록 |
| 대시보드 | 공개 | `/dashboard.html` HTTP 200 기록 |
| 표시 검증 식당 | 4/30 | progress.json |
| 가상 사례 | 1,000건 과거 규칙 검사 | progress.json; 실제 사용자 조사가 아님 |
| Android | v5.3 설치 증거, v5.4 재검증 필요 | progress/release-gate |
| iPhone/Safari | 미실시 | progress.json |
| OAuth | 코드·설계 있음, 공개 설정 disabled | site-config.js, auth-worker |
| AdSense | 계정·송출 최신 상태 미확인 | progress.json |
| 운영 주체/문의 | 준비 중 | progress/release-gate |

## 핵심 과업

`JT-01` 검색어·권역·장르 필터 → `JT-02` 근거가 붙은 상세 확인 → `JT-03` 저장/여행 후보 추가 → `JT-04` 최대 2곳 비교 → `JT-05` 공식 링크로 이동 → `JT-06` 정정 초안 작성 → `JT-07` 모바일 오프라인 재접속.

## 여정

유입 → 검색 시작 → 첫 결과 → 근거 이해 → 저장/비교 → 공식 예약·지도 링크 이동 → 재방문/정정 → 삭제. 계정·결제·동기화는 현재 미제공 또는 기본 꺼짐이다.
