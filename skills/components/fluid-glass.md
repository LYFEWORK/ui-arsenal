---
name: fluid-glass
source: ReactBits
source_url: https://reactbits.dev/components/fluid-glass
category: components
tags: glass, fluid, glassmorphism, panel, blur, premium
dependencies: none
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# FluidGlass

> A fluid glassmorphism card/panel effect with dynamic blur that responds to mouse movement or scroll. The glass surface subtly warps and shifts, creating a living, breathing transparent panel that feels premium and tactile.

## When to Use

- Hero section overlay panels with text content over a dynamic background
- Pricing cards or feature panels that need a premium frosted look
- Modal or dialog overlays with a glassmorphism aesthetic
- Dashboard sidebar panels on dark-themed interfaces
- Any container where static glass blur feels too flat and needs dimension

## When NOT to Use

- Light background layouts (glass effect needs contrast behind it)
- Text-heavy content where readability is paramount (fluid motion can distract)
- Older browser targets where `backdrop-filter` is not supported
- Performance-constrained mobile devices (backdrop-filter is GPU-intensive)

## Pairs Well With

- `spotlight-card` - Spotlight hover inside a fluid glass panel
- `gradient-text` - Gradient heading on a glass surface
- `aurora` - Aurora background visible through the glass panel
- `particles` - Particles floating behind the glass for depth

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Content inside the glass panel |
| blur | number | 20 | Backdrop blur intensity in px |
| opacity | number | 0.05 | Background white opacity (0-1) |
| borderOpacity | number | 0.08 | Border white opacity |
| fluid | boolean | true | Enable fluid/dynamic glass distortion |
| borderRadius | string | "16px" | Border radius of the glass panel |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/FluidGlass-TS-TW
```

## Usage Example

```jsx
import FluidGlass from '@/components/ui/FluidGlass';

function HeroSection() {
  return (
    <section className="relative min-h-screen bg-[#0a0a0a] flex items-center justify-center overflow-hidden">
      {/* Background gradient blobs */}
      <div className="absolute top-1/4 left-1/4 w-96 h-96 bg-[#ff642a]/20 rounded-full blur-[120px]" />
      <div className="absolute bottom-1/4 right-1/4 w-96 h-96 bg-[#ff0301]/15 rounded-full blur-[120px]" />

      <FluidGlass
        blur={24}
        opacity={0.04}
        borderOpacity={0.06}
        borderRadius="16px"
        className="p-12 max-w-xl text-center"
      >
        <h1 className="text-5xl font-extrabold text-white font-[Manrope] leading-tight">
          Build Systems That Scale
        </h1>
        <p className="mt-4 text-lg text-gray-300 font-[Manrope]">
          CRM, automation, and AI infrastructure for clinics that want to grow without the chaos.
        </p>
        <div className="mt-8 flex gap-4 justify-center">
          <a
            href="/book"
            className="px-6 py-3 bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-bold rounded-lg text-sm"
          >
            Book a Strategy Call
          </a>
          <a
            href="/work"
            className="px-6 py-3 border border-white/10 text-white font-medium rounded-lg text-sm hover:bg-white/5 transition"
          >
            See Our Work
          </a>
        </div>
      </FluidGlass>
    </section>
  );
}
```

## Lyfework Customization Notes

- This is the definitive implementation of the `lyf-glass` aesthetic in component form
- Default values align with Lyfework glass standard: `blur: 24, opacity: 0.04, borderOpacity: 0.06`
- Border radius: `16px` for hero panels, `12px` for standard cards
- Background blobs behind the glass: `#ff642a` and `#ff0301` at 15-20% opacity with 120px blur
- For client builds, adjust blob colors to their brand palette
- GHL compatible for static glass; fluid animation requires JS embed

## Performance Notes

- `backdrop-filter: blur()` is GPU-accelerated but can be expensive on large surfaces
- Fluid distortion uses CSS `transform` with mouse-tracking JS (requestAnimationFrame)
- Limit glass panels to 2-3 per viewport to avoid stacking backdrop-filter costs
- Provide a `@supports not (backdrop-filter: blur())` fallback with solid semi-transparent bg
- On mobile, consider disabling the fluid motion and using static glass only
