---
name: Pokemon-Trader-Gos
colors:
  surface: '#fbf9f3'
  surface-dim: '#dbdad4'
  surface-bright: '#fbf9f3'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#f5f3ee'
  surface-container: '#f0eee8'
  surface-container-high: '#eae8e2'
  surface-container-highest: '#e4e2dd'
  on-surface: '#1b1c19'
  on-surface-variant: '#444748'
  inverse-surface: '#30312d'
  inverse-on-surface: '#f2f1eb'
  outline: '#747878'
  outline-variant: '#c4c7c7'
  surface-tint: '#5f5e5e'
  primary: '#000000'
  on-primary: '#ffffff'
  primary-container: '#1c1b1b'
  on-primary-container: '#858383'
  inverse-primary: '#c9c6c5'
  secondary: '#446464'
  on-secondary: '#ffffff'
  secondary-container: '#c4e6e6'
  on-secondary-container: '#496868'
  tertiary: '#000000'
  on-tertiary: '#ffffff'
  tertiary-container: '#210b4e'
  on-tertiary-container: '#8c79be'
  error: '#EF4444'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#e5e2e1'
  primary-fixed-dim: '#c9c6c5'
  on-primary-fixed: '#1c1b1b'
  on-primary-fixed-variant: '#474646'
  secondary-fixed: '#c7e9e8'
  secondary-fixed-dim: '#abcdcc'
  on-secondary-fixed: '#002020'
  on-secondary-fixed-variant: '#2d4c4c'
  tertiary-fixed: '#e9ddff'
  tertiary-fixed-dim: '#cfbcff'
  on-tertiary-fixed: '#210b4e'
  on-tertiary-fixed-variant: '#4d3c7c'
  background: '#fbf9f3'
  on-background: '#1b1c19'
  surface-variant: '#e4e2dd'
  surface-soft: '#FAF5E8'
  surface-card: '#F5F0E0'
  surface-strong: '#EBE6D6'
  brand-pink: '#FF4D8B'
  brand-teal: '#1A3A3A'
  brand-lavender: '#B8A4ED'
  brand-peach: '#FFB084'
  brand-ochre: '#E8B94A'
  brand-mint: '#A4D4C5'
  brand-coral: '#FF6B5A'
  success: '#22C55E'
  warning: '#F59E0B'
typography:
  title-lg:
    fontFamily: Noto Sans
    fontSize: 24px
    fontWeight: '700'
    lineHeight: '1.35'
    letterSpacing: -0.4px
  title-md:
    fontFamily: Noto Sans
    fontSize: 20px
    fontWeight: '700'
    lineHeight: '1.4'
    letterSpacing: -0.3px
  title-sm:
    fontFamily: Noto Sans
    fontSize: 16px
    fontWeight: '600'
    lineHeight: '1.4'
    letterSpacing: 0px
  body-md:
    fontFamily: Noto Sans
    fontSize: 16px
    fontWeight: '400'
    lineHeight: '1.55'
    letterSpacing: 0px
  body-sm:
    fontFamily: Noto Sans
    fontSize: 14px
    fontWeight: '400'
    lineHeight: '1.5'
    letterSpacing: 0px
  caption:
    fontFamily: Noto Sans
    fontSize: 13px
    fontWeight: '500'
    lineHeight: '1.45'
    letterSpacing: 0px
  button:
    fontFamily: Noto Sans
    fontSize: 14px
    fontWeight: '700'
    lineHeight: '1.4'
    letterSpacing: 0px
  nav-link:
    fontFamily: Noto Sans
    fontSize: 14px
    fontWeight: '600'
    lineHeight: '1.4'
    letterSpacing: 0px
rounded:
  sm: 0.25rem
  DEFAULT: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  full: 9999px
spacing:
  gutter: 0.75rem
  margin: 1rem
  space-xs: 0.25rem
  space-sm: 0.5rem
  space-md: 1rem
  space-lg: 1.5rem
  space-xl: 2rem
---

## Brand & Style

This design system supports a mobile-first physical Pokémon card marketplace where collectors buy inspected cards, open random packs, and manage storage, shipping, and buyback. The visual direction pairs a bright ivory canvas with warm, tactile surfaces and playful, high-contrast accent colors—evoking the feeling of a physical collector's binder brought to life in a modern, approachable digital space.

The style blends **Corporate / Modern** clarity with **Tactile** warmth:
- **Clarity & Trust:** High-contrast ink typography (`#0A0A0A`) and clean, flat layouts ensure that card prices, inspection statuses, and transaction confirmations are immediately scannable.
- **Tactile Warmth:** Bright ivory (`#FFFDF7`) and warm cream surfaces (`#FAF5E8`, `#F5F0E0`) frame physical card photography without competing with the artwork.
- **Playful Accents:** Distinct pastel and jewel tones—lavender, ochre, teal, pink, and peach—differentiate random packs, rarity badges, and active navigation states.

## Colors

The palette is anchored in a **light** color mode with a bright ivory canvas (`#FFFDF7`) and warm, paper-like surface tiers (`#FAF5E8`, `#F5F0E0`, `#EBE6D6`).

- **Primary (`#0A0A0A`):** Used for primary ink, headings, and high-emphasis confirmation actions (Buy, Open Pack, Submit Intake, Accept Buyback) paired with `#FFFFFF` text.
- **Secondary (`#1A3A3A`):** Brand teal used for active category tabs and selected filters, paired with `#FFFFFF` text.
- **Tertiary (`#B8A4ED`):** Brand lavender used for random pack cards and pack-opening highlights, paired with `#0A0A0A` ink.
- **Named Accents:**
  - `brand-ochre` (`#E8B94A`): Reserved for rarity badges (e.g., `UR`, `SR`) with `#0A0A0A` text.
  - `brand-pink` (`#FF4D8B`), `brand-peach` (`#FFB084`), `brand-mint` (`#A4D4C5`), and `brand-coral` (`#FF6B5A`): Used for pack covers and opening result accents.
  - Semantic tokens (`success`, `warning`, `error`) are paired with dark text labels and inline error messages.

Never overlay prices or status badges directly on top of card photography; place them in dedicated surface areas below or beside the image.

## Typography

This design system uses `Noto Sans` (with `Noto Sans KR` prioritized for Korean UI copy and system sans-serif fallbacks) across all roles for clean, legible rendering of card names, set numbers, and pricing.

- **Titles (`title-lg`, `title-md`, `title-sm`):** Bold and semi-bold weights (`700`, `600`) with tight tracking (`-0.4px` to `-0.3px` on larger sizes) for screen headers, pack titles, card names, and highlighted transaction amounts.
- **Body (`body-md`, `body-sm`):** Regular weight (`400`) with generous line height (`1.5`–`1.55`) for descriptions, input text, rarity labels, and inspection notes.
- **Labels (`caption`, `button`, `nav-link`):** Medium to bold weights (`500`–`700`) for set/card numbers, action buttons, and navigation items.

Always include currency/coin units with prices and balances, and clearly label pilot/test balances as `테스트 잔액` (Test Balance).

## Layout & Spacing

The layout follows a **4px-based fluid grid** designed mobile-first, scaling up to a centered `1200px` maximum content width on desktop.

- **Mobile (< 768px):** Bottom navigation bar, `1rem` (`16px`) outer margins, `0.75rem` (`12px`) grid gutters, and a 2-column card grid for Market and Collection views. Detail and intake screens stack in a single column.
- **Tablet (768px – 1023px):** Top navigation bar, 3-column card grid, and side-by-side photo and detail layout.
- **Desktop (≥ 1024px):** Top navigation bar, 4-column card grid, centered within a `1200px` max-width container.

All interactive targets—including buttons, category tabs, and navigation links—must maintain a minimum touch area of `44×44px`. Reserve sufficient bottom padding on mobile so fixed bottom navigation and action bars never obscure content or inline error messages.

## Elevation & Depth

Hierarchy is achieved through **tonal layers** and **low-contrast outlines** rather than heavy drop shadows:

- **Base Level:** Screen backgrounds and top/bottom navigation bars sit flat on the bright ivory canvas (`#FFFDF7`).
- **Card Level:** Physical card listings, intake history, and status panels use warm surface fills (`#FAF5E8`, `#F5F0E0`) paired with subtle `1px` hairline borders (`#E5E5E5`).
- **Transaction & Overlay Level:** Confirmation sheets (`transaction-sheet`) for buying, pack opening, shipping, and buyback float above the page with a dimmed backdrop overlay.

Pack cards rely on saturated pastel fills (`#B8A4ED` lavender) for visual separation. Never apply filters or heavy effects over physical card photography.

## Shapes

This design system uses a **Rounded** shape language (`roundedness: 2`) that softens containers while keeping card photography crisp:

- **Small elements & Card media (`6px` / `8px`):** Used for compact badges and `5:7` aspect-ratio card images.
- **Buttons & Inputs (`12px`):** Applied to primary/secondary buttons and text input fields.
- **Cards & Panels (`16px`):** Applied to marketplace card tiles (`card-tile`) and status panels (`status-panel`).
- **Packs & Sheets (`24px`):** Applied to random pack cards (`pack-card`) and transaction confirmation sheets (`transaction-sheet`).
- **Pills (`9999px`):** Applied to rarity badges, status badges, and category filter tabs.

## Components

- **Buttons:**
  - `button-primary`: `#0A0A0A` background, `#FFFFFF` text, `12px` radius, `12px 20px` padding, `44px` min-height. Active state shifts to `#1F1F1F`; disabled state uses `#E5E5E5` with `#0A0A0A` text and an adjacent explanation.
  - `button-secondary`: `#FFFDF7` background, `#0A0A0A` text, `1px` `#6A6A6A` border, `12px` radius. Used for secondary actions like View Details or Cancel.
- **Navigation (`top-nav`, `bottom-nav`):** `64px` min-height on `#FFFDF7` canvas with 5 core items: **마켓 · 랜덤팩 · 입고 · 컬렉션 · 내 정보**. Active items are clearly distinguished by color and selection state.
- **Inputs & Filters (`text-input`, `category-tab`):** Text inputs use `#FFFDF7` background, `#6A6A6A` border (`#0A0A0A` on focus), `12px` radius, and `44px` min-height. Category tabs use pill radius (`9999px`), switching from `#FFFDF7` to `#1A3A3A` (brand-teal) with `#FFFFFF` text when active.
- **Card Tiles (`card-tile` & `card-media`):** `#FAF5E8` background, `#E5E5E5` hairline border, `16px` radius, `12px` padding. Houses a `5:7` `#F5F0E0` media container, card name, set/number, rarity badge, inspection status, and price.
- **Pack Cards (`pack-card`):** `#B8A4ED` (brand-lavender) background, `#0A0A0A` ink, `24px` radius, `24px` padding. Displays pack name, single/mixed rarity type, included rarities, and test coin price.
- **Badges (`badge-rarity`, `badge-status`):** Pill-shaped (`9999px`) with `4px 8px` padding. Rarity badges use `#E8B94A` (brand-ochre) with `#0A0A0A` text to display printed rarity codes (e.g., `레어도 UR`). Status badges use `#EBE6D6` (`surface-strong`) with `#0A0A0A` text.
- **Transaction Sheets (`transaction-sheet`):** `#FFFDF7` background, `24px` radius, `24px` padding. Used for confirming purchases, pack openings, shipping requests, and buyback offers, preventing duplicate submissions while processing.