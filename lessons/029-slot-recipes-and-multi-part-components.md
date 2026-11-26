# 029 - Slot recipes and multi-part components

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Slot recipes and multi-part components.
- Identify the main API: `defineSlotRecipe, slots, base, variants, useSlotRecipe, @chakra-ui/react/recipes`.
- Choose an appropriate use case: Use slot recipes when several parts share variants or state. Use a single-part recipe when only one rendered element needs a style variant.
- Avoid the main implementation risks: Styling a slot that the component never renders or using a mismatched slot name. Keep recipe slots aligned with actual component anatomy.

## Core idea

A slot recipe styles several named parts of one component, such as a field root, label, and input. It keeps related part styles coordinated while preserving the component's compound structure.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `defineSlotRecipe, slots, base, variants, useSlotRecipe, @chakra-ui/react/recipes`.

The slot recipe returns coordinated styles for each named part. Keep state and accessibility behavior in the component implementation rather than duplicating it in CSS.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

```jsx
import { defineSlotRecipe } from "@chakra-ui/react"

export const fieldRecipe = defineSlotRecipe({
  slots: ["root", "label", "helperText"],
  base: {
    root: { display: "flex", flexDirection: "column", gap: "2" },
    label: { fontWeight: "medium" },
    helperText: { color: "fg.muted", fontSize: "sm" },
  },
  variants: {
    size: {
      sm: { root: { gap: "1" }, label: { fontSize: "sm" } },
      md: { root: { gap: "2" }, label: { fontSize: "md" } },
    },
  },
})
```

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Use slot recipes when several parts share variants or state. Use a single-part recipe when only one rendered element needs a style variant.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Styling a slot that the component never renders or using a mismatched slot name. Keep recipe slots aligned with actual component anatomy.
- Forgetting to update generated types after adding slots or variants.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

A slot recipe styles several named parts of one component, such as a field root, label, and input. It keeps related part styles coordinated while preserving the component's compound structure. Remember the API boundary: defineSlotRecipe, slots, base, variants, useSlotRecipe, @chakra-ui/react/recipes. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Create a compact Field slot recipe with root, label, and helperText styles. Apply its styles to a controlled field and regenerate types.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="028-recipes-and-reusable-component-variants.md">028 - Recipes and reusable component variants</a></td>
      <td><a href="../qnas/029-slot-recipes-and-multi-part-components.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/029-slot-recipes-and-multi-part-components.md">Chapter example</a></td>
      <td><a href="030-composition-chakra-factory-and-aschild.md">030 - Composition, Chakra factory, and asChild</a></td>
    </tr>
  </tbody>
</table>
