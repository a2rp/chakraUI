# 014 - Buttons and action components

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Buttons and action components.
- Identify the main API: `Button, IconButton, colorPalette, variant, loading, disabled, asChild`.
- Choose an appropriate use case: Use a button for an action and a link for navigation. Choose visual variants by priority and keep destructive actions distinct.
- Avoid the main implementation risks: Using a Button for navigation without link semantics, or a link when the action changes state.

## Core idea

Buttons communicate and trigger actions. Chakra Button provides palette, size, loading, disabled, and composition options; IconButton needs an accessible name when its icon is the only visible label.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `Button, IconButton, colorPalette, variant, loading, disabled, asChild`.

Native buttons support keyboard activation and disabled state. Loading state should prevent duplicate submissions and explain progress where the wait is meaningful.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

```jsx
import { Button, HStack, IconButton } from "@chakra-ui/react"

export function ActionBar() {
  return (
    <HStack gap="3">
      <Button colorPalette="blue">Save changes</Button>
      <Button variant="outline">Cancel</Button>
      <IconButton aria-label="Refresh results" variant="ghost">
        <span aria-hidden="true">↻</span>
      </IconButton>
    </HStack>
  )
}
```

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Use a button for an action and a link for navigation. Choose visual variants by priority and keep destructive actions distinct.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Using a Button for navigation without link semantics, or a link when the action changes state.
- Showing only an icon without an accessible label, or removing focus styling without an equivalent.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Buttons communicate and trigger actions. Chakra Button provides palette, size, loading, disabled, and composition options; IconButton needs an accessible name when its icon is the only visible label. Remember the API boundary: Button, IconButton, colorPalette, variant, loading, disabled, asChild. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Make a page header with one primary action, one secondary action, and an icon-only refresh action with a useful accessible name.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="013-grid-containers-and-positioning.md">013 - Grid, containers, and positioning</a></td>
      <td><a href="../qnas/014-buttons-and-action-components.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/014-buttons-and-action-components.md">Chapter example</a></td>
      <td><a href="015-fields-inputs-and-textareas.md">015 - Fields, inputs, and textareas</a></td>
    </tr>
  </tbody>
</table>
