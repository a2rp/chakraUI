# 005 - Style props and token-aware styling

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Style props and token-aware styling.
- Identify the main API: `Box, p, px, bg, color, borderRadius, _hover, css`.
- Choose an appropriate use case: Use style props for local component styles and small compositions. Move repeated patterns into a recipe, semantic token, or stylesheet when the same decision appears across many components.
- Avoid the main implementation risks: Treating every style value as a design token. Arbitrary CSS values are sometimes useful, but shared design decisions should use named tokens.

## Core idea

Style props let Chakra components express common CSS properties directly in JSX. The styling system resolves token references, responsive values, pseudo selectors, and component-specific props into CSS.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `Box, p, px, bg, color, borderRadius, _hover, css`.

Style props describe presentation. Keep interactive state in React or Chakra's component state machine rather than inferring it from styling props.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

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

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Use style props for local component styles and small compositions. Move repeated patterns into a recipe, semantic token, or stylesheet when the same decision appears across many components.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Treating every style value as a design token. Arbitrary CSS values are sometimes useful, but shared design decisions should use named tokens.
- Building very long style objects inline. Extract repeated or complex styles so JSX continues to describe the interface clearly.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Style props let Chakra components express common CSS properties directly in JSX. The styling system resolves token references, responsive values, pseudo selectors, and component-specific props into CSS. Remember the API boundary: Box, p, px, bg, color, borderRadius, _hover, css. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Create two Card-like Boxes that share a token-based border and spacing style. Extract a shared object or component once the values repeat.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="004-component-anatomy-compound-apis-and-state.md">004 - Component anatomy, compound APIs, and state</a></td>
      <td><a href="../qnas/005-style-props-and-token-aware-styling.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/005-style-props-and-token-aware-styling.md">Chapter example</a></td>
      <td><a href="006-responsive-and-conditional-styles.md">006 - Responsive and conditional styles</a></td>
    </tr>
  </tbody>
</table>
