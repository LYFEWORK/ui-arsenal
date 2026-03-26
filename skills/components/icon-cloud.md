---
name: icon-cloud
source: Magic UI
source_url: https://magicui.design/docs/components/icon-cloud
category: components
tags: icons, cloud, floating, brands, tech-stack
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-25
---

# IconCloud

> Floating cloud of tech/brand icons with interactive 3D rotation and hover effects.

## When to Use
- Tech stack or "built with" sections
- Partner/integration logo showcases
- Skills or technology proficiency displays
- "We work with" sections showing supported platforms
- Developer portfolio technology highlights

## When NOT to Use
- When logos need precise grid alignment and equal sizing
- Text-heavy content that needs structured layout
- Sections where accessibility for screen readers is critical (icons lack context)
- Mobile layouts where the 3D effect is difficult to interact with

## Pairs Well With
- `particles` - Particle field background behind the icon cloud
- `aurora` - Aurora gradient glow beneath the floating icons
- `gradient-text` - "Our tech stack" heading with brand gradient
- `animated-content` - Fade in the cloud section on scroll

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| iconSlugs | string[] | required | Array of Simple Icons slug names |
| imageArray | string[] | [] | Array of custom image URLs |
| className | string | "" | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/icon-cloud"
```

## Usage Example
```jsx
import { IconCloud } from "@/components/magicui/icon-cloud";

const techStack = [
  "react", "nextdotjs", "typescript", "tailwindcss",
  "vercel", "stripe", "postgresql", "prisma",
  "framer", "figma", "github", "nodejs",
];

export function TechStackSection() {
  return (
    <section className="bg-[#0a0a0a] py-24">
      <h2 className="text-center font-manrope font-800 text-3xl text-white mb-4">
        Built with the{" "}
        <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
          best tools
        </span>
      </h2>
      <p className="text-center font-manrope font-400 text-white/60 mb-12">
        Modern stack, production-ready infrastructure
      </p>
      <div className="mx-auto max-w-lg">
        <IconCloud iconSlugs={techStack} />
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Icons render in their native brand colors — no additional tinting needed
- Container should have dark background (`#0a0a0a`) for best contrast
- Use Manrope font-800 headings with gradient text for section titles
- Add `lyf-glass rounded-[12px]` wrapper for a contained card look
- GHL compatible — uses canvas/SVG rendering without Shadow DOM

## Performance Notes
- Uses requestAnimationFrame for 3D rotation — moderate CPU usage
- Icon images are fetched from CDN on mount — cache headers apply
- Limit to 15-20 icons for optimal visual clarity and performance
- Lazy-load the component if placed below the fold
- Consider reducing animation speed on mobile for battery savings
