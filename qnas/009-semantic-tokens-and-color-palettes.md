# 009 - Semantic tokens and color palettes Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind semantic tokens and color palettes?

Primitive tokens identify raw values, while semantic tokens describe how a value is used, such as surface, text, border, or focus ring. Chakra also exposes component colorPalette values that map a component's palette-aware styles to a chosen color family.

## 2. Which API should I learn first?

`theme.semanticTokens, bg.subtle, fg.muted, colorPalette, virtual color`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Prefer semantic names for component surfaces and text because they express intent and can change with color mode. Use primitive palette values for deliberate one-off emphasis.

## 4. What state and accessibility detail matters most?

Semantic tokens resolve to mode-aware values. Component colorPalette selects coordinated recipe values rather than setting arbitrary CSS on every descendant. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Using a primitive color for a semantic role everywhere. A literal gray value does not tell future maintainers whether it is a surface, muted text, or border.

## 6. How can I practice it?

Build a success callout with semantic foreground and background tokens, then change the active color palette and compare component states. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. When should I choose semantic tokens?

Choose them for roles such as page background, subtle surface, muted text, border, or focus ring, especially when the role must adapt to a color mode.

## 8. What does colorPalette do?

It selects the color family used by a palette-aware component recipe. It is not a global override for every explicit color style inside the component.

## 9. Can a semantic token map differently in light and dark mode?

Yes. Configure mode-specific values for the semantic token or use built-in semantic tokens that already adapt to color mode.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="custom-system-and-theme-configuration.md">008 - Custom system and theme configuration</a></td>
      <td><a href="../lessons/009-semantic-tokens-and-color-palettes.md">Chapter lesson</a></td>
      <td><a href="../examples/009-semantic-tokens-and-color-palettes.md">Chapter example</a></td>
      <td><a href="color-modes-and-dark-mode.md">010 - Color modes and dark mode</a></td>
    </tr>
  </tbody>
</table>
