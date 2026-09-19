# 데이터·API 명세 (계획)

현재 공개판은 정적 자산과 로컬 저장을 중심으로 한다. 원격 API는 OAuth·동기화 제공자와 동일 도메인 경계가 확정된 뒤 별도 설계한다.

식당 레코드 최소 계약: `id`, `name_ko`, `name_ja`, `region`, `genre`, `price_band`, `dietary_flags`, `hours`, `official_url`, `map_url`, `evidence_ids`, `verified_at`, `freshness_state`.

로컬 파일 계약: JSON UTF-8, 스키마 버전 필수, 알 수 없는 필드 보존, 삭제 시 복구 불가 경고, import는 임시 파싱 후 검증 성공 때만 교체. OAuth API가 없는 상태에서 자격 증명을 수집하지 않는다.
