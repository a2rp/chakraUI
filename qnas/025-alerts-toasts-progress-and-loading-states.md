# 025 - Alerts, toasts, progress, and loading states Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind alerts, toasts, progress, and loading states?

Feedback components communicate results and ongoing work. Alerts remain part of page content, toasts briefly announce a transient event, progress reports measurable completion, and skeletons preview a loading layout.

## 2. Which API should I learn first?

`Alert.Root, Progress.Root, Skeleton, toaster snippet, live region`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Choose persistent inline feedback for important errors and short transient feedback for success confirmations that do not require action.

## 4. What state and accessibility detail matters most?

Feedback must be perceivable visually and to assistive technology. Use progress semantics when determinate and a suitable status announcement for indeterminate work. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Communicating an important error only in a toast that disappears before it can be read.

## 6. How can I practice it?

Design an async save interaction with disabled/loading button state, a persistent inline error, and a success notification that is announced clearly. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. Toast or Alert for a failure?

Use a persistent inline Alert when the failure blocks a task or needs to remain available. Use a toast for a brief result that does not need an ongoing action.

## 8. When is progress determinate?

When the application can report a meaningful completed fraction. Otherwise expose an indeterminate loading state and a textual status.

## 9. What makes a skeleton useful?

It previews the shape of expected content while loading. It is not a progress indicator and must not be mistaken for real content.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="dialogs-drawers-and-alert-dialogs.md">024 - Dialogs, drawers, and alert dialogs</a></td>
      <td><a href="../lessons/025-alerts-toasts-progress-and-loading-states.md">Chapter lesson</a></td>
      <td><a href="../examples/025-alerts-toasts-progress-and-loading-states.md">Chapter example</a></td>
      <td><a href="tables-and-data-display.md">026 - Tables and data display</a></td>
    </tr>
  </tbody>
</table>
