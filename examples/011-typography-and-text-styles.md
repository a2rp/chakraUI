# 011 - Typography and text styles Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Create a settings panel with a semantic h2 heading, supporting description, and compact metadata text using a consistent text scale.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    011-typography-and-text-styles.jsx
```

## 011-typography-and-text-styles.jsx

```jsx
import { Heading, Stack, Text } from "@chakra-ui/react"

export function SectionIntro() {
  return (
    <Stack gap="2">
      <Heading as="h2" size="lg">Notification preferences</Heading>
      <Text color="fg.muted">
        Choose which updates should reach your inbox.
      </Text>
      <Text textStyle="sm" color="fg.subtle">Last updated today</Text>
    </Stack>
  )
}
```

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 011, inspect the result described below and interact with every trigger, field, or control.

The heading provides a real h2 in the document, while supporting and metadata text use distinct visual roles.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Create a settings panel with a semantic h2 heading, supporting description, and compact metadata text using a consistent text scale.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Selecting Heading size without considering its semantic level. Visual size and heading hierarchy are separate decisions.
- Using truncation without another way to reach the full content. Clipped text must not hide information users need.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="color-modes-and-dark-mode.md">010 - Color modes and dark mode</a></td>
      <td><a href="../lessons/011-typography-and-text-styles.md">Chapter lesson</a></td>
      <td><a href="../qnas/011-typography-and-text-styles.md">Chapter Q&amp;A</a></td>
      <td><a href="layout-primitives-box-flex-and-stack.md">012 - Layout primitives: Box, Flex, and Stack</a></td>
    </tr>
  </tbody>
</table>
