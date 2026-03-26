---
name: masonry
source: ReactBits
source_url: https://reactbits.dev/components/masonry
category: components
tags: masonry, grid, pinterest, gallery, layout, responsive
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# Masonry

> An animated masonry/Pinterest-style grid layout that arranges items in columns with varied heights. Items animate into position on load and reflow smoothly on resize. Supports lazy loading and infinite scroll.

## When to Use

- Portfolio or gallery pages with images of varying aspect ratios
- Blog post grids where cards have different content heights
- Testimonial walls where review cards are different lengths
- Social media-style content feeds with mixed media types
- Case study or project showcase sections with asymmetric content

## When NOT to Use

- Uniform content where all cards are the same height (use regular grid)
- Data tables or structured information layouts
- Content that needs strict left-to-right reading order
- Mobile-first designs where masonry collapses to a single column anyway

## Pairs Well With

- `animated-content` - Scroll-reveal masonry items as they enter viewport
- `spotlight-card` - Add spotlight hover to individual masonry items
- `tilted-card` - Tilted cards within masonry layout for image galleries
- `blur-text` - Blur-reveal text overlays on masonry image items

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Masonry items |
| columns | number \| object | 3 | Column count or responsive breakpoint object |
| gap | number | 16 | Gap between items in px |
| animated | boolean | true | Enable layout animation |
| staggerDelay | number | 0.05 | Delay between each item's entrance |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Masonry-TS-TW
```

## Usage Example

```jsx
import Masonry from '@/components/ui/Masonry';

function TestimonialWall() {
  const reviews = [
    { name: 'Dr. Patel', clinic: 'Summit Dental', text: 'Our bookings tripled in 90 days. The automation handles everything.' },
    { name: 'Sarah Kim', clinic: 'Glow Aesthetics', text: 'The AI chatbot qualifies leads while we sleep. Game changer for our practice.' },
    { name: 'Mike Torres', clinic: 'Peak PT', text: 'Best ROI ever.' },
    { name: 'Lisa Chen', clinic: 'Clarity Wellness', text: 'We went from manual follow-ups to fully automated pipelines. The team saved 20 hours a week. Cannot recommend enough.' },
    { name: 'James Park', clinic: 'Urban Chiro', text: 'Professional, fast, and the results speak for themselves.' },
    { name: 'Ana Martinez', clinic: 'Bloom Spa', text: 'The dashboard alone was worth it. We can finally see where every dollar goes.' },
  ];

  return (
    <section className="py-24 px-8 bg-[#0a0a0a]">
      <h2 className="text-4xl font-extrabold text-white text-center font-[Manrope] mb-16">
        What Our Clients Say
      </h2>
      <Masonry
        columns={{ sm: 1, md: 2, lg: 3 }}
        gap={16}
        animated
        staggerDelay={0.06}
        className="max-w-5xl mx-auto"
      >
        {reviews.map((r, i) => (
          <div key={i} className="lyf-glass rounded-xl p-6">
            <p className="text-gray-300 text-sm leading-relaxed">"{r.text}"</p>
            <div className="mt-4 flex items-center gap-3">
              <div className="w-8 h-8 rounded-full bg-gradient-to-br from-[#ff642a] to-[#ff0301]" />
              <div>
                <p className="text-white font-bold text-sm font-[Manrope]">{r.name}</p>
                <p className="text-gray-500 text-xs">{r.clinic}</p>
              </div>
            </div>
          </div>
        ))}
      </Masonry>
    </section>
  );
}
```

## Lyfework Customization Notes

- Masonry items: `lyf-glass` with `rounded-xl` (12px) for Lyfework glass standard
- Avatar placeholders: `bg-gradient-to-br from-[#ff642a] to-[#ff0301]` brand gradient
- Font: `Manrope` 700 for names, 400 for review text
- Responsive columns: `{ sm: 1, md: 2, lg: 3 }` for standard testimonial layouts
- Background: `#0a0a0a` dark canvas for glass cards to pop
- GHL compatible when built as a React embed; masonry logic is self-contained

## Performance Notes

- Layout calculation uses column-based positioning, not CSS masonry (better browser support)
- Framer Motion `layout` animations handle smooth reflows on resize
- Items use Intersection Observer for lazy entrance animations
- Images inside masonry items should have explicit `width` and `height` to prevent layout shift
- Stagger delay keeps entrance smooth; avoid rendering 20+ items simultaneously
