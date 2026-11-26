# 008 - Custom system and theme configuration Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind custom system and theme configuration?

Chakra v3 builds a styling system by combining configuration with a base config through createSystem. The config can define tokens, breakpoints, global CSS, preflight behavior, recipes, and shared style collections.

## 2. Which API should I learn first?

`defineConfig, createSystem, defaultConfig, ChakraProvider value`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Create a custom system when a product needs a coherent theme shared across pages or a reusable design system. Keep application-specific values out of a generic theme unless they are stable shared decisions.

## 4. What state and accessibility detail matters most?

createSystem returns the styling engine configuration. ChakraProvider's value prop provides it to descendants; the system does not replace React context for application data. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Passing a v2 extendTheme object into the v3 provider. v3 uses createSystem and token leaves with value fields.

## 6. How can I practice it?

Move two repeated palette values and a global focus style into a theme file. Pass the resulting system to ChakraProvider. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. What is the role of defineConfig?

It marks and types the configuration object that describes theme and system customizations.

## 8. What does createSystem return?

It combines the base config and custom config into the system consumed by ChakraProvider and available through system helpers.

## 9. Can I disable preflight?

Yes. Configure preflight in the system, for example preflight: false. Consider the impact on native element defaults and document that choice.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="design-tokens-and-css-variables.md">007 - Design tokens and CSS variables</a></td>
      <td><a href="../lessons/008-custom-system-and-theme-configuration.md">Chapter lesson</a></td>
      <td><a href="../examples/008-custom-system-and-theme-configuration.md">Chapter example</a></td>
      <td><a href="semantic-tokens-and-color-palettes.md">009 - Semantic tokens and color palettes</a></td>
    </tr>
  </tbody>
</table>
