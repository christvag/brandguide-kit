# Brandguide Kit

Brandguide Kit is a single-file HTML template for presenting a complete SaaS brand identity system. The current sample content is built around **Connect Matrix**, an agentic SaaS provider, but the structure is intentionally generic so future brand JSON or manual content edits can replace the sample copy, colors, typography, components, and icon names.

## Preview

Open `index.html` directly in a browser. No build step is required.

The page is designed as a responsive bento-style brand board with:

- Light and dark mode support.
- A persistent theme toggle using `localStorage`.
- Google Fonts loaded through CSS references.
- Lucide icons loaded from a pinned CDN version.
- Semantic IDs on sections and components for easier inspection, schema mapping, and future automation.

## File Structure

```text
brandguide-kit/
├── index.html
└── README.md
```

`index.html` contains all markup, CSS, and JavaScript needed to render the template. This keeps the project portable and easy to deploy to GitHub Pages, static hosts, or a design-review workflow.

## Main Sections

The template is organized around a complete brand identity presentation flow:

| Section ID | Purpose |
| --- | --- |
| `brand-header` | Brand name, positioning statement, descriptors, and logo direction suggestions. |
| `color-system` | Neutral palette, swatches, gradients, semantic state colors, and alternative mode studies. |
| `typography-system` | Display, body, and accent font studies with hierarchy and character specimens. |
| `visual-language` | Image-system placeholders arranged with named slots for hero, mood, detail, lighting, and pattern references. |
| `application-mockups` | Brand application cards for product UI, mobile, social, collateral, and large-format surfaces. |
| `ui-components` | Compact static UI specimens for SaaS components, including nav, hero sample, feature card, phone widget, toast/input, empty state, and command input. |
| `iconography` | Lucide-based icon set recommendations for SaaS and agentic workflow brands. |
| `layout-tokens` | Spacing and layout token examples for design-system consistency. |
| `schema-mapping` | Practical guide for mapping future JSON schema fields into the template. |
| `brand-footer` | Footer with brand mark, contact information, and copyright. |

## Technology

This template uses browser-native web technology:

- HTML5
- CSS custom properties
- CSS Grid and Flexbox
- Responsive media queries
- Vanilla JavaScript
- Google Fonts
- Lucide icons via CDN

There is no package manager, framework, bundler, or local server requirement.

## Typography

The current Connect Matrix sample uses:

- **Sora** for display headings and major brand moments.
- **Onest** for body copy, UI labels, and paragraph-level reading.
- **JetBrains Mono** for technical identifiers, metadata, and accent specimens.

These are loaded through Google Fonts in the `<head>` of `index.html`, so fonts can be swapped by changing the font import and CSS variables.

## Icons

Lucide is used as the icon source:

```html
<script src="https://unpkg.com/lucide@1.14.0/dist/umd/lucide.min.js"></script>
```

Icons are declared in markup with `data-lucide` attributes, then rendered at page load:

```html
<i data-lucide="network" aria-hidden="true"></i>
```

```js
window.lucide.createIcons({ attrs: { "stroke-width": 1.9 } });
```

## Schema Mapping Concept

The `schema-mapping` section explains how future structured data can populate the template. A future JSON schema can be organized around:

- `brand`: name, tagline, promise, descriptors, audience, and contact details.
- `visual`: palette, typography, logo options, image prompts, and icon names.
- `applications`: mockup types, product surfaces, UI components, and campaign assets.
- `metadata`: version, generated date, copyright, source model, and export notes.

The semantic IDs throughout the page make it easier for future scripts or agents to target specific sections and replace content safely.

## Responsive Behavior

The desktop layout uses a 12-column poster grid. It progressively adapts down to tablet and mobile:

- At tablet width, major sections shift into two-column spans.
- At mobile width, sections stack into a single column.
- The Image System keeps the locked desktop proportions, then stacks cleanly on mobile.
- The component navigation gains a compact mobile layout at very small widths.

The latest verification pass checked `1440px`, `900px`, `390px`, and `320px` widths for horizontal overflow and clipped text.

## Customization Guide

To adapt this for another brand:

1. Replace the brand name, tagline, descriptors, and footer details.
2. Update the CSS color variables in `:root` and `[data-theme="dark"]`.
3. Swap the Google Font imports and font-family variables.
4. Replace logo suggestion labels and descriptions.
5. Update image placeholder text or replace placeholders with real image assets.
6. Change Lucide icon names in `data-lucide` attributes.
7. Update the Schema Mapping notes to match the data fields your generator will provide.

## Deployment

Because the project is static, it can be deployed through GitHub Pages by serving the root folder and using `index.html` as the entry point.

Recommended GitHub Pages setup:

- Source: deploy from branch.
- Branch: `main`.
- Folder: `/root`.

## Current Sample Brand

The included sample brand is **Connect Matrix**:

> Agentic SaaS infrastructure that connects business apps, coordinates AI assistance, and compresses operational work into faster automated flows.

The sample is intentionally specific enough to look realistic while remaining reusable as a generic brand identity board template.
