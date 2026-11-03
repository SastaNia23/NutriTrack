---
name: NutriTrack Vitality System
colors:
  surface: '#faf8ff'
  surface-dim: '#d2d9f4'
  surface-bright: '#faf8ff'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#f2f3ff'
  surface-container: '#eaedff'
  surface-container-high: '#e2e7ff'
  surface-container-highest: '#dae2fd'
  on-surface: '#131b2e'
  on-surface-variant: '#3c4a42'
  inverse-surface: '#283044'
  inverse-on-surface: '#eef0ff'
  outline: '#6c7a71'
  outline-variant: '#bbcabf'
  surface-tint: '#006c49'
  primary: '#006c49'
  on-primary: '#ffffff'
  primary-container: '#10b981'
  on-primary-container: '#00422b'
  inverse-primary: '#4edea3'
  secondary: '#006c4a'
  on-secondary: '#ffffff'
  secondary-container: '#82f5c1'
  on-secondary-container: '#00714e'
  tertiary: '#855300'
  on-tertiary: '#ffffff'
  tertiary-container: '#e29100'
  on-tertiary-container: '#523200'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#6ffbbe'
  primary-fixed-dim: '#4edea3'
  on-primary-fixed: '#002113'
  on-primary-fixed-variant: '#005236'
  secondary-fixed: '#85f8c4'
  secondary-fixed-dim: '#68dba9'
  on-secondary-fixed: '#002114'
  on-secondary-fixed-variant: '#005137'
  tertiary-fixed: '#ffddb8'
  tertiary-fixed-dim: '#ffb95f'
  on-tertiary-fixed: '#2a1700'
  on-tertiary-fixed-variant: '#653e00'
  background: '#faf8ff'
  on-background: '#131b2e'
  surface-variant: '#dae2fd'
typography:
  display-lg:
    fontFamily: Plus Jakarta Sans
    fontSize: 44px
    fontWeight: '700'
    lineHeight: 52px
    letterSpacing: -0.02em
  display-lg-mobile:
    fontFamily: Plus Jakarta Sans
    fontSize: 32px
    fontWeight: '700'
    lineHeight: 40px
    letterSpacing: -0.02em
  headline-lg:
    fontFamily: Plus Jakarta Sans
    fontSize: 32px
    fontWeight: '600'
    lineHeight: 40px
    letterSpacing: -0.015em
  headline-lg-mobile:
    fontFamily: Plus Jakarta Sans
    fontSize: 24px
    fontWeight: '600'
    lineHeight: 32px
    letterSpacing: -0.015em
  headline-md:
    fontFamily: Plus Jakarta Sans
    fontSize: 24px
    fontWeight: '600'
    lineHeight: 32px
    letterSpacing: -0.01em
  headline-sm:
    fontFamily: Plus Jakarta Sans
    fontSize: 20px
    fontWeight: '600'
    lineHeight: 28px
  title-md:
    fontFamily: Plus Jakarta Sans
    fontSize: 16px
    fontWeight: '600'
    lineHeight: 24px
  body-lg:
    fontFamily: Plus Jakarta Sans
    fontSize: 16px
    fontWeight: '400'
    lineHeight: 24px
  body-md:
    fontFamily: Plus Jakarta Sans
    fontSize: 14px
    fontWeight: '400'
    lineHeight: 20px
  label-lg:
    fontFamily: Plus Jakarta Sans
    fontSize: 14px
    fontWeight: '600'
    lineHeight: 20px
  label-md:
    fontFamily: Plus Jakarta Sans
    fontSize: 12px
    fontWeight: '500'
    lineHeight: 16px
    letterSpacing: 0.02em
  label-sm:
    fontFamily: Plus Jakarta Sans
    fontSize: 11px
    fontWeight: '600'
    lineHeight: 14px
    letterSpacing: 0.04em
rounded:
  sm: 0.25rem
  DEFAULT: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  full: 9999px
spacing:
  gutter: 1.5rem
  gutter-mobile: 1rem
  margin: 2rem
  margin-mobile: 1rem
  space-xs: 0.25rem
  space-sm: 0.5rem
  space-md: 1rem
  space-lg: 1.5rem
  space-xl: 2rem
---

## Brand & Style
The design system embodies modern wellness clarity: an inviting, energetic, and scientifically credible interface designed for daily nutritional tracking and sustained metabolic health. The audience spans health-conscious professionals, athletes, and individuals managing dietary wellness who require fast micro-logging alongside comprehensive macro trends.

The visual style blends crisp modern minimalism with soft tactile dimension. Pure white surfaces rest on subtle mint-tinted canvases, balanced by organic curvature, high-contrast slate typography, and distinct chromatic accents that map directly to key nutritional components (hydration, energy, rebuilding, and recovery). The atmosphere feels clinical yet human—reassuring, precise, and effortlessly light.

## Colors
The palette balances vital, chlorophyll-rich greens with targeted functional accents:

- **Primary & Secondary (`#10B981`, `#059669`):** The primary emerald and mint axis denotes optimal daily status, completed goals, fluid balances, and high-priority call-to-actions.
- **Tertiary Accent (`#F59E0B`):** Warm amber reflects carbohydrates, quick burn energy expenditure, and caloric metrics.
- **Nutritional Semantic Accents:**
  - Protein & Recovery: Rose and Soft Purple (`#F43F5E` and `#8B5CF6`) indicate amino profiles, high-density nutrition, and structural targets.
  - Dietary Fats & Micro-elements: Light indigo and deep sky blues (`#6366F1`) provide contrast in breakdown charts.
- **Neutrals & Surfaces:**
  - Base canvas: `#F8FAFC` running into subtle zones of `#F0FDF4` for restorative sections.
  - Surface cards: Absolute white (`#FFFFFF`).
  - Text: Deep slate (`#0F172A`) for primary hierarchy, slate muted (`#334155`) for secondary data values, and slate caption (`#64748B`) for units and metadata.

## Typography
Plus Jakarta Sans provides high clarity, gentle geometric terminals, and excellent legibility across small metric units (grams, kilocalories, micro-percentages). 

Tabular figures (`tnum`) must be enforced for all nutritional numbers, real-time counters, and analytical breakdowns to prevent horizontal layout shift during dynamic entry. Use `label-sm` with upper casing and tracked spacing exclusively for macronutrient category tagging (`PROTEIN`, `CARBS`, `FATS`).

## Layout & Spacing
The layout relies on a fluid grid system paired with strict interior spatial rhythms:

- **Desktop (1024px+):** 12-column layout, 24px (`1.5rem`) gutters, and dynamic side margins pinned to a 1440px maximum container. Three-column breakdown: Left navigation (compact/fixed), central analytical tracking canvas, and right-hand daily log breakdown.
- **Tablet (768px – 1023px):** 8-column layout, 20px gutters. Right drawer transitions to a collapsible slide-over sheet.
- **Mobile (< 768px):** 4-column layout, 16px (`1rem`) gutters, 16px edge margin. Dynamic data blocks stack vertically into a singular daily progression scroll with persistent bottom navigation.

Component spacing strictly follows an 8px grid scale (`space-xs` = 4px, `space-sm` = 8px, `space-md` = 16px, `space-lg` = 24px, `space-xl` = 32px) to preserve rhythmic scannability across dense macro cards.

## Elevation & Depth
Depth is created through ambient tinted drop shadows over clean white cards, avoiding hard borders or heavy dividers:

- **Flat/Ground:** Canvas base `#F8FAFC` to `#F0FDF4` linear blend.
- **Elevated Card (Level 1):** Solid `#FFFFFF` card with `box-shadow: 0 4px 20px -2px rgba(15, 23, 42, 0.04), 0 2px 6px -1px rgba(16, 185, 129, 0.03)`. Border: 1px solid `rgba(226, 232, 240, 0.8)`.
- **Floating Interactive (Level 2):** Quick-log floating action buttons, search bars, and active states use `box-shadow: 0 10px 25px -5px rgba(16, 185, 129, 0.12), 0 8px 10px -6px rgba(15, 23, 42, 0.04)`.
- **Modals & Overlays (Level 3):** Frosted ambient backdrop blur (`backdrop-filter: blur(8px); background: rgba(15, 23, 42, 0.3)`) paired with high-lift center stage cards using `box-shadow: 0 25px 50px -12px rgba(15, 23, 42, 0.18)`.

## Shapes
The visual identity embraces soft, welcoming geometry to alleviate the clinical friction of dietary tracking:

- Primary dashboard cards, macro summary panels, and modal containers use `rounded-2xl` (1.5rem / 24px) for expansive visual containment.
- Secondary elements such as inner metric boxes, food log row elements, and input fields use `rounded-xl` (1rem / 16px).
- Badges, status chips, quick-add buttons, and progress caps use full pill shapes (`rounded-full` / 9999px) to echo fluid cellular and nutritional motifs.

## Components

### Buttons
- **Primary:** Filled with emerald gradient (`linear-gradient(135deg, #10B981, #059669)`), text pure white, `rounded-xl` or full pill, subtle emerald hover shadow.
- **Secondary:** Surface white `#FFFFFF`, 1.5px border `#E2E8F0`, slate text `#334155`. Hover state elevates to light mint tint `#F0FDF4` with `#10B981` border.
- **Icon Quick-Add:** Pill-shaped circular triggers featuring centered icons with micro-interactions that scale smoothly to 0.95 on active press.

### Nutritional Data Visualizations
- **Progress Rings:** Multi-track concentric circular SVGs. Track background is tinted neutral (`rgba(15, 23, 42, 0.04)`), progress arcs end in rounded caps, filled with macro-specific hexes (Emerald = Calories/Target, Amber = Carbs, Rose = Protein, Indigo = Fats).
- **Segmented Nutrition Bars:** Linear horizontal progress bars with an overall height of 8px to 12px, wrapped inside `rounded-full` containers. Split-segment layouts display current consumption against target ceilings with an ultra-thin white segment divider.

### Cards
- Pure `#FFFFFF` background with dual-stage ambient green/slate shadow and hairline border (`1px solid #F1F5F9`).
- Internal layout divides content into micro-metrics: dynamic nutrient numbers top-left, micro-trend chart or icon top-right, and horizontal fuel-burn or progress gauge anchored to the bottom.

### Inputs & Log Fields
- Heights set to 48px on mobile and 44px on desktop. Surface set to `#FFFFFF` with default `#E2E8F0` border.
- Focus state activates an emerald halo: `border-color: #10B981` paired with `box-shadow: 0 0 0 3px rgba(16, 185, 129, 0.15)`.
- Input fields support leading metric selectors (e.g., dropdowns for `g`, `ml`, `oz`, `kcal`) nested seamlessly within the trailing edge.

### Chips & Badges
- Macro category tags use muted tinted backgrounds with bold text:
  - Protein: Background `rgba(244, 63, 94, 0.1)`, Text `#E11D48`.
  - Carbs: Background `rgba(245, 158, 11, 0.12)`, Text `#D97706`.
  - Fats: Background `rgba(139, 92, 246, 0.1)`, Text `#7C3AED`.
- Padding fixed at 4px vertical, 10px horizontal with `rounded-full` profile.

### Lists & Meal Logs
- Row items utilize divided list formats or grouped floating tile sets.
- Left-hand side hosts food/meal icon or thumbnail, middle zone presents ingredient/item label alongside time logged, and right-hand zone displays total kcal counter in bold slate accompanied by a stacked micro macro breakdown (P / C / F).