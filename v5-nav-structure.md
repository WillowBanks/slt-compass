# Communication Compass v5 — Navigation Structure

## Old Structure (v4)
Flat 13-button pill navigation — all options visible at once:
```
[Browse All] [Diagnoses] [Assessments] [Strategies] [MoE Overview]
[NZ Pathways] [Milestones] [Red Flags] [Evidence Library]
[Classroom Strategies] [Key Resources] [Parent Workshops] [IEP Goal Bank]
```

**Issues:**
- Cluttered on mobile
- No clear hierarchy
- Hard to scan
- Takes up significant vertical space

---

## New Structure (v5)
Organised dropdown navigation — 5 main categories:

### 1. Explore
- Browse All
- Diagnoses
- Assessments
- Strategies

### 2. Learn
- Milestones
- Red Flags
- Evidence Library

### 3. Tools
- IEP Goal Bank
- Classroom Strategies

### 4. For Parents
- Parent Workshops
- MoE Overview

### 5. Resources
- NZ Pathways
- Key Resources

---

## Mapping Table

| Old Button | New Location | Category |
|------------|-------------|----------|
| Browse All | Explore → Browse All | Explore |
| Diagnoses | Explore → Diagnoses | Explore |
| Assessments | Explore → Assessments | Explore |
| Strategies | Explore → Strategies | Explore |
| Milestones | Learn → Milestones | Learn |
| Red Flags | Learn → Red Flags | Learn |
| Evidence Library | Learn → Evidence Library | Learn |
| IEP Goal Bank | Tools → IEP Goal Bank | Tools |
| Classroom Strategies | Tools → Classroom Strategies | Tools |
| Parent Workshops | For Parents → Parent Workshops | For Parents |
| MoE Overview | For Parents → MoE Overview | For Parents |
| NZ Pathways | Resources → NZ Pathways | Resources |
| Key Resources | Resources → Key Resources | Resources |

**Total:** 13 items reorganised into 5 categories (4+3+2+2+2)

---

## Desktop Behavior

### Hover Interaction
- Hover over category button → dropdown appears
- Hover over dropdown item → highlight with teal background + left border
- Click item → navigate to view, close dropdown
- Move mouse away → dropdown closes

### Visual Design
- White background with shadow
- Rounded corners (10px)
- Min-width 200px
- Teal text (#2a9d8f)
- Active item: teal background + left border accent

---

## Mobile Behavior (<768px)

### Hamburger Menu
- Hamburger icon (☰) appears in top-right
- Click to toggle menu open/close
- Menu slides down with smooth transition

### Accordion Dropdowns
- Category buttons stack vertically
- Click category → dropdown expands below
- Dropdowns use left-border accent (2px teal)
- Only one dropdown open at a time
- Click item → navigate + close entire menu

### Responsive Adjustments
- Nav becomes `position: relative` (not sticky)
- Dropdowns are `position: static` (no absolute positioning)
- Full-width buttons
- No box shadows (cleaner mobile look)

---

## Active State Management

### JavaScript Logic
When a view is shown:
1. `showView(name)` is called with view name (e.g., "diagnosis")
2. All `.view` elements get `active` class removed
3. Target view gets `active` class added
4. All `.nav-btn` (old) get active state updated
5. All `.nav-drop-item` (new) get active state updated
6. Scroll to top

### CSS Active State
```css
.nav-drop-item.active {
    background: var(--accent-l);
    color: var(--accent-d);
    border-left-color: var(--accent);
}
```

---

## Accessibility

### Keyboard Navigation
- Tab through category buttons
- Arrow keys within dropdowns (browser default)
- Enter/Space to activate

### ARIA Labels
- Hamburger has `aria-label="Menu"`
- Semantic `<nav>` element
- Button elements for all interactive items

### Screen Readers
- Clear hierarchy: "Explore menu, Browse All button"
- Active state announced
- Dropdown state changes announced

---

## Print Behavior
Navigation is hidden in print view:
```css
@media print {
    .top-nav { display: none !important; }
}
```

---

## Backwards Compatibility

### Old Nav Preserved
The old `.nav-bar` div is still in the HTML with all 13 `.nav-btn` buttons:
```html
<div class="nav-bar" id="navBar">
    <button class="nav-btn active" data-v="browse">Browse All</button>
    <!-- ... all 13 buttons ... -->
</div>
```

**Hidden with CSS:**
```css
.nav-bar { display: none !important; }
```

**Why preserve it?**
- Old JavaScript event listeners still work
- Active state management unchanged
- Easy rollback if needed
- No risk of breaking existing functionality

---

## Future Enhancements (Phase 2+)
- Search integration (filter dropdowns by search term)
- Recent views tracking
- Keyboard shortcuts (e.g., press 1-5 for categories)
- Breadcrumb trail for nested views
- View history (back/forward)

---

**Status:** Fully implemented and functional. Old nav hidden but preserved.
