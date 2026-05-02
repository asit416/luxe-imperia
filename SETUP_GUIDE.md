# Maison Luxe — Shopify Luxury Theme
## Gucci-Inspired Premium Fashion Theme

---

## FILE STRUCTURE

```
luxury-theme/
├── layout/
│   └── theme.liquid          ← MAIN LAYOUT (required)
├── sections/
│   ├── announcement-bar.liquid
│   ├── header.liquid
│   ├── hero-banner.liquid
│   ├── editorial-campaign.liquid
│   ├── featured-collection.liquid
│   ├── storytelling.liquid
│   ├── split-campaign.liquid
│   ├── marquee-ticker.liquid
│   └── footer.liquid
├── templates/
│   └── index.json            ← HOMEPAGE TEMPLATE
├── config/
│   └── settings_schema.json
└── locales/
    └── en.default.json
```

---

## HOW TO INSTALL IN SHOPIFY

### Method 1: Shopify CLI (Recommended)
```bash
npm install -g @shopify/cli @shopify/theme
shopify theme push --store=your-store.myshopify.com
```

### Method 2: Manual Upload via Theme Editor

**Step 1 — layout/theme.liquid**
- Shopify Admin → Online Store → Themes → "..." → Edit Code
- Click `layout/theme.liquid`
- Replace ALL content with the provided file

**Step 2 — Upload each section**
- In the code editor, under "Sections" folder:
  - Click "Add a new section"
  - Name it exactly as listed (e.g., `header`)
  - Paste the corresponding `.liquid` file content

**Step 3 — Upload templates/index.json**
- Under "Templates" folder
- Find or create `index.json`
- Paste the content from `templates/index.json`

---

## SECTION PLACEMENT GUIDE

| Section File | Where to Place | Purpose |
|---|---|---|
| `announcement-bar.liquid` | Sections folder | Top strip message |
| `header.liquid` | Sections folder | Navigation + logo |
| `hero-banner.liquid` | Sections folder, add via Customize | Full-screen hero |
| `editorial-campaign.liquid` | Sections folder, add via Customize | Campaign panels |
| `featured-collection.liquid` | Sections folder, add via Customize | Product grids |
| `storytelling.liquid` | Sections folder, add via Customize | Editorial text |
| `split-campaign.liquid` | Sections folder, add via Customize | Dual image panels |
| `marquee-ticker.liquid` | Sections folder, add via Customize | Scrolling ticker |
| `footer.liquid` | Sections folder | Footer |

---

## HOMEPAGE SETUP

After uploading all sections:
1. Go to Online Store → Themes → Customize
2. Select "Home page" template
3. Click "Add section" to add sections in this order:
   - Hero Banner
   - Marquee Ticker
   - Editorial Campaign (Women)
   - Split Campaign
   - Featured Collection (New Arrivals)
   - Storytelling
   - Editorial Campaign (Men)
   - Featured Collection (Accessories)

---

## TYPOGRAPHY USED
- **Display/Headlines:** Cormorant Garamond (Google Fonts — Serif, luxury feel)
- **Body/UI:** Montserrat (Google Fonts — Thin weight, modern)

Both load via Google Fonts CDN in theme.liquid.

---

## COLOR PALETTE
- Black: `#0a0a0a` — Background, text, nav
- White: `#fafaf8` — Page background, cards
- Cream: `#f5f2ec` — Section backgrounds
- Warm Grey: `#e8e4de` — Borders, dividers
- Gold: `#b8a98a` — Accents, labels, hover states
- Text Muted: `#6b6560` — Descriptions, secondary text

To update colors, edit `:root` CSS variables in `theme.liquid`.

---

## CUSTOMIZATION

### Logo
- Header → Logo → Upload your logo (recommended: SVG or PNG, max 200px height)
- If no logo uploaded, shop name displays in serif type

### Hero Images
- Minimum 2400×1600px for full-screen hero
- Use high-quality editorial/campaign photography
- Supports video (MP4) for cinematic effect

### Products
- Each "Featured Collection" section links to any Shopify collection
- Products display with automatic hover image swap (uses product's 2nd image)

### Footer Navigation
- Add "Navigation Column" blocks in footer section
- Up to 6 links per column, unlimited columns

---

## PERFORMANCE NOTES
- Images use `srcset` for responsive loading
- `loading="lazy"` on all below-fold images
- Hero image uses `fetchpriority="high"` for LCP
- Minimal JavaScript (no jQuery dependency)
- CSS animations use `transform` and `opacity` (GPU-accelerated)
- IntersectionObserver for scroll reveals (no scroll event overhead)

