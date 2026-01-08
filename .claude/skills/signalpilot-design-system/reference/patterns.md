# Patterns & Backgrounds

## Isometric pattern (default)

SignalPilot uses the Isometric pattern at **8% opacity**.

### SVG implementation

```svg
<svg preserveAspectRatio="xMidYMid slice">
  <defs>
    <pattern id="isometric" x="0" y="0" width="56" height="48" patternUnits="userSpaceOnUse">
      <g stroke="#C4B5FD" stroke-width="0.4" fill="none" opacity="0.08">
        <path d="M0,24 L28,0 L56,24 L28,48 Z" />
        <path d="M28,0 L28,48" />
        <path d="M0,24 L56,24" />
      </g>
    </pattern>
  </defs>
  <rect width="100%" height="100%" fill="url(#isometric)" />
</svg>
```

### React component

```jsx
const IsometricPattern = ({ opacity = 0.08, color = '#C4B5FD' }) => (
  <svg 
    className="absolute inset-0 w-full h-full pointer-events-none" 
    preserveAspectRatio="xMidYMid slice"
  >
    <defs>
      <pattern id="isometric" x="0" y="0" width="56" height="48" patternUnits="userSpaceOnUse">
        <g stroke={color} strokeWidth="0.4" fill="none" opacity={opacity}>
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

### Usage

```jsx
<div className="relative">
  <IsometricPattern opacity={0.08} />
  {/* Content */}
</div>
```

## Gradient glow overlay

For hero sections, layer gradient glow above the pattern:

```jsx
<div className="absolute inset-0" style={{
  background: `radial-gradient(ellipse 60% 50% at 50% 0%, rgba(196,181,253,0.08) 0%, transparent 60%)`
}} />
```

## Full hero background

Complete layering for hero sections:

```jsx
<div className="relative" style={{ backgroundColor: '#000000' }}>
  {/* Layer 1: Gradient glow */}
  <div className="absolute inset-0" style={{
    background: `
      radial-gradient(ellipse 80% 50% at 20% -20%, rgba(196,181,253,0.06) 0%, transparent 50%),
      radial-gradient(ellipse 60% 40% at 80% 10%, rgba(249,168,212,0.04) 0%, transparent 50%)
    `
  }} />
  
  {/* Layer 2: Pattern */}
  <IsometricPattern opacity={0.08} />
  
  {/* Content */}
  <div className="relative z-10">
    {children}
  </div>
</div>
```

## Active/focus states

For cards or cells with active state, add pattern + glow:

```jsx
const ActiveCard = ({ isActive, children }) => (
  <div style={{
    backgroundColor: isActive ? '#0F0F12' : '#0F0F0F',
    border: `1px solid ${isActive ? 'rgba(196,181,253,0.3)' : '#1A1A1A'}`,
    boxShadow: isActive ? '0 0 20px rgba(196,181,253,0.25), inset 0 0 30px rgba(196,181,253,0.03)' : 'none',
    borderRadius: '12px',
    position: 'relative',
    overflow: 'hidden',
  }}>
    {isActive && <IsometricPattern opacity={0.04} />}
    <div className="relative">{children}</div>
  </div>
);
```

## Pattern guidelines

### Do

- Use at 8% opacity (default)
- Apply to hero sections, large backgrounds
- Layer with gradient overlays
- Use in active/focus states for emphasis
- Keep pattern color as brand primary `#C4B5FD`

### Don't

- Use above 12% opacity
- Place behind dense text
- Use in small UI components
- Change pattern color from brand primary
- Mix multiple patterns

## Opacity reference

| Use case | Opacity |
|----------|---------|
| Hero background | 8% |
| Active card | 4% |
| Subtle emphasis | 4-6% |
| Maximum | 12% |

## CSS-only version

```css
.isometric-pattern {
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='56' height='48'%3E%3Cg stroke='%23C4B5FD' stroke-width='0.4' fill='none' opacity='0.08'%3E%3Cpath d='M0,24 L28,0 L56,24 L28,48 Z'/%3E%3Cpath d='M28,0 L28,48'/%3E%3Cpath d='M0,24 L56,24'/%3E%3C/g%3E%3C/svg%3E");
  background-repeat: repeat;
}
```
