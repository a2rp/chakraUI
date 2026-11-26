# 038 - Production design system and maintenance

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Production design system and maintenance.
- Identify the main API: `system config, semantic tokens, recipes, slot recipes, typegen, visual and interaction tests`.
- Choose an appropriate use case: Promote a pattern into the system when multiple teams or screens share the same intent and behavior. Keep one-off product decisions local until repetition proves the abstraction.
- Avoid the main implementation risks: Turning every component into a design-system primitive. Excess abstractions make the system harder to change and can hide native semantics.

## Core idea

A production design system combines stable tokens, component recipes, accessible patterns, documentation, ownership, and upgrade practices. The goal is not maximum abstraction; it is reliable shared decisions that help teams build consistent interfaces.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `system config, semantic tokens, recipes, slot recipes, typegen, visual and interaction tests`.

A design system is a maintained product interface. Version custom components, document accessibility expectations, and test behavior in consuming applications.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

```jsx
import { ChakraProvider, createSystem, defaultConfig, defineConfig } from "@chakra-ui/react"

const config = defineConfig({
  theme: {
    semanticTokens: {
      colors: {
        "surface.panel": { value: { _light: "{colors.white}", _dark: "{colors.gray.900}" } },
      },
    },
  },
})

const system = createSystem(defaultConfig, config)

export function DesignSystemProvider({ children }) {
  return <ChakraProvider value={system}>{children}</ChakraProvider>
}
```

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Promote a pattern into the system when multiple teams or screens share the same intent and behavior. Keep one-off product decisions local until repetition proves the abstraction.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Turning every component into a design-system primitive. Excess abstractions make the system harder to change and can hide native semantics.
- Changing shared tokens without regression checks or migration notes. Token changes can affect many routes at once.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

A production design system combines stable tokens, component recipes, accessible patterns, documentation, ownership, and upgrade practices. The goal is not maximum abstraction; it is reliable shared decisions that help teams build consistent interfaces. Remember the API boundary: system config, semantic tokens, recipes, slot recipes, typegen, visual and interaction tests. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Design a small product system with semantic surface tokens, one Button recipe, one Field slot recipe, and a review checklist for changes.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="037-migration-from-chakra-ui-v2-to-v3.md">037 - Migration from Chakra UI v2 to v3</a></td>
      <td><a href="../qnas/038-production-design-system-and-maintenance.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/038-production-design-system-and-maintenance.md">Chapter example</a></td>
      <td>End of course</td>
    </tr>
  </tbody>
</table>
