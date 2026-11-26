# 010 - Color modes and dark mode Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind color modes and dark mode?

Current Chakra color-mode support uses next-themes, commonly wrapped in a project-owned provider snippet. Components should favor semantic tokens for automatic adaptation and use _dark only for deliberate exceptions.

## 2. Which API should I learn first?

`next-themes, ThemeProvider, ColorModeProvider snippet, semantic tokens, _dark`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Use semantic tokens for most mode-aware colors. Add a toggle only when the product lets users choose a mode, and respect system preference where appropriate.

## 4. What state and accessibility detail matters most?

Color mode is managed by next-themes in the current setup. CSS selectors and variables adapt styles; application hooks can still cause server/client timing differences. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Following v2 instructions for ColorModeScript or removed Chakra color-mode hooks. v3 delegates the mode provider to next-themes and the current CLI snippet.

## 6. How can I practice it?

Add a color-mode provider snippet, use semantic tokens in a card, and compare initial rendering under light and dark system preferences. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. Does v3 still use ColorModeScript?

No. The v2 color-mode API changed. Current v3 setup uses next-themes, with a project-local provider or CLI-generated color-mode snippet.

## 8. Why prefer semantic tokens over _dark on every component?

Semantic tokens centralize mode differences and make styles consistent. Use _dark for a local exception that is clearer than adding a new semantic role.

## 9. How can I avoid hydration mismatches?

Avoid rendering different server and client markup from an unknown stored mode. Use CSS semantic tokens for visual changes and client-only boundaries for mode-dependent content when necessary.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="009-semantic-tokens-and-color-palettes.md">009 - Semantic tokens and color palettes</a></td>
      <td><a href="../lessons/010-color-modes-and-dark-mode.md">Chapter lesson</a></td>
      <td><a href="../examples/010-color-modes-and-dark-mode.md">Chapter example</a></td>
      <td><a href="011-typography-and-text-styles.md">011 - Typography and text styles</a></td>
    </tr>
  </tbody>
</table>
