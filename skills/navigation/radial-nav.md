---
name: radial-nav
source: Animate UI
source_url: https://animate-ui.com/docs/components/navigation/radial-nav
category: navigation
tags: radial, navigation, spoke, wheel, animated, hub
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# RadialNav

> Radial navigation component with animated spoke layout, positioning navigation items in a wheel pattern around a central hub.

## When to Use
- Portfolio or personal sites with a creative hub-and-spoke navigation concept
- Dashboard home screens with category navigation radiating from center
- Product feature explorers where users navigate between related features
- Interactive presentations or microsites with non-linear navigation
- Skill or capability visualizations where nodes connect to a center

## When NOT to Use
- Standard websites requiring conventional top/side navigation
- Sites with 10+ navigation items — spokes become too dense
- Mobile-primary layouts where radial nav doesn't fit small screens
- E-commerce or content sites needing clear hierarchical navigation
- SEO-critical pages where crawlers expect standard nav patterns

## Pairs Well With
- `radial-menu` - radial menu for actions, radial nav for section navigation
- `gradient-text` - gradient labels on each navigation spoke
- `cursor-follow` - custom cursor that interacts with the spoke layout
- `aurora` - aurora background behind the radial navigation hub

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| items | NavItem[] | — | Array of navigation items |
| centerContent | ReactNode | — | Content for the central hub |
| radius | number | 150 | Distance of items from center |
| className | string | — | Container CSS classes |
| activeItem | string | — | Currently active nav item ID |
| onNavigate | (id: string) => void | — | Callback on navigation item click |
| showConnectors | boolean | true | Show lines connecting items to center |
| connectorColor | string | "rgba(255,255,255,0.1)" | Connector line color |
| animateOnMount | boolean | true | Animate items into position on mount |

## Installation
```bash
npx shadcn@latest add "https://animate-ui.com/r/radial-nav"
```

## Usage Example
```jsx
import { RadialNav } from "@/components/ui/radial-nav";

export function PortfolioHub() {
  return (
    <section className="min-h-screen flex items-center justify-center bg-[#0a0a0a]">
      <RadialNav
        radius={180}
        showConnectors
        connectorColor="rgba(255,100,42,0.15)"
        animateOnMount
        centerContent={
          <div className="w-24 h-24 rounded-full bg-gradient-to-r from-[#ff642a] to-[#ff0301] flex items-center justify-center">
            <span className="font-manrope font-800 text-white text-xl">LW</span>
          </div>
        }
        onNavigate={(id) => scrollToSection(id)}
        items={[
          { id: "services", label: "Services", icon: "🛠" },
          { id: "portfolio", label: "Portfolio", icon: "💼" },
          { id: "about", label: "About", icon: "👤" },
          { id: "blog", label: "Blog", icon: "📝" },
          { id: "contact", label: "Contact", icon: "📧" },
        ]}
        className="[&_button]:font-manrope [&_button]:font-700 [&_button]:text-white [&_button]:text-sm"
      />
    </section>
  );
}
```

## Lyfework Customization Notes
- Center hub: `bg-gradient-to-r from-[#ff642a] to-[#ff0301] rounded-full` with brand initials
- Connector lines: `"rgba(255,100,42,0.15)"` for brand-tinted spoke lines
- Nav item labels: `font-manrope font-700 text-white text-sm`
- Active item: highlight with `text-[#ff642a]` and brighter connector line
- GHL compatible — renders as positioned divs, works within page builder embeds
- On `#0a0a0a` background, the spoke lines and hub glow create a constellation effect

## Performance Notes
- Item positions calculated via trigonometry on mount — not recalculated per frame
- Mount animation uses staggered springs — sequential spoke reveal
- Connector lines are SVG elements — resolution-independent and lightweight
- Hover effects use CSS transitions — no JavaScript overhead
- Click handlers are standard — no gesture detection overhead
