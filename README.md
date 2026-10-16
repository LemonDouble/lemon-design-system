# LemonDouble Design System

AI 에이전트가 읽을 수 있는 개인 디자인 시스템입니다. AI가 `DESIGN.md`를 읽고 프로젝트의 CSS에 직접 적용하는 방식으로 사용합니다.

## Usage

- AI에게 `DESIGN.md`의 raw URL을 주고 "이 디자인 시스템으로 만들어"라고 요청합니다.
  - `https://raw.githubusercontent.com/LemonDouble/lemon-design-system/main/DESIGN.md`
- 컴포넌트 미리보기: https://lemondouble.github.io/lemon-design-system/
- 로고, 아바타, 파비콘 등 이미지는 GitHub Pages URL로 받습니다. 경로는 `DESIGN.md`의 Brand Images 표를 참고합니다.

## Files

| File | Description |
|------|-------------|
| `DESIGN.md` | 디자인 시스템 전체 스펙 (토큰, 컬러, 타이포, 컴포넌트, 레이아웃 등) |
| `preview.html` | 컴포넌트 시각 카탈로그. `DESIGN.md`와 같은 토큰 블록을 사용합니다 |
| `images/` | 로고, 아바타, 마스코트 원본 이미지 + 파비콘 세트 |

## Key Decisions

- **Colors**: Logo Yellow `#F0B90B` + Coral `#CD6B5E` on Warm Dark `#12100E`
- **Fonts**: Galmuri11 Bold (headings only) + Pretendard (everything else) + JetBrains Mono (code)
- **Icons**: Lucide (UI) + Simple Icons (brands)
- **Theme**: Dark mode only
