---
name: folder
source: ReactBits
source_url: https://reactbits.dev/components/folder
category: components
tags: folder, file, open, close, animated, interactive, ui
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# Folder

> An animated folder UI component that opens and closes with a realistic paper-folding motion. Click or hover to reveal contents inside. Works as a creative container for content, file previews, or nested information.

## When to Use

- Portfolio sections where projects are "filed" inside interactive folders
- Resource or download pages where documents are organized by category
- Creative agency sites that want a tactile, skeuomorphic accent
- Course or lesson organizers where chapters are grouped in folders
- Dashboard file managers with animated open/close interactions

## When NOT to Use

- Standard content layouts where a folder metaphor adds confusion
- Mobile-first designs where the open/close animation consumes too much space
- Data-heavy file listings where a simple list/table is more efficient
- Accessibility-critical interfaces where the metaphor may not translate to screen readers

## Pairs Well With

- `animated-content` - Scroll-reveal folder components into view
- `spotlight-card` - Spotlight hover on the folder surface
- `staggered-menu` - Staggered reveal of items inside the folder when opened
- `blur-text` - Blur-reveal content labels inside folders

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Content inside the folder |
| label | string | "Folder" | Label displayed on the folder tab |
| isOpen | boolean | false | Controlled open/close state |
| onToggle | () => void | undefined | Callback when folder is toggled |
| color | string | "#ff642a" | Folder tab/accent color |
| size | "sm" \| "md" \| "lg" | "md" | Folder size preset |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Folder-TS-TW
```

## Usage Example

```jsx
import { useState } from 'react';
import Folder from '@/components/ui/Folder';

function ResourcesSection() {
  const [openIndex, setOpenIndex] = useState(null);

  const resources = [
    {
      label: 'Brand Guidelines',
      files: ['Logo Pack.zip', 'Color Palette.pdf', 'Typography Guide.pdf'],
    },
    {
      label: 'Campaign Assets',
      files: ['Q1 Ad Creatives.fig', 'Email Templates.html', 'Social Media Kit.zip'],
    },
    {
      label: 'Reports',
      files: ['Monthly Analytics.pdf', 'ROI Dashboard.xlsx', 'Pipeline Report.csv'],
    },
  ];

  return (
    <section className="py-24 px-8 bg-[#0a0a0a]">
      <h2 className="text-4xl font-extrabold text-white text-center font-[Manrope] mb-16">
        Client Resources
      </h2>
      <div className="grid grid-cols-1 md:grid-cols-3 gap-8 max-w-5xl mx-auto">
        {resources.map((res, i) => (
          <Folder
            key={i}
            label={res.label}
            isOpen={openIndex === i}
            onToggle={() => setOpenIndex(openIndex === i ? null : i)}
            color="#ff642a"
            size="md"
          >
            <ul className="space-y-2 p-4">
              {res.files.map((file, j) => (
                <li key={j} className="text-sm text-gray-300 flex items-center gap-2">
                  <span className="text-[#ff642a]">&#128196;</span> {file}
                </li>
              ))}
            </ul>
          </Folder>
        ))}
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Folder tab color: `#ff642a` Lyfework orange for the tab accent
- Folder body: `lyf-glass` background with `rounded-xl` (12px) corners
- Font: `Manrope` 700 for folder labels, 400 for file names
- Animation: Framer Motion with `rotateX` for the paper-folding open effect
- GHL compatible via code embed; self-contained component with minimal dependencies
- For client builds, swap folder colors to match their brand accent

## Performance Notes

- Framer Motion `animate` with `rotateX` transform for the folding animation
- Only the open folder renders its children; closed folders are collapsed in the DOM
- CSS `perspective` on the parent creates 3D depth for the fold
- Keep folder contents lightweight; heavy content inside delays the open animation
- `AnimatePresence` handles mount/unmount of folder contents for clean transitions
