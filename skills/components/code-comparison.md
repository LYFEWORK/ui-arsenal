---
name: code-comparison
source: Magic UI
source_url: https://magicui.design/docs/components/code-comparison
category: components
tags: code, diff, comparison, before-after, developer
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-25
---

# CodeComparison

> Side-by-side code diff comparison component for showcasing before/after code transformations.

## When to Use
- Showing before/after code improvements in developer tool landing pages
- Comparing old vs new API implementations
- Demonstrating SDK simplification (e.g., "5 lines instead of 50")
- Technical blog posts or documentation pages
- AI code generation showcases

## When NOT to Use
- Non-technical audiences who won't understand code
- Full file diffs with hundreds of lines (use a dedicated diff viewer)
- When the comparison is not code-related (use a generic before/after slider)

## Pairs Well With
- `blur-text` - Blur-reveal the code comparison heading on scroll
- `animated-content` - Animate the comparison panel into view
- `spotlight-card` - Wrap the comparison in a spotlight-hover card
- `gradient-text` - "Before / After" labels with brand gradient

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| beforeCode | string | required | Code string for the "before" panel |
| afterCode | string | required | Code string for the "after" panel |
| language | string | "typescript" | Syntax highlighting language |
| filename | string | "" | Filename shown in tab header |
| lightTheme | string | "github-light" | Theme for light mode |
| darkTheme | string | "github-dark" | Theme for dark mode |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/code-comparison"
```

## Usage Example
```jsx
import { CodeComparison } from "@/components/magicui/code-comparison";

export function SDKShowcase() {
  const before = `// Old way - manual API calls
const response = await fetch('/api/appointments', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ clientId, date, service }),
});
const data = await response.json();
if (!response.ok) throw new Error(data.message);`;

  const after = `// With Lyfework SDK
const appointment = await lyfework.appointments.create({
  clientId, date, service
});`;

  return (
    <section className="bg-[#0a0a0a] py-24">
      <h2 className="text-center font-manrope font-800 text-3xl text-white mb-12">
        Ship <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">faster</span>
      </h2>
      <div className="mx-auto max-w-4xl">
        <CodeComparison
          beforeCode={before}
          afterCode={after}
          language="typescript"
          filename="booking.ts"
          darkTheme="github-dark"
        />
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Use `github-dark` theme to blend with the `#0a0a0a` background
- Add a subtle `border border-white/10 rounded-[12px]` wrapper for card consistency
- Headings above should use Manrope font-800 with the brand gradient on key words
- Keep code examples relevant to clinic/SaaS workflows for Lyfework context
- GHL compatible — renders as standard HTML pre/code blocks

## Performance Notes
- Syntax highlighting runs at build time if using static content
- Dynamic code strings trigger client-side highlighting — keep snippets short
- No animation overhead — purely structural component
- Consider lazy loading if below the fold on long landing pages
