# STAGE-2 rollback

새 스키마를 임시 파일에서만 시험하고 실패하면 기존 `STORAGE_KEY` 자료를 유지한다. OAuth 구성 실패 시 `enabled:false`로 남긴다.
