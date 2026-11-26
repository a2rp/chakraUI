# 010 - Color modes and dark mode

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Color modes and dark mode.
- Identify the main API: `next-themes, ThemeProvider, ColorModeProvider snippet, semantic tokens, _dark`.
- Choose an appropriate use case: Use semantic tokens for most mode-aware colors. Add a toggle only when the product lets users choose a mode, and respect system preference where appropriate.
- Avoid the main implementation risks: Following v2 instructions for ColorModeScript or removed Chakra color-mode hooks. v3 delegates the mode provider to next-themes and the current CLI snippet.

## Core idea

Current Chakra color-mode support uses next-themes, commonly wrapped in a project-owned provider snippet. Components should favor semantic tokens for automatic adaptation and use _dark only for deliberate exceptions.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `next-themes, ThemeProvider, ColorModeProvider snippet, semantic tokens, _dark`.

Color mode is managed by next-themes in the current setup. CSS selectors and variables adapt styles; application hooks can still cause server/client timing differences.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

```jsx
import { Box, Heading, Text } from "@chakra-ui/react"

export function ModeAwareCard() {
  return (
    <Box bg="bg.panel" color="fg" borderColor="border" borderWidth="1px" p="5" borderRadius="lg">
      <Heading size="md">Account settings</Heading>
      <Text color="fg.muted" mt="2">
        Semantic tokens keep text readable in both color modes.
      </Text>
    </Box>
  )
}

// Set up the current color-mode snippet with:
// npx @chakra-ui/cli snippet add color-mode
```

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Use semantic tokens for most mode-aware colors. Add a toggle only when the product lets users choose a mode, and respect system preference where appropriate.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Following v2 instructions for ColorModeScript or removed Chakra color-mode hooks. v3 delegates the mode provider to next-themes and the current CLI snippet.
- Reading mode-dependent values during server rendering without accounting for hydration. Gate client-only visuals or use stable semantic CSS where possible.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Current Chakra color-mode support uses next-themes, commonly wrapped in a project-owned provider snippet. Components should favor semantic tokens for automatic adaptation and use _dark only for deliberate exceptions. Remember the API boundary: next-themes, ThemeProvider, ColorModeProvider snippet, semantic tokens, _dark. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Add a color-mode provider snippet, use semantic tokens in a card, and compare initial rendering under light and dark system preferences.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="semantic-tokens-and-color-palettes.md">009 - Semantic tokens and color palettes</a></td>
      <td><a href="../qnas/010-color-modes-and-dark-mode.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/010-color-modes-and-dark-mode.md">Chapter example</a></td>
      <td><a href="typography-and-text-styles.md">011 - Typography and text styles</a></td>
    </tr>
  </tbody>
</table>
