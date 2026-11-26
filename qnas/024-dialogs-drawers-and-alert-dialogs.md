# 024 - Dialogs, drawers, and alert dialogs Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind dialogs, drawers, and alert dialogs?

Dialog presents focused content in a modal or nonmodal layer. Drawer is a spatial presentation for a dialog-like interaction, and an alert dialog is reserved for consequential decisions that need an explicit response.

## 2. Which API should I learn first?

`Dialog.Root, Trigger, Backdrop, Positioner, Content, CloseTrigger, Portal, Drawer`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Use a dialog for a short focused task; use a drawer when the side panel preserves context; use an alert dialog for an important confirmation.

## 4. What state and accessibility detail matters most?

A modal dialog should move focus inside, trap it while open, and return focus on close. Keep its accessible title and dismissal behavior intact. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Opening multiple dialogs for every row in a list. Prefer one dialog with data from the active trigger.

## 6. How can I practice it?

Build an edit-profile dialog with a title, labelled input, cancel action, save action, and controlled open state. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. Dialog or Drawer?

Use Dialog for a focused prompt. A Drawer is useful when a side panel can preserve visual context, such as filters or a detail view.

## 8. Why use Portal?

Portal places the floating layer outside clipping ancestors and supports a consistent overlay stack. Preserve theme and focus behavior.

## 9. When should a dialog be an alertdialog?

Use alertdialog semantics for a consequential message that requires a response, such as confirming an irreversible action.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="menus-popovers-tooltips-and-hover-cards.md">023 - Menus, popovers, tooltips, and hover cards</a></td>
      <td><a href="../lessons/024-dialogs-drawers-and-alert-dialogs.md">Chapter lesson</a></td>
      <td><a href="../examples/024-dialogs-drawers-and-alert-dialogs.md">Chapter example</a></td>
      <td><a href="alerts-toasts-progress-and-loading-states.md">025 - Alerts, toasts, progress, and loading states</a></td>
    </tr>
  </tbody>
</table>
