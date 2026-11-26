# 011 - Typography and text styles Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind typography and text styles?

Typography is a system of readable hierarchy, not just font-size props. Chakra provides semantic text components and theme-defined text styles that can coordinate size, weight, line height, and letter spacing.

## 2. Which API should I learn first?

`Heading, Text, textStyle, fontFamily, lineHeight, truncate`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Use headings for document structure and text styles for recurring visual roles. Choose an HTML heading level from the page outline rather than from its appearance alone.

## 4. What state and accessibility detail matters most?

Typography components render semantic HTML defaults and style props. Preserve logical headings and sufficient contrast regardless of visual tokens. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Selecting Heading size without considering its semantic level. Visual size and heading hierarchy are separate decisions.

## 6. How can I practice it?

Create a settings panel with a semantic h2 heading, supporting description, and compact metadata text using a consistent text scale. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. Should I choose Heading size based on hierarchy?

Choose the heading element level based on the document outline, then choose a size that fits the visual design.

## 8. What belongs in a textStyle token?

A repeated typographic combination such as font size, weight, line height, and letter spacing that represents a named role.

## 9. When is truncation appropriate?

Use it for secondary labels in constrained layouts when the full value remains available through another accessible path or on a detail view.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="010-color-modes-and-dark-mode.md">010 - Color modes and dark mode</a></td>
      <td><a href="../lessons/011-typography-and-text-styles.md">Chapter lesson</a></td>
      <td><a href="../examples/011-typography-and-text-styles.md">Chapter example</a></td>
      <td><a href="012-layout-primitives-box-flex-and-stack.md">012 - Layout primitives: Box, Flex, and Stack</a></td>
    </tr>
  </tbody>
</table>
