---
name: profile-card
source: ReactBits
source_url: https://reactbits.dev/components/profile-card
category: components
tags: card, profile, team, member, avatar, hover, animated
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# ProfileCard

> An animated profile/team member card with hover effects that reveal additional information. Features avatar, name, role, and optional social links with smooth expand-on-hover or flip-to-reveal animations.

## When to Use

- Team/about pages showing company members with roles and bios
- Speaker or instructor cards for events and courses
- Client success stories with named contacts
- Advisory board or investor sections
- Any "people" section that needs more personality than a static grid

## When NOT to Use

- Large directories with 50+ people (use a searchable list instead)
- Anonymous testimonials where individual identity is not important
- Designs where hover interactions are unavailable (mobile-only contexts)
- Minimal layouts where a simple avatar + name is sufficient

## Pairs Well With

- `animated-content` - Scroll-reveal profile cards into view
- `spotlight-card` - Spotlight hover effect behind the profile card
- `gradient-text` - Gradient-styled name text on the card
- `click-spark` - Spark effect when a social link on the card is clicked

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| name | string | required | Person's name |
| role | string | required | Job title or role |
| avatar | string | required | URL to avatar image |
| bio | string | "" | Short biography text |
| socials | SocialLink[] | [] | Array of social links with platform, url |
| variant | "expand" \| "flip" \| "slide" | "expand" | Hover reveal animation style |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/ProfileCard-TS-TW
```

## Usage Example

```jsx
import ProfileCard from '@/components/ui/ProfileCard';
import AnimatedContent from '@/components/ui/AnimatedContent';

function TeamSection() {
  const team = [
    {
      name: 'Sarah Chen',
      role: 'CEO & Founder',
      avatar: '/team/sarah.jpg',
      bio: 'Former growth lead at HubSpot. Built 3 startups from zero to acquisition.',
      socials: [
        { platform: 'linkedin', url: 'https://linkedin.com/in/sarah' },
        { platform: 'twitter', url: 'https://twitter.com/sarah' },
      ],
    },
    {
      name: 'Marcus Williams',
      role: 'CTO',
      avatar: '/team/marcus.jpg',
      bio: '15 years building SaaS infrastructure. Ex-Stripe, ex-Vercel.',
      socials: [
        { platform: 'linkedin', url: 'https://linkedin.com/in/marcus' },
        { platform: 'github', url: 'https://github.com/marcus' },
      ],
    },
    {
      name: 'Elena Rodriguez',
      role: 'Head of Client Success',
      avatar: '/team/elena.jpg',
      bio: 'Helped 200+ clinics scale their patient acquisition by 3x or more.',
      socials: [
        { platform: 'linkedin', url: 'https://linkedin.com/in/elena' },
      ],
    },
  ];

  return (
    <section className="py-24 px-8 bg-[#0a0a0a]">
      <h2 className="text-4xl font-extrabold text-white text-center font-[Manrope] mb-16">
        Meet the Team
      </h2>
      <div className="grid grid-cols-1 md:grid-cols-3 gap-8 max-w-5xl mx-auto">
        {team.map((person, i) => (
          <AnimatedContent key={i} direction="up" delay={i * 0.1}>
            <ProfileCard
              name={person.name}
              role={person.role}
              avatar={person.avatar}
              bio={person.bio}
              socials={person.socials}
              variant="expand"
              className="lyf-glass rounded-xl"
            />
          </AnimatedContent>
        ))}
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Card container: `lyf-glass rounded-xl` (12px) for Lyfework glass standard
- Avatar border: `border-2 border-[#ff642a]/20` subtle brand-colored ring
- Name font: `Manrope` 700, role font: `Manrope` 400 in `text-gray-400`
- Social icons: use Lucide icons in `text-gray-500 hover:text-[#ff642a]` with transition
- Hover expand: reveals bio with smooth height animation from Framer Motion
- GHL compatible as a React code embed; profile data can come from GHL custom values

## Performance Notes

- Framer Motion `animate` handles the expand/flip/slide hover transitions
- Avatar images should be optimized thumbnails (200x200px, WebP format)
- Hover state content (bio, socials) is always in the DOM but hidden via `overflow: hidden`
- `AnimatePresence` not needed here; height animation is sufficient
- Lightweight enough to render 12+ cards on a single page without performance concern
