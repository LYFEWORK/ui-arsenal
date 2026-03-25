# Curation Guide

How to evaluate, extract, and package components for the UI Arsenal.

## Step 1: Discover

When you find a new source (like ReactBits), evaluate it against these criteria:

**Must Have:**
- Open source with permissive license (MIT, Apache 2.0, BSD)
- React-compatible (JSX, hooks-based)
- Actively maintained (commits within last 3 months)
- Clean, readable code (not minified black boxes)

**Nice to Have:**
- Tailwind variant available
- TypeScript support
- Minimal external dependencies
- Good documentation with examples

**Reject If:**
- Requires paid license for commercial use
- Monolithic package (must install entire library)
- No customization through props
- Abandoned (no commits in 6+ months)
- Heavy dependencies (Three.js exceptions for background effects only)

## Step 2: Evaluate Individual Components

Not every component in a library is worth including. For each one ask:

1. **Does it solve a real build problem?** If you can't name a specific use case on a Lyfework client site, skip it.
2. **Is it better than what we can build in 30 minutes?** If Claude Code can generate equivalent quality from a text prompt, we don't need it pre-built.
3. **Does it look premium?** Does it pass the "$30k website" test? Would this look out of place on a site for a major brand?
4. **Is it performant?** Heavy WebGL components are fine for hero backgrounds. Not fine for a card hover effect.

## Step 3: Package as a Skill File

1. Copy `_templates/COMPONENT-SKILL.md`
2. Name the file: `[component-name].md` (lowercase, hyphens)
3. Fill in every section. The "When to Use" and "Pairs Well With" sections are the most important. These are what tell Claude Code *when* to apply the component.
4. Include the full source code in the Implementation section
5. Add a real usage example, not just the component in isolation
6. Add Lyfework-specific customization notes

## Step 4: Organize

Drop the file in the correct category folder:

| Folder | What Goes Here |
|--------|----------------|
| `animations/` | Scroll animations, hover effects, cursor effects, page transitions, reveal animations |
| `text-animations/` | Text reveal, blur, gradient, typing, scramble, any text-specific animation |
| `components/` | Cards, modals, lists, accordions, tooltips, interactive UI elements |
| `navigation/` | Menus, docks, tabs, sidebars, breadcrumbs, any navigation pattern |
| `backgrounds/` | Animated backgrounds, particle effects, gradient animations, ambient effects |

If a component spans two categories, put it in the one most relevant to its primary function and cross-reference in the "Pairs Well With" section.

## Step 5: Track the Source

Add an entry to `docs/SOURCES.md` with:
- Source name and URL
- License type
- Number of components extracted
- Date added
- Notes on quality

## Step 6: Push

```bash
cd ~/.lyfework/ui-arsenal
git add .
git commit -m "Add [component-name] from [source]"
git push
```

Then message Ryan to pull.

## Batch Processing Tips

When processing an entire library like ReactBits (100+ components), don't try to package all of them. Here's the workflow:

1. **Scan the full component list** in 10 minutes
2. **Star/flag the top 15-20** that pass the premium test
3. **Package 5 per session** to maintain quality
4. **Review with Ryan** after each batch to confirm they're useful in practice

Quality over quantity. 20 perfectly packaged skills are worth more than 100 sloppy ones.

## Component Quality Tiers

When packaging, tag components with a quality tier in the filename or metadata:

- **Tier 1 (Core):** Use on almost every build. Hero animations, scroll reveals, text effects.
- **Tier 2 (Situational):** Use when the design calls for it. Specific card styles, unique backgrounds.
- **Tier 3 (Showcase):** Impressive but niche. 3D effects, complex interactive demos. Use sparingly.

This helps Claude Code prioritize what to reach for first.
