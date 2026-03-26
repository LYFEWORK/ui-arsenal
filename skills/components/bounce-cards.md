---
name: bounce-cards
source: ReactBits
source_url: https://reactbits.dev/components/bounce-cards
category: components
tags: card, bounce, spring, entrance, physics, playful
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# BounceCards

> Cards that bounce into view with spring physics animation. Each card enters with a satisfying elastic overshoot, creating a playful and energetic entrance effect. Powered by Framer Motion springs.

## When to Use

- Team/about sections where member cards appear with personality
- Portfolio or project showcases that want a dynamic first impression
- Feature grids on SaaS landing pages where cards reveal on scroll
- Testimonial carousels where cards drop in one by one
- Any section where a static fade-in feels too bland

## When NOT to Use

- Corporate or law-firm sites where bouncy animation feels unprofessional
- Layouts with many cards (20+) where staggered bounces take too long
- Content-heavy dashboards where motion distracts from data
- Pages where users visit repeatedly (bounce gets annoying on repeat)

## Pairs Well With

- `animated-content` - Use AnimatedContent for the section, BounceCards for individual items
- `count-up` - Bouncing stat cards with animated numbers inside
- `gradient-text` - Gradient heading above a grid of bouncing cards
- `click-spark` - Add spark effect on click/tap of bounced cards

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Card content |
| delay | number | 0 | Delay before bounce starts (seconds) |
| stiffness | number | 260 | Spring stiffness (higher = snappier) |
| damping | number | 20 | Spring damping (lower = more bounce) |
| direction | "up" \| "down" \| "left" \| "right" | "up" | Direction cards bounce from |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/BounceCards-TS-TW
```

## Usage Example

```jsx
import BounceCards from '@/components/ui/BounceCards';

function TeamSection() {
  const team = [
    { name: 'Sarah Chen', role: 'CEO & Founder', img: '/team/sarah.jpg' },
    { name: 'Marcus Williams', role: 'CTO', img: '/team/marcus.jpg' },
    { name: 'Elena Rodriguez', role: 'Head of Growth', img: '/team/elena.jpg' },
    { name: 'James Park', role: 'Lead Engineer', img: '/team/james.jpg' },
  ];

  return (
    <section className="py-24 px-8 bg-[#0a0a0a]">
      <h2 className="text-4xl font-extrabold text-white text-center font-[Manrope] mb-16">
        The Team Behind It
      </h2>
      <div className="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6 max-w-6xl mx-auto">
        {team.map((member, i) => (
          <BounceCards key={i} delay={i * 0.12} direction="up" damping={18}>
            <div className="lyf-glass rounded-xl p-6 text-center">
              <img
                src={member.img}
                alt={member.name}
                className="w-24 h-24 rounded-full mx-auto object-cover border-2 border-[#ff642a]/20"
              />
              <h3 className="mt-4 text-lg font-bold text-white font-[Manrope]">{member.name}</h3>
              <p className="text-sm text-gray-400 mt-1">{member.role}</p>
            </div>
          </BounceCards>
        ))}
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Default spring: `stiffness: 260, damping: 18` feels premium without being too cartoon-like
- For client builds, increase damping to 24+ for a more restrained, professional feel
- Cards should use `lyf-glass` class with `rounded-xl` (12px) for Lyfework standard
- Background `#0a0a0a` makes the bounce motion pop against the dark canvas
- GHL compatible but requires Framer Motion bundled into the page -- use code embed widget
- Stagger delays at `0.1-0.15s` intervals for smooth cascading entrance

## Performance Notes

- Framer Motion spring animations use GPU-accelerated transforms
- Each card animates independently; no compound layout recalculations
- Intersection Observer triggers animation only when cards enter viewport
- Keep card count under 12 per viewport for smooth 60fps on mobile
- Consider `will-change: transform` on cards for paint optimization
