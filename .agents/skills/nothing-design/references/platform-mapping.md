# Nothing Design System - Platform Mapping

## 1. HTML / CSS

- Load Google Fonts with the `<link>` or `@import` snippet from `tokens.md`.
- Use CSS custom properties for tokens.
- Use `rem` for type if the app already does; use token px values for spacing, borders, and fixed controls.
- Use a `.theme-dark` / `.theme-light` class when the user picks a mode. Use `prefers-color-scheme` only if they ask for automatic mode.

```css
:root {
  --black: #000000;
  --surface: #111111;
  --surface-raised: #1A1A1A;
  --border: #222222;
  --border-visible: #333333;
  --text-disabled: #666666;
  --text-secondary: #999999;
  --text-primary: #E8E8E8;
  --text-display: #FFFFFF;
  --interactive: #5B9BF6;
  --accent: #D71921;
  --accent-subtle: rgba(215, 25, 33, 0.15);
  --success: #4A9E5C;
  --warning: #D4A843;
  --error: #D71921;
}

.theme-light {
  --black: #F5F5F5;
  --surface: #FFFFFF;
  --surface-raised: #F0F0F0;
  --border: #E8E8E8;
  --border-visible: #CCCCCC;
  --text-disabled: #999999;
  --text-secondary: #666666;
  --text-primary: #1A1A1A;
  --text-display: #000000;
  --interactive: #007AFF;
}
```

Base page:

```css
body {
  margin: 0;
  background: var(--black);
  color: var(--text-primary);
  font-family: "Space Grotesk", system-ui, sans-serif;
}

.nd-label {
  font: 400 11px/1.2 "Space Mono", monospace;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: var(--text-secondary);
}
```

## 2. React / Tailwind

- Prefer CSS variables in `globals.css` and Tailwind arbitrary values over custom plugin setup.
- Map tokens directly: `bg-[var(--black)]`, `text-[var(--text-primary)]`, `border-[var(--border-visible)]`.
- Use font utilities only if already configured; otherwise use inline classes with CSS variables or standard CSS.
- Component classes should stay literal and local. Do not build a theme abstraction unless the project already has one.

Minimal Tailwind font config:

```js
fontFamily: {
  display: ['Doto', 'Space Mono', 'monospace'],
  sans: ['Space Grotesk', 'system-ui', 'sans-serif'],
  mono: ['Space Mono', 'SF Mono', 'monospace'],
}
```

## 3. SwiftUI / iOS

- Bundle font files and register them in `Info.plist`.
- Use `@Environment(\.colorScheme)` only for mode-aware components; if the user chooses one mode, hard-code that token set.
- Map color tokens as static values or a tiny mode switch. Do not create a large design-system layer for a small screen.

```swift
extension Color {
    static let ndBlack = Color(hex: "000000")
    static let ndSurface = Color(hex: "111111")
    static let ndBorderVisible = Color(hex: "333333")
    static let ndTextSecondary = Color(hex: "999999")
    static let ndTextPrimary = Color(hex: "E8E8E8")
    static let ndTextDisplay = Color.white
    static let ndAccent = Color(hex: "D71921")
}

extension Font {
    static func ndDisplay(_ size: CGFloat) -> Font { .custom("Doto", size: size) }
    static func ndBody(_ size: CGFloat) -> Font { .custom("SpaceGrotesk-Regular", size: size) }
    static func ndMono(_ size: CGFloat) -> Font { .custom("SpaceMono-Regular", size: size) }
}
```

## 4. Paper / Design Tools

- Verify Doto, Space Grotesk, and Space Mono are available before styling.
- Use direct hex values from `tokens.md`; design tools do not need CSS variable names.
- Build dark and light as separate artboards when both are requested.
- Use exact spacing/token values. Avoid decorative shadows, gradients, or blur effects supplied by the tool.
