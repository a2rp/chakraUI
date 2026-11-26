# 003 - Providers, snippets, and framework integration

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Providers, snippets, and framework integration.
- Identify the main API: `ChakraProvider value, defaultSystem, @chakra-ui/cli snippet add, Provider composition`.
- Choose an appropriate use case: Use one provider near the application root so theme context is shared. Use snippets for repeated, opinionated compositions such as color-mode controls or a toaster.
- Avoid the main implementation risks: Creating nested providers without an isolation need. Separate providers can create different theme contexts and make shared behavior harder to reason about.

## Core idea

ChakraProvider makes a styling system available to descendants. The CLI can add editable component compositions to a project; these snippets are source files you own, not a mandatory hidden component layer.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `ChakraProvider value, defaultSystem, @chakra-ui/cli snippet add, Provider composition`.

The provider establishes context for the active Chakra system. Some snippets also compose third-party providers, so their props and runtime behavior depend on those libraries.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

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

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Use one provider near the application root so theme context is shared. Use snippets for repeated, opinionated compositions such as color-mode controls or a toaster.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Creating nested providers without an isolation need. Separate providers can create different theme contexts and make shared behavior harder to reason about.
- Assuming a generated snippet is a framework primitive. It is ordinary source code; review it, adapt imports, and keep it in sync with your app.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

ChakraProvider makes a styling system available to descendants. The CLI can add editable component compositions to a project; these snippets are source files you own, not a mandatory hidden component layer. Remember the API boundary: ChakraProvider value, defaultSystem, @chakra-ui/cli snippet add, Provider composition. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Create a small src/components/ui/provider.jsx wrapper and use it once at the root. Add one CLI snippet, inspect the generated files, and explain each dependency.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="installation-and-project-setup.md">002 - Installation and project setup</a></td>
      <td><a href="../qnas/003-providers-snippets-and-framework-integration.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/003-providers-snippets-and-framework-integration.md">Chapter example</a></td>
      <td><a href="component-anatomy-compound-apis-and-state.md">004 - Component anatomy, compound APIs, and state</a></td>
    </tr>
  </tbody>
</table>
