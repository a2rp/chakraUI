# 006 - Responsive and conditional styles Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind responsive and conditional styles?

Chakra supports responsive style values and conditional style props. Responsive objects map values to named breakpoints, while conditions such as _hover and _focusVisible express interaction states.

## 2. Which API should I learn first?

`Responsive values, breakpoints, _hover, _focusVisible, hideFrom, hideBelow`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Use responsive values for presentation that changes with viewport size. Prefer CSS-first responsiveness for layout; use JavaScript media queries only when behavior truly changes.

## 4. What state and accessibility detail matters most?

Responsive style changes are CSS-driven; they do not require React state or a resize listener. Conditional style props map to CSS selectors or media conditions. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Using array values without documenting which configured breakpoint each position represents. Named objects are often easier to audit.

## 6. How can I practice it?

Make a two-column card layout that becomes one column on small screens. Add distinct hover and keyboard focus-visible feedback to the action. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. Do responsive styles require a JavaScript resize hook?

No. Chakra resolves responsive values into CSS media conditions, so the browser applies them without a React resize listener.

## 8. Should I use arrays or objects for responsive values?

Both are supported patterns. Named breakpoint objects communicate intent better when there are several breakpoints or the system is customized.

## 9. What is the difference between _hover and _focusVisible?

_hover styles pointer hover. _focusVisible styles the keyboard-visible focus state, which should remain visually distinct for keyboard users.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="style-props-and-token-aware-styling.md">005 - Style props and token-aware styling</a></td>
      <td><a href="../lessons/006-responsive-and-conditional-styles.md">Chapter lesson</a></td>
      <td><a href="../examples/006-responsive-and-conditional-styles.md">Chapter example</a></td>
      <td><a href="design-tokens-and-css-variables.md">007 - Design tokens and CSS variables</a></td>
    </tr>
  </tbody>
</table>
