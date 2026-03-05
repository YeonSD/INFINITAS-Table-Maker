# INFINITAS Table Maker

INFINITAS 플레이 데이터(`tracker.tsv`)를 기반으로 SP10/11/12 HARD 서열표, 히스토리, 목표, 소셜 기능을 통합 관리하는 Electron 데스크톱 앱입니다.

## 주요 기능
- 서열표: SP10/11/12 HARD 전환, 일반/WIDE, 램프순/이름순 정렬, 이미지 다운로드
- 히스토리: 램프/점수/목표/레이더 변경 이력, 히스토리 롤백
- 목표: CLEAR/SCORE/RANK 목표 추가/갱신, 자동 달성 판정, 가져오기/내보내기
- 소셜: Google 연동, 팔로우/팔로워, 피드, 팔로우 레이더/비교, 목표 전송
- Reflux 연동: 플레이 후 갱신 완료로 tracker 반영

## 기술 스택
- Electron
- Vanilla JS + HTML + CSS
- Supabase (Auth/Postgres RPC)

## 실행
```bash
npm install
npm start
```

## 패키징
```bash
npm run build:single-exe
```

## 프로젝트 구조(핵심)
- `main.js`: Electron main process
- `preload.js`: renderer bridge
- `src/index.html`: UI 엔트리/다이얼로그 마크업
- `src/app.js`: renderer 로직
- `src/styles.css`: 스타일
- `src/helpContent.js`: 도움말 HTML 콘텐츠
- `supabase/schema.sql`: DB 스키마/RPC

## 데이터/권한 참고
- 로컬 상태 저장: `%APPDATA%/infinitas-rank-table-maker`
- Reflux 연동 특성상 관리자 권한이 필요할 수 있습니다.
