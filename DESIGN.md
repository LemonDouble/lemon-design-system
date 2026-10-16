# LemonDouble Design System

## 1. Visual Theme & Atmosphere

LemonDouble Design System은 개인 프로젝트 전반에 일관된 브랜드 아이덴티티를 부여하기 위한 다크 모드 기반 디자인 시스템이다. 로고에서 추출한 골든 옐로우(`#F0B90B`)와 코랄 레드(`#CD6B5E`)를 핵심 액센트로, 로고의 다크 브라운에서 파생된 따뜻한 다크 배경(`#12100E`)을 기반으로 한다. 순수 블랙이 아닌 미세한 따뜻함이 깔린 배경은 로고와 자연스러운 색상 연속성을 만든다.

타이포그래피는 이중 폰트 시스템을 사용한다. 페이지 제목 등 브랜딩 요소에는 8bit 픽셀 폰트 **Galmuri11**을 Bold(700) 전용으로 사용하고, 그 외 본문, 버튼, 태그 등 가독성이 필요한 모든 곳에는 **Pretendard**를 사용한다. 코드에는 고정폭 폰트 **JetBrains Mono**를 사용한다. Galmuri11은 레트로 게임 감성을 부여하면서도 Pretendard와의 조합으로 모던한 느낌을 동시에 유지한다.

**Key Characteristics:**
- 로고에서 추출한 골든 옐로우 + 코랄 레드 듀오톤 액센트
- 로고 다크 브라운 파생 따뜻한 다크 배경 (`#12100E`, 순수 블랙이 아님)
- Galmuri11 Bold(700) 전용 — 페이지 제목(h1-h3), 섹션 레이블, Stat 숫자, 로고 텍스트에만 사용
- Pretendard — 본문, 버튼, 태그 등 코드를 제외한 나머지 전부
- JetBrains Mono — 코드 블록, 인라인 코드
- 다크 모드 단일 테마 (라이트 모드 없음)
- "이 사람 작품이구나" 라고 즉시 알아볼 수 있는 개인 브랜드 시스템

### Brand Images
이 레포지토리의 `images/` 폴더에 있는 원본을 항상 사용한다.

| 파일 | 용도 | 사용처 |
|------|------|--------|
| `images/lemon-logo.webp` | 로고 (원형 엠블럼) | Nav 로고, OG 이미지 |
| `images/lemon-avatar.webp` | 아바타 (얼굴 크롭) | 프로필 사진, Avatar 컴포넌트, 댓글 프로필 |
| `images/lemon-character.webp` | 마스코트 (풀샷) | 히어로 일러스트, 랜딩 페이지, About 페이지 |
| `images/favicon.ico` | 파비콘 (멀티사이즈 ICO) | 브라우저 탭 아이콘 |
| `images/favicon-32.png` | 파비콘 32x32 PNG | 브라우저 탭 아이콘 (모던 브라우저) |
| `images/apple-touch-icon.png` | Apple Touch Icon 180x180 | iOS 홈 화면 아이콘 |
| `images/favicon-192.png` | 파비콘 192x192 PNG | Android/Chrome 앱 아이콘 |
| `images/favicon-512.png` | 파비콘 512x512 PNG | PWA 아이콘, 스플래시 스크린 |
| `images/twitter-bird.svg` | 트위터 새 로고 SVG | 소셜 링크의 Twitter/X 아이콘 (Simple Icons 대신 사용) |

#### Favicon HTML 스니펫
```html
<link rel="icon" href="/favicon.ico" sizes="48x48">
<link rel="icon" href="/favicon-32.png" type="image/png" sizes="32x32">
<link rel="apple-touch-icon" href="/apple-touch-icon.png">
<link rel="icon" href="/favicon-192.png" type="image/png" sizes="192x192">
```

### Icons
- **UI 아이콘**: [Lucide](https://lucide.dev/) — 2px stroke, 24x24 기본. 미니멀한 선형 아이콘.
  - CDN: `https://unpkg.com/lucide@latest`
  - React: `lucide-react`
  - Size: 기본 20px (본문), 16px (버튼/태그 내), 24px (네비게이션)
  - Stroke width: 2px (기본), 1.5px (큰 사이즈에서)
  - Color: 주변 텍스트 색상을 따른다 (`currentColor`)
- **브랜드 아이콘**: [Simple Icons](https://simpleicons.org/) — GitHub, Slack 등 브랜드 로고 전용.
  - CDN: `https://cdn.jsdelivr.net/npm/simple-icons@latest/icons`
  - React: `@icons-pack/react-simple-icons`
  - Color: `var(--text-muted)` 기본, 호버 시 `var(--text-primary)`
  - **예외 — Twitter**: Simple Icons의 X 로고 대신 `images/twitter-bird.svg`(클래식 트위터 새 로고)를 사용한다. `fill: currentColor`로 되어 있어 CSS 색상을 따른다.
- **기술 스택 아이콘**: [devicon](https://devicon.dev/) — 블로그 등 기술 스택 표시 용도 (보조).

## 2. Design Tokens

모든 값은 아래 토큰 블록에서 정의한다. 프로젝트에는 이 블록을 그대로 복사해 넣고, 컴포넌트 스타일에서는 항상 `var(--토큰)`으로 참조한다.

- 토큰에 있는 값을 hex나 rgba로 직접 쓰지 않는다. 값을 바꿀 때 이 블록 한 곳만 고치면 되도록 하기 위함이다.
- 토큰에 없는 일회성 값(예: Code Block 헤더 배경)은 해당 컴포넌트 스펙에 적힌 값을 그대로 쓴다.

```css
:root {
  /* Brand */
  --primary: #F0B90B;
  --primary-hover: #D4A30A;
  --primary-dim: rgba(240, 185, 11, 0.12);
  --primary-dim-border: rgba(240, 185, 11, 0.25);
  --secondary: #CD6B5E;
  --secondary-dim: rgba(205, 107, 94, 0.12);
  --secondary-dim-border: rgba(205, 107, 94, 0.25);

  /* Background & Surface */
  --bg: #12100E;
  --bg-glass: rgba(18, 16, 14, 0.85);
  --surface: #1C1816;
  --surface-hover: #231E1B;
  --overlay: rgba(0, 0, 0, 0.6);

  /* Border */
  --border: #2E2723;
  --border-hover: #3D3530;

  /* Text */
  --text-primary: #F5F0EB;
  --text-secondary: #A89E95;
  --text-muted: #8D7E72;

  /* Focus */
  --focus-ring: var(--text-muted);

  /* Semantic */
  --info: #60A5FA;
  --info-subtle: rgba(96, 165, 250, 0.06);
  --info-dim: rgba(96, 165, 250, 0.12);
  --info-dim-border: rgba(96, 165, 250, 0.25);
  --success: #4ADE80;
  --success-subtle: rgba(74, 222, 128, 0.06);
  --success-dim: rgba(74, 222, 128, 0.12);
  --success-dim-border: rgba(74, 222, 128, 0.25);
  --warning: #F59E0B;
  --warning-subtle: rgba(245, 158, 11, 0.06);
  --warning-dim: rgba(245, 158, 11, 0.12);
  --warning-dim-border: rgba(245, 158, 11, 0.25);
  --error: #EF4444;
  --error-subtle: rgba(239, 68, 68, 0.06);
  --error-dim: rgba(239, 68, 68, 0.12);
  --error-dim-border: rgba(239, 68, 68, 0.25);

  /* Font */
  --font-heading: 'Galmuri11', monospace;
  --font-body: 'Pretendard', -apple-system, BlinkMacSystemFont, sans-serif;
  --font-mono: 'JetBrains Mono Variable', 'Pretendard', monospace;

  /* Radius */
  --radius-xs: 4px;
  --radius-sm: 6px;
  --radius-md: 8px;
  --radius-lg: 12px;
  --radius-full: 9999px;

  /* Z-index */
  --z-base: 0;
  --z-dropdown: 100;
  --z-sticky: 200;
  --z-overlay: 300;
  --z-modal: 400;
  --z-toast: 500;
  --z-tooltip: 600;
}
```

## 3. Color Palette & Roles

각 색상의 의미와 사용처를 설명한다. 값은 [Design Tokens](#2-design-tokens)의 토큰 블록을 따른다.

### Brand (로고에서 추출)
- **Lemon Yellow** `--primary`: CTA 버튼, 링크, 강조 텍스트, 활성 상태, 섹션 제목 색상. 호버는 `--primary-hover`.
- **Coral Red** `--secondary`: 보조 강조, 태그 배경, 인라인 코드 텍스트, 보조 버튼.

### Background & Surface
- **BG Dark** `--bg`: 페이지 배경. 로고의 다크 브라운(`#5C4A42`)에서 파생, 미세한 따뜻함.
- **BG Glass** `--bg-glass`: 고정 네비게이션의 반투명 배경.
- **Surface** `--surface`: 카드, 코드 블록, 입력 필드 배경.
- **Surface Hover** `--surface-hover`: Surface 요소 호버 상태.
- **Overlay** `--overlay`: 모달 뒤 배경을 가리는 오버레이.

### Border
- **Border** `--border`: 카드 테두리, 구분선, 입력 필드 테두리.
- **Border Hover** `--border-hover`: 호버 상태의 테두리.

### Text
- **Text Primary** `--text-primary`: 제목, 카드 제목, 주요 텍스트. 순백이 아닌 미세한 따뜻함.
- **Text Secondary** `--text-secondary`: 본문, 설명, 부가 텍스트.
- **Text Muted** `--text-muted`: 메타데이터, 비활성 텍스트, 줄번호, placeholder.
- 모든 텍스트 색상은 BG와 Surface 위에서 대비 4.5:1(WCAG AA) 이상을 유지한다. Text Muted는 이 기준의 하한선이므로 더 어둡게 바꾸지 않는다.

### Accent Dim (배경 틴트용)
- `--primary-dim`, `--secondary-dim`: 배지, 태그, 활성 항목의 배경.
- `--primary-dim-border`, `--secondary-dim-border`: 액센트 요소의 테두리, 카드 호버 테두리.

### Semantic
- **Info** `--info`: 안내, 정보, 알림 상태.
- **Success** `--success`: 정상, 활성, 완료 상태.
- **Warning** `--warning`: 경고, 진행 중 상태.
- **Error** `--error`: 에러, 삭제, 위험 상태.
- 상태마다 틴트 토큰 세 가지를 둔다: `-subtle`(Toast처럼 넓은 영역의 배경), `-dim`(배지, 아이콘 배경), `-dim-border`(테두리).
- 상태는 색만으로 전달하지 않는다. 아이콘, 텍스트 레이블, 툴팁 중 하나를 항상 함께 둔다([WCAG 1.4.1](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color.html)). 액센트가 따뜻한 색에 몰려 있어 Warning은 Primary와, Error는 Secondary와 색만으로는 구분이 어렵기 때문이다.

### Disabled State
- **Opacity**: `0.4` — 모든 비활성 요소에 일괄 적용
- **Cursor**: `not-allowed`
- **Pointer Events**: `none`
- 적용 대상: 버튼, 입력 필드, 토글, 체크박스, 라디오, 셀렉트
- 입력 필드 비활성: 배경 `var(--surface)`, 텍스트 `var(--text-muted)` + opacity 0.4

### Focus State
- 전역 포커스 링: `:focus-visible { outline: 2px solid var(--focus-ring); outline-offset: 2px; }` 하나로 모든 인터랙티브 요소를 처리한다. 컴포넌트마다 포커스 스타일을 따로 정의하지 않는다.
- `:focus-visible`을 쓰므로 마우스 클릭에는 링이 나타나지 않고, 키보드로 이동할 때만 나타난다.
- 예외 — `overflow: hidden` 컨테이너 안에 꽉 차는 요소(Accordion trigger 등): 링이 잘리지 않도록 `outline-offset: -2px`로 안쪽에 그린다.
- 예외 — 텍스트 입력 요소(Input, Select, Textarea): 클릭해도 `:focus-visible`이 적용되므로 링 대신 `outline: none` + `border-color: var(--focus-ring)`로 표시한다.
- 포커스 표시는 주변과 대비 3:1 이상이어야 한다([WCAG 1.4.11](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast.html)). 투명도가 낮은 `-dim-border` 토큰은 이 기준을 통과하지 못하므로 포커스 표시에 쓰지 않는다.
- 포커스 색은 노란색(Primary)을 쓰지 않는다. Primary는 이미 활성·선택 상태를 뜻하므로, 포커스까지 노란색이면 "선택된 요소"와 "키보드가 가리키는 요소"가 구분되지 않는다.
- 클릭할 수 있는 요소는 `<button>`, `<a href>`, `<input>` 같은 네이티브 요소로 만든다. `<div onclick>`은 키보드로 포커스를 받을 수 없다.

## 4. Typography Rules

### Font Family
- **Heading** `--font-heading`: `Galmuri11`, fallback: `monospace`
  - CDN: `https://cdn.jsdelivr.net/npm/galmuri/dist/galmuri.css`
- **Body** `--font-body`: `Pretendard`, fallback: `-apple-system, BlinkMacSystemFont, sans-serif`
  - CDN: `https://cdnjs.cloudflare.com/ajax/libs/pretendard/1.3.9/static/pretendard.min.css`
- **Mono** `--font-mono`: `JetBrains Mono Variable`, fallback: `Pretendard`, `monospace`
  - CDN: `https://cdn.jsdelivr.net/npm/@fontsource-variable/jetbrains-mono@5.2.8/index.css`
  - JetBrains Mono에는 한글 글리프가 없으므로, 코드 안의 한글은 Pretendard로 표시된다.

### Galmuri11 사용 규칙
- **반드시 font-weight: 700 (Bold)로만 사용한다.** Regular(400) 사용 금지.
- 적용 범위: 페이지 제목 h1, h2, h3 / 섹션 레이블 (소제목 위 카테고리) / Stat 숫자 (큰 강조 숫자) / Nav·Sidebar 로고 텍스트
- 카드, 모달, Empty State 등 컴포넌트 안의 제목과 탭 레이블은 Pretendard를 사용한다.
- 그 외 어떤 곳에도 Galmuri11을 사용하지 않는다.

### Hierarchy

| Role | Font | Size | Weight | Line Height | Notes |
|------|------|------|--------|-------------|-------|
| Hero Heading | Galmuri11 | 44px | 700 | 1.2 | 히어로 섹션 메인 제목 |
| Section Title | Galmuri11 | 28px | 700 | 1.3 | 섹션 제목 |
| Sub Title | Galmuri11 | 20px | 700 | 1.4 | 페이지 소제목 (h3) |
| Section Label | Galmuri11 | 12px | 700 | 1.0 | 섹션 위 카테고리 레이블, letter-spacing: 1.5px, uppercase |
| Stat Number | Galmuri11 | 32px | 700 | 1.0 | 숫자 강조 카드 |
| Component Title | Pretendard | 15-17px | 700 | 1.4 | 카드, 모달, Empty State 제목 |
| Body Large | Pretendard | 18px | 400 | 1.7 | 히어로 설명, 긴 본문 |
| Body | Pretendard | 16px | 400 | 1.6 | 표준 본문 |
| Body Small | Pretendard | 14px | 400 | 1.6 | 카드 설명, 테이블 내용 |
| Interactive Text | Pretendard | 14px | 500 | 1.0 | Nav 링크, 탭, 페이지네이션, Breadcrumb 현재 항목 |
| Label / Button | Pretendard | 14px | 600 | 1.0 | 버튼 텍스트, 강조 레이블 |
| Tag / Badge | Pretendard | 12px | 600 | 1.0 | 태그, 배지, Chip |
| Caption / Meta | Pretendard | 12px-13px | 400 | 1.0 | 메타데이터, 줄번호 |
| Inline Code | JetBrains Mono | 13px | 500 | inherit | 인라인 코드 |
| Code Block | JetBrains Mono | 14px | 400 | 1.8 | 코드 블록 |

### Principles
- **Galmuri11은 브랜딩 전용**: 제목과 레이블에서만 사용하여 8bit 감성을 포인트로 부여한다. 본문이나 UI 요소에 Galmuri를 사용하면 가독성이 떨어진다.
- **Pretendard가 기본**: 의심스러우면 Pretendard를 쓴다. 코드(코드 블록, 인라인 코드)만 예외로 JetBrains Mono를 쓴다.
- **Weight 절제**: Galmuri11은 700 단일 weight. Pretendard는 400(본문), 500(링크/탭 등 인터랙티브 텍스트), 600(레이블/버튼), 700(컴포넌트 제목) 네 가지만 사용.

## 5. Component Stylings

### Buttons

**Primary**
- Background: `var(--primary)`
- Text: `var(--bg)` (배경색)
- Padding: 10px 20px
- Radius: `var(--radius-md)`
- Font: Pretendard 14px weight 600
- Hover: background `var(--primary-hover)`

**Secondary (Outline)**
- Background: transparent
- Text: `var(--secondary)`
- Border: 1px solid `var(--secondary-dim-border)`
- Padding: 10px 20px
- Radius: `var(--radius-md)`
- Font: Pretendard 14px weight 600
- Hover: background `var(--secondary-dim)`

**Ghost**
- Background: transparent
- Text: `var(--text-secondary)`
- Border: 1px solid `var(--border)`
- Padding: 10px 20px
- Radius: `var(--radius-md)`
- Font: Pretendard 14px weight 600
- Hover: border `var(--border-hover)`, text `var(--text-primary)`

**Small variant**: font 13px, padding 6px 14px, radius `var(--radius-sm)`.

### Cards
- Background: `var(--surface)`
- Border: 1px solid `var(--border)`
- Radius: `var(--radius-lg)`
- Padding: 24px
- Hover: border-color `var(--primary-dim-border)`
- Card footer: `border-top: 1px solid var(--border)`, padding-top 16px, margin-top 16px

### Tags / Badges
- Font: Pretendard 12px weight 600
- Padding: 4px 10px
- Radius: `var(--radius-full)`
- Primary variant: text `var(--primary)`, background `var(--primary-dim)`
- Secondary variant: text `var(--secondary)`, background `var(--secondary-dim)`
- Success variant: text `var(--success)`, background `var(--success-dim)`

### Inputs
- Background: `var(--surface)`
- Border: 1px solid `var(--border)`
- Radius: `var(--radius-md)`
- Padding: 10px 16px
- Font: Pretendard 14px
- Text: `var(--text-primary)`
- Placeholder: `var(--text-muted)`
- Focus: border-color `var(--focus-ring)`

### Code Block
- Container: background `var(--surface)`, border 1px solid `var(--border)`, radius `var(--radius-lg)`
- Header bar: background `rgba(0,0,0,0.15)`, border-bottom 1px solid `var(--border)`
- Header에 트래픽 라이트 dots: Error(`var(--error)`), Warning(`var(--warning)`), Success(`var(--success)`)
- Body: JetBrains Mono 14px, line-height 1.8
- Syntax: keyword → `var(--primary)`, string → `var(--secondary)`, type → `var(--success)`, comment → `var(--text-muted)`
- Line numbers: `var(--text-muted)`, 28px 너비, 우측 정렬, margin-right 20px

### Inline Code
- Font: JetBrains Mono 13px weight 500
- Background: `var(--surface)`
- Border: 1px solid `var(--border)`
- Padding: 2px 8px
- Radius: `var(--radius-xs)`
- Text color: `var(--secondary)`

### Callout / Alert
- Radius: `var(--radius-lg)`
- Padding: 16px 20px
- Font: Pretendard 14px, line-height 1.6
- Primary callout: background `var(--primary-dim)`, border `var(--primary-dim-border)`
- Secondary callout: background `var(--secondary-dim)`, border `var(--secondary-dim-border)`

### Navigation
- Height: 56px
- Background: `var(--bg-glass)` + `backdrop-filter: blur(12px)` (글래스 효과)
- Border-bottom: 1px solid `var(--border)`
- Position: sticky top 0
- Logo: 32px, radius `var(--radius-md)`
- Logo text: Galmuri11 Bold 16px, color `var(--primary)`
- Links: Pretendard 14px weight 500, color `var(--text-secondary)`
- Active link: color `var(--primary)`, background `var(--primary-dim)`
- CTA: Small Primary button

### Table
- Container: border 1px solid `var(--border)`, radius `var(--radius-lg)`, overflow hidden
- Header: background `var(--surface)`
- th: Pretendard 14px weight 600, color `var(--text-secondary)`, padding 12px 16px
- td: Pretendard 14px, color `var(--text-primary)`, padding 12px 16px
- Row divider: border-bottom 1px solid `var(--border)` (마지막 행 제외)
- Row hover: background `var(--surface)`

### Toggle
- Markup: `<button type="button" role="switch" aria-checked="true|false">`
- Track: 44x24px, radius `var(--radius-lg)`
- Off: background `var(--border)`
- On: background `var(--primary)`
- Thumb: 18px, white, 3px inset

### Progress Bar
- Track: height 6px, background `var(--border)`, radius 3px
- Fill: gradient `linear-gradient(90deg, var(--primary), var(--secondary))`

### Avatar
- Size: 36px
- Radius: 50%
- Border: 2px solid `var(--bg)` (배경색, 스택 겹침용)
- Stack: margin-left -8px (첫번째 제외)

### Status Dot
- Size: 8px
- Radius: 50%
- Info: `var(--info)`, Success: `var(--success)`, Warning: `var(--warning)`, Error: `var(--error)`
- 점만 단독으로 쓰지 않는다. 옆에 텍스트 레이블을 두거나, 최소한 `title`과 `aria-label`로 상태 이름을 제공한다.

### Tabs
- Container: border-bottom 1px solid `var(--border)`
- Tab item: Pretendard 14px weight 500, color `var(--text-muted)`
- Active: color `var(--primary)`, border-bottom 2px solid `var(--primary)`
- Hover: color `var(--text-secondary)`
- Padding: 10px 20px

### Pagination
- Item: min-width 36px, height 36px, radius `var(--radius-md)`
- Font: Pretendard 14px weight 500, color `var(--text-secondary)`
- Hover: background `var(--surface)`, border 1px solid `var(--border)`, color `var(--text-primary)`
- Active: background `var(--primary)`, color `var(--bg)`, weight 600
- Disabled: opacity 0.4, pointer-events none
- Ellipsis: color `var(--text-muted)`
- Gap: 4px
- **Page Jump**: 현재 페이지가 editable input. 우상단에 연필 아이콘(16px circle, `var(--surface)` 배경, `var(--border)` 테두리) badge로 편집 가능 표시. Focus 시 배경 `var(--surface)`, 텍스트 `var(--primary)`, border `var(--focus-ring)`로 전환.
- **Page Jump 동작**:
  - 숫자만 허용 (`inputmode="numeric"` + 입력 시 non-digit 제거)
  - Focus 시 값을 비워 즉시 입력 가능한 상태로 전환
  - 빈 값으로 blur되면 원래 페이지 번호로 복원 (의도치 않은 포커스로 값이 사라지는 것 방지)
  - Enter 키로 확정 (blur 트리거)

### Breadcrumb
- Font: Pretendard 14px
- Links: color `var(--text-muted)`, hover color `var(--primary)`
- Separator: `/`, color `var(--text-muted)`, font-size 12px
- Current: color `var(--text-primary)`, weight 500

### Dropdown Menu
- Container: background `var(--surface)`, border 1px solid `var(--border)`, radius `var(--radius-md)`, padding 4px
- Item: Pretendard 14px, padding 8px 12px, radius `var(--radius-sm)`
- Item hover: background `var(--surface-hover)`, color `var(--text-primary)`
- Active item: color `var(--primary)`
- Destructive item: color `var(--error)`

### Select (Native)
- appearance: none
- Background: `var(--surface)`, border 1px solid `var(--border)`, radius `var(--radius-md)`
- Padding: 10px 40px 10px 16px (우측에 화살표 공간)
- Font: Pretendard 14px
- Focus: border-color `var(--focus-ring)`

### Checkbox
- Size: 18px, radius `var(--radius-xs)`
- Unchecked: background `var(--surface)`, border `var(--border)`
- Checked: background `var(--primary)`, border `var(--primary)`, 체크 아이콘 (배경색)
- Focus: 전역 포커스 링

### Radio
- Size: 18px, radius 50%
- Unchecked: background `var(--surface)`, border `var(--border)`
- Checked: border `var(--primary)`, inner dot `box-shadow: inset 0 0 0 4px var(--primary)`
- Focus: 전역 포커스 링

### Textarea
- 기본 Input과 동일한 스타일
- min-height: 100px
- resize: vertical
- line-height: 1.6

### Modal / Dialog
- Overlay: background `var(--overlay)`, `backdrop-filter: blur(4px)`
- Container: background `var(--surface)`, border 1px solid `var(--border)`, radius `var(--radius-lg)`, max-width 480px
- Header: padding 20px 24px, border-bottom, title Pretendard 15px weight 700
- Close button: 32px, border 1px solid `var(--border)`, radius `var(--radius-sm)`
- Body: padding 24px, Pretendard 14px, color `var(--text-secondary)`
- Footer: padding 16px 24px, border-top, 버튼 우측 정렬

### Toast / Notification
- Container: padding 12px 16px, radius `var(--radius-md)`, border 1px solid
- Icon: 20px circle, 배경 틴트 + 아이콘 색상
- Message: Pretendard 14px, color `var(--text-primary)`
- Info: border `var(--info-dim-border)`, background `var(--info-subtle)`
- Success: border `var(--success-dim-border)`, background `var(--success-subtle)`
- Warning: border `var(--warning-dim-border)`, background `var(--warning-subtle)`
- Error: border `var(--error-dim-border)`, background `var(--error-subtle)`

### Tooltip
- Background: `var(--text-primary)`, color `var(--bg)`
- Font: Pretendard 12px weight 500
- Padding: 6px 12px, radius `var(--radius-sm)`
- Arrow: 5px border trick
- Trigger: text에 border-bottom 1px dashed

### Blockquote
- Border-left: 3px solid `var(--primary)`
- Background: `var(--primary-dim)`
- Padding: 12px 20px
- Radius: `0 var(--radius-md) var(--radius-md) 0`
- Font: Pretendard 15px, line-height 1.7, color `var(--text-secondary)`

### List (ul/ol)
- Padding-left: 24px
- Font: Pretendard 15px, line-height 1.8, color `var(--text-secondary)`
- Marker color: `var(--primary)`

### Sidebar Navigation
- Width: 240px, background `var(--surface)`, border-right 1px solid `var(--border)`
- Logo: Galmuri11 Bold 15px, color `var(--primary)`
- Section label: Pretendard 11px weight 600, uppercase, letter-spacing 1px, color `var(--text-muted)`
- Link: Pretendard 14px, padding 8px 12px, radius `var(--radius-sm)`
- Active link: background `var(--primary-dim)`, color `var(--primary)`
- Hover: background `var(--surface-hover)`

### Accordion
- Container: border 1px solid `var(--border)`, radius `var(--radius-lg)`
- Item divider: border-bottom 1px solid `var(--border)`
- Trigger: Pretendard 15px weight 600, padding 16px 20px
- Trigger hover: background `var(--surface)`
- Icon: 화살표, open 시 180도 회전
- Body: Pretendard 14px, color `var(--text-secondary)`, padding 4px 20px 16px

### Skeleton Loading
- Background: `var(--border)`
- Radius: `var(--radius-sm)`
- Animation: pulse (opacity 0.4 → 0.8), 1.5s ease-in-out infinite
- Card container: background `var(--surface)` + border `var(--border)`

### Empty State
- Container: border 1px dashed `var(--border)`, radius `var(--radius-lg)`, padding 64px 32px
- Text-align: center
- Title: Pretendard 17px weight 700
- Description: Pretendard 14px, color `var(--text-muted)`
- CTA: Primary button

## 6. Layout Principles

### Spacing
- Base unit: 4px
- Scale: 4, 6, 8, 10, 12, 16, 20, 24, 32, 40, 48, 64, 80, 96px
- 컴포넌트 내부: 주로 8-24px
- 섹션 간: 64px (padding top/bottom)
- 히어로: 96px top, 80px bottom

### Grid & Container
- Max content width: 1080px (일반 섹션), 800px (히어로, 텍스트 중심)
- 카드 그리드: `grid-template-columns: repeat(auto-fit, minmax(300px, 1fr))`, gap 16px
- 수평 padding: 32px

### Divider
- `border-top: 1px solid var(--border)`
- 섹션 사이에 사용, max-width 1016px, 좌우 auto margin

### Border Radius Scale
- `--radius-xs` (4px): 인라인 코드, 체크박스
- `--radius-sm` (6px): 작은 버튼, 드롭다운 항목, 툴팁
- `--radius-md` (8px): 버튼, 입력 필드, 로고
- `--radius-lg` (12px): 카드, 코드 블록, 테이블, callout, 모달
- `--radius-full` (9999px): 태그, 배지, 히어로 배지
- Circle (50%): 아바타, 상태 점, 토글 thumb

## 7. Depth & Elevation

이 디자인 시스템은 shadow 대신 border 기반 depth를 사용한다.

| Level | Treatment | Use |
|-------|-----------|-----|
| Flat (Level 0) | 없음 | 페이지 배경 |
| Surface (Level 1) | background `var(--surface)` + border `var(--border)` | 카드, 코드 블록, 입력 필드 |
| Glass (Level 2) | background `var(--bg-glass)` + `backdrop-filter: blur(12px)` | 고정 네비게이션 |
| Hover (Level 1+) | border-color → `var(--primary-dim-border)` | 카드 호버 |

**Shadow 미사용 원칙**: 따뜻한 다크 배경 위에서는 shadow보다 border가 더 자연스럽다. 깊이는 배경색 차이(BG → Surface)와 border로 표현한다.

### Z-index Scale

| Token | Value | Use |
|-------|-------|-----|
| `--z-base` | 0 | 기본 콘텐츠 |
| `--z-dropdown` | 100 | 드롭다운 메뉴, 셀렉트 팝업 |
| `--z-sticky` | 200 | 고정 네비게이션, sticky 요소 |
| `--z-overlay` | 300 | 모달 배경 오버레이 |
| `--z-modal` | 400 | 모달 다이얼로그 |
| `--z-toast` | 500 | 토스트 알림 |
| `--z-tooltip` | 600 | 툴팁 |

## 8. Do's and Don'ts

### Do
- Galmuri11은 반드시 `font-weight: 700` (Bold)으로만 사용한다
- Galmuri11은 페이지 제목(h1-h3), 섹션 레이블, Stat 숫자, 로고 텍스트에만 사용한다
- 가독성이 필요한 모든 곳에 Pretendard를 사용한다 (태그, 버튼 포함). 코드에만 JetBrains Mono를 사용한다
- 배경색은 `var(--bg)`를 사용한다 (순수 `#000000` 아님)
- 텍스트는 `var(--text-primary)`를 사용한다 (순수 `#FFFFFF` 아님) — 따뜻한 톤 유지
- Primary(`var(--primary)`)는 CTA, 링크, 활성 상태 등 "행동 유도" 요소에 사용한다
- Secondary(`var(--secondary)`)는 보조 강조, 태그, 인라인 코드에 사용한다
- 태그/배지는 `-dim` 토큰 배경 + 액센트 텍스트 조합을 사용한다
- 카드 호버에는 `border-color: var(--primary-dim-border)`를 사용한다

### Don't
- Galmuri11을 Regular(400) weight로 사용하지 않는다
- Galmuri11을 본문, 버튼, 태그, 코드 블록, placeholder 등에 사용하지 않는다
- `#000000` 순수 블랙을 배경에 사용하지 않는다 — 항상 따뜻한 다크 사용
- `#FFFFFF` 순수 화이트를 텍스트에 사용하지 않는다 — 항상 따뜻한 화이트 사용
- Primary와 Secondary를 장식적으로 남용하지 않는다 — 기능적 의미가 있어야 한다
- Shadow를 깊이 표현에 사용하지 않는다 — border와 배경색 차이로 표현한다
- 라이트 모드를 만들지 않는다 — 이 시스템은 다크 모드 전용이다
- 텍스트에 Pretendard 800-900 weight를 사용하지 않는다 — 최대 700

## 9. Responsive Behavior

### Breakpoints
| Name | Width | Key Changes |
|------|-------|-------------|
| Mobile | < 640px | 단일 컬럼, 히어로 32px, 네비 햄버거 |
| Tablet | 640-1024px | 2컬럼 카드 그리드 시작 |
| Desktop | > 1024px | 풀 레이아웃, max-width 적용 |

### Collapsing Strategy
- Hero heading: 44px → 32px (모바일)
- Section title: 28px → 22px (모바일)
- 수평 padding: 32px → 20px (모바일)
- 카드 그리드: 3컬럼 → 2컬럼 → 1컬럼
- 네비게이션: 수평 링크 → 햄버거 메뉴 (모바일)
- Stats: 4컬럼 → 2x2 그리드 (모바일)
- 섹션 간격: 64px → 48px (모바일)

### Touch Targets
- 버튼 최소 높이: 40px
- 탭/링크 padding: 최소 6px 14px
- 토글: 44x24px (충분한 터치 영역)

## 10. Agent Prompt Guide

### Token Setup
- 작업을 시작할 때 [Design Tokens](#2-design-tokens)의 토큰 블록을 프로젝트 전역 CSS의 `:root`에 그대로 복사한다.
- 자주 쓰는 토큰: 배경 `--bg`, 카드 `--surface`, 테두리 `--border`, 제목 `--text-primary`, 본문 `--text-secondary`, CTA `--primary`, 보조 강조 `--secondary`

### Font Quick Reference
- 페이지 제목/섹션 레이블: `font-family: var(--font-heading); font-weight: 700;`
- 코드: `font-family: var(--font-mono);`
- 그 외 전부: `font-family: var(--font-body);`

### Example Component Prompts
- "히어로 섹션을 만들어줘. 배경 `var(--bg)`. 제목은 Galmuri11 Bold 44px, 색상 `var(--text-primary)`, 강조 단어는 `var(--primary)`. 설명은 Pretendard 18px, 색상 `var(--text-secondary)`. Primary 버튼(`var(--primary)` 배경, `var(--bg)` 텍스트, radius `var(--radius-md)`)과 Ghost 버튼(transparent, `var(--border)` border)."
- "프로젝트 카드를 만들어줘. 배경 `var(--surface)`, border 1px solid `var(--border)`, radius `var(--radius-lg)`, padding 24px. 태그는 Pretendard 12px weight 600, `var(--primary)` 텍스트, `var(--primary-dim)` 배경, radius `var(--radius-full)`. 제목 Pretendard 17px weight 700. 설명 Pretendard 14px `var(--text-secondary)`. 호버 시 border-color `var(--primary-dim-border)`."
- "코드 블록을 만들어줘. 컨테이너: `var(--surface)` 배경, `var(--border)` border, radius `var(--radius-lg)`. 헤더에 트래픽 라이트 dots(`var(--error)`, `var(--warning)`, `var(--success)`)와 파일명. 본문 JetBrains Mono 14px line-height 1.8. 키워드 `var(--primary)`, 문자열 `var(--secondary)`, 주석 `var(--text-muted)`."
- "네비게이션 바를 만들어줘. 높이 56px, sticky top. 배경 `var(--bg-glass)` + backdrop-filter blur(12px). 왼쪽에 로고 32px + Galmuri11 Bold 16px `var(--primary)` 텍스트. 링크는 Pretendard 14px weight 500 `var(--text-secondary)`, active는 `var(--primary)` + `var(--primary-dim)` 배경."

### Iteration Guide
1. 항상 Galmuri11은 Bold(700)으로만, 페이지 제목/섹션 레이블에만 적용
2. 의심스러우면 Pretendard를 쓴다 — 가독성이 최우선
3. 순수 블랙/화이트 대신 따뜻한 변형 사용 (`var(--bg)` / `var(--text-primary)`)
4. 깊이는 shadow 없이 border + 배경색 차이로 표현
5. 액센트 색상은 기능적 맥락에서만 사용 (CTA, 상태, 링크)
6. Dim 배경은 `-dim` 토큰으로 — 불투명 색상을 사용하지 않음
7. 색상, 폰트, radius, z-index는 hex나 숫자 대신 토큰으로 참조
