# 029 - Slot recipes and multi-part components Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Create a compact Field slot recipe with root, label, and helperText styles. Apply its styles to a controlled field and regenerate types.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    029-slot-recipes-and-multi-part-components.jsx
```

## 029-slot-recipes-and-multi-part-components.jsx

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

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 029, inspect the result described below and interact with every trigger, field, or control.

The recipe defines styles for the named slots and a coordinated size variant. Connect it through the system and component as documented for the current version.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Create a compact Field slot recipe with root, label, and helperText styles. Apply its styles to a controlled field and regenerate types.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Styling a slot that the component never renders or using a mismatched slot name. Keep recipe slots aligned with actual component anatomy.
- Forgetting to update generated types after adding slots or variants.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="028-recipes-and-reusable-component-variants.md">028 - Recipes and reusable component variants</a></td>
      <td><a href="../lessons/029-slot-recipes-and-multi-part-components.md">Chapter lesson</a></td>
      <td><a href="../qnas/029-slot-recipes-and-multi-part-components.md">Chapter Q&amp;A</a></td>
      <td><a href="030-composition-chakra-factory-and-aschild.md">030 - Composition, Chakra factory, and asChild</a></td>
    </tr>
  </tbody>
</table>
