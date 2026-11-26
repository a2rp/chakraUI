# 001 - Introduction to Chakra UI v3 Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Build a small profile card with a heading, two text levels, and an action. Explain which parts are content, behavior, and styling.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    001-introduction-to-chakra-ui-v3.jsx
```

## 001-introduction-to-chakra-ui-v3.jsx

```jsx
import { Box, Button, Heading, Text } from "@chakra-ui/react"

export function ProfileCard() {
  return (
    <Box borderWidth="1px" borderRadius="lg" p="5" maxW="sm">
      <Heading size="md">Ari Patel</Heading>
      <Text color="fg.muted" mt="2">Product designer</Text>
      <Button mt="4" colorPalette="teal">View profile</Button>
    </Box>
  )
}
```

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 001, inspect the result described below and interact with every trigger, field, or control.

A bordered profile card appears with consistent spacing and a primary action. Its visual tokens come from the active Chakra system.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Build a small profile card with a heading, two text levels, and an action. Explain which parts are content, behavior, and styling.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Treating Chakra as a complete application framework. It supplies UI and styling primitives, while routing, data fetching, and business logic remain application responsibilities.
- Mixing v2 examples into a v3 project. Check the installed major version before copying old imports, props, or theme configuration.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td>Start of course</td>
      <td><a href="../lessons/001-introduction-to-chakra-ui-v3.md">Chapter lesson</a></td>
      <td><a href="../qnas/001-introduction-to-chakra-ui-v3.md">Chapter Q&amp;A</a></td>
      <td><a href="002-installation-and-project-setup.md">002 - Installation and project setup</a></td>
    </tr>
  </tbody>
</table>
