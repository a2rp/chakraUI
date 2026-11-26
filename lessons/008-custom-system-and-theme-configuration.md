# 008 - Custom system and theme configuration

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Custom system and theme configuration.
- Identify the main API: `defineConfig, createSystem, defaultConfig, ChakraProvider value`.
- Choose an appropriate use case: Create a custom system when a product needs a coherent theme shared across pages or a reusable design system. Keep application-specific values out of a generic theme unless they are stable shared decisions.
- Avoid the main implementation risks: Passing a v2 extendTheme object into the v3 provider. v3 uses createSystem and token leaves with value fields.

## Core idea

Chakra v3 builds a styling system by combining configuration with a base config through createSystem. The config can define tokens, breakpoints, global CSS, preflight behavior, recipes, and shared style collections.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `defineConfig, createSystem, defaultConfig, ChakraProvider value`.

createSystem returns the styling engine configuration. ChakraProvider's value prop provides it to descendants; the system does not replace React context for application data.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

```jsx
import { ChakraProvider, createSystem, defaultConfig, defineConfig } from "@chakra-ui/react"

const config = defineConfig({
  theme: {
    tokens: {
      colors: {
        brand: {
          500: { value: "#176B87" },
        },
      },
    },
  },
})

const system = createSystem(defaultConfig, config)

export function AppProvider({ children }) {
  return <ChakraProvider value={system}>{children}</ChakraProvider>
}
```

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Create a custom system when a product needs a coherent theme shared across pages or a reusable design system. Keep application-specific values out of a generic theme unless they are stable shared decisions.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Passing a v2 extendTheme object into the v3 provider. v3 uses createSystem and token leaves with value fields.
- Overriding defaults without documenting the decision. Keep config small, typed, and intentional; use defaults until a real product need justifies changing them.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Chakra v3 builds a styling system by combining configuration with a base config through createSystem. The config can define tokens, breakpoints, global CSS, preflight behavior, recipes, and shared style collections. Remember the API boundary: defineConfig, createSystem, defaultConfig, ChakraProvider value. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Move two repeated palette values and a global focus style into a theme file. Pass the resulting system to ChakraProvider.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="007-design-tokens-and-css-variables.md">007 - Design tokens and CSS variables</a></td>
      <td><a href="../qnas/008-custom-system-and-theme-configuration.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/008-custom-system-and-theme-configuration.md">Chapter example</a></td>
      <td><a href="009-semantic-tokens-and-color-palettes.md">009 - Semantic tokens and color palettes</a></td>
    </tr>
  </tbody>
</table>
