---
version: alpha
name: Pokemon-Trader-Gos
description: 검수된 실물 포켓몬 카드를 구매하고, 랜덤팩을 개봉하고, 보관·배송·재매입을 관리하는 모바일 우선 카드 마켓. Clay의 밝은 아이보리 배경과 포인트 컬러를 사용한다.

colors:
  primary: "#0a0a0a"
  primary-active: "#1f1f1f"
  primary-disabled: "#e5e5e5"
  ink: "#0a0a0a"
  body: "#3a3a3a"
  body-strong: "#1a1a1a"
  muted: "#6a6a6a"
  muted-soft: "#9a9a9a"
  hairline: "#e5e5e5"
  hairline-soft: "#f0f0f0"
  canvas: "#fffdf7"
  surface-soft: "#faf5e8"
  surface-card: "#f5f0e0"
  surface-strong: "#ebe6d6"
  surface-dark: "#0a1a1a"
  surface-dark-elevated: "#1a2a2a"
  on-primary: "#ffffff"
  on-dark: "#ffffff"
  on-dark-soft: "#a0a0a0"
  brand-pink: "#ff4d8b"
  brand-teal: "#1a3a3a"
  brand-lavender: "#b8a4ed"
  brand-peach: "#ffb084"
  brand-ochre: "#e8b94a"
  brand-mint: "#a4d4c5"
  brand-coral: "#ff6b5a"
  success: "#22c55e"
  warning: "#f59e0b"
  error: "#ef4444"

typography:
  title-lg:
    fontFamily: "Noto Sans KR, system-ui, sans-serif"
    fontSize: 24px
    fontWeight: 700
    lineHeight: 1.35
    letterSpacing: -0.4px
  title-md:
    fontFamily: "Noto Sans KR, system-ui, sans-serif"
    fontSize: 20px
    fontWeight: 700
    lineHeight: 1.4
    letterSpacing: -0.3px
  title-sm:
    fontFamily: "Noto Sans KR, system-ui, sans-serif"
    fontSize: 16px
    fontWeight: 600
    lineHeight: 1.4
    letterSpacing: 0
  body-md:
    fontFamily: "Noto Sans KR, system-ui, sans-serif"
    fontSize: 16px
    fontWeight: 400
    lineHeight: 1.55
    letterSpacing: 0
  body-sm:
    fontFamily: "Noto Sans KR, system-ui, sans-serif"
    fontSize: 14px
    fontWeight: 400
    lineHeight: 1.5
    letterSpacing: 0
  caption:
    fontFamily: "Noto Sans KR, system-ui, sans-serif"
    fontSize: 13px
    fontWeight: 500
    lineHeight: 1.45
    letterSpacing: 0
  button:
    fontFamily: "Noto Sans KR, system-ui, sans-serif"
    fontSize: 14px
    fontWeight: 700
    lineHeight: 1.4
    letterSpacing: 0
  nav-link:
    fontFamily: "Noto Sans KR, system-ui, sans-serif"
    fontSize: 14px
    fontWeight: 600
    lineHeight: 1.4
    letterSpacing: 0

rounded:
  xs: 6px
  sm: 8px
  md: 12px
  lg: 16px
  xl: 24px
  pill: 9999px

spacing:
  xxs: 4px
  xs: 8px
  sm: 12px
  md: 16px
  lg: 24px
  xl: 32px
  xxl: 48px

components:
  button-primary:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    typography: "{typography.button}"
    rounded: "{rounded.md}"
    padding: 12px 20px
    minHeight: 44px
  button-primary-active:
    backgroundColor: "{colors.primary-active}"
    textColor: "{colors.on-primary}"
    rounded: "{rounded.md}"
  button-primary-disabled:
    backgroundColor: "{colors.primary-disabled}"
    textColor: "{colors.ink}"
    rounded: "{rounded.md}"
  button-secondary:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink}"
    borderColor: "{colors.muted}"
    typography: "{typography.button}"
    rounded: "{rounded.md}"
    padding: 12px 20px
    minHeight: 44px
  top-nav:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink}"
    typography: "{typography.nav-link}"
    minHeight: 64px
  bottom-nav:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink}"
    typography: "{typography.nav-link}"
    minHeight: 64px
  text-input:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink}"
    borderColor: "{colors.muted}"
    typography: "{typography.body-md}"
    rounded: "{rounded.md}"
    padding: 12px 16px
    minHeight: 44px
  text-input-focused:
    borderColor: "{colors.ink}"
    rounded: "{rounded.md}"
  category-tab:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink}"
    typography: "{typography.nav-link}"
    rounded: "{rounded.pill}"
    padding: 8px 12px
    minHeight: 44px
  category-tab-active:
    backgroundColor: "{colors.brand-teal}"
    textColor: "{colors.on-dark}"
    rounded: "{rounded.pill}"
  card-tile:
    backgroundColor: "{colors.surface-soft}"
    textColor: "{colors.ink}"
    borderColor: "{colors.hairline}"
    typography: "{typography.title-sm}"
    rounded: "{rounded.lg}"
    padding: "{spacing.sm}"
  card-media:
    backgroundColor: "{colors.surface-card}"
    rounded: "{rounded.sm}"
    aspectRatio: "5 / 7"
  pack-card:
    backgroundColor: "{colors.brand-lavender}"
    textColor: "{colors.ink}"
    typography: "{typography.title-md}"
    rounded: "{rounded.xl}"
    padding: "{spacing.lg}"
  badge-rarity:
    backgroundColor: "{colors.brand-ochre}"
    textColor: "{colors.ink}"
    typography: "{typography.body-sm}"
    rounded: "{rounded.pill}"
    padding: 4px 8px
  badge-status:
    backgroundColor: "{colors.surface-strong}"
    textColor: "{colors.ink}"
    typography: "{typography.body-sm}"
    rounded: "{rounded.pill}"
    padding: 4px 8px
  status-panel:
    backgroundColor: "{colors.surface-card}"
    textColor: "{colors.ink}"
    typography: "{typography.body-md}"
    rounded: "{rounded.lg}"
    padding: "{spacing.md}"
  transaction-sheet:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink}"
    typography: "{typography.body-md}"
    rounded: "{rounded.xl}"
    padding: "{spacing.lg}"
---

# 포켓몬 카드 마켓 디자인 가이드

## Overview

밝은 아이보리 배경 위에 실물 카드의 사진과 색이 먼저 보이는 수집 앨범을 지향한다. 마켓에서는 검색과 가격 비교를 빠르게 하고, 랜덤팩에서는 개봉 전 조건과 개봉 후 배정된 카드를 명확히 보여준다.

포카마켓 공개 소개 화면의 카드 중심 탐색, 검수 안내와 구매 가격 배치, 콜렉트북 보관, 단계별 입고 안내를 참고했다. 포카마켓의 앱 화면은 공개 홍보 이미지 기준이다. 로그인 후 화면과 실제 거래는 검증 범위 밖이다. [포카마켓 공개 소개](https://phocamarket.com/) · [공식 앱 설명](https://play.google.com/store/apps/details?hl=ko&id=com.phocamarket.android) · [입고판매 안내](https://contents.phocamarket.com/how-to-use/stock-sale)

## Colors

### Brand & Accent

- `{colors.primary}`는 구매, 개봉, 입고 신청, 매입가 수락 같은 확정 버튼에 쓴다.
- `{colors.brand-teal}`은 선택된 필터에 쓴다. `{colors.brand-pink}`, `{colors.brand-lavender}`, `{colors.brand-peach}`는 랜덤팩 표지와 개봉 결과의 포인트 색이다.
- `{colors.brand-ochre}`는 희귀도 배지에 쓴다. `{colors.brand-mint}`와 `{colors.brand-coral}`은 팩 이미지의 보조 색으로 쓴다.

### Surface & Text

- `{colors.canvas}`는 앱의 밝은 아이보리 기본 배경이다. `{colors.surface-soft}`는 매물 카드에, `{colors.surface-card}`는 사진 받침과 거래 상태 패널에 쓴다.
- 제목과 주요 거래 정보는 `{colors.ink}`, 본문은 `{colors.body}`, 보조 정보는 `{colors.muted}`로 표시한다.
- 핑크·라벤더·피치·오커 바탕에는 `{colors.ink}`, 짙은 틸 바탕에는 `{colors.on-dark}`를 쓴다. 가격과 상태는 카드 이미지 위에 겹치지 않게 배치한다.

### Semantic

`{colors.success}`, `{colors.warning}`, `{colors.error}`는 상태 아이콘과 강조 표시에 쓴다. 상태 문구는 진한 글자로 함께 표시한다. 입력 오류는 해당 입력란 바로 아래에 무엇을 고쳐야 하는지 적는다.

## Typography

한글 화면에는 `Noto Sans KR`을 우선 사용하고 시스템 한글 글꼴을 대체 글꼴로 둔다.

| 토큰 | 크기 / 굵기 | 용도 |
| --- | --- | --- |
| `{typography.title-lg}` | 24px / 700 | 화면 제목, 거래에서 강조하는 금액 |
| `{typography.title-md}` | 20px / 700 | 섹션 제목, 팩 이름 |
| `{typography.title-sm}` | 16px / 600 | 카드 이름, 목록 항목 제목 |
| `{typography.body-md}` | 16px / 400 | 본문, 입력 내용, 거래 안내 |
| `{typography.body-sm}` | 14px / 400 | 희귀도, 검수 상태, 상세 설명 |
| `{typography.caption}` | 13px / 500 | 세트·카드 번호 등 보조 정보 |
| `{typography.button}` / `{typography.nav-link}` | 14px / 700·600 | 버튼과 메뉴 라벨 |

가격과 잔액에는 단위를 붙이고, 시범 거래의 금액은 `테스트 잔액`임을 화면 안에서 확인할 수 있게 한다.

## Layout

- 4px 단위를 바탕으로 `{spacing.xs}`부터 `{spacing.xxl}`까지 사용한다. 모바일 기본 좌우 여백은 `{spacing.md}`, 카드 그리드 간격은 `{spacing.sm}`이다.
- 마켓은 화면 제목·테스트 잔액, 검색창, 필터와 정렬, 카드 그리드 순서로 배치한다. 상세 화면은 사진, 카드 식별 정보, 검수 결과, 가격과 구매 버튼 순서로 읽을 수 있게 한다.
- 컬렉션도 마켓과 같은 사진 그리드를 쓴다. 입고와 거래 확인 화면은 한 열에 단계와 입력을 배치한다. 데스크톱 최대 콘텐츠 폭은 1200px을 기본으로 한다.

## Elevation & Depth

| 수준 | 처리 | 적용 |
| --- | --- | --- |
| 기본 | `{colors.canvas}` 위에 평면 배치 | 화면 본문, 상단 메뉴 |
| 카드 | 따뜻한 표면색과 `{colors.hairline}` 경계 | 실물 매물, 입고 내역, 정산 상태 |
| 거래 확인 | 페이지 위에 떠 있는 패널과 배경 오버레이 | 구매·개봉·배송·매입 확인 |

팩 표지의 색으로 랜덤팩 영역을 구분하고, 실물 사진에는 눈에 띄는 효과를 덧입히지 않는다.

## Shapes

| 토큰 | 값 | 적용 |
| --- | --- | --- |
| `{rounded.xs}` / `{rounded.sm}` | 6px / 8px | 작은 요소, 사진 영역 |
| `{rounded.md}` | 12px | 버튼, 입력란 |
| `{rounded.lg}` | 16px | 매물 카드, 상태 패널 |
| `{rounded.xl}` | 24px | 랜덤팩 카드, 거래 확인 패널 |
| `{rounded.pill}` | 9999px | 희귀도와 상태 배지, 필터 |

## Components

### Navigation, Search & Cards

- `{components.bottom-nav}`와 `{components.top-nav}`의 메뉴는 **마켓 · 랜덤팩 · 입고 · 컬렉션 · 내 정보**다. 현재 메뉴는 색과 라벨·선택 표시로 식별할 수 있게 한다.
- `{components.text-input}`과 `{components.category-tab}`으로 이름·세트·카드 번호 검색과 희귀도·검수 상태 필터를 제공한다. 결과가 없으면 검색어나 필터를 수정할 수 있게 한다.
- `{components.card-tile}`에는 앞면 사진, 이름, 세트·번호, 희귀도, 검수 상태, 판매가를 표시한다. `{components.card-media}`의 사진은 카드 가장자리까지 들어오도록 비율을 유지한다.
- `{components.badge-rarity}`에는 카드에 인쇄된 **레어도 UR**처럼 실제 코드를 표시한다. **검수 통과**는 `{components.badge-status}`로 표시한다. 팩 구성에는 인쇄 레어도 코드를 그대로 표시한다.
- `{components.button-primary}`는 화면에서 가장 중요한 확정 행동에, `{components.button-secondary}`는 상세 보기나 취소처럼 함께 제공하는 행동에 쓴다. 버튼을 사용할 수 없을 때는 제한 이유를 가까이에 표시한다.

### Screen Patterns

| 화면 | 필수 정보와 행동 |
| --- | --- |
| 카드 상세와 개별 구매 | 앞·뒷면 사진, 확대 가능한 하자 사진, 카드 이름·세트·번호, 희귀도와 검수 사유, 실물별 고유 재고 번호를 보여준다. 판매가 옆의 **구매하기**에서 차감액과 구매 후 잔액을 확인한다. 완료 후 **내 컬렉션에서 보기**를 제공한다. |
| 랜덤팩 | `{components.pack-card}`에 팩 이름과 혼합형·단일 레어도형 구분, 포함 레어도, 팩별 테스트 코인 가격을 표시한다. 개봉 전 배정 장수 한 장을 안내한다. 결과에는 실제 배정 카드와 레어도를 표시한다. 개봉 연출을 건너뛸 수 있다. |
| 입고와 검수 결과 | 접수 조건 확인, 카드 정보와 앞·뒷면 등록, 신청 확인 순서로 진행한다. 카드별 인쇄 레어도를 표시하고 적용 중인 입고 규칙이 있으면 요구 코드와 수량을 안내한다. 레어도 확인이 필요한 카드에는 확인 안내를 표시한다. 신청 상세에는 접수 번호·택배 안내·운송장과 검수 판정·사유를 표시한다. 검수 후 제안된 금액을 확인하고 수락할 수 있게 한다. |
| 컬렉션 | 구입·개봉으로 배정받은 카드와 현재 보관·배송 상태를 보여준다. 보관 중인 카드에는 **배송 신청**과 **매입가 확인**을 제공한다. 재매입 제안에는 받을 테스트 잔액과 수락 버튼을 표시한다. 배송을 신청한 카드에는 재매입이 제한되는 이유를 보여준다. |
| 내 정보 | 테스트 잔액과 구매·개봉 차감, 입고 매입·재매입 적립 내역을 카드명 또는 거래 번호와 함께 표시한다. 배송 내역에서는 출고 상태와 운송장을 확인할 수 있다. |
| 운영자 | 별도 관리 화면에서 입고 신청을 열고 실물 사진, 검수 결과와 사유, 매입가를 기록한다. 매입 확정 재고를 개별 판매나 랜덤팩에 배정하고 배송 요청의 출고 상태와 운송장을 관리한다. |

구매·개봉·배송·매입 수락에 쓰는 `{components.transaction-sheet}`에는 대상 카드 또는 팩과 확정할 내용을 표시한다. 처리 중에는 중복 확정을 제한하고, 결과를 바로 확인할 수 없으면 해당 내역을 볼 수 있게 한다.

## Do's and Don'ts

### Do

- 구매 가격과 검수 결과를 구매 버튼 가까이에 배치한다.
- 실물 사진이 없거나 불러오기 실패 상태라면 그 상태를 표시한다. 업로드에 실패하면 해당 위치에서 다시 시도할 수 있게 한다.
- 입고 보류나 반려는 해당 카드의 판정·사유와 다음 행동을 함께 보여준다.
- 키보드 초점과 현재 선택을 시각적으로 표시하고, 사진과 아이콘 조작에는 의미를 설명하는 이름을 붙인다.

### Don't

- 희귀도, 실물 상태, 보관·배송 상태를 하나의 등급이나 색으로 표시하지 않는다.
- 검수 반려 재고를 판매·개봉 가능 상태로 노출하지 않는다.
- 품절·배정 실패를 구매 성공으로 표시하지 않는다. 거래 결과가 불확실하면 내역 확인으로 연결한다.

## Responsive Behavior

| 화면 폭 | 배치 |
| --- | --- |
| 768px 미만 | 하단 메뉴, 마켓·컬렉션 2열, 사진 아래 상세 정보, 한 열 입력 화면 |
| 768–1023px | 상단 메뉴, 마켓·컬렉션 3열, 사진과 상세 정보 좌우 배치 |
| 1024px 이상 | 상단 메뉴, 마켓·컬렉션 4열, 가운데 정렬한 최대 1200px 콘텐츠 |

핵심 버튼과 메뉴의 터치 영역은 최소 44×44px로 확보한다. 360px 폭과 확대된 글꼴에서 카드명과 금액이 읽히는지 확인한다. 모바일 하단 메뉴와 고정 버튼이 본문이나 오류 메시지를 가리지 않게 여백을 둔다.

## Iteration Guide

1. 바꾸려는 화면에서 참조하는 YAML 컴포넌트와 토큰을 먼저 확인한다. 같은 역할의 요소는 기존 토큰을 사용한다.
2. 마켓 검색, 입고 신청, 구매·개봉, 컬렉션 이동, 배송·재매입까지 실제 진입점에서 확인한다. 모바일과 넓은 화면에서 구매 전 필수 정보와 다음 행동이 보이는지 점검한다.
3. 입고 조건 미충족, 검수 후 보류, 반려 카드 노출과 팩의 레어도 불일치 여부를 확인한다. 동시 구매·개봉에서도 실물 한 장은 한 사용자에게만 배정되고, 배송 신청과 재매입은 동시에 확정되지 않으며, 재전송으로 정산이 중복되지 않는지 확인한다.

## Known Gaps

- 레어도별 입고 동봉 기준, 매입가 표, 팩별 코인 가격과 재고 구성 및 일부 레어도 소진 시 판매 조건은 정책 확인이 필요하다. 시안의 가상 수치에는 `예시`를 붙인다.
- 첫 버전의 구매, 개봉, 매입과 재매입은 테스트 잔액 기준이다. 실제 결제, 유료 랜덤팩, 계좌 출금은 출시 요건을 확인한 뒤 화면을 구체화한다.
