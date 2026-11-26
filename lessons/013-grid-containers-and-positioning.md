# 013 - Grid, containers, and positioning

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Grid, containers, and positioning.
- Identify the main API: `Grid, GridItem, SimpleGrid, Container, Center, position, templateColumns`.
- Choose an appropriate use case: Use grid for row-and-column relationships, flex for a one-dimensional sequence, and Container for readable content width.
- Avoid the main implementation risks: Hardcoding a fixed number of columns on every viewport. Use responsive columns or minmax-based CSS so content can reflow.

## Core idea

CSS Grid is useful for two-dimensional page and card layouts. Chakra's Grid and SimpleGrid expose grid behavior through props, while Container, Center, and Positioner help manage width and placement.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `Grid, GridItem, SimpleGrid, Container, Center, position, templateColumns`.

Grid remains CSS layout and adapts without React state. Keep DOM order meaningful so the visual placement does not confuse keyboard or reading order.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

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

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Use grid for row-and-column relationships, flex for a one-dimensional sequence, and Container for readable content width.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Hardcoding a fixed number of columns on every viewport. Use responsive columns or minmax-based CSS so content can reflow.
- Using absolute positioning for normal document layout. Reserve it for overlays and deliberate visual anchoring.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

CSS Grid is useful for two-dimensional page and card layouts. Chakra's Grid and SimpleGrid expose grid behavior through props, while Container, Center, and Positioner help manage width and placement. Remember the API boundary: Grid, GridItem, SimpleGrid, Container, Center, position, templateColumns. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Create a responsive dashboard with a main panel and a side summary. At narrow widths, make the summary flow below the main panel.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="012-layout-primitives-box-flex-and-stack.md">012 - Layout primitives: Box, Flex, and Stack</a></td>
      <td><a href="../qnas/013-grid-containers-and-positioning.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/013-grid-containers-and-positioning.md">Chapter example</a></td>
      <td><a href="014-buttons-and-action-components.md">014 - Buttons and action components</a></td>
    </tr>
  </tbody>
</table>
