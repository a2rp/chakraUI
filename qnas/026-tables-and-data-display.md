# 026 - Tables and data display Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind tables and data display?

Data display components should preserve the meaning and relationships of the information. Use semantic HTML tables for tabular data; use DataList or definition lists for label-value pairs and a dedicated data grid only when interaction requirements justify it.

## 2. Which API should I learn first?

`Table.Root, Table.Header, Table.Body, Table.Row, Table.ColumnHeader, DataList`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Use a table when users compare values across rows and columns. Add sorting or pagination only when it solves a real task and preserve clear labels.

## 4. What state and accessibility detail matters most?

A semantic table communicates row and column relationships. Interactive sorting must expose state and usable controls, not just a visual arrow. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Using a table for page layout or unrelated cards. CSS Grid is a better layout tool.

## 6. How can I practice it?

Build an accessible project table with caption, column headers, row action, empty state, and a responsive overflow strategy. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. When should I use a table?

Use it for genuinely tabular data where users compare values across shared columns. Use lists or cards for independent content items.

## 8. Does Chakra sort a Table automatically?

No. Table provides structure and styling. Sorting, filtering, pagination, and data state belong to your application or a dedicated grid library.

## 9. Why include a caption?

A caption gives users context about what the table contains, including those navigating it outside its visual surroundings.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="alerts-toasts-progress-and-loading-states.md">025 - Alerts, toasts, progress, and loading states</a></td>
      <td><a href="../lessons/026-tables-and-data-display.md">Chapter lesson</a></td>
      <td><a href="../examples/026-tables-and-data-display.md">Chapter example</a></td>
      <td><a href="date-time-color-pickers-sliders-and-rating.md">027 - Date, time, color pickers, sliders, and rating</a></td>
    </tr>
  </tbody>
</table>
