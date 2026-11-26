# 005 - Style props and token-aware styling Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Create two Card-like Boxes that share a token-based border and spacing style. Extract a shared object or component once the values repeat.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    005-style-props-and-token-aware-styling.jsx
```

## 005-style-props-and-token-aware-styling.jsx

```jsx
import { Box, Button, Text } from "@chakra-ui/react"

export function Notice() {
  return (
    <Box bg="bg.subtle" borderWidth="1px" borderRadius="md" p={{ base: "4", md: "6" }}>
      <Text color="fg">Your profile is ready.</Text>
      <Button mt="3" colorPalette="blue" _hover={{ transform: "translateY(-1px)" }}>
        Continue
      </Button>
    </Box>
  )
}
```

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 005, inspect the result described below and interact with every trigger, field, or control.

The notice uses semantic foreground and background tokens, responsive padding, and a focused hover treatment without a separate stylesheet.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Create two Card-like Boxes that share a token-based border and spacing style. Extract a shared object or component once the values repeat.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Treating every style value as a design token. Arbitrary CSS values are sometimes useful, but shared design decisions should use named tokens.
- Building very long style objects inline. Extract repeated or complex styles so JSX continues to describe the interface clearly.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="component-anatomy-compound-apis-and-state.md">004 - Component anatomy, compound APIs, and state</a></td>
      <td><a href="../lessons/005-style-props-and-token-aware-styling.md">Chapter lesson</a></td>
      <td><a href="../qnas/005-style-props-and-token-aware-styling.md">Chapter Q&amp;A</a></td>
      <td><a href="responsive-and-conditional-styles.md">006 - Responsive and conditional styles</a></td>
    </tr>
  </tbody>
</table>
