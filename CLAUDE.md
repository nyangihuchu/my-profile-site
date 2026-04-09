# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 개발 환경

빌드 도구나 패키지 매니저가 없는 순수 정적 사이트입니다. 개발 시 `profile-site/index.html`을 브라우저에서 직접 열거나 Live Server(VS Code 확장) 등을 사용합니다.

## 아키텍처

세 파일로 구성된 단일 페이지 포트폴리오 사이트입니다:

- **`index.html`** — 페이지 구조. Hero → About → Portfolio → YouTube → Contact 순서로 섹션이 배치되며, 각 섹션은 `id`로 앵커 링크를 통해 연결됩니다.
- **`style.css`** — CSS Custom Properties로 테마 관리. 주요 변수: `--bg` (배경 #0a0a0a), `--gold` (강조색 #c9a84c), `--text`, `--muted`. 모든 섹션은 `min-height: 100vh`로 전체 화면을 차지합니다.
- **`main.js`** — 스크롤 위치에 따라 현재 섹션에 해당하는 nav 링크에 `.active` 클래스를 부여하는 로직만 포함합니다.

## 주요 설계 규칙

- 폰트: Google Fonts의 `Noto Sans KR` (한국어 지원)
- 콘텐츠 최대 너비: `1100px`, 섹션 내부는 `.section-inner`로 래핑
- 반응형 타이포그래피는 `clamp()`로 구현
- navbar는 `position: fixed` + `backdrop-filter: blur`로 반투명 처리
