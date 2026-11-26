# 006 - Responsive and conditional styles

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Responsive and conditional styles.
- Identify the main API: `Responsive values, breakpoints, _hover, _focusVisible, hideFrom, hideBelow`.
- Choose an appropriate use case: Use responsive values for presentation that changes with viewport size. Prefer CSS-first responsiveness for layout; use JavaScript media queries only when behavior truly changes.
- Avoid the main implementation risks: Using array values without documenting which configured breakpoint each position represents. Named objects are often easier to audit.

## Core idea

Chakra supports responsive style values and conditional style props. Responsive objects map values to named breakpoints, while conditions such as _hover and _focusVisible express interaction states.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `Responsive values, breakpoints, _hover, _focusVisible, hideFrom, hideBelow`.

Responsive style changes are CSS-driven; they do not require React state or a resize listener. Conditional style props map to CSS selectors or media conditions.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

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

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Use responsive values for presentation that changes with viewport size. Prefer CSS-first responsiveness for layout; use JavaScript media queries only when behavior truly changes.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Using array values without documenting which configured breakpoint each position represents. Named objects are often easier to audit.
- Using viewport breakpoints to solve a container-specific problem. Prefer container queries or flexible CSS layout when the available container width is what matters.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Chakra supports responsive style values and conditional style props. Responsive objects map values to named breakpoints, while conditions such as _hover and _focusVisible express interaction states. Remember the API boundary: Responsive values, breakpoints, _hover, _focusVisible, hideFrom, hideBelow. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Make a two-column card layout that becomes one column on small screens. Add distinct hover and keyboard focus-visible feedback to the action.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="005-style-props-and-token-aware-styling.md">005 - Style props and token-aware styling</a></td>
      <td><a href="../qnas/006-responsive-and-conditional-styles.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/006-responsive-and-conditional-styles.md">Chapter example</a></td>
      <td><a href="007-design-tokens-and-css-variables.md">007 - Design tokens and CSS variables</a></td>
    </tr>
  </tbody>
</table>
