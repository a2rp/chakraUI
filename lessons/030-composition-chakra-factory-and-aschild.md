# 030 - Composition, Chakra factory, and asChild

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Composition, Chakra factory, and asChild.
- Identify the main API: `chakra factory, asChild, Link, polymorphism, component props`.
- Choose an appropriate use case: Use asChild to preserve the real element semantics of a router link or custom button. Use the chakra factory for a custom element that needs the system styling API.
- Avoid the main implementation risks: Wrapping an interactive element inside another interactive element. Preserve one focusable control and one coherent semantic role.

## Core idea

Chakra composition lets applications style custom elements and compose Chakra triggers with router links. The asChild pattern merges behavior and props with a child element when its semantics are appropriate.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `chakra factory, asChild, Link, polymorphism, component props`.

Composition merges props and event handlers. The underlying child still determines native semantics, focusability, and whether a ref can reach the DOM.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

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

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Use asChild to preserve the real element semantics of a router link or custom button. Use the chakra factory for a custom element that needs the system styling API.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Wrapping an interactive element inside another interactive element. Preserve one focusable control and one coherent semantic role.
- Using asChild with a child that cannot accept merged props or refs. Confirm the custom component forwards them correctly.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Chakra composition lets applications style custom elements and compose Chakra triggers with router links. The asChild pattern merges behavior and props with a child element when its semantics are appropriate. Remember the API boundary: chakra factory, asChild, Link, polymorphism, component props. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Compose a Chakra-styled router link and inspect its rendered HTML, accessible name, focus state, and navigation behavior.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="slot-recipes-and-multi-part-components.md">029 - Slot recipes and multi-part components</a></td>
      <td><a href="../qnas/030-composition-chakra-factory-and-aschild.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/030-composition-chakra-factory-and-aschild.md">Chapter example</a></td>
      <td><a href="presence-animation-and-transitions.md">031 - Presence, animation, and transitions</a></td>
    </tr>
  </tbody>
</table>
