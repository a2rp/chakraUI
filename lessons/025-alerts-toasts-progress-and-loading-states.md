# 025 - Alerts, toasts, progress, and loading states

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Alerts, toasts, progress, and loading states.
- Identify the main API: `Alert.Root, Progress.Root, Skeleton, toaster snippet, live region`.
- Choose an appropriate use case: Choose persistent inline feedback for important errors and short transient feedback for success confirmations that do not require action.
- Avoid the main implementation risks: Communicating an important error only in a toast that disappears before it can be read.

## Core idea

Feedback components communicate results and ongoing work. Alerts remain part of page content, toasts briefly announce a transient event, progress reports measurable completion, and skeletons preview a loading layout.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `Alert.Root, Progress.Root, Skeleton, toaster snippet, live region`.

Feedback must be perceivable visually and to assistive technology. Use progress semantics when determinate and a suitable status announcement for indeterminate work.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

```jsx
import { Alert, Progress, Stack, Text } from "@chakra-ui/react"

export function UploadStatus() {
  const progress = 62
  return (
    <Stack gap="3">
      <Text>Uploading report: {progress}%</Text>
      <Progress.Root value={progress} max={100}>
        <Progress.Track><Progress.Range /></Progress.Track>
      </Progress.Root>
      <Alert.Root status="info">
        <Alert.Indicator />
        <Alert.Content>
          <Alert.Title>Upload in progress</Alert.Title>
          <Alert.Description>You can continue working while this completes.</Alert.Description>
        </Alert.Content>
      </Alert.Root>
    </Stack>
  )
}
```

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Choose persistent inline feedback for important errors and short transient feedback for success confirmations that do not require action.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Communicating an important error only in a toast that disappears before it can be read.
- Using a progress indicator without a meaningful estimate or loading state that leaves assistive technology unaware.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Feedback components communicate results and ongoing work. Alerts remain part of page content, toasts briefly announce a transient event, progress reports measurable completion, and skeletons preview a loading layout. Remember the API boundary: Alert.Root, Progress.Root, Skeleton, toaster snippet, live region. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Design an async save interaction with disabled/loading button state, a persistent inline error, and a success notification that is announced clearly.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="dialogs-drawers-and-alert-dialogs.md">024 - Dialogs, drawers, and alert dialogs</a></td>
      <td><a href="../qnas/025-alerts-toasts-progress-and-loading-states.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/025-alerts-toasts-progress-and-loading-states.md">Chapter example</a></td>
      <td><a href="tables-and-data-display.md">026 - Tables and data display</a></td>
    </tr>
  </tbody>
</table>
