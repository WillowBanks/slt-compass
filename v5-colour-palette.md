# Communication Compass v5 — Colour Palette

## Core Colours

### Backgrounds & Surfaces
- **Background:** `#faf8f5` (warm off-white)
- **Surface:** `#ffffff` (pure white)
- **Border:** `#e8e3dd` (warm beige border)

### Text
- **Primary text:** `#2d2319` (warm dark brown)
- **Secondary text:** `#6b6152` (warm grey)
- **Tertiary text:** `#9d9589` (light warm grey)

### Primary Accent (Teal)
- **Accent:** `#2a9d8f` (warm teal)
- **Accent light:** `#e0f2f0` (teal tint)
- **Accent dark:** `#1f7a6e` (deep teal)

### Secondary Accent (Coral)
- **Coral:** `#e76f51` (warm coral/salmon)
- **Coral background:** `#ffe8e3` (coral tint)

---

## Category Colours

### Diagnosis (Purple)
- **Primary:** `#7c3aed` (rich purple)
- **Background:** `#f3edff` (purple tint)

### Assessment (Blue)
- **Primary:** `#0284c7` (ocean blue)
- **Background:** `#e0f2fe` (blue tint)

### Intervention (Green)
- **Primary:** `#059669` (emerald green)
- **Background:** `#d1fae5` (green tint)

### Progress (Orange)
- **Primary:** `#d97706` (warm orange)
- **Background:** `#fff7ed` (orange tint)

---

## Semantic Colours

### Warning/Danger (Red)
- **Primary:** `#dc2626` (warm red)
- **Background:** `#fee2e2` (red tint)

### Success (Green)
- **Primary:** `#16a34a` (bright green)
- **Background:** `#dcfce7` (green tint)

---

## Shadows & Effects

### Box Shadows
- **Small:** `0 1px 3px rgba(45,35,25,0.06)` (subtle)
- **Medium:** `0 4px 12px rgba(45,35,25,0.08)` (cards, dropdowns)
- **Large:** `0 8px 24px rgba(45,35,25,0.12)` (modals, popovers)

### Border Radius
- **Large (cards):** `16px`
- **Small (inner elements):** `10px`

### Transitions
- **Duration:** `0.25s ease`

---

## Header Gradient
```css
background: linear-gradient(135deg, #2a9d8f 0%, #48a99d 30%, #d9846f 70%, #e76f51 100%);
```
Warm teal → mid teal → dusty coral → bright coral

---

## Usage Notes

### Warm vs Clinical
- Previous v4: Cool blues (#4a6cf7), purples (#8b5cf6), clinical grey (#f7f8fa)
- New v5: Warm teals, corals, off-white backgrounds
- **Goal:** Approachable, friendly, parent/teacher-focused (not medical/clinical)

### Accessibility
- All text colours meet WCAG AA contrast ratios on their backgrounds
- Accent colours distinct enough for colour-blind users
- Border colours provide clear visual separation

### Consistency
- All category colours use consistent pattern: primary + background tint
- Shadows use same warm rgba base (45,35,25)
- Rounded corners consistent throughout (16px/10px)

---

**Implementation:** All colours defined in `:root` CSS custom properties for easy maintenance.
