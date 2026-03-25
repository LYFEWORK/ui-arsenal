---
name: splash-cursor
source: ReactBits
source_url: https://reactbits.dev/animations/splash-cursor
category: animations
tags: cursor, splash, fluid, interactive, WebGL, premium
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# SplashCursor

> Replaces the default cursor with a fluid splash effect that trails behind mouse movement. Creates ink-in-water or paint-splash visuals wherever the user moves their cursor. WebGL-powered.

## When to Use

- Agency or portfolio websites where the cursor IS part of the experience
- Creative landing pages for design, art, or music brands
- Lyfework's own site or premium showcase builds
- Launch pages or event sites that need to feel immersive
- Any build where the client says "make it feel like nothing else"

## When NOT to Use

- Business/utility websites where users need to focus on content
- E-commerce or form-heavy pages (cursor effects distract from inputs)
- Mobile (no cursor, effect is invisible)
- Sites targeting older hardware or accessibility-focused audiences

## Pairs Well With

- `aurora` - Aurora background + splash cursor for full immersion
- `infinite-menu` - Splash cursor over fullscreen navigation
- `blur-text` - Splash cursor trails while text blur-reveals in the hero
- `gradient-text` - Cursor splash colors matching the gradient text

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| splashColor | string | "#ff642a" | Primary splash color |
| splashSize | number | 0.5 | Size of the splash effect |
| curl | number | 30 | Curl intensity of fluid simulation |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/SplashCursor-TS-TW
```

## Usage Example

```jsx
import SplashCursor from '@/components/ui/SplashCursor';

function CreativePage() {
  return (
    <div className="relative min-h-screen">
      <SplashCursor splashColor="#ff642a" splashSize={0.4} curl={25} />
      {/* Rest of page content */}
    </div>
  );
}
```

## Lyfework Customization Notes

- Splash color: `#ff642a` for Lyfework. Match client accent for client builds.
- `splashSize` of 0.3-0.5 for subtle. Above 0.7 for dramatic.
- Use ONLY on Lyfework's own site or premium creative builds. Not for standard client sites.
- This is a Tier 3 "showcase" component. Deploy sparingly for maximum impact.
- Not compatible with GHL (requires WebGL canvas overlay)

## Performance Notes

- WebGL fluid simulation runs on GPU
- Can impact performance on older devices
- Add a feature detection check and fallback to standard cursor
- Desktop only (no mobile equivalent)
- Consider adding a "reduce motion" media query check
