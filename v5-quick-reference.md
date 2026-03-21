# Communication Compass v5 — Quick Reference

## File Location
```
C:\Users\lilgi\Claude Code\2026-03-18 - SLT Glossary and Dashboard\04-outputs\communication-compass-v5.html
```

## Version
**v5** (Phase 1 - UI Redesign)

---

## What Changed

### Visual Design
- Warm colour palette (teal + coral instead of blue + purple)
- Warmer backgrounds (#faf8f5 off-white)
- Larger border radius (16px cards, 10px elements)
- Warm-toned shadows

### Navigation
- Dropdown menu bar (5 categories: Explore, Learn, Tools, For Parents, Resources)
- Mobile hamburger menu
- Old flat nav hidden but preserved

### Layout
- Hero tagline below header
- Enhanced footer
- Responsive grid (1/2/3 columns)

### Technical
- Added dropdown JS handlers
- Active state management for new nav
- Mobile click-to-open dropdowns
- Print styles updated

---

## What Didn't Change

- All JavaScript data (DATA, DEEP_DIVES, EXPANDED, etc.)
- All JavaScript functions (showView, openDetail, renderCards, etc.)
- All view containers (14 views)
- All element IDs
- Core functionality

---

## Colour Quick Reference

| Element | Colour | Code |
|---------|--------|------|
| Background | Warm off-white | #faf8f5 |
| Primary accent | Warm teal | #2a9d8f |
| Secondary accent | Coral | #e76f51 |
| Diagnosis | Rich purple | #7c3aed |
| Assessment | Ocean blue | #0284c7 |
| Intervention | Emerald | #059669 |
| Warning | Warm red | #dc2626 |
| Success | Bright green | #16a34a |
| Text primary | Warm dark | #2d2319 |
| Text secondary | Warm grey | #6b6152 |

---

## Navigation Structure

```
Explore ▾
  ├─ Browse All
  ├─ Diagnoses
  ├─ Assessments
  └─ Strategies

Learn ▾
  ├─ Milestones
  ├─ Red Flags
  └─ Evidence Library

Tools ▾
  ├─ IEP Goal Bank
  └─ Classroom Strategies

For Parents ▾
  ├─ Parent Workshops
  └─ MoE Overview

Resources ▾
  ├─ NZ Pathways
  └─ Key Resources
```

---

## Responsive Breakpoints

| Screen Size | Layout |
|-------------|--------|
| Desktop (>768px) | 3-column grid, horizontal nav with hover dropdowns |
| Tablet (480-768px) | 2-column grid, hamburger nav with click dropdowns |
| Mobile (<480px) | 1-column grid, hamburger nav with click dropdowns |

---

## Browser Requirements
- Modern browser (Chrome, Firefox, Safari, Edge)
- CSS Grid support
- CSS custom properties support
- JavaScript enabled

---

## File Stats
- **Lines:** 12,864
- **Size:** ~1.5MB
- **Functions:** 36
- **Views:** 14
- **Nav items:** 13

---

## Testing Checklist

### Desktop
- [ ] All dropdowns open on hover
- [ ] Dropdown items highlight on hover
- [ ] Clicking nav item navigates to view
- [ ] Active state shows on current view
- [ ] All 14 views render correctly
- [ ] Search works
- [ ] Cards are clickable
- [ ] Detail pages open/close
- [ ] Header gradient displays correctly
- [ ] Footer displays

### Mobile (<768px)
- [ ] Hamburger menu appears
- [ ] Clicking hamburger opens/closes nav
- [ ] Dropdowns expand on click
- [ ] Clicking nav item navigates and closes menu
- [ ] Grid becomes 1 column
- [ ] Search input resizes correctly
- [ ] Header stacks vertically
- [ ] Hero tagline is readable

### Print
- [ ] Header hidden
- [ ] Nav hidden
- [ ] Footer hidden
- [ ] Hero tagline hidden
- [ ] Content prints cleanly
- [ ] All views visible

---

## Known Issues
None identified in Phase 1.

---

## Next Phases
- Phase 2: Data enhancements
- Phase 3: Search improvements
- Phase 4: Advanced filtering
- Phase 5+: TBD

---

**Status:** Phase 1 complete. Ready for QA and user testing.
