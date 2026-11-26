# 005 - Style props and token-aware styling Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind style props and token-aware styling?

Style props let Chakra components express common CSS properties directly in JSX. The styling system resolves token references, responsive values, pseudo selectors, and component-specific props into CSS.

## 2. Which API should I learn first?

`Box, p, px, bg, color, borderRadius, _hover, css`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Use style props for local component styles and small compositions. Move repeated patterns into a recipe, semantic token, or stylesheet when the same decision appears across many components.

## 4. What state and accessibility detail matters most?

Style props describe presentation. Keep interactive state in React or Chakra's component state machine rather than inferring it from styling props. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Treating every style value as a design token. Arbitrary CSS values are sometimes useful, but shared design decisions should use named tokens.

## 6. How can I practice it?

Create two Card-like Boxes that share a token-based border and spacing style. Extract a shared object or component once the values repeat. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. Are Chakra style props just inline styles?

They are JSX props resolved by Chakra's styling system. They support theme tokens, responsive conditions, pseudo selectors, and system configuration beyond the browser's basic style attribute.

## 8. Should every value be a token?

No. Use tokens for shared design decisions such as spacing, colors, and radii. One-off layout or measured values can remain explicit when they improve clarity.

## 9. When should styles leave the JSX?

Extract a recipe, style object, component, or stylesheet when style logic repeats, becomes hard to scan, or needs a clear reusable boundary.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="004-component-anatomy-compound-apis-and-state.md">004 - Component anatomy, compound APIs, and state</a></td>
      <td><a href="../lessons/005-style-props-and-token-aware-styling.md">Chapter lesson</a></td>
      <td><a href="../examples/005-style-props-and-token-aware-styling.md">Chapter example</a></td>
      <td><a href="006-responsive-and-conditional-styles.md">006 - Responsive and conditional styles</a></td>
    </tr>
  </tbody>
</table>
