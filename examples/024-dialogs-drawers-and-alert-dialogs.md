# 024 - Dialogs, drawers, and alert dialogs Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Build an edit-profile dialog with a title, labelled input, cancel action, save action, and controlled open state.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    024-dialogs-drawers-and-alert-dialogs.jsx
```

## 024-dialogs-drawers-and-alert-dialogs.jsx

```jsx
import { Button, Dialog, Portal } from "@chakra-ui/react"

export function EditDialog() {
  return (
    <Dialog.Root>
      <Dialog.Trigger asChild>
        <Button variant="outline">Edit profile</Button>
      </Dialog.Trigger>
      <Portal>
        <Dialog.Backdrop />
        <Dialog.Positioner>
          <Dialog.Content>
            <Dialog.Header>
              <Dialog.Title>Edit profile</Dialog.Title>
            </Dialog.Header>
            <Dialog.Body>Update your profile details, then save.</Dialog.Body>
            <Dialog.Footer>
              <Dialog.CloseTrigger asChild><Button variant="outline">Cancel</Button></Dialog.CloseTrigger>
              <Button colorPalette="blue">Save</Button>
            </Dialog.Footer>
          </Dialog.Content>
        </Dialog.Positioner>
      </Portal>
    </Dialog.Root>
  )
}
```

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 024, inspect the result described below and interact with every trigger, field, or control.

The dialog is labelled and modal, and the portal allows it to render above page layout without clipping.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Build an edit-profile dialog with a title, labelled input, cancel action, save action, and controlled open state.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Opening multiple dialogs for every row in a list. Prefer one dialog with data from the active trigger.
- Suppressing Escape, outside dismissal, focus return, or scroll handling without a clear usability reason.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="menus-popovers-tooltips-and-hover-cards.md">023 - Menus, popovers, tooltips, and hover cards</a></td>
      <td><a href="../lessons/024-dialogs-drawers-and-alert-dialogs.md">Chapter lesson</a></td>
      <td><a href="../qnas/024-dialogs-drawers-and-alert-dialogs.md">Chapter Q&amp;A</a></td>
      <td><a href="alerts-toasts-progress-and-loading-states.md">025 - Alerts, toasts, progress, and loading states</a></td>
    </tr>
  </tbody>
</table>
