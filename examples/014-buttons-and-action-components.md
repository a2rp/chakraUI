# 014 - Buttons and action components Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Make a page header with one primary action, one secondary action, and an icon-only refresh action with a useful accessible name.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    014-buttons-and-action-components.jsx
```

## 014-buttons-and-action-components.jsx

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

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 014, inspect the result described below and interact with every trigger, field, or control.

The action hierarchy is clear, the icon-only control has an accessible name, and the actions remain keyboard-operable.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Make a page header with one primary action, one secondary action, and an icon-only refresh action with a useful accessible name.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Using a Button for navigation without link semantics, or a link when the action changes state.
- Showing only an icon without an accessible label, or removing focus styling without an equivalent.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="grid-containers-and-positioning.md">013 - Grid, containers, and positioning</a></td>
      <td><a href="../lessons/014-buttons-and-action-components.md">Chapter lesson</a></td>
      <td><a href="../qnas/014-buttons-and-action-components.md">Chapter Q&amp;A</a></td>
      <td><a href="fields-inputs-and-textareas.md">015 - Fields, inputs, and textareas</a></td>
    </tr>
  </tbody>
</table>
