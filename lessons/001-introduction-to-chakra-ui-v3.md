# 001 - Introduction to Chakra UI v3

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Introduction to Chakra UI v3.
- Identify the main API: `@chakra-ui/react, ChakraProvider, defaultSystem, Box, semantic tokens`.
- Choose an appropriate use case: Use Chakra when a React product benefits from reusable accessible building blocks and a shared visual system; use plain CSS when a dependency or abstraction is not justified.
- Avoid the main implementation risks: Treating Chakra as a complete application framework. It supplies UI and styling primitives, while routing, data fetching, and business logic remain application responsibilities.

## Core idea

Chakra UI is a React component and styling system that combines accessible component behavior with a design-token-aware styling API. Version 3 uses compound components, a configurable system, and a runtime CSS-in-JS styling layer powered by Emotion.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `@chakra-ui/react, ChakraProvider, defaultSystem, Box, semantic tokens`.

Chakra helps with component structure and interaction patterns, but the application still owns content semantics, correct labels, and meaningful feedback.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

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

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Use Chakra when a React product benefits from reusable accessible building blocks and a shared visual system; use plain CSS when a dependency or abstraction is not justified.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Treating Chakra as a complete application framework. It supplies UI and styling primitives, while routing, data fetching, and business logic remain application responsibilities.
- Mixing v2 examples into a v3 project. Check the installed major version before copying old imports, props, or theme configuration.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Chakra UI is a React component and styling system that combines accessible component behavior with a design-token-aware styling API. Version 3 uses compound components, a configurable system, and a runtime CSS-in-JS styling layer powered by Emotion. Remember the API boundary: @chakra-ui/react, ChakraProvider, defaultSystem, Box, semantic tokens. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Build a small profile card with a heading, two text levels, and an action. Explain which parts are content, behavior, and styling.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td>Start of course</td>
      <td><a href="../qnas/001-introduction-to-chakra-ui-v3.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/001-introduction-to-chakra-ui-v3.md">Chapter example</a></td>
      <td><a href="installation-and-project-setup.md">002 - Installation and project setup</a></td>
    </tr>
  </tbody>
</table>
