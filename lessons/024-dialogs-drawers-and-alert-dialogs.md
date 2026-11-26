# 024 - Dialogs, drawers, and alert dialogs

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Dialogs, drawers, and alert dialogs.
- Identify the main API: `Dialog.Root, Trigger, Backdrop, Positioner, Content, CloseTrigger, Portal, Drawer`.
- Choose an appropriate use case: Use a dialog for a short focused task; use a drawer when the side panel preserves context; use an alert dialog for an important confirmation.
- Avoid the main implementation risks: Opening multiple dialogs for every row in a list. Prefer one dialog with data from the active trigger.

## Core idea

Dialog presents focused content in a modal or nonmodal layer. Drawer is a spatial presentation for a dialog-like interaction, and an alert dialog is reserved for consequential decisions that need an explicit response.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `Dialog.Root, Trigger, Backdrop, Positioner, Content, CloseTrigger, Portal, Drawer`.

A modal dialog should move focus inside, trap it while open, and return focus on close. Keep its accessible title and dismissal behavior intact.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

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

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Use a dialog for a short focused task; use a drawer when the side panel preserves context; use an alert dialog for an important confirmation.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Opening multiple dialogs for every row in a list. Prefer one dialog with data from the active trigger.
- Suppressing Escape, outside dismissal, focus return, or scroll handling without a clear usability reason.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Dialog presents focused content in a modal or nonmodal layer. Drawer is a spatial presentation for a dialog-like interaction, and an alert dialog is reserved for consequential decisions that need an explicit response. Remember the API boundary: Dialog.Root, Trigger, Backdrop, Positioner, Content, CloseTrigger, Portal, Drawer. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Build an edit-profile dialog with a title, labelled input, cancel action, save action, and controlled open state.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="023-menus-popovers-tooltips-and-hover-cards.md">023 - Menus, popovers, tooltips, and hover cards</a></td>
      <td><a href="../qnas/024-dialogs-drawers-and-alert-dialogs.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/024-dialogs-drawers-and-alert-dialogs.md">Chapter example</a></td>
      <td><a href="025-alerts-toasts-progress-and-loading-states.md">025 - Alerts, toasts, progress, and loading states</a></td>
    </tr>
  </tbody>
</table>
