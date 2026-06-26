# Nothing Design System - Tokens

## 1. Fonts

Declare required Google Fonts before design work:

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Doto:wght@400..700&family=Space+Grotesk:wght@300;400;500;700&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
```

CSS fallback:

```css
@import url("https://fonts.googleapis.com/css2?family=Doto:wght@400..700&family=Space+Grotesk:wght@300;400;500;700&family=Space+Mono:wght@400;700&display=swap");
```

| Role | Font | Fallback | Use |
| --- | --- | --- | --- |
| Display | `Doto` | `"Space Mono", monospace` | Hero moments only, 36px+ |
| Body/UI | `Space Grotesk` | `system-ui, sans-serif` | Headings, body, controls |
| Data/Labels | `Space Mono` | `"SF Mono", monospace` | Numbers, captions, all-caps labels |

Use at most 2 families per screen. Doto counts as the one expressive break.

## 2. Type Scale

| Token | Size | Line | Tracking | Use |
| --- | ---: | ---: | ---: | --- |
| `--display-xl` | `72px` | `1` | `0` | Hero number/time |
| `--display-lg` | `48px` | `1.05` | `0` | Primary metric/title |
| `--display-md` | `36px` | `1.1` | `0` | Compact hero |
| `--heading` | `24px` | `1.2` | `0` | Section heading |
| `--subheading` | `18px` | `1.3` | `0` | Secondary heading |
| `--body` | `16px` | `1.5` | `0` | Body/UI |
| `--body-sm` | `14px` | `1.5` | `0` | Secondary body |
| `--caption` | `12px` | `1.4` | `0.04em` | Metadata |
| `--label` | `11px` | `1.2` | `0.08em` | ALL CAPS labels |

Labels are always `Space Mono`, uppercase, `--text-secondary` unless disabled.
Units next to large numbers use `--label` or `--caption`.

## 3. Color

| Token | Dark | Light | Role |
| --- | --- | --- | --- |
| `--black` | `#000000` | `#F5F5F5` | Page background |
| `--surface` | `#111111` | `#FFFFFF` | Raised surface |
| `--surface-raised` | `#1A1A1A` | `#F0F0F0` | Higher contrast surface |
| `--border` | `#222222` | `#E8E8E8` | Subtle divider |
| `--border-visible` | `#333333` | `#CCCCCC` | Intentional border |
| `--text-disabled` | `#666666` | `#999999` | Disabled/hints |
| `--text-secondary` | `#999999` | `#666666` | Labels/metadata |
| `--text-primary` | `#E8E8E8` | `#1A1A1A` | Body/content |
| `--text-display` | `#FFFFFF` | `#000000` | Primary hero |
| `--interactive` | `#5B9BF6` | `#007AFF` | Links/picker values |

| Token | Value | Use |
| --- | --- | --- |
| `--accent` | `#D71921` | Urgent/destructive/one signal moment |
| `--accent-subtle` | `rgba(215, 25, 33, 0.15)` | Rare tint, never page chrome |
| `--success` | `#4A9E5C` | Good/complete/connected |
| `--warning` | `#D4A843` | Caution/pending/degraded |
| `--error` | `#D71921` | Error text/borders |

Status color goes on the value, not the label or row background.

## 4. Spacing

| Token | Value | Use |
| --- | ---: | --- |
| `--space-2xs` | `2px` | Optical adjustment |
| `--space-xs` | `4px` | Icon-label gap |
| `--space-sm` | `8px` | Tight group |
| `--space-md` | `16px` | Standard gap/padding |
| `--space-lg` | `24px` | Group separation |
| `--space-xl` | `32px` | Section margin |
| `--space-2xl` | `48px` | Major break |
| `--space-3xl` | `64px` | Page rhythm |
| `--space-4xl` | `96px` | Hero breathing room |

Use spacing before dividers, borders, or cards.

## 5. Grid

- Page max width: `1200px`.
- Gutters: `16px` mobile, `24px` tablet, `32px` desktop.
- Use 4/8px alignment.
- Prefer asymmetric 12-column desktop layouts and single-column mobile stacks.
- Keep primary content edge-anchored or left-aligned; avoid centered default layouts.

## 6. Motion

- Duration: `150ms` micro, `200ms` control state, `300ms` panel/modal.
- Easing: `cubic-bezier(0.25, 0.1, 0.25, 1)`.
- Animate opacity or color. Avoid scale, bounce, parallax, and decorative motion.
- Loading is text `[LOADING]`, segmented spinner, or segmented progress. No skeletons.

## 7. Iconography

- Monoline only, no fill, no multi-color.
- Stroke: `1.5px`.
- Base: `24px`; compact controls may use `16-20px`.
- Color inherits current text.
- Preferred libraries: Lucide or Phosphor thin.

## 8. Dot Matrix

Use for Doto hero type, subtle grids, loading, or data texture. Do not use as button or card decoration.

```css
.dot-grid {
  background-image: radial-gradient(circle, var(--border-visible) 1px, transparent 1px);
  background-size: 16px 16px;
}

.dot-grid-subtle {
  background-image: radial-gradient(circle, var(--border) 0.5px, transparent 0.5px);
  background-size: 12px 12px;
  opacity: 0.2;
}
```
