# 002 - Installation and project setup Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Add Chakra UI to a fresh Vite React app, record the Node and React versions, and render one Button inside ChakraProvider.

## Assumptions and prerequisites

- `@chakra-ui/react` and `@emotion/react`; use the package manager and compatible React version already configured in the host app.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    002-installation-and-project-setup.jsx
```

## 002-installation-and-project-setup.jsx

```jsx
# Use one package manager in the project
npm install @chakra-ui/react @emotion/react

# In a Vite React entry file
# src/main.jsx
# import React from "react"
# import { createRoot } from "react-dom/client"
# import { ChakraProvider, defaultSystem } from "@chakra-ui/react"
# import App from "./App.jsx"
#
# createRoot(document.getElementById("root")).render(
#   <ChakraProvider value={defaultSystem}>
#     <App />
#   </ChakraProvider>,
# )
```

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 002, inspect the result described below and interact with every trigger, field, or control.

The app starts through its normal development command, and Chakra components receive the configured styling system from the provider.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Add Chakra UI to a fresh Vite React app, record the Node and React versions, and render one Button inside ChakraProvider.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Installing the obsolete v2 package set or relying on an old tutorial. v3 uses @chakra-ui/react and @emotion/react; older examples may include packages no longer required.
- Skipping the existing React peer-dependency check. A successful install is not proof that the app's framework versions are compatible.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="introduction-to-chakra-ui-v3.md">001 - Introduction to Chakra UI v3</a></td>
      <td><a href="../lessons/002-installation-and-project-setup.md">Chapter lesson</a></td>
      <td><a href="../qnas/002-installation-and-project-setup.md">Chapter Q&amp;A</a></td>
      <td><a href="providers-snippets-and-framework-integration.md">003 - Providers, snippets, and framework integration</a></td>
    </tr>
  </tbody>
</table>
