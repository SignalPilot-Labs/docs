---
name: signalpilot-design-system
description: Design system for SignalPilot UI with Soft Violet gradient, Isometric pattern, and brand-native components. Use when building any SignalPilot frontend, UI components, styling, or visual design work.
---

# SignalPilot Design System

## Quick reference

```javascript
// Brand colors
const brand = {
  primary: '#C4B5FD',
  secondary: '#F9A8D4',
  gradient: 'linear-gradient(135deg, #C4B5FD 0%, #F9A8D4 100%)',
};

// Backgrounds (dark mode only)
const bg = {
  void: '#000000',
  surface: '#0F0F0F',
  card: '#141414',
};

// Text
const text = {
  primary: '#FAFAFA',
  secondary: '#A1A1A1',
  tertiary: '#666666',
};
```

For complete tokens: [reference/tokens.md](reference/tokens.md)

## Core decisions

| Decision | Value |
|----------|-------|
| Primary color | Soft Violet `#C4B5FD` |
| Gradient | `135deg, #C4B5FD → #F9A8D4` |
| Pattern | Isometric at 8% opacity |
| Mode | Dark only |
| Button shape | Pill (`rounded-full`) |
| Font | Inter (UI), JetBrains Mono (code) |

## Pattern implementation

```jsx
const IsometricPattern = ({ opacity = 0.08 }) => (
  <svg className="absolute inset-0 w-full h-full" preserveAspectRatio="xMidYMid slice">
    <defs>
      <pattern id="isometric" x="0" y="0" width="56" height="48" patternUnits="userSpaceOnUse">
        <g stroke="#C4B5FD" strokeWidth="0.4" fill="none" opacity={opacity}>
          <path d="M0,24 L28,0 L56,24 L28,48 Z" />
          <path d="M28,0 L28,48" />
          <path d="M0,24 L56,24" />
        </g>
      </pattern>
    </defs>
    <rect width="100%" height="100%" fill="url(#isometric)" />
  </svg>
);
```

Use pattern at 8% opacity. Layer with gradient glow for hero sections.

## Gradient text

```jsx
const GradientText = ({ children }) => (
  <span style={{ 
    background: 'linear-gradient(135deg, #C4B5FD 0%, #F9A8D4 100%)',
    WebkitBackgroundClip: 'text',
    WebkitTextFillColor: 'transparent',
  }}>
    {children}
  </span>
);
```

## Detailed references

- **Colors & tokens**: [reference/tokens.md](reference/tokens.md)
- **Components**: [reference/components.md](reference/components.md)
- **Patterns & backgrounds**: [reference/patterns.md](reference/patterns.md)

## Key principles

1. **Dark mode only** — No light variants
2. **Violet-harmonized semantics** — Success is lime `#A3E635`, error is rose `#FB7185` (not generic red/green)
3. **Pill buttons** — All buttons use `rounded-full`
4. **Glow on emphasis** — Primary buttons and active states get `box-shadow: 0 4px 20px rgba(196,181,253,0.25)`
5. **Progressive disclosure** — Reveal actions on hover
6. **Less is more** — Single containers over nested boxes
