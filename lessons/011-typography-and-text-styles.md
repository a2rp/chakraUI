# 011 - Typography and text styles

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Typography and text styles.
- Identify the main API: `Heading, Text, textStyle, fontFamily, lineHeight, truncate`.
- Choose an appropriate use case: Use headings for document structure and text styles for recurring visual roles. Choose an HTML heading level from the page outline rather than from its appearance alone.
- Avoid the main implementation risks: Selecting Heading size without considering its semantic level. Visual size and heading hierarchy are separate decisions.

## Core idea

Typography is a system of readable hierarchy, not just font-size props. Chakra provides semantic text components and theme-defined text styles that can coordinate size, weight, line height, and letter spacing.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `Heading, Text, textStyle, fontFamily, lineHeight, truncate`.

Typography components render semantic HTML defaults and style props. Preserve logical headings and sufficient contrast regardless of visual tokens.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

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

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Use headings for document structure and text styles for recurring visual roles. Choose an HTML heading level from the page outline rather than from its appearance alone.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Selecting Heading size without considering its semantic level. Visual size and heading hierarchy are separate decisions.
- Using truncation without another way to reach the full content. Clipped text must not hide information users need.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Typography is a system of readable hierarchy, not just font-size props. Chakra provides semantic text components and theme-defined text styles that can coordinate size, weight, line height, and letter spacing. Remember the API boundary: Heading, Text, textStyle, fontFamily, lineHeight, truncate. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Create a settings panel with a semantic h2 heading, supporting description, and compact metadata text using a consistent text scale.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="color-modes-and-dark-mode.md">010 - Color modes and dark mode</a></td>
      <td><a href="../qnas/011-typography-and-text-styles.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/011-typography-and-text-styles.md">Chapter example</a></td>
      <td><a href="layout-primitives-box-flex-and-stack.md">012 - Layout primitives: Box, Flex, and Stack</a></td>
    </tr>
  </tbody>
</table>
