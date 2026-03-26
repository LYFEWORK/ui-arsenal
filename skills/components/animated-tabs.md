---
name: animated-tabs
source: Luxe
source_url: https://www.luxeui.com/ui/animated-tabs
category: components
tags: tabs, animated, indicator, navigation, segmented control
dependencies: framer-motion
variants: both
license: MIT
tier: 1
added: 2026-03-26
---

# AnimatedTabs

> Tabs component with a smooth animated indicator that slides between active tabs using spring physics.

## When to Use
- Feature comparison sections switching between plan tiers or product views
- Dashboard navigation between different data views or settings panels
- Portfolio sections toggling between project categories (Web, Mobile, Branding)
- Pricing page toggling between monthly/yearly billing periods
- Service pages switching between different service offerings

## When NOT to Use
- Navigation with 8+ tabs — use a dropdown or sidebar instead
- Deeply nested tab content requiring URL routing — use actual routes
- Content that should all be visible simultaneously — use accordion
- Mobile layouts where horizontal tabs overflow — use a scrollable tab bar

## Pairs Well With
- `animated-content` - animate tab panel content as it appears on switch
- `spotlight-card` - tab content panels rendered as spotlight cards
- `blur-text` - blur-reveal the heading inside each tab panel
- `number-ticker` - animate numeric values when switching between data tabs

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| tabs | TabItem[] | — | Array of tab items with label and content |
| defaultValue | string | — | Default active tab value |
| value | string | — | Controlled active tab value |
| onValueChange | (value: string) => void | — | Callback on tab change |
| className | string | — | Container CSS classes |
| indicatorClassName | string | — | Active indicator CSS classes |
| tabClassName | string | — | Individual tab button CSS classes |

## Installation
```bash
npx shadcn@latest add "https://www.luxeui.com/r/animated-tabs"
```

## Usage Example
```jsx
import { AnimatedTabs } from "@/components/ui/animated-tabs";

export function ServiceTabs() {
  return (
    <section className="py-20 bg-[#0a0a0a]">
      <h2 className="font-manrope font-800 text-4xl text-white text-center mb-12">
        Our Services
      </h2>
      <AnimatedTabs
        className="max-w-3xl mx-auto"
        indicatorClassName="bg-gradient-to-r from-[#ff642a] to-[#ff0301] rounded-[8px]"
        tabClassName="font-manrope font-700 text-gray-400 data-[state=active]:text-white px-6 py-3"
        tabs={[
          {
            label: "Web Design",
            value: "web",
            content: (
              <div className="lyf-glass rounded-[12px] p-8 mt-6">
                <p className="font-manrope font-400 text-gray-300">
                  Custom websites built to convert visitors into patients.
                </p>
              </div>
            ),
          },
          {
            label: "SEO",
            value: "seo",
            content: (
              <div className="lyf-glass rounded-[12px] p-8 mt-6">
                <p className="font-manrope font-400 text-gray-300">
                  Dominate local search results in your area.
                </p>
              </div>
            ),
          },
          {
            label: "Automation",
            value: "automation",
            content: (
              <div className="lyf-glass rounded-[12px] p-8 mt-6">
                <p className="font-manrope font-400 text-gray-300">
                  GHL-powered workflows that run your practice on autopilot.
                </p>
              </div>
            ),
          },
        ]}
      />
    </section>
  );
}
```

## Lyfework Customization Notes
- Set `indicatorClassName` to `"bg-gradient-to-r from-[#ff642a] to-[#ff0301] rounded-[8px]"` for brand indicator
- Use `font-manrope font-700` on tab labels for brand consistency
- Tab content panels should use `lyf-glass rounded-[12px]` card styling
- Active tab text should be white, inactive `text-gray-400` on `#0a0a0a` backgrounds
- GHL compatible — no DOM measurement conflicts with iframe embedding
- Consider pill-style variant with `rounded-full` for hero section toggles

## Performance Notes
- Layout animation uses framer-motion `layoutId` — single animated element, not per-tab
- Only active tab content is rendered — lazy mounting by default
- Spring physics animation completes in ~300ms with no jank
- Indicator position calculated via DOM measurement — cached between renders
- No forced reflows — uses transform-based positioning
