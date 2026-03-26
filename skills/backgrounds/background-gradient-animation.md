---
name: background-gradient-animation
source: Aceternity UI
source_url: https://ui.aceternity.com/components/background-gradient-animation
category: backgrounds
tags: gradient, animation, morphing, background, moving, ambient, colorful
dependencies: none
variants: both
license: Free for commercial use
tier: 2
added: 2026-03-25
---

# BackgroundGradientAnimation

> Moving and morphing gradient background animation with multiple color blobs that shift, merge, and separate.

## When to Use
- Full-section hero backgrounds with immersive color movement
- CTA sections with ambient atmospheric depth
- About or mission page backgrounds with creative energy
- Event or launch page backdrops with dynamic feel
- Sign-up or login page backgrounds with visual engagement

## When NOT to Use
- When text readability is compromised by moving colors
- On pages with other heavy animated effects
- For conservative brands where morphing gradients are off-brand

## Pairs Well With
- `gradient-text` - Text that complements the background gradient palette
- `blur-text` - Headline entrance animation over morphing background
- `animated-content` - Content stagger on top of the animated gradient
- `floating-navbar` - Transparent nav over the gradient hero

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | - | Content rendered over the gradient |
| className | string | - | Classes for the animation container |
| gradientBackgroundStart | string | "rgb(108, 0, 162)" | Start gradient color |
| gradientBackgroundEnd | string | "rgb(0, 17, 82)" | End gradient color |
| size | string | "80%" | Size of gradient blobs |
| blendingValue | string | "hard-light" | CSS mix-blend-mode value |
| interactive | boolean | true | Whether gradient responds to mouse |

## Installation
```bash
npx aceternity-ui@latest add background-gradient-animation
```

## Usage Example
```jsx
import { BackgroundGradientAnimation } from "@/components/ui/background-gradient-animation";

export function ImmersiveHero() {
  return (
    <BackgroundGradientAnimation
      gradientBackgroundStart="rgb(10, 10, 10)"
      gradientBackgroundEnd="rgb(30, 10, 5)"
      size="80%"
    >
      <div className="absolute inset-0 flex items-center justify-center z-10 px-6">
        <div className="text-center">
          <h1 className="font-[Manrope] font-800 text-5xl md:text-7xl text-white">
            Design Without{" "}
            <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
              Limits
            </span>
          </h1>
          <p className="font-[Manrope] font-400 text-neutral-300 text-xl mt-6 max-w-2xl mx-auto">
            Lyfework brings AI-powered creativity to every pixel.
          </p>
        </div>
      </div>
    </BackgroundGradientAnimation>
  );
}
```

## Lyfework Customization Notes
- Set gradient start to `rgb(10, 10, 10)` and end to `rgb(30, 10, 5)` for dark warm tones
- Blob colors can include `#ff642a` and `#ff0301` mixed into the morphing blobs
- Content overlay needs `z-10` and centered positioning
- Manrope 800 for headline, 400 for subtext, white for readability on dark gradients
- Test opacity and blend mode for GHL iframe compatibility on various devices

## Performance Notes
- Gradient blobs use CSS `filter: blur()` which is GPU-composited
- Multiple blob divs (3-5) with `mix-blend-mode` can stress older GPUs
- Interactive mode uses mousemove for one blob following cursor; adds minimal overhead
- Consider reducing blob count on mobile for smoother rendering
- CSS animations run indefinitely; use `IntersectionObserver` to pause when off-screen
