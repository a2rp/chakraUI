# 008 - Custom system and theme configuration Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Move two repeated palette values and a global focus style into a theme file. Pass the resulting system to ChakraProvider.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    008-custom-system-and-theme-configuration.jsx
```

## 008-custom-system-and-theme-configuration.jsx

```jsx
import { ChakraProvider, createSystem, defaultConfig, defineConfig } from "@chakra-ui/react"

const config = defineConfig({
  theme: {
    tokens: {
      colors: {
        brand: {
          500: { value: "#176B87" },
        },
      },
    },
  },
})

const system = createSystem(defaultConfig, config)

export function AppProvider({ children }) {
  return <ChakraProvider value={system}>{children}</ChakraProvider>
}
```

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 008, inspect the result described below and interact with every trigger, field, or control.

Components inside AppProvider can use brand.500 and the shared default system tokens.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Move two repeated palette values and a global focus style into a theme file. Pass the resulting system to ChakraProvider.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Passing a v2 extendTheme object into the v3 provider. v3 uses createSystem and token leaves with value fields.
- Overriding defaults without documenting the decision. Keep config small, typed, and intentional; use defaults until a real product need justifies changing them.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="design-tokens-and-css-variables.md">007 - Design tokens and CSS variables</a></td>
      <td><a href="../lessons/008-custom-system-and-theme-configuration.md">Chapter lesson</a></td>
      <td><a href="../qnas/008-custom-system-and-theme-configuration.md">Chapter Q&amp;A</a></td>
      <td><a href="semantic-tokens-and-color-palettes.md">009 - Semantic tokens and color palettes</a></td>
    </tr>
  </tbody>
</table>
