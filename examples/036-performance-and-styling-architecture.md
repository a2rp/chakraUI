# 036 - Performance and styling architecture Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Measure an app route, identify one expensive render or imported package, make one evidence-based change, and record before/after results.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    036-performance-and-styling-architecture.jsx
```

## 036-performance-and-styling-architecture.jsx

```jsx
import { lazy, Suspense } from "react"
import { Button, Stack, Text } from "@chakra-ui/react"

const ReportsChart = lazy(() => import("./ReportsChart.jsx"))

export function ReportsPage() {
  return (
    <Stack gap="4">
      <Text>Reports</Text>
      <Button>Export CSV</Button>
      <Suspense fallback={<Text>Loading chart...</Text>}>
        <ReportsChart />
      </Suspense>
    </Stack>
  )
}
```

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 036, inspect the result described below and interact with every trigger, field, or control.

The chart code can be deferred by the application bundler while the core page remains available. Confirm the actual chunk split with a production build analyzer.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Measure an app route, identify one expensive render or imported package, make one evidence-based change, and record before/after results.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Memoizing every component before profiling. It adds complexity and can obscure state flow without a measurable gain.
- Treating a planned styling roadmap as already delivered behavior. Confirm the actual package and runtime architecture for the installed version.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="035-testing-chakra-ui-components.md">035 - Testing Chakra UI components</a></td>
      <td><a href="../lessons/036-performance-and-styling-architecture.md">Chapter lesson</a></td>
      <td><a href="../qnas/036-performance-and-styling-architecture.md">Chapter Q&amp;A</a></td>
      <td><a href="037-migration-from-chakra-ui-v2-to-v3.md">037 - Migration from Chakra UI v2 to v3</a></td>
    </tr>
  </tbody>
</table>
