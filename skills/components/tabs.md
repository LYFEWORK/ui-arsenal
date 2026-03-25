---
name: tabs
source: ReactBits
source_url: https://reactbits.dev/components/tabs
category: components
tags: tabs, navigation, content, switch, panel, animated
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# Tabs

> Animated tab navigation with a sliding active indicator and smooth content transitions. The indicator bar glides between tabs on click.

## When to Use

- Feature comparison sections (tab per feature category)
- Pricing page with different plan views
- Service breakdowns (tab per service)
- Dashboard or settings panels with multiple sections
- Any content that can be logically grouped into 2-5 categories

## When NOT to Use

- More than 6 tabs (switch to a different navigation pattern)
- Content that users need to see simultaneously (tabs hide content)
- Mobile layouts where tabs are too narrow to read labels

## Pairs Well With

- `animated-content` - Tab content fades/slides in on tab switch
- `spotlight-card` - Tab panels containing spotlight card grids
- `count-up` - Stats inside tab panels that count up when tab is activated
- `blur-text` - Section headline above tabs

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| tabs | TabItem[] | [] | Array of label/content pairs |
| defaultTab | number | 0 | Initially active tab index |
| indicatorColor | string | "#ff642a" | Active tab indicator color |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Tabs-TS-TW
```

## Usage Example

```jsx
import Tabs from '@/components/ui/Tabs';

function ServiceBreakdown() {
  const tabs = [
    { label: 'Build', content: <div className="p-8"><h3 className="text-xl font-bold text-white">System Build</h3><p className="mt-3 text-gray-400">Full CRM, automations, and AI modules installed in 30 days.</p></div> },
    { label: 'Software', content: <div className="p-8"><h3 className="text-xl font-bold text-white">Software Plan</h3><p className="mt-3 text-gray-400">$297/mo. You manage the system. We provide the tools.</p></div> },
    { label: 'Managed', content: <div className="p-8"><h3 className="text-xl font-bold text-white">Managed Plan</h3><p className="mt-3 text-gray-400">$997/mo. We run everything. You focus on patients.</p></div> },
  ];

  return (
    <section className="py-24 px-8 max-w-3xl mx-auto">
      <Tabs tabs={tabs} indicatorColor="#ff642a" />
    </section>
  );
}
```

## Lyfework Customization Notes

- Indicator: Lyfework gradient bar (`from-[#ff642a] to-[#ff0301]`), 3px height
- Tab labels: Manrope 700, white when active, gray-500 when inactive
- Tab content transitions: slide left/right based on direction of tab change
- 3-4 tabs is the sweet spot. 2 tabs might work better as a toggle.
- Works in GHL with React embeds

## Performance Notes

- framer-motion layout animation for the sliding indicator
- Content panels use AnimatePresence for enter/exit transitions
- Only active panel renders content (lazy panels)
- Lightweight, no performance concerns
