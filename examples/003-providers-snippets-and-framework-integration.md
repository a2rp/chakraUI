# 003 - Providers, snippets, and framework integration Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Create a small src/components/ui/provider.jsx wrapper and use it once at the root. Add one CLI snippet, inspect the generated files, and explain each dependency.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    003-providers-snippets-and-framework-integration.jsx
```

## 003-providers-snippets-and-framework-integration.jsx

```jsx
import { ChakraProvider, defaultSystem } from "@chakra-ui/react"

export function Provider({ children }) {
  return (
    <ChakraProvider value={defaultSystem}>
      {children}
    </ChakraProvider>
  )
}

// Add optional source snippets with the project CLI:
// npx @chakra-ui/cli snippet add
```

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 003, inspect the result described below and interact with every trigger, field, or control.

Every descendant uses the same default token system. A project can wrap this Provider with additional app-wide context without placing providers inside individual pages.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Create a small src/components/ui/provider.jsx wrapper and use it once at the root. Add one CLI snippet, inspect the generated files, and explain each dependency.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Creating nested providers without an isolation need. Separate providers can create different theme contexts and make shared behavior harder to reason about.
- Assuming a generated snippet is a framework primitive. It is ordinary source code; review it, adapt imports, and keep it in sync with your app.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="installation-and-project-setup.md">002 - Installation and project setup</a></td>
      <td><a href="../lessons/003-providers-snippets-and-framework-integration.md">Chapter lesson</a></td>
      <td><a href="../qnas/003-providers-snippets-and-framework-integration.md">Chapter Q&amp;A</a></td>
      <td><a href="component-anatomy-compound-apis-and-state.md">004 - Component anatomy, compound APIs, and state</a></td>
    </tr>
  </tbody>
</table>
