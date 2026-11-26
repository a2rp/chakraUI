# 030 - Composition, Chakra factory, and asChild Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Compose a Chakra-styled router link and inspect its rendered HTML, accessible name, focus state, and navigation behavior.

## Assumptions and prerequisites

- `@chakra-ui/react` and the project router package shown in the import.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    030-composition-chakra-factory-and-aschild.jsx
```

## 030-composition-chakra-factory-and-aschild.jsx

```jsx
import { Link } from "@chakra-ui/react"
import { Link as RouterLink } from "react-router-dom"

export function DocumentationLink() {
  return (
    <Link asChild color="blue.600" fontWeight="semibold">
      <RouterLink to="/docs">Open documentation</RouterLink>
    </Link>
  )
}
```

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 030, inspect the result described below and interact with every trigger, field, or control.

The rendered element remains a router link and receives Chakra styles without nesting an anchor inside another interactive control.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Compose a Chakra-styled router link and inspect its rendered HTML, accessible name, focus state, and navigation behavior.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Wrapping an interactive element inside another interactive element. Preserve one focusable control and one coherent semantic role.
- Using asChild with a child that cannot accept merged props or refs. Confirm the custom component forwards them correctly.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="slot-recipes-and-multi-part-components.md">029 - Slot recipes and multi-part components</a></td>
      <td><a href="../lessons/030-composition-chakra-factory-and-aschild.md">Chapter lesson</a></td>
      <td><a href="../qnas/030-composition-chakra-factory-and-aschild.md">Chapter Q&amp;A</a></td>
      <td><a href="presence-animation-and-transitions.md">031 - Presence, animation, and transitions</a></td>
    </tr>
  </tbody>
</table>
