---
name: tweet-grid
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/tweet-grid
category: components
tags: tweets, social-proof, testimonials, grid, twitter, embed
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# TweetGrid

> Grid layout for embedding social proof tweets and testimonials with masonry-style arrangement.

## When to Use
- Social proof sections showcasing customer testimonials from Twitter/X
- SaaS landing pages with user praise and endorsements
- Product launch pages with early adopter reactions
- Agency portfolio pages with client testimonials
- Community-driven product pages highlighting user love

## When NOT to Use
- When testimonials are not from Twitter/X (use a generic testimonial component)
- Pages requiring real-time tweet fetching (this is static embed)
- Sites where third-party embed scripts are blocked by CSP
- Minimal pages where a social proof grid feels heavy

## Pairs Well With
- `marquee` - Continuous scrolling tweets for dynamic testimonial display
- `animated-content` - Staggered tweet card entrance animations
- `spotlight-card` - Individual tweet cards with hover spotlight effect
- `number-ticker` - "1,000+ happy users" stat alongside tweet grid

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| tweets | { id: string; author: string; handle: string; avatar: string; content: string; date: string }[] | [] | Tweet data array |
| columns | number | 3 | Grid column count |
| gap | number | 16 | Gap between cards in pixels |
| variant | 'card' \| 'minimal' \| 'bordered' | 'card' | Tweet card style |
| animated | boolean | true | Enable entrance animations |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/tweet-grid"
```

## Usage Example
```jsx
import { TweetGrid } from "@/components/ui/tweet-grid";

const testimonials = [
  {
    id: "1",
    author: "Dr. Sarah Chen",
    handle: "@drsarahchen",
    avatar: "/avatars/sarah.jpg",
    content: "Switched our practice to Lyfework 3 months ago. Patient booking up 40%, no-shows down 60%. The GHL integration is seamless.",
    date: "Mar 15, 2026",
  },
  {
    id: "2",
    author: "Mike Torres",
    handle: "@miketorres_dev",
    avatar: "/avatars/mike.jpg",
    content: "The component library from Lyfework is insane. Shipped our entire SaaS landing page in 2 hours.",
    date: "Mar 12, 2026",
  },
];

export function SocialProof() {
  return (
    <section className="bg-[#0a0a0a] py-24 px-6">
      <h2 className="font-manrope font-700 text-3xl text-white text-center mb-12">
        What People Are Saying
      </h2>
      <TweetGrid
        tweets={testimonials}
        columns={3}
        variant="card"
        animated={true}
        className="max-w-6xl mx-auto"
      />
    </section>
  );
}
```

## Lyfework Customization Notes
- Use variant="card" with lyf-glass styling for frosted tweet cards on #0a0a0a
- Manrope 400 for tweet body, 700 for author names
- Apply 12px border-radius to match card radius standard
- Works in GHL pages as static content -- no third-party scripts required
- Brand gradient accent on hover state for tweet cards

## Performance Notes
- Static tweet data means zero API calls and instant rendering
- Masonry layout uses CSS grid -- no JavaScript layout calculation
- Animated entrance uses IntersectionObserver for on-scroll triggers
- Image avatars should be optimized to 48x48px for minimal payload
- No Twitter/X embed script dependency -- fully self-contained
