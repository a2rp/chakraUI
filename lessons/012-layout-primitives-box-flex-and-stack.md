# 012 - Layout primitives: Box, Flex, and Stack

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Layout primitives: Box, Flex, and Stack.
- Identify the main API: `Box, Flex, Stack, HStack, VStack, gap, align, justify`.
- Choose an appropriate use case: Use Stack for simple repeated spacing, Flex for alignment and distribution along one axis, and Box for a semantic or styled wrapper.
- Avoid the main implementation risks: Using margins on every child when Stack gap expresses the relationship more clearly.

## Core idea

Box is the generic styleable container, Flex provides one-dimensional flexbox layout, and Stack arranges children with a consistent gap and direction. Their roles help keep structure readable.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `Box, Flex, Stack, HStack, VStack, gap, align, justify`.

Layout primitives render ordinary layout elements. Choose suitable HTML semantics with as or native elements when the wrapper has a meaningful role.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

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

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Use Stack for simple repeated spacing, Flex for alignment and distribution along one axis, and Box for a semantic or styled wrapper.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Using margins on every child when Stack gap expresses the relationship more clearly.
- Adding fixed widths and heights before checking whether the content should naturally size or wrap.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Box is the generic styleable container, Flex provides one-dimensional flexbox layout, and Stack arranges children with a consistent gap and direction. Their roles help keep structure readable. Remember the API boundary: Box, Flex, Stack, HStack, VStack, gap, align, justify. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Build a toolbar that keeps actions aligned at wide widths and wraps or stacks at narrow widths without hardcoded child margins.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="typography-and-text-styles.md">011 - Typography and text styles</a></td>
      <td><a href="../qnas/012-layout-primitives-box-flex-and-stack.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/012-layout-primitives-box-flex-and-stack.md">Chapter example</a></td>
      <td><a href="grid-containers-and-positioning.md">013 - Grid, containers, and positioning</a></td>
    </tr>
  </tbody>
</table>
