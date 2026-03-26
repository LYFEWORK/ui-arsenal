---
name: file-tree
source: Magic UI
source_url: https://magicui.design/docs/components/file-tree
category: components
tags: file, tree, directory, explorer, hierarchy
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-25
---

# FileTree

> Animated file explorer directory tree component for displaying project structures or navigation hierarchies.

## When to Use
- Showing project or SDK file structure in documentation
- Visualizing template or starter kit contents
- Developer onboarding sections explaining codebase layout
- Product feature pages showing organized file management
- Technical landing pages for developer tools

## When NOT to Use
- Actual interactive file management (use a real file manager)
- Non-technical audiences who won't understand file hierarchies
- Simple flat lists without nesting (use a regular list component)

## Pairs Well With
- `animated-content` - Stagger-reveal tree nodes on scroll
- `spotlight-card` - Wrap the file tree in a glowing card
- `gradient-text` - Gradient section heading above the tree
- `blur-text` - Blur-reveal the heading text

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| elements | TreeElement[] | required | Array of file/folder objects with nested children |
| initialExpandedItems | string[] | [] | IDs of initially expanded folders |
| className | string | "" | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/file-tree"
```

## Usage Example
```jsx
import { FileTree } from "@/components/magicui/file-tree";

const projectStructure = [
  {
    id: "1", name: "lyfework-starter", isSelectable: true,
    children: [
      {
        id: "2", name: "src", isSelectable: true,
        children: [
          { id: "3", name: "components", isSelectable: true, children: [
            { id: "4", name: "BookingForm.tsx", isSelectable: true },
            { id: "5", name: "PatientCard.tsx", isSelectable: true },
          ]},
          { id: "6", name: "app", isSelectable: true, children: [
            { id: "7", name: "page.tsx", isSelectable: true },
            { id: "8", name: "layout.tsx", isSelectable: true },
          ]},
        ],
      },
      { id: "9", name: "tailwind.config.ts", isSelectable: true },
      { id: "10", name: "package.json", isSelectable: true },
    ],
  },
];

export function StarterKitSection() {
  return (
    <section className="bg-[#0a0a0a] py-24">
      <h2 className="text-center font-manrope font-800 text-3xl text-white mb-12">
        Everything you need,{" "}
        <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">organized</span>
      </h2>
      <div className="mx-auto max-w-md lyf-glass rounded-[12px] p-6">
        <FileTree elements={projectStructure} initialExpandedItems={["1", "2", "3"]} />
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Wrap in `lyf-glass rounded-[12px]` for card styling on dark backgrounds
- File/folder icons can be customized to match brand accent colors
- Use Manrope font-400 for file names, font-700 for folder names
- Folder expand/collapse animation is CSS-only — GHL compatible
- Works well on `#0a0a0a` backgrounds with `text-white/80` file labels

## Performance Notes
- Pure CSS animations for expand/collapse — no JS animation frames
- Tree depth should be kept to 4-5 levels for readability
- Large trees (100+ items) should use virtualization or lazy expansion
- Initial expanded state set via props avoids runtime DOM manipulation
