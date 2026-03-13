# MATTSMITHERS-AVIATION.COM REBUILD SPEC SHEET
## REV - (DRAFT) | Reverse-Engineered from DrawHistory.com
## Date: March 10, 2026

---

## 1. TECH STACK (What DrawHistory Is Built On)

| Component | What They Use | What It Means |
|-----------|--------------|---------------|
| CMS | WordPress | Content management system |
| Theme | Custom ("Hatchet") by hatchet.com.au | NOT a template - fully custom |
| CSS Framework | Tailwind CSS | Utility-first CSS (those crazy class names like `lg:px-8`) |
| JS Framework | Vue.js (Petite Vue) | Lightweight reactive framework for menus, popups |
| Animations | Custom JS + CSS transitions | Scroll-triggered fade/slide animations |
| Slider | Swiper.js | Horizontal card/case study sliders |
| Custom Cursor | Custom Vue component | That fancy cursor that changes text on hover |
| Forms | Gravity Forms + hCaptcha | Contact/newsletter forms |
| Font Loading | Web Font Loader (async) | Loads Google Fonts without blocking page |
| Performance | LiteSpeed Cache | Server-side caching + JS/CSS minification |
| Analytics | Google Analytics (UA-33548333-1) | Legacy Universal Analytics |
| Drawing Feature | Custom Canvas JS | That interactive drawing thing on hero/footer |

---

## 2. TYPOGRAPHY

| Element | Font | Details |
|---------|------|---------|
| Body / Primary | Eloquia Text | Serif font - this is what gives it the premium feel |
| Monospace / Labels | Roboto Mono | Used for eyebrow labels, nav items, footer text |
| Headings | Eloquia Text (uppercase) | Big, bold, uppercase with tight letter-spacing |

**Key CSS:**
- Body class: `font-eloquia`
- Headings: UPPERCASE with negative letter-spacing (`tracking-[-0.06rem]`)
- "Eyebrow" labels: Roboto Mono, uppercase, small size
- Display headings scale: 40px mobile > 82px tablet > 104px desktop > 130px ultrawide

**NOTE FOR YOUR REBUILD:** Eloquia Text is a premium/paid font. Alternatives that give a similar feel:
- **Libre Baskerville** (free, Google Fonts)
- **Playfair Display** (free, Google Fonts)
- **DM Serif Display** (free, Google Fonts)
- Or pair something like **Sora** or **General Sans** for a more modern aerospace feel

---

## 3. COLOR PALETTE

| Name | Hex | Usage |
|------|-----|-------|
| Onyx | `#101010` | Near-black - menu backgrounds, footer, dark sections |
| Warm Sand | `#F2E9E1` | Primary background - warm cream/beige |
| Wet Sand | `#E1D3C7` | Secondary background - slightly darker cream |
| Sage | `#A9A591` | Muted green accent |
| Sage Dark | `#3D3B2F` | Dark olive/brown - hero night mode, theme color |
| Orange Flair | `#FF6714` | Bright accent - notification dots, CTAs |
| Orange Shade | `#B64F26` | Darker orange variant |
| Lavender | `#AB86E2` | Purple accent (barely used) |
| Grey | `#D7D7D7` | Borders, dividers |
| White | `#FFFFFF` | Content sections |
| Black | `#000000` | Footer, text |

**NOTE FOR YOUR REBUILD:** You said you want DARK. So flip this:
- **Background:** Onyx (#101010) or deep navy (#0A0F1C)
- **Text:** Warm Sand (#F2E9E1) or pure white
- **Accent:** Pick ONE bold color - electric blue, aviation orange, or something that pops against dark

---

## 4. ANIMATION SYSTEM

DrawHistory uses custom HTML attributes to trigger animations on scroll:

| Attribute | What It Does |
|-----------|-------------|
| `animate-down` | Element slides down + fades in when scrolled into view |
| `animate-fade` | Element fades in when scrolled into view |
| `animate-delay-1/2/3` | Staggered delays for sequential entrance |
| `animate-desktop` | Only animates on desktop (skips mobile) |
| `animate-manual` | Controlled programmatically, not by scroll |
| `animate-border-4-gap` | Animated border lines (the grid lines that appear) |
| `animate-border-2` | Two-column border animation |
| `animate-border-left` | Left border slides in |
| `background-overlapping-lines` | Those moving background line elements |
| `data-cursor` | Triggers custom cursor effect |
| `data-cursor-text` | Sets custom cursor label (e.g. "Read More") |
| `data-cursor-theme` | Cursor color theme (dark/light/warm-sand) |

**Key animation patterns:**
- Page loads with `body opacity: 0`, then fades to 1
- Elements slide in from below (translateY) as you scroll
- Staggered delays create "choreographed" entrance
- Border lines animate in separately from content
- Custom cursor follows mouse with smooth interpolation

**FOR YOUR REBUILD:** This is the "wow factor" part. In Framer or Webflow, these map to:
- **Scroll-triggered animations** (built-in to both platforms)
- **Staggered reveals** (set delays on child elements)
- **Parallax scrolling** (native in both)
- Custom cursor would need Webflow interactions or skip it

---

## 5. LAYOUT STRUCTURE

### Header (Fixed, 49px mobile / 58px desktop)
- Logo left, hamburger menu right
- Rotating announcement banner center (desktop only)
- Background: Warm Sand
- Full-screen overlay menu (black/onyx background, huge typography)

### Hero Section
- Full viewport height
- Centered headline (massive uppercase text)
- Decorative scribble image below headline
- 4-column grid on desktop with text left, image right
- Interactive drawing canvas overlay
- Sticky scroll behavior

### Content Sections (alternating pattern)
- White background sections with 2-column grids
- Warm Sand background sections for case studies
- Wet Sand for podcast section
- Full-width horizontal sliders (Swiper.js)

### Footer
- Black background
- 3-column layout: nav + social | drawing canvas | B-Corp badge
- Full navigation repeated

### Grid System
- Tailwind's built-in grid: `grid-cols-2`, `grid-cols-3`, `grid-cols-4`
- Full-width with padding: `px-4` mobile, `px-8` desktop
- Max content widths vary by section

---

## 6. KEY INTERACTIVE FEATURES

1. **Full-screen Navigation Menu** - Hamburger triggers black overlay with massive text links
2. **Horizontal Card Sliders** - Swiper.js for case studies, clients, latest posts
3. **Custom Cursor** - Vue-powered cursor that changes shape/text based on hover target
4. **Drawing Canvas** - Interactive freehand drawing on hero and footer (fun but unnecessary for you)
5. **Day/Night Mode** - Hero section can toggle between light and dark themes
6. **Popup/Modal** - Announcement popup on page load
7. **Rotating Header Messages** - Auto-cycling announcement text in header bar

---

## 7. WHAT TO STEAL vs. WHAT TO SKIP

### STEAL (adapt for your site):
- Full-viewport hero with big bold headline
- Scroll-triggered fade-in animations with staggered delays
- Full-screen navigation overlay with oversized typography
- Horizontal sliding sections for showcasing work/experience
- Clean grid-based layout with generous spacing
- The "eyebrow label + big headline + body text + CTA button" pattern
- Client/partner logo section for credibility
- Fixed header with subtle border

### SKIP (not relevant for you):
- Drawing canvas (cool but gimmicky for aerospace professional)
- Custom cursor (diminishing returns for effort required)
- Day/night toggle on hero
- Podcast section structure
- B-Corp badge/certification section
- Gravity Forms (overkill - use a simple contact form)

---

## 8. RECOMMENDED APPROACH FOR YOUR REBUILD

### Platform: Framer or Webflow
Both can replicate 90% of this site's feel. Framer is easier to learn; Webflow is more powerful.

### Key Design Decisions Needed:
1. **Color scheme** - Dark navy/black background with what accent color?
2. **Typography pairing** - Serif or sans-serif for headlines?
3. **Hero content** - What's the big bold statement? (e.g. "30 Years of Aerospace. Now Building What's Next.")
4. **Sections** - About / Experience / Ventures / Contact?
5. **Photography** - Professional headshot? Aviation imagery?
6. **Credibility signals** - Client logos? Certifications? Testimonials?

---

*This spec sheet is your parts list. Bring it back with your design decisions and we'll start building.*
