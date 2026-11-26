# 023 - Menus, popovers, tooltips, and hover cards Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Build an actions menu with descriptive item labels and a separate help tooltip. Test opening, Escape dismissal, and keyboard traversal.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    023-menus-popovers-tooltips-and-hover-cards.jsx
```

## 023-menus-popovers-tooltips-and-hover-cards.jsx

```jsx
import { Menu } from "@chakra-ui/react"

export function ProjectActions() {
  return (
    <Menu.Root>
      <Menu.Trigger>Project actions</Menu.Trigger>
      <Menu.Positioner>
        <Menu.Content>
          <Menu.Item value="rename">Rename project</Menu.Item>
          <Menu.Item value="archive">Archive project</Menu.Item>
        </Menu.Content>
      </Menu.Positioner>
    </Menu.Root>
  )
}
```

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 023, inspect the result described below and interact with every trigger, field, or control.

The trigger opens a command menu with distinct actions. The component's keyboard and dismissal behavior should be verified in the actual application.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Build an actions menu with descriptive item labels and a separate help tooltip. Test opening, Escape dismissal, and keyboard traversal.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Putting buttons or form controls inside a tooltip. Use a popover or dialog for interactive content.
- Making a menu item navigate without link semantics, or failing to support keyboard navigation and dismissal.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="022-tabs-steps-and-navigation.md">022 - Tabs, steps, and navigation</a></td>
      <td><a href="../lessons/023-menus-popovers-tooltips-and-hover-cards.md">Chapter lesson</a></td>
      <td><a href="../qnas/023-menus-popovers-tooltips-and-hover-cards.md">Chapter Q&amp;A</a></td>
      <td><a href="024-dialogs-drawers-and-alert-dialogs.md">024 - Dialogs, drawers, and alert dialogs</a></td>
    </tr>
  </tbody>
</table>
