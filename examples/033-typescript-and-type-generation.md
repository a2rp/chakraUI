# 033 - TypeScript and type generation Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Add a custom token and a recipe variant, run typegen, then use the generated variant type in a reusable component prop.

## Assumptions and prerequisites

- `@chakra-ui/react`, TypeScript, and `@chakra-ui/cli` for type generation.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    033-typescript-and-type-generation.jsx
```

## 033-typescript-and-type-generation.jsx

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

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 033, inspect the result described below and interact with every trigger, field, or control.

The recipe type captures its variant options, and typegen keeps custom system tokens available to the TypeScript tooling.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Add a custom token and a recipe variant, run typegen, then use the generated variant type in a reusable component prop.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Changing theme tokens but not regenerating types. The editor can otherwise report missing values or offer stale completions.
- Using type assertions to silence an error that indicates a real token or component API mismatch.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="032-accessibility-keyboard-interaction-and-rtl.md">032 - Accessibility, keyboard interaction, and RTL</a></td>
      <td><a href="../lessons/033-typescript-and-type-generation.md">Chapter lesson</a></td>
      <td><a href="../qnas/033-typescript-and-type-generation.md">Chapter Q&amp;A</a></td>
      <td><a href="034-nextjs-server-components-and-ssr.md">034 - Next.js, Server Components, and SSR</a></td>
    </tr>
  </tbody>
</table>
