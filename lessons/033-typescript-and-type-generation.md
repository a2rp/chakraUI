# 033 - TypeScript and type generation

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of TypeScript and type generation.
- Identify the main API: `@chakra-ui/react types, RecipeVariantProps, strictTokens, @chakra-ui/cli typegen`.
- Choose an appropriate use case: Use TypeScript to catch invalid props and model component contracts. Enable strictTokens when the team is ready to use the configured system consistently.
- Avoid the main implementation risks: Changing theme tokens but not regenerating types. The editor can otherwise report missing values or offer stale completions.

## Core idea

Chakra's TypeScript definitions provide component props and token-aware types. When a custom system introduces new tokens or recipes, CLI type generation can synchronize the app's generated types with that configuration.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `@chakra-ui/react types, RecipeVariantProps, strictTokens, @chakra-ui/cli typegen`.

Types improve development-time feedback but do not validate runtime data or guarantee that a browser renders the intended result.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

```jsx
import type { RecipeVariantProps } from "@chakra-ui/react"
import { defineRecipe } from "@chakra-ui/react"

export const badgeRecipe = defineRecipe({
  base: { borderRadius: "full", px: "3" },
  variants: {
    tone: {
      neutral: { bg: "gray.subtle", color: "gray.fg" },
      success: { bg: "green.subtle", color: "green.fg" },
    },
  },
})

export type BadgeRecipeProps = RecipeVariantProps<typeof badgeRecipe>

// Regenerate configured Chakra types with:
// npx @chakra-ui/cli typegen ./src/theme.ts
```

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Use TypeScript to catch invalid props and model component contracts. Enable strictTokens when the team is ready to use the configured system consistently.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Changing theme tokens but not regenerating types. The editor can otherwise report missing values or offer stale completions.
- Using type assertions to silence an error that indicates a real token or component API mismatch.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Chakra's TypeScript definitions provide component props and token-aware types. When a custom system introduces new tokens or recipes, CLI type generation can synchronize the app's generated types with that configuration. Remember the API boundary: @chakra-ui/react types, RecipeVariantProps, strictTokens, @chakra-ui/cli typegen. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Add a custom token and a recipe variant, run typegen, then use the generated variant type in a reusable component prop.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="accessibility-keyboard-interaction-and-rtl.md">032 - Accessibility, keyboard interaction, and RTL</a></td>
      <td><a href="../qnas/033-typescript-and-type-generation.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/033-typescript-and-type-generation.md">Chapter example</a></td>
      <td><a href="nextjs-server-components-and-ssr.md">034 - Next.js, Server Components, and SSR</a></td>
    </tr>
  </tbody>
</table>
