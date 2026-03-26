---
name: github-stars-wheel
source: Animate UI
source_url: https://animate-ui.com/docs/components/components/github-stars-wheel
category: components
tags: github, stars, wheel, animated, counter, odometer
dependencies: none
variants: both
license: MIT
tier: 3
added: 2026-03-26
---

# GithubStarsWheel

> Animated wheel/odometer display showing GitHub star count with rolling digit transitions like a slot machine.

## When to Use
- Open source project hero sections needing dramatic star count display
- Developer landing pages where the star count is a key selling point
- Dashboard widgets showing real-time open source metrics
- Event or launch pages celebrating star count milestones
- Portfolio pages showcasing high-traction open source work

## When NOT to Use
- Repositories with very few stars — the wheel animation emphasizes the number
- Non-technical audiences unfamiliar with GitHub star significance
- Small UI elements where the wheel digits are too small to read
- Pages with many animated elements where the wheel adds visual overload

## Pairs Well With
- `number-ticker` - similar odometer aesthetic for other metrics alongside stars
- `aurora` - star wheel over aurora background for a cosmic open source hero
- `gradient-text` - gradient repo name heading above the star wheel
- `particles` - star particles floating around the star count wheel

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| owner | string | — | GitHub repository owner/org |
| repo | string | — | GitHub repository name |
| className | string | — | Additional CSS classes |
| digitClassName | string | — | CSS classes for individual digits |
| animationDuration | number | 1.5 | Wheel spin duration in seconds |
| size | "sm" \| "md" \| "lg" | "md" | Wheel size preset |

## Installation
```bash
npx shadcn@latest add "https://animate-ui.com/r/github-stars-wheel"
```

## Usage Example
```jsx
import { GithubStarsWheel } from "@/components/ui/github-stars-wheel";

export function OpenSourceHero() {
  return (
    <section className="min-h-[50vh] flex flex-col items-center justify-center bg-[#0a0a0a] gap-6">
      <h2 className="font-manrope font-800 text-3xl text-white">Community Love</h2>
      <GithubStarsWheel
        owner="lyfework"
        repo="ui-kit"
        size="lg"
        className="text-white"
        digitClassName="font-manrope font-800 text-5xl bg-gradient-to-b from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent"
        animationDuration={2}
      />
      <p className="font-manrope font-400 text-gray-400">GitHub Stars and counting</p>
    </section>
  );
}
```

## Lyfework Customization Notes
- Digit text: apply brand gradient `from-[#ff642a] to-[#ff0301]` via `bg-clip-text`
- Use `font-manrope font-800` for digits to match brand heading weight
- Surrounding text uses `font-manrope font-400` in `text-gray-400`
- Best displayed on `#0a0a0a` dark backgrounds for maximum contrast
- GHL compatible — pure CSS/JS animation, no external API dependencies at runtime
- Consider preloading the star count server-side to avoid the initial spin-up delay

## Performance Notes
- GitHub API called once on mount — result cached for session duration
- Wheel animation uses CSS transforms on digit columns — GPU-accelerated
- Each digit is an independent column — only changed digits animate
- No continuous animation — wheels spin once and stop at final value
- Graceful fallback to static number display if animation fails
