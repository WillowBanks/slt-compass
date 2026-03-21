# Communication Compass v5 — Dashboard UI Redesign

**Project:** Speech & Language Therapy Dashboard
**Client:** Parent/Teacher/Whānau Tool
**Date:** 2026-03-18
**Version:** v5 (Phase 1)

---

## Project Files

### Main Dashboard
- **File:** `communication-compass-v5.html`
- **Size:** 12,864 lines (~1.5MB)
- **Status:** Phase 1 complete
- **Type:** Self-contained single HTML file (inline CSS/JS)

### Documentation
- `v5-phase1-changelog.md` — Complete list of changes
- `v5-colour-palette.md` — Visual design system reference
- `v5-nav-structure.md` — Navigation reorganisation details
- `v5-quick-reference.md` — Testing checklist and quick facts
- `README.md` — This file

---

## What is Communication Compass?

An evidence-based, NZ-focused speech & language therapy dashboard designed to help:
- **Parents** understand their child's communication needs
- **Teachers** implement classroom strategies
- **Whānau** support language development

### Features
- **Comprehensive glossary** of SLT diagnoses, assessments, and interventions
- **Interactive deep-dives** with case studies, home activities, and FAQs
- **Developmental milestones** and red flags by age
- **IEP goal bank** for educators
- **Parent workshops** and resources
- **NZ-specific pathways** (MoE, RTLB, GSE)
- **Evidence library** with research citations
- **Classroom strategies** (Universal, Targeted, Specialist)

---

## Phase 1 Changes (This Release)

### Visual Redesign
✓ Warm colour palette (teal + coral replacing clinical blue)
✓ Larger border radius (16px cards, 10px elements)
✓ Warm-toned shadows and backgrounds
✓ Enhanced typography and spacing

### Navigation Overhaul
✓ Dropdown menu system (5 categories, 13 items)
✓ Mobile hamburger menu
✓ Responsive accordion dropdowns
✓ Active state management

### Layout Improvements
✓ Hero tagline section
✓ Sticky navigation bar
✓ Enhanced footer
✓ Responsive grid (1/2/3 columns)

### Technical
✓ All JavaScript preserved (no logic changes)
✓ All data preserved (no content changes)
✓ Backwards compatible (old nav hidden but functional)
✓ Print styles updated

---

## Opening the Dashboard

### Local File
1. Open `communication-compass-v5.html` in any modern browser
2. No server required — fully self-contained
3. Works offline

### Browser Requirements
- Chrome, Firefox, Safari, or Edge (latest versions)
- JavaScript enabled
- CSS Grid support
- Screen width: 375px+ recommended

---

## Navigation Structure

```
Explore        Learn           Tools               For Parents      Resources
─────────────  ──────────────  ──────────────────  ───────────────  ─────────────
Browse All     Milestones      IEP Goal Bank       Parent Workshops NZ Pathways
Diagnoses      Red Flags       Classroom Strategies MoE Overview    Key Resources
Assessments    Evidence Library
Strategies
```

---

## Colour Palette

| Purpose | Colour | Hex |
|---------|--------|-----|
| Primary accent | Warm teal | #2a9d8f |
| Secondary accent | Coral | #e76f51 |
| Background | Off-white | #faf8f5 |
| Diagnosis | Purple | #7c3aed |
| Assessment | Blue | #0284c7 |
| Intervention | Green | #059669 |
| Warning | Red | #dc2626 |

---

## Data Summary

### Content Counts
- **Diagnoses:** 12+ conditions (APD, ASD, CAS, DLD, etc.)
- **Assessments:** 12+ tools (CELF-5, PPVT-5, BPVS-4, etc.)
- **Interventions:** 12+ strategies (Colourful Semantics, Hanen, PECS, etc.)
- **Deep-dives:** Detailed entries with case studies and FAQs
- **Milestones:** Birth to 18 years developmental markers
- **Red flags:** Age-specific warning signs
- **IEP goals:** 60+ SMART goal templates
- **Classroom strategies:** 30+ tiered interventions
- **Workshops:** 6 parent workshop modules
- **Resources:** NZ-specific links and references

### Age Range
- **Coverage:** Birth to 18 years
- **User controls:** Adjustable age filter (min/max)
- **Age stages:** Baby, Toddler, Preschool, Early School, Primary, Intermediate, Secondary

---

## Testing Status

### Desktop
✓ All views load correctly
✓ Navigation dropdowns work
✓ Search functional
✓ Cards clickable
✓ Detail pages open/close
✓ Active states correct

### Mobile
✓ Hamburger menu functional
✓ Dropdowns expand on click
✓ Grid responsive (1 column)
✓ Touch targets appropriate
✓ Text readable at all sizes

### Print
✓ Navigation hidden
✓ Content prints cleanly
✓ No layout breaks

---

## Known Issues
None identified in Phase 1.

---

## Future Roadmap

### Phase 2 (Planned)
- Data enhancements and additional deep-dives
- Cross-referencing improvements
- Related content suggestions

### Phase 3 (Planned)
- Advanced search with filters
- Bookmarking functionality
- Export to PDF

### Phase 4+ (TBD)
- Multi-language support (Te Reo Māori)
- User accounts and saved preferences
- Printable handout generator
- Video/audio resources

---

## Technical Details

### File Structure
```
communication-compass-v5.html
├─ <head>
│  ├─ Meta tags
│  ├─ Google Fonts (Inter)
│  └─ <style> (all CSS inline)
├─ <body>
│  ├─ Header (brand, age controls)
│  ├─ Top Nav (dropdown menus)
│  ├─ Hero Tagline
│  ├─ Search
│  ├─ Old Nav (hidden)
│  ├─ Views (14 containers)
│  ├─ Footer
│  ├─ <script> (SVG constants + DATA)
│  └─ <script> (main JS logic + v5 handlers)
```

### CSS Architecture
- CSS Custom Properties (variables)
- CSS Grid for layouts
- Flexbox for components
- Mobile-first responsive breakpoints
- Print media queries

### JavaScript
- Vanilla JS (no frameworks)
- Event delegation
- View routing with `showView()`
- Dynamic content rendering
- Search filtering
- Collapsible panels

---

## NZ English Compliance
- "whānau" with macron
- "colour", "organise", "analyse"
- NZ-specific terminology (MoE, RTLB, GSE, NCEA)
- Day/month date format

---

## Credits
- **Design:** Caleb (Dashboard Master)
- **Data:** Evidence-based SLT resources
- **Framework:** Vanilla HTML/CSS/JS
- **Fonts:** Inter (Google Fonts)
- **Icons:** SVG inline
- **Target audience:** NZ parents, teachers, whānau

---

## Contact & Support
This is a static tool. No server-side processing or data collection.

For technical issues:
- Check browser console for errors
- Ensure JavaScript is enabled
- Try in different browser
- Clear cache and reload

---

## License
Built for educational and professional use. Not a substitute for professional SLT advice.

---

**Last updated:** 2026-03-18
**Version:** v5.0 (Phase 1)
**Status:** Production-ready
