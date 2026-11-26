# 013 - Grid, containers, and positioning Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Create a responsive dashboard with a main panel and a side summary. At narrow widths, make the summary flow below the main panel.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    013-grid-containers-and-positioning.jsx
```

## 013-grid-containers-and-positioning.jsx

```jsx
import { Grid, GridItem } from "@chakra-ui/react"

export function DashboardGrid() {
  return (
    <Grid templateColumns={{ base: "1fr", lg: "minmax(0, 2fr) minmax(16rem, 1fr)" }} gap="4">
      <GridItem borderWidth="1px" p="5" borderRadius="md">Recent activity</GridItem>
      <GridItem borderWidth="1px" p="5" borderRadius="md">Account summary</GridItem>
    </Grid>
  )
}
```

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 013, inspect the result described below and interact with every trigger, field, or control.

The panels stack on small screens and sit in a flexible two-column layout at the lg breakpoint.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Create a responsive dashboard with a main panel and a side summary. At narrow widths, make the summary flow below the main panel.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Hardcoding a fixed number of columns on every viewport. Use responsive columns or minmax-based CSS so content can reflow.
- Using absolute positioning for normal document layout. Reserve it for overlays and deliberate visual anchoring.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="012-layout-primitives-box-flex-and-stack.md">012 - Layout primitives: Box, Flex, and Stack</a></td>
      <td><a href="../lessons/013-grid-containers-and-positioning.md">Chapter lesson</a></td>
      <td><a href="../qnas/013-grid-containers-and-positioning.md">Chapter Q&amp;A</a></td>
      <td><a href="014-buttons-and-action-components.md">014 - Buttons and action components</a></td>
    </tr>
  </tbody>
</table>
