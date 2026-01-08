# Color & Design Tokens

## Brand colors

```javascript
const brand = {
  primary: '#C4B5FD',      // Soft Violet
  secondary: '#F9A8D4',    // Soft Pink
  tertiary: '#A78BFA',     // Deeper Violet
  
  gradient: 'linear-gradient(135deg, #C4B5FD 0%, #F9A8D4 100%)',
  gradientSubtle: 'linear-gradient(135deg, rgba(196,181,253,0.12) 0%, rgba(249,168,212,0.12) 100%)',
  gradientVerySubtle: 'linear-gradient(135deg, rgba(196,181,253,0.06) 0%, rgba(249,168,212,0.06) 100%)',
  
  glow: 'rgba(196, 181, 253, 0.25)',
  glowStrong: 'rgba(196, 181, 253, 0.4)',
};
```

## Semantic colors (Violet-harmonized)

NOT generic framework colors. These complement the violet palette.

```javascript
const semantic = {
  success: {
    base: '#A3E635',   // Lime - complements violet
    bg: 'rgba(163, 230, 53, 0.08)',
    border: 'rgba(163, 230, 53, 0.2)',
  },
  warning: {
    base: '#FBBF24',   // Amber
    bg: 'rgba(251, 191, 36, 0.08)',
    border: 'rgba(251, 191, 36, 0.2)',
  },
  error: {
    base: '#FB7185',   // Rose - matches secondary pink
    bg: 'rgba(251, 113, 133, 0.08)',
    border: 'rgba(251, 113, 133, 0.2)',
  },
  info: {
    base: '#C4B5FD',   // Uses brand primary
    bg: 'rgba(196, 181, 253, 0.08)',
    border: 'rgba(196, 181, 253, 0.2)',
  },
};
```

## Backgrounds

```javascript
const bg = {
  void: '#000000',      // Base page
  base: '#050505',      // Sidebars
  elevated: '#0A0A0A',  // Elevated surfaces
  surface: '#0F0F0F',   // Main content
  card: '#141414',      // Cards
  cardHover: '#1A1A1A', // Card hover
  overlay: 'rgba(0, 0, 0, 0.85)',
};
```

## Borders

```javascript
const border = {
  subtle: '#1A1A1A',   // Default
  default: '#262626',  // Hover
  strong: '#333333',   // Emphasis
  focus: '#C4B5FD',    // Focus state
};
```

## Text

```javascript
const text = {
  primary: '#FAFAFA',   // Headlines, body
  secondary: '#A1A1A1', // Supporting
  tertiary: '#666666',  // Labels, metadata
  disabled: '#404040',  // Disabled
  inverse: '#000000',   // On gradient
};
```

## Syntax highlighting

```javascript
const syntax = {
  keyword: '#C4B5FD',   // import, for, if
  string: '#F9A8D4',    // 'hello'
  function: '#93C5FD',  // print()
  number: '#A3E635',    // 42
  comment: '#6B7280',   // # comment
  variable: '#E5E7EB',  // x, data
  builtin: '#F0ABFC',   // print, len
};
```

## Spacing

```
xs: 4px    sm: 8px    md: 12px   lg: 16px
xl: 24px   2xl: 32px  3xl: 48px  4xl: 64px
```

## Border radius

```
sm: 6px    md: 8px    lg: 12px   xl: 16px
2xl: 24px  full: 9999px (pill)
```

## Shadows

```javascript
const shadow = {
  sm: '0 2px 8px rgba(0,0,0,0.3)',
  md: '0 4px 16px rgba(0,0,0,0.3)',
  lg: '0 8px 32px rgba(0,0,0,0.4)',
  glow: '0 4px 20px rgba(196,181,253,0.25)',
  glowLg: '0 8px 40px rgba(196,181,253,0.3)',
};
```

## Typography

```
Font:    'Inter', -apple-system, sans-serif
Code:    'JetBrains Mono', monospace

Display: 48px/700   H1: 36px/600   H2: 28px/600
H3: 22px/600       H4: 18px/500   Body: 16px/400
Small: 14px/400    Micro: 12px/500 (uppercase)
```

## CSS custom properties

```css
:root {
  --brand-primary: #C4B5FD;
  --brand-secondary: #F9A8D4;
  --brand-gradient: linear-gradient(135deg, #C4B5FD 0%, #F9A8D4 100%);
  
  --bg-void: #000000;
  --bg-surface: #0F0F0F;
  --bg-card: #141414;
  
  --text-primary: #FAFAFA;
  --text-secondary: #A1A1A1;
  
  --border-subtle: #1A1A1A;
  --border-default: #262626;
  
  --glow: 0 4px 20px rgba(196,181,253,0.25);
}
```

## Tailwind config

```javascript
module.exports = {
  theme: {
    extend: {
      colors: {
        brand: { primary: '#C4B5FD', secondary: '#F9A8D4' },
        surface: { void: '#000000', DEFAULT: '#0F0F0F', card: '#141414' },
      },
      backgroundImage: {
        'brand-gradient': 'linear-gradient(135deg, #C4B5FD 0%, #F9A8D4 100%)',
      },
      boxShadow: {
        'glow': '0 4px 20px rgba(196, 181, 253, 0.25)',
      },
    },
  },
};
```
