---
name: fuzzy-text
source: ReactBits
source_url: https://reactbits.dev/text-animations/fuzzy-text
category: text-animations
tags: text, fuzzy, blur, sharpen, hover, focus, reveal
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# FuzzyText

> Text rendered with fuzzy, blurred edges that sharpens into focus on hover or scroll, creating a depth-of-field reveal effect.

## When to Use

- Secondary headlines or taglines that sharpen as the user engages
- Hover-to-reveal text on portfolio or case study cards
- Mysterious or teaser content that invites interaction
- Decorative background text that sharpens when scrolled into focus
- "Coming soon" or preview text that hints at content without fully showing it

## When NOT to Use

- Primary navigation or any text critical to wayfinding
- Form labels, error messages, or instructional text
- Heavily content-driven pages where readability is paramount
- Mobile-only contexts where hover is unavailable (unless using scroll trigger)

## Pairs Well With

- `spotlight-card` - Fuzzy card titles that sharpen when the spotlight sweeps over
- `tilted-card` - Fuzzy description text that focuses as the card tilts toward the user
- `blur-text` - Use BlurText for the headline entrance, FuzzyText for supporting text hover
- `aurora` - Fuzzy text floating over aurora gradients for a dreamy hero section

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | "" | Text content to render |
| blurAmount | number | 8 | Initial blur radius in pixels |
| hoverBlur | number | 0 | Blur radius on hover (0 = fully sharp) |
| duration | number | 0.4 | Transition duration in seconds |
| trigger | "hover" \| "scroll" | "hover" | What triggers the sharpen effect |
| color | string | "white" | Text color |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/FuzzyText-TS-TW
```

## Usage Example

```jsx
import FuzzyText from '@/components/ui/FuzzyText';

function CaseStudyTeaser() {
  return (
    <section className="py-24 px-8 bg-[#0a0a0a]">
      <div className="max-w-4xl mx-auto grid grid-cols-1 md:grid-cols-2 gap-12">
        <div className="lyf-glass rounded-2xl p-8 flex flex-col justify-end min-h-[300px]">
          <FuzzyText
            text="MedSpa Revenue +340%"
            blurAmount={10}
            hoverBlur={0}
            duration={0.5}
            trigger="hover"
            className="text-3xl font-extrabold text-white"
            style={{ fontFamily: 'Manrope, sans-serif' }}
          />
          <p className="mt-3 text-gray-500 text-sm font-normal">
            Hover to reveal the result
          </p>
        </div>
        <div className="lyf-glass rounded-2xl p-8 flex flex-col justify-end min-h-[300px]">
          <FuzzyText
            text="Dental Clinic 5x Bookings"
            blurAmount={10}
            hoverBlur={0}
            duration={0.5}
            trigger="hover"
            className="text-3xl font-extrabold text-white"
          />
          <p className="mt-3 text-gray-500 text-sm font-normal">
            Hover to reveal the result
          </p>
        </div>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Use Manrope 800 for fuzzy headlines so the letterforms remain recognizable even when blurred
- `blurAmount={8-12}` is the sweet spot: enough to obscure but still hint at content
- On #0a0a0a backgrounds, white text blur creates a natural glow halo effect
- For mobile builds, switch `trigger` to `"scroll"` since hover is unavailable
- For GHL: use CSS `filter: blur()` with a transition class toggle rather than JS-driven blur
- Combine with `lyf-glass` card backgrounds to amplify the frosted depth-of-field feel

## Performance Notes

- Uses CSS `filter: blur()` which is GPU-accelerated on all modern browsers
- Zero JavaScript animation overhead when using CSS transitions
- No layout shift, blur does not affect element dimensions
- Add `will-change: filter` for smoother transitions on lower-end devices
- Very lightweight, no external dependencies needed
