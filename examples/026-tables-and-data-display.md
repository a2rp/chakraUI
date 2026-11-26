# 026 - Tables and data display Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Build an accessible project table with caption, column headers, row action, empty state, and a responsive overflow strategy.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    026-tables-and-data-display.jsx
```

## 026-tables-and-data-display.jsx

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

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 026, inspect the result described below and interact with every trigger, field, or control.

The table preserves header-to-cell relationships and has a caption describing the data. A production version should define empty and loading states.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Build an accessible project table with caption, column headers, row action, empty state, and a responsive overflow strategy.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Using a table for page layout or unrelated cards. CSS Grid is a better layout tool.
- Adding sortable-looking headers without exposing sort state or keyboard-operable controls.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="025-alerts-toasts-progress-and-loading-states.md">025 - Alerts, toasts, progress, and loading states</a></td>
      <td><a href="../lessons/026-tables-and-data-display.md">Chapter lesson</a></td>
      <td><a href="../qnas/026-tables-and-data-display.md">Chapter Q&amp;A</a></td>
      <td><a href="027-date-time-color-pickers-sliders-and-rating.md">027 - Date, time, color pickers, sliders, and rating</a></td>
    </tr>
  </tbody>
</table>
