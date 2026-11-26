# 007 - Design tokens and CSS variables Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind design tokens and css variables?

Design tokens give recurring values names, such as colors, spacing, typography, and radii. Chakra's system emits CSS variables for theme values, enabling consistent styling and runtime color-scheme adaptation.

## 2. Which API should I learn first?

`theme.tokens, system.token, system.token.var, CSS custom properties`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Use tokens for values that represent a reusable design decision. Keep raw CSS variables for integration boundaries or values that are intentionally outside the system.

## 4. What state and accessibility detail matters most?

Tokens are resolved by the styling system and can be referenced by Chakra styles. The system's token lookup helpers expose raw values or CSS variable references for integrations. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Forgetting the v3 token shape. Custom token leaves use objects with a value field, such as colors.brand.500.value.

## 6. How can I practice it?

Add brand colors and spacing tokens to the system. Use one token through a style prop and inspect its computed CSS variable in browser developer tools. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. Why use tokens instead of repeating CSS values?

A token gives a shared value a stable name. Changing that named decision can update all consumers and makes design intent easier to review.

## 8. What does a CSS variable add?

It lets the browser resolve a value at runtime and supports theme changes through selectors or cascade layers without recomputing every style in JavaScript.

## 9. How are token leaves shaped in v3?

Custom token values are wrapped in an object with a value property, for example colors.brand.500: { value: '#176B87' }.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="responsive-and-conditional-styles.md">006 - Responsive and conditional styles</a></td>
      <td><a href="../lessons/007-design-tokens-and-css-variables.md">Chapter lesson</a></td>
      <td><a href="../examples/007-design-tokens-and-css-variables.md">Chapter example</a></td>
      <td><a href="custom-system-and-theme-configuration.md">008 - Custom system and theme configuration</a></td>
    </tr>
  </tbody>
</table>
