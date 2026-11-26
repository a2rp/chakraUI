# 009 - Semantic tokens and color palettes

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Semantic tokens and color palettes.
- Identify the main API: `theme.semanticTokens, bg.subtle, fg.muted, colorPalette, virtual color`.
- Choose an appropriate use case: Prefer semantic names for component surfaces and text because they express intent and can change with color mode. Use primitive palette values for deliberate one-off emphasis.
- Avoid the main implementation risks: Using a primitive color for a semantic role everywhere. A literal gray value does not tell future maintainers whether it is a surface, muted text, or border.

## Core idea

Primitive tokens identify raw values, while semantic tokens describe how a value is used, such as surface, text, border, or focus ring. Chakra also exposes component colorPalette values that map a component's palette-aware styles to a chosen color family.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `theme.semanticTokens, bg.subtle, fg.muted, colorPalette, virtual color`.

Semantic tokens resolve to mode-aware values. Component colorPalette selects coordinated recipe values rather than setting arbitrary CSS on every descendant.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

```jsx
import { Badge, Box, Button, Text } from "@chakra-ui/react"

export function StatusPanel() {
  return (
    <Box bg="bg.subtle" color="fg" borderWidth="1px" p="4" borderRadius="md">
      <Badge colorPalette="green">Healthy</Badge>
      <Text color="fg.muted" mt="2">All services are responding.</Text>
      <Button colorPalette="green" mt="3">View status</Button>
    </Box>
  )
}
```

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Prefer semantic names for component surfaces and text because they express intent and can change with color mode. Use primitive palette values for deliberate one-off emphasis.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Using a primitive color for a semantic role everywhere. A literal gray value does not tell future maintainers whether it is a surface, muted text, or border.
- Assuming colorPalette changes every color prop automatically. It affects palette-aware component styles; explicit style values still mean what they say.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Primitive tokens identify raw values, while semantic tokens describe how a value is used, such as surface, text, border, or focus ring. Chakra also exposes component colorPalette values that map a component's palette-aware styles to a chosen color family. Remember the API boundary: theme.semanticTokens, bg.subtle, fg.muted, colorPalette, virtual color. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Build a success callout with semantic foreground and background tokens, then change the active color palette and compare component states.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="008-custom-system-and-theme-configuration.md">008 - Custom system and theme configuration</a></td>
      <td><a href="../qnas/009-semantic-tokens-and-color-palettes.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/009-semantic-tokens-and-color-palettes.md">Chapter example</a></td>
      <td><a href="010-color-modes-and-dark-mode.md">010 - Color modes and dark mode</a></td>
    </tr>
  </tbody>
</table>
