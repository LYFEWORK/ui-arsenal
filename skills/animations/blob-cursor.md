---
name: blob-cursor
source: ReactBits
source_url: https://reactbits.dev/animations/blob-cursor
category: animations
tags: cursor, blob, organic, morph, interactive, creative
dependencies: none
variants: both
license: MIT+Commons
tier: 3
added: 2026-03-25
---

# BlobCursor

> Replaces the cursor with a morphing organic blob that follows mouse movement. The blob stretches and deforms based on movement speed. Softer and more organic than SplashCursor.

## When to Use

- Creative/design agency portfolio sites
- Art, music, or lifestyle brand websites
- Lyfework's own showcase or creative builds
- Any build where organic movement fits the brand aesthetic
- Pages where the cursor itself should be part of the experience

## When NOT to Use

- Business or utility-focused sites
- Form-heavy pages (blob interferes with input targeting)
- Mobile (no cursor)
- Sites needing high accessibility

## Pairs Well With

- `aurora` - Organic blob cursor over organic aurora background
- `waves` - Blob cursor with wave section transitions
- `infinite-menu` - Blob cursor on creative fullscreen nav
- `gradient-text` - Blob color matching gradient text

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| blobColor | string | "rgba(255,100,42,0.6)" | Blob fill color |
| blobSize | number | 40 | Blob diameter in px |
| smoothing | number | 0.2 | Movement smoothing factor (0-1) |
| morphSpeed | number | 0.5 | How fast the blob morphs shape |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/BlobCursor-TS-TW
```

## Usage Example

```jsx
import BlobCursor from '@/components/ui/BlobCursor';

function CreativeSite() {
  return (
    <div className="relative min-h-screen">
      <BlobCursor blobColor="rgba(255,100,42,0.5)" blobSize={35} smoothing={0.15} />
      {/* Page content */}
    </div>
  );
}
```

## Lyfework Customization Notes

- Blob color: `rgba(255,100,42,0.5)` for Lyfework brand
- `blobSize` of 30-50px. Larger feels more playful, smaller more refined.
- Choose either BlobCursor OR SplashCursor. Never both.
- Reserve for Tier 3 showcase builds. Not standard client sites.
- Not compatible with GHL

## Performance Notes

- SVG filter-based morphing (GPU accelerated)
- requestAnimationFrame for smooth tracking
- Lighter than SplashCursor (no WebGL)
- Desktop only
