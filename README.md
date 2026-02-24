# Furwise Design System v2.0

Furwise APP 的設計系統，包含 design tokens 與 component spec baseline。

## Files

| File | Purpose |
|---|---|
| `furwise-design-system.json` | Design tokens + component specs (single source of truth) |
| `furwise-design-system.html` | Visual documentation with live previews + spec tables |

## For Engineers

### JSON Structure

```
├── colors          # Color tokens (primary, text, background, border, semantic)
├── typography      # Font families, weights, 7-token type scale
├── spacing         # Spacing scale + layout dimensions
├── borderRadius    # Border radius tokens
├── shadows         # Shadow tokens
├── components      # Component specs with token refs (_ref fields)
├── screens         # Screen definitions with Figma node IDs
└── iconography     # Icon set (Iconly Pro)
```

### Component Spec Baseline

Every component in `components` has precise CSS-like properties with `_ref` fields linking back to design tokens:

```json
{
  "backgroundColor": "#3C2E21",
  "backgroundColor_ref": "colors.text.primary",
  "borderRadius": 100,
  "fontSize": 14,
  "fontWeight": 500
}
```

This enables diffing — when a component changes in Figma, only the changed properties are updated.

### How to Use

1. **Read tokens** from the JSON file
2. **View components** by opening the HTML file in a browser
3. **Check specs** — each component shows visual preview + property table side by side

## Workflow

```
Designer updates Figma
  → Updates JSON (tokens + component specs)
  → HTML regenerated (visual reference)
  → Engineer syncs changes
```

## Tech Stack

- **Font:** Inter (Latin) + 源柔ゴシック Gen Jyuu Gothic (CJK)
- **Icons:** Iconly Pro
- **Platform:** iOS (Swift)
