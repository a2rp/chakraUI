# 025 - Alerts, toasts, progress, and loading states Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Design an async save interaction with disabled/loading button state, a persistent inline error, and a success notification that is announced clearly.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    025-alerts-toasts-progress-and-loading-states.jsx
```

## 025-alerts-toasts-progress-and-loading-states.jsx

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

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 025, inspect the result described below and interact with every trigger, field, or control.

The numeric value and progress bar communicate determinate progress, while the alert supplies context about the ongoing task.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Design an async save interaction with disabled/loading button state, a persistent inline error, and a success notification that is announced clearly.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Communicating an important error only in a toast that disappears before it can be read.
- Using a progress indicator without a meaningful estimate or loading state that leaves assistive technology unaware.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="024-dialogs-drawers-and-alert-dialogs.md">024 - Dialogs, drawers, and alert dialogs</a></td>
      <td><a href="../lessons/025-alerts-toasts-progress-and-loading-states.md">Chapter lesson</a></td>
      <td><a href="../qnas/025-alerts-toasts-progress-and-loading-states.md">Chapter Q&amp;A</a></td>
      <td><a href="026-tables-and-data-display.md">026 - Tables and data display</a></td>
    </tr>
  </tbody>
</table>
