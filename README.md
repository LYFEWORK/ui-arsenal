# Lyfework UI Arsenal

The curated component skills library for building world-class websites at Lyfework.

This repo is **not** a raw code dump. Every component is packaged as a **Claude Code skill file** (.md) that tells the AI *what it does, when to use it, and how to implement it* inside any Lyfework build.

## How It Works

1. **Justyn curates** - Finds components from open-source libraries, evaluates quality, extracts the best pieces
2. **Components get structured** - Each component becomes a skill file following the standard template
3. **Ryan pulls** - Clones or pulls the repo to his local machine
4. **Claude Code reads** - During builds, Claude Code references skill files to intelligently apply the right components

## Repo Structure

```
ui-arsenal/
  skills/
    animations/          # Scroll, hover, cursor, transition effects
    text-animations/     # Text reveal, blur, gradient, typing effects
    components/          # Interactive UI elements (cards, modals, lists)
    navigation/          # Menus, docks, tabs, navigation patterns
    backgrounds/         # Animated backgrounds, particles, gradients
  docs/
    CURATION-GUIDE.md    # How to add new components to the arsenal
    SOURCES.md           # Tracked list of all component sources
    INSTALL-GUIDE.md     # How Ryan sets this up on his machine
  _templates/
    COMPONENT-SKILL.md   # Template for new skill files
```

## For Ryan: Setup

```bash
# Clone once
git clone git@github.com:LYFEWORK/ui-arsenal.git ~/.lyfework/ui-arsenal

# Add to Claude Code skills path
# In your Claude Code config, add:
# skills_path: ~/.lyfework/ui-arsenal/skills

# Pull updates whenever Justyn pushes new components
cd ~/.lyfework/ui-arsenal && git pull
```

## For Justyn: Adding Components

1. Read `docs/CURATION-GUIDE.md`
2. Copy `_templates/COMPONENT-SKILL.md`
3. Fill in the component details
4. Drop it in the right category folder
5. Update `docs/SOURCES.md`
6. Push to repo

## Component Sources

| Source | Type | License | Status |
|--------|------|---------|--------|
| [ReactBits](https://reactbits.dev) | Animated React components | MIT + Commons Clause | Active |

More sources will be added as they are discovered and vetted.

## Standards

- Every skill file follows the template exactly
- No raw code without context (when to use, what it pairs with, props reference)
- All components must be tested before inclusion
- Components must support both CSS and Tailwind variants where available
- Everything maps back to Lyfework build quality standards
