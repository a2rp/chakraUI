# 028 - Recipes and reusable component variants Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Define a Notice recipe with tone and size variants, then use typegen and apply it to two instances.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    028-recipes-and-reusable-component-variants.jsx
```

## 028-recipes-and-reusable-component-variants.jsx

```jsx
import { chakra, defineRecipe } from "@chakra-ui/react"

const noticeRecipe = defineRecipe({
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

const Notice = chakra("div", noticeRecipe)

export function Example() {
  return <Notice tone="success" size="sm">Profile saved</Notice>
}
```

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 028, inspect the result described below and interact with every trigger, field, or control.

The recipe centralizes reusable style variants and supplies predictable defaults for every notice instance.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Define a Notice recipe with tone and size variants, then use typegen and apply it to two instances.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Creating a new variant for every isolated page need. Too many variants make the component API hard to understand.
- Using a variant name that describes CSS mechanics instead of the design intent or semantic role.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="027-date-time-color-pickers-sliders-and-rating.md">027 - Date, time, color pickers, sliders, and rating</a></td>
      <td><a href="../lessons/028-recipes-and-reusable-component-variants.md">Chapter lesson</a></td>
      <td><a href="../qnas/028-recipes-and-reusable-component-variants.md">Chapter Q&amp;A</a></td>
      <td><a href="029-slot-recipes-and-multi-part-components.md">029 - Slot recipes and multi-part components</a></td>
    </tr>
  </tbody>
</table>
