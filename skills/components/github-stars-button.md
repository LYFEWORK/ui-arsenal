---
name: github-stars-button
source: Animate UI
source_url: https://animate-ui.com/docs/components/components/github-stars-button
category: components
tags: github, stars, button, social proof, open source, count
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# GithubStarsButton

> GitHub star count button that displays a live repository star count with animated number transitions.

## When to Use
- Open source project landing pages showing community traction
- Developer tool marketing sites with social proof via star count
- Portfolio pages showcasing open source contributions
- Documentation site headers linking to the GitHub repository
- SaaS product pages where open source components build trust

## When NOT to Use
- Non-developer audiences who don't understand GitHub stars
- Private repositories without public star counts
- Sites where the star count is low and might reduce credibility
- Contexts unrelated to open source or developer ecosystems

## Pairs Well With
- `number-ticker` - animated star count transition when data loads
- `luxe-badge` - "Open Source" badge alongside the stars button
- `shimmer-button` - shimmer effect on the star button for extra attention
- `copy-button` - copy the repo URL alongside the star count display

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| owner | string | — | GitHub repository owner/org |
| repo | string | — | GitHub repository name |
| className | string | — | Additional CSS classes |
| showCount | boolean | true | Display the star count |
| variant | "default" \| "outline" | "default" | Button style variant |

## Installation
```bash
npx shadcn@latest add "https://animate-ui.com/r/github-stars-button"
```

## Usage Example
```jsx
import { GithubStarsButton } from "@/components/ui/github-stars-button";

export function OpenSourceBanner() {
  return (
    <section className="py-12 bg-[#0a0a0a] text-center">
      <p className="font-manrope font-400 text-gray-400 mb-4">
        Powered by open source
      </p>
      <GithubStarsButton
        owner="lyfework"
        repo="ui-components"
        className="rounded-[8px] font-manrope font-700 border border-white/10 bg-white/5 text-white hover:border-[#ff642a]/50"
      />
    </section>
  );
}
```

## Lyfework Customization Notes
- Button border: `border-white/10` resting, `hover:border-[#ff642a]/50` on hover
- Star icon color: `text-[#ff642a]` to match brand accent
- Text uses `font-manrope font-700` for the count and label
- Background: `bg-white/5` on `#0a0a0a` for subtle glass-like appearance
- GHL compatible — fetches data via GitHub API, no special embedding requirements
- Apply `rounded-[8px]` for Lyfework button radius standard

## Performance Notes
- GitHub API call is made once on mount and cached — no repeated fetching
- Star count formatted with Intl.NumberFormat for locale-aware display
- No dependencies — lightweight vanilla implementation
- Gracefully handles API rate limits with fallback display
- Consider server-side rendering the count to avoid layout shift on load
