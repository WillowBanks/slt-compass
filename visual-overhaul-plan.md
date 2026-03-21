# Communication Compass v29 — Visual Overhaul Plan
**Date:** 19/03/2026
**Goal:** Transform the dashboard from functional to warm, welcoming, and visually engaging with images, infographics, and decorative flair.

## Approach
- Append a new `<script>` block (V29 patch) before `</body>` — same pattern as V28
- Use Unsplash/Pexels CDN URLs for imagery (no base64 bloat)
- Inline SVG illustrations for icons and decorative elements
- All changes respect dark mode via CSS custom properties

## Phase 1: Landing Page Hero Overhaul
- Replace compass SVG with a warm illustrated scene (child speaking/communicating)
- Add floating decorative shapes (speech bubbles, stars, hearts)
- Add subtle particle/confetti animation behind CTA
- Warm gradient adjustment with softer, more child-friendly colours

## Phase 2: Section Hero Banners
Each major view gets a visual header banner with:
- Relevant illustration/image (rounded, soft shadow)
- Warm gradient background strip
- Descriptive subtitle text

| View | Image Theme | Colour Accent |
|------|-------------|---------------|
| Browse All | Children communicating | Teal |
| IEP Goals | Therapist with child | Green |
| Workshops | Parent and child reading | Pink |
| Milestones | Baby/toddler playing | Orange |
| Red Flags | Supportive adult checking | Coral |
| Evidence | Books/research | Blue |
| Classroom | Classroom scene | Purple |
| Resources | Helpful tools | Amber |
| NZ Pathways | NZ landscape/fern | Green |
| MoE | School environment | Blue |

## Phase 3: Inline SVG Infographic Icons
- Custom SVG icons for each stat card (speech bubble for Terms, stethoscope for Diagnoses, clipboard for Assessments, lightbulb for Interventions)
- Animated SVG decorations: floating speech bubbles, gentle waves
- Category-specific decorative icons in view headers (milestone = stepping stones, red flag = flag, evidence = microscope, etc.)

## Phase 4: Card & UI Enhancements
- Soft gradient backgrounds on card categories
- Playful rounded shapes and blob backgrounds
- Warm illustration thumbnails on browse cards where relevant
- Confetti/sparkle micro-animation on favourite heart click
- Gentle pulsing glow on CTA buttons
- Rounded photo thumbnails in workshop cards

## Phase 5: Polish & Dark Mode
- All images get `filter: brightness(0.85)` in dark mode
- Decorative elements use CSS custom properties for theme-aware colours
- Ensure no layout shifts from loaded images (fixed aspect ratios)
- Lazy loading on all external images

## Technical Notes
- External images: `loading="lazy"` + `crossorigin="anonymous"`
- All injected via JS DOM manipulation (same pattern as V28)
- CSS injected via single `<style>` element
- Images sized to 400-800px width for fast loading
- Fallback: if image fails to load, graceful CSS gradient placeholder
