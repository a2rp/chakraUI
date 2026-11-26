# 026 - Tables and data display

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Tables and data display.
- Identify the main API: `Table.Root, Table.Header, Table.Body, Table.Row, Table.ColumnHeader, DataList`.
- Choose an appropriate use case: Use a table when users compare values across rows and columns. Add sorting or pagination only when it solves a real task and preserve clear labels.
- Avoid the main implementation risks: Using a table for page layout or unrelated cards. CSS Grid is a better layout tool.

## Core idea

Data display components should preserve the meaning and relationships of the information. Use semantic HTML tables for tabular data; use DataList or definition lists for label-value pairs and a dedicated data grid only when interaction requirements justify it.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `Table.Root, Table.Header, Table.Body, Table.Row, Table.ColumnHeader, DataList`.

A semantic table communicates row and column relationships. Interactive sorting must expose state and usable controls, not just a visual arrow.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

```jsx
import { Table } from "@chakra-ui/react"

const projects = [
  { name: "Atlas", owner: "Mina", status: "Active" },
  { name: "Beacon", owner: "Ravi", status: "Paused" },
]

export function ProjectTable() {
  return (
    <Table.Root size="sm">
      <Table.Caption>Project status by owner</Table.Caption>
      <Table.Header>
        <Table.Row>
          <Table.ColumnHeader>Project</Table.ColumnHeader>
          <Table.ColumnHeader>Owner</Table.ColumnHeader>
          <Table.ColumnHeader>Status</Table.ColumnHeader>
        </Table.Row>
      </Table.Header>
      <Table.Body>
        {projects.map((project) => (
          <Table.Row key={project.name}>
            <Table.Cell>{project.name}</Table.Cell>
            <Table.Cell>{project.owner}</Table.Cell>
            <Table.Cell>{project.status}</Table.Cell>
          </Table.Row>
        ))}
      </Table.Body>
    </Table.Root>
  )
}
```

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Use a table when users compare values across rows and columns. Add sorting or pagination only when it solves a real task and preserve clear labels.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Using a table for page layout or unrelated cards. CSS Grid is a better layout tool.
- Adding sortable-looking headers without exposing sort state or keyboard-operable controls.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Data display components should preserve the meaning and relationships of the information. Use semantic HTML tables for tabular data; use DataList or definition lists for label-value pairs and a dedicated data grid only when interaction requirements justify it. Remember the API boundary: Table.Root, Table.Header, Table.Body, Table.Row, Table.ColumnHeader, DataList. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Build an accessible project table with caption, column headers, row action, empty state, and a responsive overflow strategy.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="025-alerts-toasts-progress-and-loading-states.md">025 - Alerts, toasts, progress, and loading states</a></td>
      <td><a href="../qnas/026-tables-and-data-display.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/026-tables-and-data-display.md">Chapter example</a></td>
      <td><a href="027-date-time-color-pickers-sliders-and-rating.md">027 - Date, time, color pickers, sliders, and rating</a></td>
    </tr>
  </tbody>
</table>
