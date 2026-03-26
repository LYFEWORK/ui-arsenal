---
name: sidebar
source: Aceternity UI
source_url: https://ui.aceternity.com/components/sidebar
category: navigation
tags: sidebar, navigation, slide-out, panel, menu, drawer, animated
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 1
added: 2026-03-25
---

# Sidebar

> Animated slide-out sidebar navigation panel with smooth open/close transitions, icon-to-text expansion, and nested navigation support.

## When to Use
- Dashboard or admin panel navigation for SaaS products
- Mobile menu slide-out panels on marketing sites
- App-style navigation for complex multi-page applications
- Settings or configuration panels on web applications
- Documentation site navigation with collapsible sections

## When NOT to Use
- For simple 3-5 link navigation where a top nav suffices
- On single-page landing pages without navigation depth
- When the sidebar would occlude critical content on small screens

## Pairs Well With
- `floating-navbar` - Top nav for marketing, sidebar for app/dashboard
- `animated-content` - Main content animates when sidebar opens
- `gradient-text` - Brand name in sidebar header with gradient
- `dock` - Quick-action dock at sidebar bottom

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | - | Sidebar content (links, sections) |
| open | boolean | false | Controlled open/close state |
| setOpen | function | - | State setter for open/close |
| className | string | - | Classes for the sidebar panel |
| animate | boolean | true | Enable slide animation |

## Installation
```bash
npx aceternity-ui@latest add sidebar
```

## Usage Example
```jsx
import { Sidebar, SidebarBody, SidebarLink } from "@/components/ui/sidebar";
import { useState } from "react";

const links = [
  { label: "Dashboard", href: "/dashboard", icon: "📊" },
  { label: "Patients", href: "/patients", icon: "👥" },
  { label: "Appointments", href: "/appointments", icon: "📅" },
  { label: "Analytics", href: "/analytics", icon: "📈" },
  { label: "Settings", href: "/settings", icon: "⚙️" },
];

export function ClinicDashboardLayout({ children }) {
  const [open, setOpen] = useState(false);

  return (
    <div className="flex h-screen bg-[#0a0a0a]">
      <Sidebar open={open} setOpen={setOpen}>
        <SidebarBody className="bg-[#0a0a0a] border-r border-white/10">
          <div className="flex flex-col h-full">
            <div className="p-4">
              <h2 className="font-[Manrope] font-800 text-xl bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
                Lyfework
              </h2>
            </div>
            <nav className="flex-1 px-2 space-y-1">
              {links.map((link) => (
                <SidebarLink
                  key={link.href}
                  link={link}
                  className="font-[Manrope] font-400 text-neutral-400 hover:text-white rounded-[8px] px-3 py-2"
                />
              ))}
            </nav>
          </div>
        </SidebarBody>
      </Sidebar>
      <main className="flex-1 overflow-auto p-8">{children}</main>
    </div>
  );
}
```

## Lyfework Customization Notes
- Sidebar background `bg-[#0a0a0a]` with `border-r border-white/10` divider
- Brand name uses `from-[#ff642a] to-[#ff0301]` gradient with Manrope 800
- Nav links use Manrope 400 in neutral-400, `hover:text-white` for active feedback
- Link items use `rounded-[8px]` for hover backgrounds
- Active link state highlighted with `text-[#ff642a]` or gradient background
- GHL dashboard integrations should set sidebar z-index above GHL toolbar elements

## Performance Notes
- Slide animation uses framer-motion `animate` with `width` transition
- Collapsed state renders icon-only, saving horizontal space
- Link hover states are CSS-only, no JavaScript overhead
- Sidebar body uses `overflow-y: auto` for scrollable navigation lists
- Transition between collapsed and expanded is a single width animation, GPU-composited
