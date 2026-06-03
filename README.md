# Studio Forma — Agency Website

A cinematic, single-file agency website with a live Three.js landscape, scroll-driven animations, and premium editorial design.

## How to run

**Option A — Zero setup (recommended):**
Open `index.html` directly in any modern browser (Chrome, Firefox, Safari, Edge). No server needed — everything runs from CDN.

**Option B — Local server (for development):**
```bash
# Python
python3 -m http.server 3000

# Node (if npx is available)
npx serve .

# Then open http://localhost:3000
```

## Customization

### Agency name and branding
Search and replace `Studio Forma` with your agency name throughout `index.html`.

### Color palette
All colors are CSS variables at the top of the `<style>` block:
```css
:root {
  --midnight: #050b1a;
  --sand:     #c8b89a;
  --cyan-soft:#7ab8c9;
  --gold:     #c9a84c;
  /* ... */
}
```

### Content sections
- **Hero** — edit `.hero-title`, `.hero-sub`, and CTA links
- **Manifesto** — edit the `#manifesto` section text
- **Services** — 8 cards in `.services-grid`, each editable
- **Digital Craft Facts** — 5 quote blocks with `.craft-text` class
- **Process steps** — 6 steps in `.process-steps`
- **Portfolio** — 4 cards in `.portfolio-grid`
- **CTA / Contact** — email, WhatsApp, Instagram links in `#cta`

### 3D scene
The Three.js scene is self-contained in the last `<script>` block:
- `starCount` — number of stars (default 2500 desktop / 800 mobile)
- `glowCount` — mid-field glow particles
- Terrain geometry: `PlaneGeometry(80, 120, 80, 100)` — reduce last 2 args for mobile performance
- `scene.fog = new THREE.FogExp2(0x050b1a, 0.018)` — adjust fog density

### Contact details
Replace these placeholders in the `#cta` section:
```html
href="mailto:hello@studioforma.co"
href="https://wa.me/1234567890"
href="https://instagram.com/studioforma"
```

## Browser support
- Chrome 90+ ✓
- Firefox 88+ ✓
- Safari 14+ ✓
- Edge 90+ ✓
- WebGL required for 3D scene (graceful fallback included)

## Performance notes
- Mobile automatically reduces particle count
- Terrain detail scales with device
- WebGL fallback activates if GPU is unavailable
- All fonts loaded from Google Fonts CDN
- Three.js loaded from cdnjs (r128)

## Tech stack
- Three.js r128 (3D scene + particles + terrain)
- Vanilla JS (scroll detection, cursor, IntersectionObserver)
- CSS custom properties + clamp() fluid typography
- Google Fonts: Cormorant (display) + DM Sans (body) + DM Mono (code)
- Zero build step, zero npm, zero dependencies
