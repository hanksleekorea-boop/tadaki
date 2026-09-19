# ITADAKI 5단계 상세개발계획서 v3.3

정본일: `2026-09-09`  
대상: `D:\Desktop\챗지피티프로젝트들\이타다키`  
공개 기준 URL: `https://hanksleekorea-boop.github.io/itadaki/`  
실행 모드: `END_TO_END`

## 0. 적용 계약

이 문서는 구현·배포 결과가 아니라 실행 명세다. 모든 작업은 정확히 아래 다섯 단계 순서로 수행하며, 한 단계의 종료 증거가 없으면 다음 단계로 이동하지 않는다. 사실·관찰·계산·추론·가설을 분리하고, 계획을 구현 완료로 표시하지 않는다. B드라이브·프로젝트 밖 파일·비밀값·토큰·쿠키는 사용하지 않는다.

현재 기준선: 공개판 `v5.4.20260904.1`, `public-development`, 검증 식당 4/30, `release-gate.json`의 `overall_complete=false`와 차단 9개, `site-config.js` 인증 비활성, 현재 `adb devices -l` 0대. 운영 주체·비공개 문의·OAuth 왕복·AdSense 실제 송출·iPhone/Safari는 미확인 또는 미실시다.

공통 경로: `04_코드/apps/web/`, `04_코드/apps/auth-worker/`, `progress.json`, `release-gate.json`, `.world-top10-planning/20260909T123249Z/evidence/`.

공통 상태값: `PLANNED`(계획), `DISCOVERY_REQUIRED`(기호·입력 확인 필요), `WAITING_EXTERNAL`(기기·운영자·외부 계정 필요), `BLOCKED_EXTERNAL`(외부 계약 차단), `READY`, `DONE`.

---

# 1단계 — `STAGE-1-BASELINE` 기준선·안전 기반

## 목표와 완료 모습

현재 파일·공개판·콘텐츠·화면 폭을 재현 가능한 기준선으로 고정한다. 완료 시 공식 출처·확인일·권역을 가진 식당 30곳, 8권역 균형표, 동일 공개판 Android PWA 증거, 기준선 지문이 존재한다.

## 24개 필수 절

1. 목표: 지금 있는 자료를 안전하게 복사하고 사실을 확인한다.
2. 사용자 모습: 카드에 공식 출처와 확인일이 보인다.
3. 범위: 규칙·Git·파일·URL·콘텐츠·기기·360/390/768/1280px.
4. 제외: OAuth 활성, 결제, AdSense 승인, iPhone, B드라이브.
5. 진입: 프로젝트 폴더와 규칙 확인, 기존 변경 보존.
6. 입력: `STATE.md`, `HISTORY.md`, `progress.json`, `release-gate.json`, 후보 풀.
7. 산출물: `00-integrated-run-control.json`, `service-baseline.*`, 검증표, 증거 폴더.
8. ID: `REQ-001~003`, `GAP-001~003`, `D-BASE-001~004`.
9. 순서: 지문→콘텐츠 계약→기기·폭 기준선→판정.
10. 병렬: URL HEAD와 파일 지문, 콘텐츠 조사와 문법 검사.
11. 순차: 검증 승인 전 생성 데이터 교체 금지.
12. 변경 위치: `generated/verified-data-v5.js`, `progress.json`, `release-gate.json`.
13. 계약: `id`, 한·일 이름, 공식 HTTPS URL, 확인일, 권역, 장르, `isVerified`.
14. 정상: 공식 URL 확인→필드 검사→레코드 승인→카드 노출.
15. 빈/로딩: 후보 없음·응답 지연·부분 필드는 각각 보류 상태.
16. 실패/복구: 기존 레코드를 덮어쓰지 않고 격리 큐로 이동.
17. 접근성/플랫폼: 일본어 `lang`, 터치 44px, PC 키보드 포커스.
18. 보안: 공개 URL만 저장하고 개인·인증 자료를 제거.
19. 예산: 기존 정적 자산과 CI만 재사용.
20. 자동 시험: JSON·중복 ID·HTTPS·날짜·JS 문법·diff 공백.
21. 수동 시험: 유휴 Android 한 대 PWA·오프라인, iPhone/Safari 예약.
22. 중단: 레코드 감소·판 불일치·출처 누락 시 백업 복원.
23. 종료: 30곳·8권역·동일판 기기·폭 기준선 증거.
24. 인계: `verified_ids`, `content_hash`, `public_version`, `device_evidence_id`.

## 작업카드

### `TASK-1-001` 기준선·지문 고정 (`DISCOVERY_REQUIRED`)

12단계: 작업 폴더 고정; 규칙·잠금 확인; `rg --files` 저장; Git 상태 저장; progress/gate 복사; 공개 URL 상태 저장; 버전 비교; B드라이브 검색; SHA-256 생성; 사실/추론 분리; 실패 로그 보존; 증거 저장.

시험 `TEST-001~012`: 지문 재현, URL HEAD, B드라이브 차단, Git 변경 보존, 손상 JSON, 버전 불일치, 누락 파일, 중복 ID, 날짜, HTTPS, 비밀값, 복구 비교.

### `TASK-1-002` 공식 검증 콘텐츠 30곳 (`WAITING_EXTERNAL`)

12단계: 중복·폐업 분리; 공식 URL 확인; 한·일 상호명; 역·주소; 영업시간; 휴무일; 예산·장르; 1인 방문 근거; 확인일·확인자; 권역·장르 분포; 누락 격리; 전후 해시 저장.

시험 `TEST-013~024`: URL 200, 필수 필드, 중복, 폐업 격리, 8권역, 8장르, 신선도, 비공식 출처, 일본어, 샘플 배지, 빈 큐, 롤백.

### `TASK-1-003` 공개판·기기·폭 기준선 (`WAITING_EXTERNAL`)

12단계: 유휴 Android 선택; serial 기록; 공개 v5.4 실행; 설치; standalone; 검색·상세·저장·비교; 오프라인; 360px; 390px; PC 768/1280px; 개인정보 마스킹; 증거 저장.

시험 `TEST-025~036`: 설치, standalone, 오프라인, service worker, overflow, 터치, 키보드, 의미 일치, 오류, 재설치, 판 버전, 증거 무결성.

인수·복구: 30곳·8권역·동일판 기기 증거가 없으면 종료하지 않는다. 새 생성 파일은 격리하고 이전 `verified-data-v5.js`, progress, gate를 복사본에서 복원한다.

---

# 2단계 — `STAGE-2-FOUNDATION` 구조·데이터·권한 기반

## 목표와 완료 모습

데이터 스키마, JSON import/export, 삭제·복원, 공통 dialog, PWA 캐시, OAuth fail-closed 경계를 시험 가능하게 한다. 인증이 비활성인 동안에는 로그인 성공을 가장하지 않는다.

## 24개 필수 절

1. 목표: 기능보다 먼저 데이터와 권한 계약을 고정한다.
2. 모습: 미리보기 후 저장, 삭제 후 복원, 명확한 인증 오류.
3. 범위: `app.js`, `advanced-features.js`, `service-worker.js`, Worker 경계.
4. 제외: 실제 client/secret 생성·배포·동기화 DB·결제.
5. 진입: 1단계 지문과 30곳 데이터 통과.
6. 입력: `parseImport`, `confirmImport`, `validateState`, Worker 테스트.
7. 산출물: 스키마, 계약시험, 복원 로그, OAuth 체크리스트.
8. ID: `REQ-004~006`, `GAP-004~006`, `D-FOUND-001~005`.
9. 순서: 기호 탐색→스키마→저장→권한→캐시.
10. 병렬: 스키마와 Worker 경계.
11. 순차: origin/issuer 검증 전 인증 활성 금지.
12. 변경 위치: `app.js` 174~204행, `advanced-features.js` 33~47행, Worker.
13. 계약: import는 확인 버튼 뒤에만 persist, 토큰은 HttpOnly 세션.
14. 정상: 유효 JSON 미리보기→확인→저장→복원.
15. 빈/로딩: 빈 파일·부분 유효·저장공간 부족 문구.
16. 실패/복구: 손상 JSON은 상태 불변, 미설정 인증은 실패-폐쇄.
17. 접근성: dialog label·초점 복귀·모바일 읽기 순서.
18. 보안: OAuth·API 경로 캐시 금지, localStorage 토큰 금지.
19. 예산: import 1MB, 여행 20개, 메모 200자.
20. 자동 시험: 스키마·계약·Worker·캐시·삭제.
21. 외부 시험: 실제 OAuth는 endpoint 확정 후에만.
22. 중단: validator 실패 시 이전 버전 유지.
23. 종료: 계약 통과, 미확인 기호 0 또는 DISCOVERY 배정.
24. 인계: 스키마 버전·키·origin·민감 캐시 prefix.

## 작업카드

### `TASK-2-001` 데이터·로컬 자료 계약 (`DISCOVERY_REQUIRED`)

12단계: 상태 키 목록화; 필드 형식; 버전 고정; 손상 샘플; 미리보기; 확인 persist; 삭제 범위; 복원 순서; 저장공간 오류; 계약 테스트; pytest; 증거 저장.

시험: 정상·빈·손상·과대·중복·미지원 버전·부분 성공·저장공간 부족·삭제 복원·새로고침·오프라인·동시 탭.

### `TASK-2-002` OAuth fail-closed (`WAITING_EXTERNAL`)

12단계: issuer 확인; redirect 고정; PKCE; secret 길이; CORS; 미설정 오류; 오염 cookie; JWKS 실패; logout; 로그 누출; Worker 8종; endpoint 전 `enabled=false`.

시험: 미설정·짧은 secret·origin 불일치·미로그인·오염 cookie·state/PKCE·CORS·미확인 provider·replay·JWKS timeout·logout·만료.

### `TASK-2-003` 공통 UI·PWA 캐시 (`PLANNED`)

12단계: dialog label; 초점; 오류 문구; 44px; manifest; shell 지문; 민감 prefix; offline fallback; 갱신 메시지; 삭제 시 cache 제거; 문법·스키마; 증거 저장.

인수·복구: 계약 실패 시 새 validator만 폐기하고 UI·데이터·기존 백업은 유지한다.

---

# 3단계 — `STAGE-3-CORE` 핵심 사용자 여정

## 목표와 완료 모습

검색→공식 근거→저장·비교→여행 초안→상황·지역 가이드→공유를 정상·빈·오프라인에서 동일 의미로 제공한다. 예약 실행·전화 자동화·결제는 범위에서 제외한다.

## 24개 필수 절

1. 목표: 사용자가 믿을 이유와 다음 행동을 한 번에 얻는다.
2. 모습: 모든 탭이 같은 레코드·근거·신선도를 표시한다.
3. 범위: `matches`, `renderDiscover`, `openDetail`, 저장·비교·여행·가이드·공유.
4. 제외: 비공식 사실과 예약·결제 실행.
5. 진입: 2단계 계약 통과.
6. 입력: 레코드·필터·여행 state·근거 규칙.
7. 산출물: 12여정 시험, 빈 결과 UX, payload 계약.
8. ID: `REQ-007~009`, `GAP-007~012`, `D-CORE-001~006`.
9. 순서: 검색/상세→저장/비교→여행→가이드→공유.
10. 병렬: 빈 결과와 배지.
11. 순차: payload 검증 후 persist.
12. 변경 위치: `app.js` 110~230행, `advanced-features.js` 50~120행.
13. 계약: 공식만 기본 노출, 샘플 배지, 공유는 미리보기 후 확인.
14. 정상: 검색→카드→상세→저장→비교→여행→공유.
15. 빈/로딩: 완화·초기화·대체 권역 제공.
16. 실패/오프라인: 링크 재확인, 저장 카드만 사용, 손상 payload 무시.
17. 접근성: heading·`aria-pressed`·일본어 `lang`·키보드 동등.
18. 보안: `safeHttps`, HTML escape, 메모 공유 제외.
19. 예산: payload 1MB, 여행 20개.
20. 자동 시험: 필터·상한·validator·악성 decode.
21. 수동 시험: 한·일 검색·0결과·오프라인·PC/모바일.
22. 중단: 근거 없는 값 발견 시 레코드 격리.
23. 종료: 12여정 통과, 근거 없는 값 0.
24. 인계: 여정 ID·payload schema·문구·실패 로그.

## 작업카드

### `TASK-3-001` 검색·상세·저장·비교 (`PLANNED`)

12단계: 필터 표준화; `matches`; 배지; 신선도; dialog; 저장; 비교 3곳; 빈 결과; HTTPS; 오류; 12여정; 증거.

### `TASK-3-002` 여행·상황·지역 가이드 (`PLANNED`)

12단계: state; 기본 여행; 후보; 메모; 방문 상태; 삭제 상한; 지역 필터; 상황 행동; 일본어 복사; 빈 권역; 오프라인; 복구.

### `TASK-3-003` 공유·악성 입력 (`PLANNED`)

12단계: payload 버전; ID 대조; escape; 메모 제외; duplicate key; 미리보기; 취소 불변; 확인 1회 persist; 과대 입력; base64 오류; 반대 시험; 증거.

---

# 4단계 — `STAGE-4-QUALITY` 품질·통합·운영 내구성

## 목표와 완료 모습

WCAG AA 목표, Core Web Vitals, 보안 헤더, 저속망, 광고 투명성, 개인정보·삭제, 관측과 복구가 동일 보고서로 연결된다. 외부 승인 없이 광고·법률·OAuth 완료를 표시하지 않는다.

## 24개 필수 절

1. 목표: 빠르고 읽기 쉽고 안전하며 장애 원인을 찾는다.
2. 모습: Lighthouse·axe·헤더·법적·광고 결과가 판과 연결된다.
3. 범위: `styles.css`, `commercial.css`, `adsense.js`, telemetry, headers.
4. 제외: 법률 자문·AdSense 검토를 승인으로 간주하지 않음.
5. 진입: 3단계 여정 통과.
6. 입력: 여정 증거, 광고·법적 파일, robots/sitemap.
7. 산출물: 품질 보고서, 헤더 표, 운영 runbook.
8. ID: `REQ-010~014`, `GAP-013~020`, `D-QUALITY-001~006`.
9. 순서: 접근성→성능→보안→광고/법적→관측/복구.
10. 병렬: axe/Lighthouse와 법적/헤더.
11. 순차: 광고 전 CLS 기준선, 최적화 후 재측정.
12. 변경 위치: 위 파일과 CI workflow.
13. 계약: 광고 라벨·동의·레이아웃 예약, telemetry 최소 이벤트.
14. 정상: 로드·검색·저장이 예산 내 완료.
15. 빈/로딩: 광고·분석 차단과 느린 망에서도 핵심 유지.
16. 실패: 외부 측정 실패는 미검증, rollback 실행.
17. 접근성: 키보드·스크린리더·200% 확대·한/일 읽기 순서.
18. 보안: CSP/CORS 최소화·민감 캐시 금지·비밀 스캔.
19. 예산: LCP·CLS·TBT·광고·폰트·이미지 예산.
20. 자동 시험: lint·axe·Lighthouse·headers·dependency·secret.
21. 외부 시험: 저속망·스크린리더·AdSense·문의 예행연습.
22. 중단: 예산 초과·정책 위반이면 새 자산 공개 금지.
23. 종료: 모든 결과에 날짜·브라우저·판·증거 경로.
24. 인계: 임계치·대시보드·rollback.

## 작업카드

`TASK-4-001` 접근성/반응형: heading→dialog focus→키보드→확대→대비→터치→360/390→768/1280→lang→axe→수정 재측정→증거.  
`TASK-4-002` 성능/보안: URL 고정→Lighthouse→LCP→CLS→TBT→저속망→CSP→CORS→민감 캐시→의존성→비밀 스캔→rollback 임계치.  
`TASK-4-003` 광고/법적/운영: 위치→라벨→CMP→ads.txt→실제 송출 분리→약관→개인정보→삭제→운영자→문의→외부 결과→gate 반영.

---

# 5단계 — `STAGE-5-RELEASE` 공개 인수·안정화

## 목표와 완료 모습

실제 Android·iPhone/Safari·운영 책임·외부 검토·Pages·QR·rollback 증거가 하나의 인수 패키지가 된다. `release-gate.json` 차단 조건이 0개일 때만 공개 100%로 판정한다.

## 24개 필수 절

1. 목표: 실제 사용자가 설치하고 장애 시 운영자가 복구한다.
2. 모습: 공개판·progress·gate·QR이 같은 판을 가리킨다.
3. 범위: 기기·Pages·QR·SLA·OAuth/AdSense 확인·독립 검토.
4. 제외: 승인 없는 결제·B드라이브·비공식 OAuth.
5. 진입: 4단계 품질 통과.
6. 입력: 품질 보고서·gate·runbook·artifact.
7. 산출물: release manifest·기기 증거·rollback·인수서.
8. ID: `REQ-015~018`, `GAP-021~030`, `D-RELEASE-001~007`.
9. 순서: 후보판→기기→운영/복구→외부 검토→Pages/QR→gate.
10. 병렬: 동일 공개판 Android/iPhone 시험.
11. 순차: 배포 후 progress/gate/QR 확인 뒤 인수.
12. 변경 위치: Pages workflow, progress, gate, QR, 운영 문서.
13. 계약: 공개 파일·버전·해시·URL이 manifest와 일치.
14. 정상: 설치→검색→저장→오프라인→업데이트→문의→복구.
15. 빈/로딩: 네트워크·콘텐츠·업데이트 대기 안내.
16. 실패: gate 실패 시 `public-development` 유지·이전판 복구.
17. 플랫폼: Android Chrome·iPhone Safari·PC 주요 브라우저.
18. 보안: 기기·운영자·OAuth 비밀값 마스킹.
19. 예산: artifact·cache·외부 호출·운영 비용 확인.
20. 자동 시험: 전체 회귀·지문·링크·QR·rollback dry-run.
21. 외부 시험: 실제 기기·운영 문의·독립 검토·OAuth·AdSense.
22. 중단: 필수 gate 하나라도 실패하면 공개 완료 금지.
23. 종료: 차단 0, 동일판 증거, 운영 인수·외부 검토 기록.
24. 인계: manifest·연락망·복구 명령·모니터링 작업.

## 작업카드

`TASK-5-001` 기기 인수: 공개판 고정→Android serial→설치→standalone→핵심 여정→오프라인→iPhone→폭→마스킹→증거.  
`TASK-5-002` 운영 복구: 운영 주체→채널→책임자→SLA→테스트 문의→수신/응답→장애 분류→이전판→rollback→데이터 복구→사고 보고서→서명.  
`TASK-5-003` 공개판/QR/검토: manifest→해시→Pages→HEAD→QR→접속→gate 0→외부 검토→결함 0→rollback 포인트→handoff→최종 판정.

---

# 6. 공통 추적·시험·복구

모든 항목은 `EVIDENCE → GAP → DECISION → REQUIREMENT → STAGE → TASK → STEP → TEST → ACCEPTANCE`로 연결한다. 전체 매핑은 `five-stage-requirement-traceability.csv`, 의존성은 `five-stage-dependency-graph.md`, 시험 표는 `five-stage-test-matrix.csv`, 96필드 카드는 `development-task-cards.json`을 사용한다.

단계 판정 명령:

```powershell
Set-Location 'D:\Desktop\챗지피티프로젝트들\이타다키'
git status --short
Get-Content 04_코드/apps/web/progress.json
Get-Content 04_코드/apps/web/release-gate.json
```

```powershell
Set-Location 'D:\Desktop\챗지피티프로젝트들\이타다키\04_코드\packages\core'
$env:PYTHONDONTWRITEBYTECODE='1'
$env:PYTEST_DISABLE_PLUGIN_AUTOLOAD='1'
python -m pytest -q -p no:cacheprovider
```

```powershell
Set-Location 'D:\Desktop\챗지피티프로젝트들\이타다키'
node --check 04_코드/apps/web/app.js
node --check 04_코드/apps/web/advanced-features.js
node --test 04_코드/apps/auth-worker/test/worker-auth.test.mjs
git diff --check
```

인수 증거가 하나라도 빠지면 `DONE`이 아니며, 현재 계획은 외부 운영자·기기·OAuth·AdSense·독립 검토 증거가 없어 `PLANNED` 또는 `WAITING_EXTERNAL`이다. 새 데이터·설정은 별도 복사본에서 검증하고 기존 사용자 변경·추적 파일·Git 기록은 보존한다.
