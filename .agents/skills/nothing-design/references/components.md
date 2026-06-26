# Nothing Design System - Components

## 1. Cards / Surfaces

- Prefer spacing alone. Use cards only for repeated items, widgets, modals, or framed tools.
- Background: `--surface`; stronger: `--surface-raised`.
- Border: `1px solid var(--border)` or none.
- Radius: `4px` technical, `8px` compact, `12-16px` card maximum.
- Padding: `16-24px`.
- No shadows, blur, nested cards, or boxed hero elements.

## 2. Buttons

| Variant | Background | Border | Text | Radius |
| --- | --- | --- | --- | --- |
| Primary | `--text-display` | none | `--black` | `999px` |
| Secondary | transparent | `1px solid --border-visible` | `--text-primary` | `999px` |
| Ghost | transparent | none | `--text-secondary` | `4px` or none |
| Destructive | transparent | `1px solid --accent` | `--accent` | `999px` |

- Font: `Space Mono`, `13px`, uppercase, `0.06em`.
- Padding: `12px 24px`; min height/touch target `44px`.
- Hover/focus: brighten border/text. No scale or shadow.
- Icon buttons use familiar symbols/icons with tooltip text.

## 3. Inputs

- Prefer underline input: bottom border `1px solid --border-visible`.
- Full border input: `8px` radius, no fill unless surface contrast is needed.
- Label above: `--label` style, `--text-secondary`.
- Focus: border/text to `--text-primary`.
- Error: border and message in `--accent`; message starts `[ERROR]`.
- Numeric/data fields use `Space Mono`.

## 4. Lists / Data Rows

- Row padding: `12-16px` vertical.
- Divider: `1px solid --border`, only for structurally identical rows.
- Left: label in `Space Mono`, uppercase, `--text-secondary`.
- Right: value in `--text-primary` or status color.
- No zebra striping or row background color except selected/active state.
- Hierarchy uses `16-24px` indentation, not tree lines.

## 5. Tables / Data Grids

- Header: `--label`, `--text-secondary`, bottom border `--border-visible`.
- Cell padding: `12px 16px`.
- Text left, numbers right.
- Numeric cells: `Space Mono`; text cells: `Space Grotesk`.
- Active row: `--surface-raised` with `2px` left accent rule.
- No zebra striping, cell fills, or legend boxes.

## 6. Navigation

- Desktop: horizontal text bar.
- Mobile: bottom bar or top edge text row.
- Labels: `Space Mono`, uppercase.
- Active: `--text-display` plus dot or underline.
- Inactive: `--text-disabled`.
- Acceptable styles: `[ HOME ] GALLERY INFO` or `HOME | GALLERY | INFO`.
- Back button: 40-44px circular or technical square, top-left, thin chevron.

## 7. Tags / Chips

- Border: `1px solid --border-visible`; no fill.
- Text: `Space Mono`, `--caption`, uppercase.
- Radius: `999px` pill or `4px` technical.
- Padding: `4px 12px`.
- Active: border and text become `--text-display`.

## 8. Segmented Controls

- Container: `1px solid --border-visible`, pill or `8px`.
- Height: `36-44px`.
- Active: `--text-display` background, `--black` text.
- Inactive: transparent, `--text-secondary`.
- Text: `--label`, uppercase.
- Use 2-4 segments.

## 9. Date / Period Navigation

- Layout: `< LABEL >`.
- Label: `Space Mono` or `Space Grotesk`, uppercase.
- Arrows: thin chevrons, `--text-secondary`, 44px target.
- Prefer linear stepping over custom calendar popovers.

## 10. Toggles / Switches

- Pill track, circular thumb.
- Off: border-visible track, disabled thumb.
- On: text-display track, black thumb.
- Min target: `44px`.
- Motion: `200ms` ease-out, no bounce.

## 11. Segmented Progress Bars

- Anatomy: label/value row above, discrete rectangular segments below.
- Segment gap: `2px`; square ends.
- Empty: `--border` dark, `#E0E0E0` light.
- Hero height: `16-20px`; standard `8-12px`; compact `4-6px`.

| State | Fill |
| --- | --- |
| Neutral | `--text-display` |
| Good | `--success` |
| Moderate | `--warning` |
| Over/error | `--accent` |

Always pair a bar with the exact numeric value.

## 12. Charts / Data Visualization

- Show numeric values alongside visuals.
- Differentiate by opacity, pattern, or line style before color.
- Lines: `1.5-2px --text-display`; comparison/average dashed `1px --text-secondary`.
- Grid: horizontal only, `--border`.
- Bars: square ends, filled value plus muted remainder.
- Gauges/rings: thin stroke with tick marks and adjacent or centered numeric readout.
- Sparklines: no area fill.

## 13. Widgets

- Use for dashboard cards and instrument panels.
- Surface: `--surface`, radius `12-16px`.
- Category: top-left `--label`.
- Hero metric: large Doto or Space Mono, left aligned.
- Unit: adjacent `--label`.
- One heavy widget per screen; secondary widgets use lighter forms.

## 14. Overlays

- No shadows. Layer through backdrop, surface, and border.
- Modal backdrop: `rgba(0,0,0,0.8)`.
- Dialog: `--surface`, `1px solid --border-visible`, `16px`, max width `480px`.
- Bottom sheet: `--surface`, top radius `16px`, 2px centered handle.
- Dropdown: `--surface-raised`, border-visible, `8px`, 44px items; selected row has left accent rule.
- No toasts. Use inline status text near the trigger.

## 15. State Patterns

- Loading: `[LOADING]`, segmented spinner, or progress percentage.
- Saved: `[SAVED]` inline, `Space Mono`, `--caption`.
- Error: `[ERROR]` inline; form-level errors may use a border-only summary box.
- Empty: one sentence, `--text-secondary`; optional subtle dot matrix.
- Disabled: `--text-disabled` or `opacity: 0.4`.
