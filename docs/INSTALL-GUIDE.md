# Ryan's Install Guide

## Initial Setup

### 1. Clone the Repo

```bash
# Create Lyfework skills directory if it doesn't exist
mkdir -p ~/.lyfework

# Clone the arsenal
git clone git@github.com:LYFEWORK/ui-arsenal.git ~/.lyfework/ui-arsenal
```

### 2. Configure Claude Code

Add the skills path to your Claude Code configuration so it reads from the arsenal during builds.

**Option A: Project-level (recommended for client builds)**

In your project's `.claude/settings.json`:
```json
{
  "skills_paths": [
    "~/.lyfework/ui-arsenal/skills"
  ]
}
```

**Option B: Global**

In your global Claude Code config:
```json
{
  "skills_paths": [
    "~/.lyfework/ui-arsenal/skills"
  ]
}
```

### 3. Verify

Ask Claude Code: "What UI animation skills do you have access to?"

It should list the components from the arsenal.

## Pulling Updates

Whenever Justyn pushes new components:

```bash
cd ~/.lyfework/ui-arsenal && git pull
```

Claude Code picks up changes on next conversation. No restart needed.

## How Claude Code Uses These Skills

The skill files are structured so Claude Code knows:

1. **What the component does** - visual description
2. **When to use it** - specific build scenarios
3. **When NOT to use it** - anti-patterns
4. **What it pairs with** - other components that combine well
5. **Full implementation code** - ready to drop in
6. **Lyfework customization notes** - brand-specific adjustments

During a build, when you describe what you want (e.g., "I need an animated text reveal for the hero section"), Claude Code will match your description against the "When to Use" sections across all skills and pull the right component.

## Tips for Best Results

- **Be specific in your prompts.** "Add a blur text reveal on the headline" will trigger the right skill better than "make the text look cool."
- **Reference components by name** once you know them: "Use the SplitText animation from the arsenal for this section."
- **Combine components explicitly:** "Use Aurora background with BlurText overlay for the hero."
- **Override when needed:** "Use the TiltedCard component but adjust the rotation to 8 degrees instead of the default."

## MCP Server (Optional, Advanced)

ReactBits also has an MCP server that lets Claude Code query their component library in real-time:

```json
{
  "mcpServers": {
    "reactbits": {
      "command": "npx",
      "args": ["reactbits-dev-mcp-server"]
    }
  }
}
```

This is supplementary to the skills library. The skills library gives Claude Code curated, Lyfework-adapted components. The MCP server gives access to the full raw ReactBits catalog for exploration.
