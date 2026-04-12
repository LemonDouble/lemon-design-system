# LemonDouble Design System

## 1. Visual Theme & Atmosphere

LemonDouble Design System은 개인 프로젝트 전반에 일관된 브랜드 아이덴티티를 부여하기 위한 다크 모드 기반 디자인 시스템이다. 로고에서 추출한 골든 옐로우(`#F0B90B`)와 코랄 레드(`#CD6B5E`)를 핵심 액센트로, 로고의 다크 브라운에서 파생된 따뜻한 다크 배경(`#12100E`)을 기반으로 한다. 순수 블랙이 아닌 미세한 따뜻함이 깔린 배경은 로고와 자연스러운 색상 연속성을 만든다.

타이포그래피는 이중 폰트 시스템을 사용한다. 제목과 탭 등 브랜딩 요소에는 8bit 픽셀 폰트 **Galmuri11**을 Bold(700) 전용으로 사용하고, 그 외 본문, 버튼, 태그, 코드 블록 등 가독성이 필요한 모든 곳에는 **Pretendard**를 사용한다. Galmuri11은 레트로 게임 감성을 부여하면서도 Pretendard와의 조합으로 모던한 느낌을 동시에 유지한다.

**Key Characteristics:**
- 로고에서 추출한 골든 옐로우 + 코랄 레드 듀오톤 액센트
- 로고 다크 브라운 파생 따뜻한 다크 배경 (`#12100E`, 순수 블랙이 아님)
- Galmuri11 Bold(700) 전용 — 제목, 탭, 섹션 레이블에만 사용
- Pretendard — 본문, 버튼, 태그, 코드 블록, 인라인 코드 등 나머지 전부
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
  - Color: Text Muted (`#5C524A`) 기본, 호버 시 Text Primary (`#F5F0EB`)
  - **예외 — Twitter**: Simple Icons의 X 로고 대신 `images/twitter-bird.svg`(클래식 트위터 새 로고)를 사용한다. `fill: currentColor`로 되어 있어 CSS 색상을 따른다.
- **기술 스택 아이콘**: [devicon](https://devicon.dev/) — 블로그 등 기술 스택 표시 용도 (보조).

## 2. Color Palette & Roles

### Brand (로고에서 추출)
- **Lemon Yellow** (`#F0B90B`): Primary. CTA 버튼, 링크, 강조 텍스트, 활성 상태, 섹션 제목 색상.
- **Coral Red** (`#CD6B5E`): Secondary. 보조 강조, 태그 배경, 인라인 코드 텍스트, 보조 버튼.

### Background & Surface
- **BG Dark** (`#12100E`): 페이지 배경. 로고의 다크 브라운(`#5C4A42`)에서 파생, 미세한 따뜻함.
- **Surface** (`#1C1816`): 카드, 코드 블록, 입력 필드 배경.
- **Surface Hover** (`#231E1B`): Surface 요소 호버 상태.

### Border
- **Border** (`#2E2723`): 카드 테두리, 구분선, 입력 필드 테두리.
- **Border Hover** (`#3D3530`): 호버 상태의 테두리.

### Text
- **Text Primary** (`#F5F0EB`): 제목, 카드 제목, 주요 텍스트. 순백이 아닌 미세한 따뜻함.
- **Text Secondary** (`#A89E95`): 본문, 설명, 부가 텍스트.
- **Text Muted** (`#5C524A`): 메타데이터, 비활성 텍스트, 줄번호, placeholder.

### Accent Dim (배경 틴트용)
- **Primary Dim** (`rgba(240, 185, 11, 0.12)`): Primary 배지/태그 배경.
- **Primary Dim Border** (`rgba(240, 185, 11, 0.25)`): Primary 요소 테두리, 호버 카드 테두리.
- **Secondary Dim** (`rgba(205, 107, 94, 0.12)`): Secondary 배지/태그 배경.
- **Secondary Dim Border** (`rgba(205, 107, 94, 0.25)`): Secondary 요소 테두리.

### Semantic
- **Info** (`#60A5FA`): 안내, 정보, 알림 상태.
- **Success** (`#4ADE80`): 정상, 활성, 완료 상태.
- **Warning** (`#FACC15`): 경고, 진행 중 상태.
- **Error** (`#EF4444`): 에러, 삭제, 위험 상태.

### Disabled State
- **Opacity**: `0.4` — 모든 비활성 요소에 일괄 적용
- **Cursor**: `not-allowed`
- **Pointer Events**: `none`
- 적용 대상: 버튼, 입력 필드, 토글, 체크박스, 라디오, 셀렉트
- 입력 필드 비활성: 배경 Surface, 텍스트 Text Muted + opacity 0.4

## 3. Typography Rules

### Font Family
- **Heading**: `Galmuri11`, fallback: `monospace`
  - CDN: `https://cdn.jsdelivr.net/npm/galmuri/dist/galmuri.css`
- **Body**: `Pretendard`, fallback: `-apple-system, BlinkMacSystemFont, sans-serif`
  - CDN: `https://cdnjs.cloudflare.com/ajax/libs/pretendard/1.3.9/static/pretendard.min.css`

### Galmuri11 사용 규칙
- **반드시 font-weight: 700 (Bold)로만 사용한다.** Regular(400) 사용 금지.
- 적용 범위: h1, h2, h3 제목 / 탭 레이블 / 섹션 레이블 (소제목 위 카테고리) / Stat 숫자 (큰 강조 숫자)
- 그 외 어떤 곳에도 Galmuri11을 사용하지 않는다.

### Hierarchy

| Role | Font | Size | Weight | Line Height | Notes |
|------|------|------|--------|-------------|-------|
| Hero Heading | Galmuri11 | 44px | 700 | 1.2 | 히어로 섹션 메인 제목 |
| Section Title | Galmuri11 | 28px | 700 | 1.3 | 섹션 제목 |
| Card/Sub Title | Galmuri11 | 20px | 700 | 1.4 | 카드 헤딩, 소제목 |
| Section Label | Galmuri11 | 12px | 700 | 1.0 | 섹션 위 카테고리 레이블, letter-spacing: 1.5px, uppercase |
| Tab Label | Galmuri11 | 14px | 700 | 1.0 | 네비게이션 탭 |
| Stat Number | Galmuri11 | 32px | 700 | 1.0 | 숫자 강조 카드 |
| Body Large | Pretendard | 18px | 400 | 1.7 | 히어로 설명, 긴 본문 |
| Body | Pretendard | 16px | 400 | 1.6 | 표준 본문 |
| Body Small | Pretendard | 14px | 400 | 1.6 | 카드 설명, 테이블 내용 |
| Label / Button | Pretendard | 14px | 600 | 1.0 | 버튼 텍스트, 강조 레이블 |
| Tag / Badge | Pretendard | 12px | 600 | 1.0 | 태그, 배지, Chip |
| Caption / Meta | Pretendard | 12px-13px | 400 | 1.0 | 메타데이터, 줄번호 |
| Inline Code | Pretendard | 13px | 600 | inherit | 인라인 코드 (Galmuri 아님) |
| Code Block | Pretendard | 14px | 400 | 1.8 | 코드 블록 (Galmuri 아님), tabular-nums |

### Principles
- **Galmuri11은 브랜딩 전용**: 제목과 레이블에서만 사용하여 8bit 감성을 포인트로 부여한다. 본문이나 UI 요소에 Galmuri를 사용하면 가독성이 떨어진다.
- **Pretendard가 기본**: 의심스러우면 Pretendard를 쓴다. 코드 블록도, 인라인 코드도, 태그도 전부 Pretendard.
- **Weight 절제**: Galmuri11은 700 단일 weight. Pretendard는 400(본문), 600(레이블/버튼), 700(카드 제목) 세 가지만 사용.

## 4. Component Stylings

### Buttons

**Primary**
- Background: `#F0B90B`
- Text: `#12100E` (배경색)
- Padding: 10px 20px
- Radius: 8px
- Font: Pretendard 14px weight 600
- Hover: background `#D4A30A`

**Secondary (Outline)**
- Background: transparent
- Text: `#CD6B5E`
- Border: 1px solid `rgba(205, 107, 94, 0.25)`
- Padding: 10px 20px
- Radius: 8px
- Font: Pretendard 14px weight 600
- Hover: background `rgba(205, 107, 94, 0.12)`

**Ghost**
- Background: transparent
- Text: `#A89E95`
- Border: 1px solid `#2E2723`
- Padding: 10px 20px
- Radius: 8px
- Font: Pretendard 14px weight 600
- Hover: border `#3D3530`, text `#F5F0EB`

**Small variant**: font 13px, padding 6px 14px, radius 6px.

### Cards
- Background: `#1C1816`
- Border: 1px solid `#2E2723`
- Radius: 12px
- Padding: 24px
- Hover: border-color `rgba(240, 185, 11, 0.25)`
- Card footer: `border-top: 1px solid #2E2723`, padding-top 16px, margin-top 16px

### Tags / Badges
- Font: Pretendard 12px weight 600
- Padding: 4px 10px
- Radius: 9999px (full pill)
- Primary variant: text `#F0B90B`, background `rgba(240, 185, 11, 0.12)`
- Secondary variant: text `#CD6B5E`, background `rgba(205, 107, 94, 0.12)`
- Success variant: text `#4ADE80`, background `rgba(74, 222, 128, 0.1)`

### Inputs
- Background: `#1C1816`
- Border: 1px solid `#2E2723`
- Radius: 8px
- Padding: 10px 16px
- Font: Pretendard 14px
- Text: `#F5F0EB`
- Placeholder: `#5C524A`
- Focus: border-color `rgba(240, 185, 11, 0.25)`

### Code Block
- Container: background `#1C1816`, border 1px solid `#2E2723`, radius 12px
- Header bar: background `rgba(0,0,0,0.15)`, border-bottom 1px solid `#2E2723`
- Header에 트래픽 라이트 dots: Error(`#EF4444`), Warning(`#FACC15`), Success(`#4ADE80`)
- Body: Pretendard 14px, line-height 1.8, tabular-nums
- Syntax: keyword → `#F0B90B` (Primary), string → `#CD6B5E` (Secondary), type → `#4ADE80` (Success), comment → `#5C524A` (Text Muted)
- Line numbers: `#5C524A`, 28px 너비, 우측 정렬, margin-right 20px

### Inline Code
- Font: Pretendard 13px weight 600 (Galmuri 아님)
- Background: `#1C1816`
- Border: 1px solid `#2E2723`
- Padding: 2px 8px
- Radius: 4px
- Text color: `#CD6B5E` (Secondary)

### Callout / Alert
- Radius: 10px
- Padding: 16px 20px
- Font: Pretendard 14px, line-height 1.6
- Primary callout: background `rgba(240, 185, 11, 0.12)`, border `rgba(240, 185, 11, 0.25)`
- Secondary callout: background `rgba(205, 107, 94, 0.12)`, border `rgba(205, 107, 94, 0.25)`

### Navigation
- Height: 56px
- Background: `rgba(18, 16, 14, 0.85)` + `backdrop-filter: blur(12px)` (글래스 효과)
- Border-bottom: 1px solid `#2E2723`
- Position: sticky top 0
- Logo: 32px, radius 8px
- Logo text: Galmuri11 Bold 16px, color Primary
- Links: Pretendard 14px weight 500, color Text Secondary
- Active link: color Primary, background Primary Dim
- CTA: Small Primary button

### Table
- Container: border 1px solid `#2E2723`, radius 12px, overflow hidden
- Header: background `#1C1816`
- th: Pretendard 14px weight 600, color Text Secondary, padding 12px 16px
- td: Pretendard 14px, color Text Primary, padding 12px 16px
- Row divider: border-bottom 1px solid `#2E2723` (마지막 행 제외)
- Row hover: background `#1C1816`

### Toggle
- Track: 44x24px, radius 12px
- Off: background `#2E2723`
- On: background `#F0B90B`
- Thumb: 18px, white, 3px inset

### Progress Bar
- Track: height 6px, background `#2E2723`, radius 3px
- Fill: gradient `linear-gradient(90deg, #F0B90B, #CD6B5E)`

### Avatar
- Size: 36px
- Radius: 50%
- Border: 2px solid `#12100E` (배경색, 스택 겹침용)
- Stack: margin-left -8px (첫번째 제외)

### Status Dot
- Size: 8px
- Radius: 50%
- Info: `#60A5FA`, Success: `#4ADE80`, Warning: `#FACC15`, Error: `#EF4444`

### Tabs
- Container: border-bottom 1px solid `#2E2723`
- Tab item: Pretendard 14px weight 500, color Text Muted
- Active: color Primary, border-bottom 2px solid Primary
- Hover: color Text Secondary
- Padding: 10px 20px

### Pagination
- Item: min-width 36px, height 36px, radius 8px
- Font: Pretendard 14px weight 500, color Text Secondary
- Hover: background Surface, border 1px solid Border, color Text Primary
- Active: background Primary, color BG, weight 600
- Disabled: opacity 0.4, pointer-events none
- Ellipsis: color Text Muted
- Gap: 4px

### Breadcrumb
- Font: Pretendard 14px
- Links: color Text Muted, hover color Primary
- Separator: `/`, color Text Muted, font-size 12px
- Current: color Text Primary, weight 500

### Dropdown Menu
- Container: background Surface, border 1px solid `#2E2723`, radius 8px, padding 4px
- Item: Pretendard 14px, padding 8px 12px, radius 6px
- Item hover: background Surface Hover, color Text Primary
- Active item: color Primary
- Destructive item: color Error

### Select (Native)
- appearance: none
- Background: Surface, border 1px solid `#2E2723`, radius 8px
- Padding: 10px 40px 10px 16px (우측에 화살표 공간)
- Font: Pretendard 14px
- Focus: border-color Primary Dim Border

### Checkbox
- Size: 18px, radius 4px
- Unchecked: background Surface, border `#2E2723`
- Checked: background Primary, border Primary, 체크 아이콘 (배경색)
- Focus: outline 2px solid Primary Dim Border

### Radio
- Size: 18px, radius 50%
- Unchecked: background Surface, border `#2E2723`
- Checked: border Primary, inner dot `box-shadow: inset 0 0 0 4px Primary`
- Focus: outline 2px solid Primary Dim Border

### Textarea
- 기본 Input과 동일한 스타일
- min-height: 100px
- resize: vertical
- line-height: 1.6

### Modal / Dialog
- Overlay: background `rgba(0,0,0,0.6)`, `backdrop-filter: blur(4px)`
- Container: background Surface, border 1px solid `#2E2723`, radius 12px, max-width 480px
- Header: padding 20px 24px, border-bottom, title Pretendard 15px weight 700
- Close button: 32px, border 1px solid `#2E2723`, radius 6px
- Body: padding 24px, Pretendard 14px, color Text Secondary
- Footer: padding 16px 24px, border-top, 버튼 우측 정렬

### Toast / Notification
- Container: padding 12px 16px, radius 8px, border 1px solid
- Icon: 20px circle, 배경 틴트 + 아이콘 색상
- Message: Pretendard 14px, color Text Primary
- Info: border `rgba(96,165,250,0.25)`, background `rgba(96,165,250,0.06)`
- Success: border `rgba(74,222,128,0.25)`, background `rgba(74,222,128,0.06)`
- Warning: border `rgba(250,204,21,0.25)`, background `rgba(250,204,21,0.06)`
- Error: border `rgba(239,68,68,0.25)`, background `rgba(239,68,68,0.06)`

### Tooltip
- Background: Text Primary (`#F5F0EB`), color BG (`#12100E`)
- Font: Pretendard 12px weight 500
- Padding: 6px 12px, radius 6px
- Arrow: 5px border trick
- Trigger: text에 border-bottom 1px dashed

### Blockquote
- Border-left: 3px solid Primary
- Background: Primary Dim
- Padding: 12px 20px
- Radius: 0 8px 8px 0
- Font: Pretendard 15px, line-height 1.7, color Text Secondary

### List (ul/ol)
- Padding-left: 24px
- Font: Pretendard 15px, line-height 1.8, color Text Secondary
- Marker color: Primary

### Sidebar Navigation
- Width: 240px, background Surface, border-right 1px solid `#2E2723`
- Logo: Galmuri11 Bold 15px, color Primary
- Section label: Pretendard 11px weight 600, uppercase, letter-spacing 1px, color Text Muted
- Link: Pretendard 14px, padding 8px 12px, radius 6px
- Active link: background Primary Dim, color Primary
- Hover: background Surface Hover

### Accordion
- Container: border 1px solid `#2E2723`, radius 12px
- Item divider: border-bottom 1px solid `#2E2723`
- Trigger: Pretendard 15px weight 600, padding 16px 20px
- Trigger hover: background Surface
- Icon: 화살표, open 시 180도 회전
- Body: Pretendard 14px, color Text Secondary, padding 4px 20px 16px

### Skeleton Loading
- Background: `#2E2723` (Border 색상)
- Radius: 6px
- Animation: pulse (opacity 0.4 → 0.8), 1.5s ease-in-out infinite
- Card container: Surface background + Border

### Empty State
- Container: border 1px dashed `#2E2723`, radius 12px, padding 64px 32px
- Text-align: center
- Title: Pretendard 17px weight 700
- Description: Pretendard 14px, color Text Muted
- CTA: Primary button

## 5. Layout Principles

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
- `border-top: 1px solid #2E2723`
- 섹션 사이에 사용, max-width 1016px, 좌우 auto margin

### Border Radius Scale
- Small (4px): 인라인 코드, 작은 요소
- Medium (6px): 작은 버튼
- Standard (8px): 버튼, 입력 필드, 로고
- Large (12px): 카드, 코드 블록, 테이블, callout
- Pill (9999px): 태그, 배지, 히어로 배지
- Circle (50%): 아바타, 상태 점, 토글 thumb

## 6. Depth & Elevation

이 디자인 시스템은 shadow 대신 border 기반 depth를 사용한다.

| Level | Treatment | Use |
|-------|-----------|-----|
| Flat (Level 0) | 없음 | 페이지 배경 |
| Surface (Level 1) | background `#1C1816` + border `#2E2723` | 카드, 코드 블록, 입력 필드 |
| Glass (Level 2) | background `rgba(18,16,14,0.85)` + `backdrop-filter: blur(12px)` | 고정 네비게이션 |
| Hover (Level 1+) | border-color → `rgba(240,185,11,0.25)` | 카드 호버 |

**Shadow 미사용 원칙**: 따뜻한 다크 배경 위에서는 shadow보다 border가 더 자연스럽다. 깊이는 배경색 차이(BG → Surface)와 border로 표현한다.

### Z-index Scale

| Token | Value | Use |
|-------|-------|-----|
| `z-base` | 0 | 기본 콘텐츠 |
| `z-dropdown` | 100 | 드롭다운 메뉴, 셀렉트 팝업 |
| `z-sticky` | 200 | 고정 네비게이션, sticky 요소 |
| `z-overlay` | 300 | 모달 배경 오버레이 |
| `z-modal` | 400 | 모달 다이얼로그 |
| `z-toast` | 500 | 토스트 알림 |
| `z-tooltip` | 600 | 툴팁 |

## 7. Do's and Don'ts

### Do
- Galmuri11은 반드시 `font-weight: 700` (Bold)으로만 사용한다
- Galmuri11은 제목(h1-h3), 탭 레이블, 섹션 레이블, Stat 숫자에만 사용한다
- 가독성이 필요한 모든 곳에 Pretendard를 사용한다 (태그, 코드, 버튼 포함)
- 배경색은 `#12100E`를 사용한다 (순수 `#000000` 아님)
- 텍스트는 `#F5F0EB`를 사용한다 (순수 `#FFFFFF` 아님) — 따뜻한 톤 유지
- Primary(`#F0B90B`)는 CTA, 링크, 활성 상태 등 "행동 유도" 요소에 사용한다
- Secondary(`#CD6B5E`)는 보조 강조, 태그, 인라인 코드에 사용한다
- 태그/배지는 Dim 배경(`rgba` 투명도) + 액센트 텍스트 조합을 사용한다
- 카드 호버에는 `border-color: rgba(240, 185, 11, 0.25)` 를 사용한다

### Don't
- Galmuri11을 Regular(400) weight로 사용하지 않는다
- Galmuri11을 본문, 버튼, 태그, 코드 블록, placeholder 등에 사용하지 않는다
- `#000000` 순수 블랙을 배경에 사용하지 않는다 — 항상 따뜻한 다크 사용
- `#FFFFFF` 순수 화이트를 텍스트에 사용하지 않는다 — 항상 따뜻한 화이트 사용
- Primary와 Secondary를 장식적으로 남용하지 않는다 — 기능적 의미가 있어야 한다
- Shadow를 깊이 표현에 사용하지 않는다 — border와 배경색 차이로 표현한다
- 라이트 모드를 만들지 않는다 — 이 시스템은 다크 모드 전용이다
- 텍스트에 Pretendard 800-900 weight를 사용하지 않는다 — 최대 700

## 8. Responsive Behavior

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

## 9. Agent Prompt Guide

### Quick Color Reference
- Primary CTA: `#F0B90B` (Lemon Yellow)
- Secondary accent: `#CD6B5E` (Coral Red)
- Background: `#12100E` (Warm Dark)
- Surface: `#1C1816`
- Border: `#2E2723`
- Text heading: `#F5F0EB`
- Text body: `#A89E95`
- Text muted: `#5C524A`

### Font Quick Reference
- 제목/탭: `font-family: 'Galmuri11', monospace; font-weight: 700;`
- 그 외 전부: `font-family: 'Pretendard', -apple-system, BlinkMacSystemFont, sans-serif;`

### Example Component Prompts
- "히어로 섹션을 만들어줘. 배경 #12100E. 제목은 Galmuri11 Bold 44px, 색상 #F5F0EB, 강조 단어는 #F0B90B. 설명은 Pretendard 18px, 색상 #A89E95. Primary 버튼(#F0B90B 배경, #12100E 텍스트, 8px radius)과 Ghost 버튼(transparent, #2E2723 border)."
- "프로젝트 카드를 만들어줘. 배경 #1C1816, border 1px solid #2E2723, radius 12px, padding 24px. 태그는 Pretendard 12px weight 600, #F0B90B 텍스트, rgba(240,185,11,0.12) 배경, pill radius. 제목 Pretendard 17px weight 700. 설명 Pretendard 14px #A89E95. 호버 시 border-color rgba(240,185,11,0.25)."
- "코드 블록을 만들어줘. 컨테이너: #1C1816 배경, #2E2723 border, 12px radius. 헤더에 트래픽 라이트 dots(#EF4444, #FACC15, #4ADE80)와 파일명. 본문 Pretendard 14px line-height 1.8. 키워드 #F0B90B, 문자열 #CD6B5E, 주석 #5C524A."
- "네비게이션 바를 만들어줘. 높이 56px, sticky top. 배경 rgba(18,16,14,0.85) + backdrop-filter blur(12px). 왼쪽에 로고 32px + Galmuri11 Bold 16px #F0B90B 텍스트. 링크는 Pretendard 14px weight 500 #A89E95, active는 #F0B90B + rgba(240,185,11,0.12) 배경."

### Iteration Guide
1. 항상 Galmuri11은 Bold(700)으로만, 제목/탭/레이블에만 적용
2. 의심스러우면 Pretendard를 쓴다 — 가독성이 최우선
3. 순수 블랙/화이트 대신 따뜻한 변형 사용 (#12100E / #F5F0EB)
4. 깊이는 shadow 없이 border + 배경색 차이로 표현
5. 액센트 색상은 기능적 맥락에서만 사용 (CTA, 상태, 링크)
6. Dim 배경은 항상 rgba 투명도로 — 불투명 색상을 사용하지 않음
