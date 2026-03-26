---
name: tweet-card
source: Magic UI
source_url: https://magicui.design/docs/components/tweet-card
category: components
tags: tweet, social, embed, card, testimonial
dependencies: none
variants: both
license: MIT
tier: 3
added: 2026-03-25
---

# TweetCard

> Embedded tweet/X post card component for displaying social proof or testimonials in tweet format.

## When to Use
- Social proof sections showing real customer tweets
- Testimonial walls with authentic social media posts
- Product launch announcement embeds
- Community highlight sections
- Press mentions from social media

## When NOT to Use
- When you need the full interactive Twitter embed (likes, retweets)
- Private or DM content that should not be displayed publicly
- Long-form testimonials that exceed tweet length
- When tweets may be deleted and show broken embeds

## Pairs Well With
- `marquee` - Scrolling row of tweet cards for social proof walls
- `animated-content` - Stagger-reveal tweet cards on scroll
- `spotlight-card` - Spotlight glow on featured testimonial tweets
- `avatar-circles` - Avatar stack above the testimonial tweet section

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| id | string | required | Tweet ID to render |
| className | string | "" | Additional CSS classes |
| components | object | {} | Custom component overrides |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/tweet-card"
```

## Usage Example
```jsx
import { TweetCard } from "@/components/magicui/tweet-card";

export function TestimonialSection() {
  const tweetIds = ["1234567890", "9876543210", "5678901234"];

  return (
    <section className="bg-[#0a0a0a] py-24">
      <h2 className="text-center font-manrope font-800 text-3xl text-white mb-4">
        What clinics are{" "}
        <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
          saying
        </span>
      </h2>
      <p className="text-center font-manrope font-400 text-white/60 mb-16">
        Real feedback from healthcare professionals.
      </p>
      <div className="mx-auto max-w-5xl grid grid-cols-1 md:grid-cols-3 gap-6 px-6">
        {tweetIds.map((id) => (
          <TweetCard key={id} id={id} className="rounded-[12px]" />
        ))}
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Style the card container with `rounded-[12px] border border-white/10` for consistency
- Dark theme variant blends well with `#0a0a0a` backgrounds
- Use Manrope font for section headings around the tweet grid
- Consider creating static tweet mockups for guaranteed display (no API dependency)
- GHL compatible — renders as standard HTML card, no iframe embedding

## Performance Notes
- Static rendering — no Twitter API calls at runtime if using static data
- Tweet images within cards should be optimized
- No JavaScript SDK required unlike official Twitter embeds
- Lightweight compared to the full Twitter embed widget
- Grid of 3-6 tweet cards is the optimal range for visual balance
