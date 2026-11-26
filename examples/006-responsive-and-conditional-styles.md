# 006 - Responsive and conditional styles Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Make a two-column card layout that becomes one column on small screens. Add distinct hover and keyboard focus-visible feedback to the action.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    006-responsive-and-conditional-styles.jsx
```

## 006-responsive-and-conditional-styles.jsx

```jsx
import { Box, Button, SimpleGrid } from "@chakra-ui/react"

export function ResponsiveCards() {
  return (
    <SimpleGrid columns={{ base: 1, md: 2 }} gap="4">
      {["Overview", "Activity"].map((label) => (
        <Box key={label} borderWidth="1px" borderRadius="md" p="4">
          {label}
        </Box>
      ))}
      <Button _hover={{ bg: "blue.600" }} _focusVisible={{ outline: "2px solid", outlineColor: "blue.500" }}>
        Open report
      </Button>
    </SimpleGrid>
  )
}
```

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 006, inspect the result described below and interact with every trigger, field, or control.

The cards stack at the base breakpoint and share two columns from the configured md breakpoint upward. Keyboard focus remains visible.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Make a two-column card layout that becomes one column on small screens. Add distinct hover and keyboard focus-visible feedback to the action.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Using array values without documenting which configured breakpoint each position represents. Named objects are often easier to audit.
- Using viewport breakpoints to solve a container-specific problem. Prefer container queries or flexible CSS layout when the available container width is what matters.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="style-props-and-token-aware-styling.md">005 - Style props and token-aware styling</a></td>
      <td><a href="../lessons/006-responsive-and-conditional-styles.md">Chapter lesson</a></td>
      <td><a href="../qnas/006-responsive-and-conditional-styles.md">Chapter Q&amp;A</a></td>
      <td><a href="design-tokens-and-css-variables.md">007 - Design tokens and CSS variables</a></td>
    </tr>
  </tbody>
</table>
