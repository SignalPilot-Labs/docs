# Components

## Icons

Unified icon component - never define inline SVGs.

### Usage

```tsx
import { Icon } from './ui/Icon'

<Icon name="edit" size="sm" />
<Icon name="terminal" size="md" color="var(--color-primary)" />
```

### Available Icons

`edit`, `folder`, `link`, `external-link`, `reset`, `terminal`, `server`, `copy`, `close`, `file`, `plus`, `cloud`, `chevron-right`, `chevron-down`, `trash`

### Sizes

| Size | Pixels |
|------|--------|
| `xs` | 12px |
| `sm` | 14px |
| `md` | 16px |
| `lg` | 20px |
| `xl` | 24px |

## IconButton

Icon-only button with encapsulated hover states.

```tsx
import { IconButton } from './ui/IconButton'

<IconButton icon="edit" label="Edit port" onClick={handleEdit} />
<IconButton icon="trash" variant="danger" onClick={handleDelete} />
```

### Variants

| Variant | Hover Color | Use case |
|---------|-------------|----------|
| `ghost` | Secondary | Default, subtle actions |
| `subtle` | Text | Close buttons, minimal |
| `danger` | Error rose | Delete, destructive |

## Buttons

All buttons use `rounded-full` (pill shape).

### Variants

| Variant | Background | Color | Use case |
|---------|------------|-------|----------|
| `primary` | Gradient | #000 | Main CTA |
| `secondary` | Gradient subtle | #C4B5FD | Secondary actions |
| `tertiary` | transparent | #A1A1A1 | Low emphasis |
| `outline` | transparent | #FAFAFA | Alternative |
| `outlineBrand` | transparent | #C4B5FD | Brand outline |
| `ghost` | #141414 | #A1A1A1 | Subtle |
| `danger` | Rose→Pink gradient | #FFF | Destructive |
| `dangerSubtle` | error bg | #FB7185 | Soft destructive |

### Sizes

```
xs: h-28px, px-12px, text-12px
sm: h-32px, px-16px, text-13px
md: h-40px, px-20px, text-14px (default)
lg: h-48px, px-24px, text-15px
xl: h-56px, px-32px, text-16px
```

### States

- Hover: `scale(1.02)`
- Active: `scale(0.98)`
- Loading: spinner + opacity 0.8
- Disabled: opacity 0.5

### Primary button example

```jsx
<button style={{
  background: 'linear-gradient(135deg, #C4B5FD 0%, #F9A8D4 100%)',
  color: '#000000',
  padding: '10px 20px',
  borderRadius: '9999px',
  border: 'none',
  boxShadow: '0 4px 20px rgba(196,181,253,0.25)',
}}>
  Get Started
</button>
```

## Badges

Brand-native, not generic framework colors.

### Variants

| Variant | Style |
|---------|-------|
| `default` | Dark bg, subtle border |
| `primary` | Gradient subtle bg |
| `gradient` | Full gradient |
| `outline` | Violet border only |
| `active` | Lime + violet (live/running) |
| `pending` | Amber + pink (processing) |
| `inactive` | Rose + pink (stopped) |
| `new` | Pink accent (beta/new) |

### Features

- Optional dot indicator
- Pulse animation for live states
- Always uppercase with letter-spacing

```jsx
<span style={{
  background: 'linear-gradient(135deg, rgba(196,181,253,0.12) 0%, rgba(249,168,212,0.12) 100%)',
  color: '#C4B5FD',
  padding: '4px 12px',
  borderRadius: '9999px',
  fontSize: '11px',
  fontWeight: 500,
  textTransform: 'uppercase',
  letterSpacing: '0.05em',
}}>
  Active
</span>
```

## Alerts

Gradient accent line on left edge, violet-harmonized backgrounds.

### Structure

```
┌─────────────────────────────────────┐
│▌ [icon]  Title                    × │
│▌         Description                │
└─────────────────────────────────────┘
 ↑ gradient accent line
```

### Variants

| Variant | Accent | Background |
|---------|--------|------------|
| `info` | Violet | Gradient very subtle |
| `success` | Lime→Violet | Lime 6% blend |
| `warning` | Amber→Pink | Amber 6% blend |
| `error` | Rose→Pink | Rose 6% blend |
| `announcement` | Full gradient | Gradient subtle |

## Cards

```
default:  bg #0F0F0F, border #1A1A1A
elevated: bg #141414, border #262626, shadow
gradient: gradient subtle bg
glass:    surface 80% + backdrop-blur(12px)

Border radius: 16px
Padding: sm (16px), md (24px), lg (32px)
```

## Form elements

### Inputs

```jsx
<input style={{
  backgroundColor: '#0F0F0F',
  border: '1px solid #262626',
  borderRadius: '12px',
  padding: '12px 16px',
  color: '#FAFAFA',
}} />
// Focus: border-color #C4B5FD
// Error: border-color #FB7185
```

### Toggle (on state)

```jsx
<div style={{
  background: 'linear-gradient(135deg, #C4B5FD 0%, #F9A8D4 100%)',
  width: '48px',
  height: '28px',
  borderRadius: '9999px',
  boxShadow: '0 0 12px rgba(196,181,253,0.25)',
}}>
  <div style={{
    width: '20px',
    height: '20px',
    backgroundColor: '#FFF',
    borderRadius: '50%',
    transform: 'translateX(24px)',
  }} />
</div>
```

## Progress bars

```jsx
// Track
<div style={{ backgroundColor: '#141414', borderRadius: '9999px', height: '8px' }}>
  // Fill
  <div style={{
    background: 'linear-gradient(135deg, #C4B5FD 0%, #F9A8D4 100%)',
    borderRadius: '9999px',
    height: '100%',
    width: '60%',
    boxShadow: '0 0 8px rgba(196,181,253,0.25)',
  }} />
</div>
```

## Logo

```jsx
const Logo = ({ size = 48 }) => (
  <svg width={size} height={size} viewBox="0 0 48 48">
    <defs>
      <linearGradient id="logoGrad" x1="0%" y1="0%" x2="100%" y2="100%">
        <stop offset="0%" stopColor="#C4B5FD" />
        <stop offset="100%" stopColor="#F9A8D4" />
      </linearGradient>
    </defs>
    <rect width="48" height="48" rx="12" fill="#141414" stroke="#1A1A1A"/>
    <path d="M10 32 L16 24 L22 28 L28 18 L34 22 L38 14" 
      stroke="url(#logoGrad)" strokeWidth="2.5" 
      strokeLinecap="round" strokeLinejoin="round" fill="none"/>
    <circle cx="38" cy="14" r="3" fill="#F9A8D4"/>
  </svg>
);
```

With glow: `filter: drop-shadow(0 0 12px rgba(196,181,253,0.25))`

## LogViewer

Terminal-style log viewer with auto-scroll and intelligent color detection.

```tsx
import { LogViewer } from './ui/LogViewer'

<LogViewer
  logs={logLines}
  maxHeight={200}
  emptyMessage="No logs yet..."
/>
```

### Features

- Auto-scrolls to bottom on new logs
- Color detection:
  - `ERROR` → Rose `#FB7185`
  - `warn` → Amber `#FBBF24`
  - `success`, `Started` → Lime `#A3E635`
  - `$ ` (commands) → Violet `#C4B5FD`

### Styling

```jsx
background: 'var(--bg-terminal)'      // #0A0A0A
fontFamily: 'var(--font-mono)'
fontSize: '11px'
border: '1px solid var(--border-subtle)'
```

## Modal

Modal wrapper with header, body, and footer structure.

```tsx
import { Modal } from './ui/Modal'

<Modal
  isOpen={open}
  onClose={() => setOpen(false)}
  title="Edit Cluster"
  canClose={!loading}
  maxWidth={520}
  footer={
    <>
      <Button variant="ghost" onClick={onClose}>Cancel</Button>
      <Button variant="primary" onClick={save}>Save</Button>
    </>
  }
>
  {/* Modal body content */}
</Modal>
```

### Props

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| `isOpen` | boolean | required | Visibility |
| `onClose` | function | required | Close handler |
| `title` | string | required | Header title |
| `canClose` | boolean | `true` | Allow closing (set false during operations) |
| `maxWidth` | number | `500` | Max width in px |
| `footer` | ReactNode | - | Footer buttons |

### Structure

```
┌─────────────────────────────────────┐
│  Title                            × │  ← Header with IconButton close
├─────────────────────────────────────┤
│                                     │
│  {children}                         │  ← Body content
│                                     │
├─────────────────────────────────────┤
│           [Cancel]  [Primary]       │  ← Footer (optional)
└─────────────────────────────────────┘
```

### Styling

- Backdrop: `rgba(0,0,0,0.8)` + `backdrop-filter: blur(4px)`
- Uses Card component with `variant="elevated"`
- Border radius: `var(--radius-xl)` (16px)
