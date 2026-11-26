# 009 - Semantic tokens and color palettes Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Build a success callout with semantic foreground and background tokens, then change the active color palette and compare component states.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    009-semantic-tokens-and-color-palettes.jsx
```

## 009-semantic-tokens-and-color-palettes.jsx

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

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 009, inspect the result described below and interact with every trigger, field, or control.

The panel adapts through semantic surface and text tokens, while the Badge and Button use coordinated green palette variants.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Build a success callout with semantic foreground and background tokens, then change the active color palette and compare component states.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Using a primitive color for a semantic role everywhere. A literal gray value does not tell future maintainers whether it is a surface, muted text, or border.
- Assuming colorPalette changes every color prop automatically. It affects palette-aware component styles; explicit style values still mean what they say.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="008-custom-system-and-theme-configuration.md">008 - Custom system and theme configuration</a></td>
      <td><a href="../lessons/009-semantic-tokens-and-color-palettes.md">Chapter lesson</a></td>
      <td><a href="../qnas/009-semantic-tokens-and-color-palettes.md">Chapter Q&amp;A</a></td>
      <td><a href="010-color-modes-and-dark-mode.md">010 - Color modes and dark mode</a></td>
    </tr>
  </tbody>
</table>
