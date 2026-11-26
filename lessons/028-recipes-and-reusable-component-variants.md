# 028 - Recipes and reusable component variants

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Recipes and reusable component variants.
- Identify the main API: `defineRecipe, recipe, variants, compoundVariants, defaultVariants, RecipeVariantProps`.
- Choose an appropriate use case: Create a recipe when repeated style combinations form a stable component API. Keep one-off styling local rather than promoting every variation into the design system.
- Avoid the main implementation risks: Creating a new variant for every isolated page need. Too many variants make the component API hard to understand.

## Core idea

A recipe defines base styles and variants for a single-part component. It can standardize choices such as size, visual variant, and state without repeating style props across every consumer.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `defineRecipe, recipe, variants, compoundVariants, defaultVariants, RecipeVariantProps`.

Recipe variants select styles, not business logic. The component still owns semantic markup, behavior, and accessible labels.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

```jsx
import { defineRecipe } from "@chakra-ui/react"

export const noticeRecipe = defineRecipe({
  base: { borderRadius: "md", borderWidth: "1px" },
  variants: {
    tone: {
      info: { bg: "blue.subtle", color: "blue.fg" },
      success: { bg: "green.subtle", color: "green.fg" },
    },
    size: {
      sm: { p: "2", fontSize: "sm" },
      md: { p: "4", fontSize: "md" },
    },
  },
  defaultVariants: { tone: "info", size: "md" },
})
```

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Create a recipe when repeated style combinations form a stable component API. Keep one-off styling local rather than promoting every variation into the design system.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Creating a new variant for every isolated page need. Too many variants make the component API hard to understand.
- Using a variant name that describes CSS mechanics instead of the design intent or semantic role.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

A recipe defines base styles and variants for a single-part component. It can standardize choices such as size, visual variant, and state without repeating style props across every consumer. Remember the API boundary: defineRecipe, recipe, variants, compoundVariants, defaultVariants, RecipeVariantProps. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Define a Notice recipe with tone and size variants, then use typegen and apply it to two instances.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="date-time-color-pickers-sliders-and-rating.md">027 - Date, time, color pickers, sliders, and rating</a></td>
      <td><a href="../qnas/028-recipes-and-reusable-component-variants.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/028-recipes-and-reusable-component-variants.md">Chapter example</a></td>
      <td><a href="slot-recipes-and-multi-part-components.md">029 - Slot recipes and multi-part components</a></td>
    </tr>
  </tbody>
</table>
