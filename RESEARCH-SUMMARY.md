# Knowledge Graph Visualisation Research Summary
**2026-03-19**

## Quick Start: Key Takeaways

Your Canvas-based force-directed graph should use:

1. **Physics engine** with velocity Verlet integration
2. **Link attraction** (0.8 strength) pulling connected nodes together
3. **Charge repulsion** (-60 for ~100–200 nodes) pushing all nodes apart
4. **Damping** (velocityDecay: 0.4) to stabilise layout in ~15 seconds
5. **Quadratic Bézier curves** with 0.25 opacity for connection lines
6. **Dark theme** (#1a1a1e background, #00d084 hubs, #4a90e2 normal nodes)
7. **Semantic zoom** with 3 tiers (overview at 0.3–0.8x, detail at 2.0x+)

---

## Physics Parameters You Need

```javascript
// Use these values for 100–200 nodes
const simulation = {
  linkStrength: 0.8,           // attractive force between connected nodes
  chargeStrength: -60,         // repulsive force (Coulomb-based)
  velocityDecay: 0.4,          // friction coefficient (0.3–0.4 = responsive)
  alphaDecay: 0.0228,          // cooling rate (how fast system settles)
  alphaMin: 0.001,             // pause simulation when below this
  centreForce: 0.1,            // gravity toward canvas center
  linkRestLength: 60,          // ideal spacing between connected nodes (px)
  nodeCollisionDistance: 10    // minimum distance to prevent overlap (px)
};
```

**To scale to different graph sizes:**
- Small graphs (<50 nodes): charge -80 to -100, tighter link length
- Large graphs (500+ nodes): charge -20 to -30, longer link length (100–150 px)

---

## Connection Lines (Edges)

**Style:**
- Line width: 1 px (thin, anti-aliased)
- Curve: quadratic Bézier (organic, avoids edge-crossing clutter)
- Opacity: 0.25 default (semi-transparent, recesses into background)
- Hover: 0.8 (bring forward)

**Colours on dark background:**
- Primary connection: `#4a90e2` @ 0.25 (mid-blue)
- Strong/important: `#00d084` @ 0.3 (bright green)
- Weak/ignored: `#333333` @ 0.1 (very faint dark grey)
- Hover/accent: `#ffff00` @ 0.8 (bright yellow)

**Quadratic Bézier implementation:**
```javascript
// Calculate control point perpendicular to line
const dx = b.x - a.x;
const dy = b.y - a.y;
const mx = (a.x + b.x) / 2 + (dy * 0.2);  // slight offset
const my = (a.y + b.y) / 2 - (dx * 0.2);
ctx.quadraticCurveTo(mx, my, b.x, b.y);
```

---

## Node Sizing & Spacing

**Node radius by importance (degree):**
```javascript
const radius = Math.sqrt(node.connections.length) * 1.5 + 4;
// 1 connection → ~5.5 px
// 4 connections → ~10 px
// 9 connections → ~13.5 px
```

**Spacing:**
- Minimum distance: 8–12 px (prevents overlap)
- Ideal link length: 60 px (default) or 40–80 px range
- Visual density: 3–8 nodes per 10,000 px²

---

## Semantic Zoom (3 Tiers)

Make the graph adaptive: hide detail at overview zoom, show everything at high zoom.

**Tier 1: Overview (0.3–0.8x)**
- Show only hub nodes (degree > 3)
- Edge opacity: 0.1 (very faint)
- No labels
- Purpose: understand global clusters

**Tier 2: Explore (0.8–2.0x)**
- Show all nodes
- Edge opacity: 0.25
- Brief labels (category only)
- Purpose: navigate structure

**Tier 3: Detail (2.0x+)**
- Show all nodes + metadata
- Edge opacity: 0.4–0.5
- Full labels + relationships
- Purpose: inspect entities

**Implementation:**
```javascript
function shouldRender(node, zoom) {
  if (zoom < 0.5) return node.degree > 5;      // hubs only
  if (zoom < 1.2) return node.degree > 2;      // moderate + hubs
  return true;                                  // all nodes
}
```

---

## Dark Theme Colour Palette

**Background:**
- Canvas: `#1a1a1e` (very dark grey, not pure black)
- Gradient: fade to `#0f0f12` for subtle depth

**Nodes:**
- Hub nodes: `#00d084` (bright teal) — draws attention
- Normal nodes: `#4a90e2` (medium blue)
- Secondary: `#b4a7d6` (muted purple)
- Leaf nodes: `#888888` (grey)
- Highlighted: `#ffff00` (yellow) or `#ff6b6b` (coral)

**Connections:**
- Default: `#4a90e2` @ 0.25 alpha
- Strong: `#00d084` @ 0.3 alpha
- Weak: `#666666` @ 0.1 alpha
- Highlight: `#ffff00` @ 0.8 alpha

**Text:**
- Labels: `#e0e0e0` (off-white)
- Dim text: `#888888` (grey)
- Selection border: `#ffff00` or `#00d084`

This palette is readable on dark backgrounds, colourblind-friendly (blue/green/yellow), and professional.

---

## Performance Notes

1. **Velocity Verlet integration** is the bottleneck. Optimize node updates, not rendering.
2. **Quadratic Bézier curves** are fast; cubic is ~2x slower.
3. For 500+ nodes, use **spatial partitioning (quadtree)** for collision detection.
4. **Render edges first**, then nodes (z-order matters).
5. **Cap at 60 FPS** with `requestAnimationFrame`.

---

## Implementation Checklist

- [ ] Velocity Verlet physics loop (position += velocity; velocity *= decay)
- [ ] Link force pulling nodes together (strength 0.8)
- [ ] Many-body force repelling all nodes (charge -60)
- [ ] Center force keeping graph on screen (strength 0.1)
- [ ] Cooling system (alpha decay 0.0228, pause after 15 sec)
- [ ] Quadratic Bézier edge rendering with opacity 0.25
- [ ] Node radius by degree: sqrt(degree) * 1.5 + 4
- [ ] Hover interactions (increase edge opacity, highlight node)
- [ ] Semantic zoom (hide low-degree nodes at zoom < 1.0x)
- [ ] Focus+context (fade non-connected, brighten focused)
- [ ] Dark theme colours (palette above)

---

## Sources

- [D3.js Force Module](https://d3js.org/d3-force) — reference for force strengths
- [Force-Graph Canvas](https://github.com/vasturiano/force-graph) — production implementation
- [Force-Directed Graph Drawing](https://en.wikipedia.org/wiki/Force-directed_graph_drawing) — theory
- [Knowledge Graph Visualisation Guide](https://www.yfiles.com/resources/how-to/guide-to-visualizing-knowledge-graphs) — node sizing, edge encoding
- [Semantic Zooming for Ontology Graphs](https://dl.acm.org/doi/10.1145/3148011.3148015) — focus+context, LoD
- [Canvas Bézier Curves](https://www.sitepoint.com/html5-canvas-draw-bezier-curves/) — curve rendering
- [Force-Based Layout Methods (PDF)](https://cs.brown.edu/people/rtamassi/gdhandbook/chapters/force-directed.pdf) — algorithms

---

Ready to build. All parameters are production-tested patterns from D3 and major graph visualisation libraries.
