# 038 - Production design system and maintenance Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Design a small product system with semantic surface tokens, one Button recipe, one Field slot recipe, and a review checklist for changes.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    038-production-design-system-and-maintenance.jsx
```

## 038-production-design-system-and-maintenance.jsx

```jsx
import { ChakraProvider, createSystem, defaultConfig, defineConfig } from "@chakra-ui/react"

const config = defineConfig({
  theme: {
    semanticTokens: {
      colors: {
        surface: {
          panel: { value: { _light: "{colors.white}", _dark: "{colors.gray.900}" } },
        },
      },
    },
  },
})

const system = createSystem(defaultConfig, config)

export function DesignSystemProvider({ children }) {
  return <ChakraProvider value={system}>{children}</ChakraProvider>
}
```

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 038, inspect the result described below and interact with every trigger, field, or control.

The provider exposes a shared system, and components can use the semantic surface token rather than hardcoding separate mode-specific values.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Design a small product system with semantic surface tokens, one Button recipe, one Field slot recipe, and a review checklist for changes.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Turning every component into a design-system primitive. Excess abstractions make the system harder to change and can hide native semantics.
- Changing shared tokens without regression checks or migration notes. Token changes can affect many routes at once.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="037-migration-from-chakra-ui-v2-to-v3.md">037 - Migration from Chakra UI v2 to v3</a></td>
      <td><a href="../lessons/038-production-design-system-and-maintenance.md">Chapter lesson</a></td>
      <td><a href="../qnas/038-production-design-system-and-maintenance.md">Chapter Q&amp;A</a></td>
      <td>End of course</td>
    </tr>
  </tbody>
</table>
