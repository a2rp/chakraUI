# 012 - Layout primitives: Box, Flex, and Stack Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Build a toolbar that keeps actions aligned at wide widths and wraps or stacks at narrow widths without hardcoded child margins.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    012-layout-primitives-box-flex-and-stack.jsx
```

## 012-layout-primitives-box-flex-and-stack.jsx

```jsx
import { Button, Flex, Heading } from "@chakra-ui/react"

export function PageToolbar() {
  return (
    <Flex as="header" align="center" justify="space-between" gap="4" wrap="wrap">
      <Heading size="md">Projects</Heading>
      <Button colorPalette="blue">New project</Button>
    </Flex>
  )
}
```

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 012, inspect the result described below and interact with every trigger, field, or control.

The heading and action share a row when space permits and can wrap when the available width is small.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Build a toolbar that keeps actions aligned at wide widths and wraps or stacks at narrow widths without hardcoded child margins.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Using margins on every child when Stack gap expresses the relationship more clearly.
- Adding fixed widths and heights before checking whether the content should naturally size or wrap.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="011-typography-and-text-styles.md">011 - Typography and text styles</a></td>
      <td><a href="../lessons/012-layout-primitives-box-flex-and-stack.md">Chapter lesson</a></td>
      <td><a href="../qnas/012-layout-primitives-box-flex-and-stack.md">Chapter Q&amp;A</a></td>
      <td><a href="013-grid-containers-and-positioning.md">013 - Grid, containers, and positioning</a></td>
    </tr>
  </tbody>
</table>
