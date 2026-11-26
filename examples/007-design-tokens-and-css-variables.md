# 007 - Design tokens and CSS variables Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Add brand colors and spacing tokens to the system. Use one token through a style prop and inspect its computed CSS variable in browser developer tools.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    007-design-tokens-and-css-variables.jsx
```

## 007-design-tokens-and-css-variables.jsx

```jsx
import { Box } from "@chakra-ui/react"

export function TokenPanel() {
  return (
    <Box bg="brand.500" color="white" p="4" borderRadius="md">
      Token-backed panel
    </Box>
  )
}

// Custom token leaves use { value: ... } in the system configuration.
```

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 007, inspect the result described below and interact with every trigger, field, or control.

The component styles resolve to configured CSS custom properties, so changing a token updates all consumers consistently.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Add brand colors and spacing tokens to the system. Use one token through a style prop and inspect its computed CSS variable in browser developer tools.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Forgetting the v3 token shape. Custom token leaves use objects with a value field, such as colors.brand.500.value.
- Treating the generated CSS variable name as a permanent public contract. Prefer semantic token names or the system token helpers over hardcoded generated names.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="006-responsive-and-conditional-styles.md">006 - Responsive and conditional styles</a></td>
      <td><a href="../lessons/007-design-tokens-and-css-variables.md">Chapter lesson</a></td>
      <td><a href="../qnas/007-design-tokens-and-css-variables.md">Chapter Q&amp;A</a></td>
      <td><a href="008-custom-system-and-theme-configuration.md">008 - Custom system and theme configuration</a></td>
    </tr>
  </tbody>
</table>
