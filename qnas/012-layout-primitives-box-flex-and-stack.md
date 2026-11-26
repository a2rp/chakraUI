# 012 - Layout primitives: Box, Flex, and Stack Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind layout primitives: box, flex, and stack?

Box is the generic styleable container, Flex provides one-dimensional flexbox layout, and Stack arranges children with a consistent gap and direction. Their roles help keep structure readable.

## 2. Which API should I learn first?

`Box, Flex, Stack, HStack, VStack, gap, align, justify`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Use Stack for simple repeated spacing, Flex for alignment and distribution along one axis, and Box for a semantic or styled wrapper.

## 4. What state and accessibility detail matters most?

Layout primitives render ordinary layout elements. Choose suitable HTML semantics with as or native elements when the wrapper has a meaningful role. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Using margins on every child when Stack gap expresses the relationship more clearly.

## 6. How can I practice it?

Build a toolbar that keeps actions aligned at wide widths and wraps or stacks at narrow widths without hardcoded child margins. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. When should I use Stack instead of Box with margins?

Use Stack when siblings share a consistent gap and direction. It communicates their relationship and avoids assigning spacing to every child.

## 8. What distinguishes Flex from Stack?

Flex exposes the general one-dimensional flex layout. Stack is a simpler composition focused on arranging children with a shared gap.

## 9. Does Box add semantic meaning?

No. Box is primarily a layout and styling primitive. Use as or a semantic HTML element when the content needs a landmark or document role.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="011-typography-and-text-styles.md">011 - Typography and text styles</a></td>
      <td><a href="../lessons/012-layout-primitives-box-flex-and-stack.md">Chapter lesson</a></td>
      <td><a href="../examples/012-layout-primitives-box-flex-and-stack.md">Chapter example</a></td>
      <td><a href="013-grid-containers-and-positioning.md">013 - Grid, containers, and positioning</a></td>
    </tr>
  </tbody>
</table>
