# 010 - Color modes and dark mode Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Add a color-mode provider snippet, use semantic tokens in a card, and compare initial rendering under light and dark system preferences.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    010-color-modes-and-dark-mode.jsx
```

## 010-color-modes-and-dark-mode.jsx

```jsx
import { Box, Heading, Text } from "@chakra-ui/react"

export function ModeAwareCard() {
  return (
    <Box bg="bg.panel" color="fg" borderColor="border" borderWidth="1px" p="5" borderRadius="lg">
      <Heading size="md">Account settings</Heading>
      <Text color="fg.muted" mt="2">
        Semantic tokens keep text readable in both color modes.
      </Text>
    </Box>
  )
}

// Set up the current color-mode snippet with:
// npx @chakra-ui/cli snippet add color-mode
```

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 010, inspect the result described below and interact with every trigger, field, or control.

The card uses mode-aware semantic variables and does not need separate hardcoded light and dark colors for each element.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Add a color-mode provider snippet, use semantic tokens in a card, and compare initial rendering under light and dark system preferences.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Following v2 instructions for ColorModeScript or removed Chakra color-mode hooks. v3 delegates the mode provider to next-themes and the current CLI snippet.
- Reading mode-dependent values during server rendering without accounting for hydration. Gate client-only visuals or use stable semantic CSS where possible.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="009-semantic-tokens-and-color-palettes.md">009 - Semantic tokens and color palettes</a></td>
      <td><a href="../lessons/010-color-modes-and-dark-mode.md">Chapter lesson</a></td>
      <td><a href="../qnas/010-color-modes-and-dark-mode.md">Chapter Q&amp;A</a></td>
      <td><a href="011-typography-and-text-styles.md">011 - Typography and text styles</a></td>
    </tr>
  </tbody>
</table>
