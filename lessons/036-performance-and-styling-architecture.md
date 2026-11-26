# 036 - Performance and styling architecture

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Performance and styling architecture.
- Identify the main API: `Emotion runtime, bundle analyzer, direct imports, CSS variables, memoization`.
- Choose an appropriate use case: Profile before optimizing. Use CSS for responsive presentation and reserve React state for behavior; split heavy features when measurements show meaningful bundle cost.
- Avoid the main implementation risks: Memoizing every component before profiling. It adds complexity and can obscure state flow without a measurable gain.

## Core idea

Chakra v3 currently uses Emotion at runtime while its long-term styling direction evolves toward a zero-runtime model in phases. Optimize based on measurements, keep component trees focused, and avoid work that duplicates what CSS can do.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `Emotion runtime, bundle analyzer, direct imports, CSS variables, memoization`.

Styling runtime and bundle trade-offs depend on the installed Chakra version and build. The official docs describe the current direction; do not assume future architecture has shipped.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

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

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Profile before optimizing. Use CSS for responsive presentation and reserve React state for behavior; split heavy features when measurements show meaningful bundle cost.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Memoizing every component before profiling. It adds complexity and can obscure state flow without a measurable gain.
- Treating a planned styling roadmap as already delivered behavior. Confirm the actual package and runtime architecture for the installed version.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Chakra v3 currently uses Emotion at runtime while its long-term styling direction evolves toward a zero-runtime model in phases. Optimize based on measurements, keep component trees focused, and avoid work that duplicates what CSS can do. Remember the API boundary: Emotion runtime, bundle analyzer, direct imports, CSS variables, memoization. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Measure an app route, identify one expensive render or imported package, make one evidence-based change, and record before/after results.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="035-testing-chakra-ui-components.md">035 - Testing Chakra UI components</a></td>
      <td><a href="../qnas/036-performance-and-styling-architecture.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/036-performance-and-styling-architecture.md">Chapter example</a></td>
      <td><a href="037-migration-from-chakra-ui-v2-to-v3.md">037 - Migration from Chakra UI v2 to v3</a></td>
    </tr>
  </tbody>
</table>
