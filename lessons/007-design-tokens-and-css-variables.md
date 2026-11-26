# 007 - Design tokens and CSS variables

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Design tokens and CSS variables.
- Identify the main API: `theme.tokens, system.token, system.token.var, CSS custom properties`.
- Choose an appropriate use case: Use tokens for values that represent a reusable design decision. Keep raw CSS variables for integration boundaries or values that are intentionally outside the system.
- Avoid the main implementation risks: Forgetting the v3 token shape. Custom token leaves use objects with a value field, such as colors.brand.500.value.

## Core idea

Design tokens give recurring values names, such as colors, spacing, typography, and radii. Chakra's system emits CSS variables for theme values, enabling consistent styling and runtime color-scheme adaptation.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `theme.tokens, system.token, system.token.var, CSS custom properties`.

Tokens are resolved by the styling system and can be referenced by Chakra styles. The system's token lookup helpers expose raw values or CSS variable references for integrations.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

```jsx
import { Box } from "@chakra-ui/react"

export function TokenPanel() {
  return (
    <Box bg="brand.500" color="white" p="space.4" borderRadius="radii.card">
      Token-backed panel
    </Box>
  )
}

// Custom token leaves use { value: ... } in the system configuration.
```

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Use tokens for values that represent a reusable design decision. Keep raw CSS variables for integration boundaries or values that are intentionally outside the system.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Forgetting the v3 token shape. Custom token leaves use objects with a value field, such as colors.brand.500.value.
- Treating the generated CSS variable name as a permanent public contract. Prefer semantic token names or the system token helpers over hardcoded generated names.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Design tokens give recurring values names, such as colors, spacing, typography, and radii. Chakra's system emits CSS variables for theme values, enabling consistent styling and runtime color-scheme adaptation. Remember the API boundary: theme.tokens, system.token, system.token.var, CSS custom properties. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Add brand colors and spacing tokens to the system. Use one token through a style prop and inspect its computed CSS variable in browser developer tools.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="responsive-and-conditional-styles.md">006 - Responsive and conditional styles</a></td>
      <td><a href="../qnas/007-design-tokens-and-css-variables.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/007-design-tokens-and-css-variables.md">Chapter example</a></td>
      <td><a href="custom-system-and-theme-configuration.md">008 - Custom system and theme configuration</a></td>
    </tr>
  </tbody>
</table>
