# 013 - Grid, containers, and positioning Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind grid, containers, and positioning?

CSS Grid is useful for two-dimensional page and card layouts. Chakra's Grid and SimpleGrid expose grid behavior through props, while Container, Center, and Positioner help manage width and placement.

## 2. Which API should I learn first?

`Grid, GridItem, SimpleGrid, Container, Center, position, templateColumns`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Use grid for row-and-column relationships, flex for a one-dimensional sequence, and Container for readable content width.

## 4. What state and accessibility detail matters most?

Grid remains CSS layout and adapts without React state. Keep DOM order meaningful so the visual placement does not confuse keyboard or reading order. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Hardcoding a fixed number of columns on every viewport. Use responsive columns or minmax-based CSS so content can reflow.

## 6. How can I practice it?

Create a responsive dashboard with a main panel and a side summary. At narrow widths, make the summary flow below the main panel. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. When is Grid a better fit than Flex?

Use Grid when rows and columns form a two-dimensional structure. Use Flex for one-dimensional alignment or distribution.

## 8. Why use minmax(0, 1fr)?

The zero minimum lets a grid track shrink below a child's intrinsic min-content width, preventing long content from forcing horizontal overflow.

## 9. Should visual order differ from DOM order?

Avoid unnecessary differences. Keyboard and screen-reader order follow the DOM, so preserve a logical source order.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="012-layout-primitives-box-flex-and-stack.md">012 - Layout primitives: Box, Flex, and Stack</a></td>
      <td><a href="../lessons/013-grid-containers-and-positioning.md">Chapter lesson</a></td>
      <td><a href="../examples/013-grid-containers-and-positioning.md">Chapter example</a></td>
      <td><a href="014-buttons-and-action-components.md">014 - Buttons and action components</a></td>
    </tr>
  </tbody>
</table>
