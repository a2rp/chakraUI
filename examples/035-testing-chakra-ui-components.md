# 035 - Testing Chakra UI components Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Write tests for a labelled form field and a dialog trigger. Assert the dialog opens, Escape closes it, and focus returns appropriately.

## Assumptions and prerequisites

- React, `@chakra-ui/react`, `@emotion/react`, Vitest or Jest, and React Testing Library.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    035-testing-chakra-ui-components.jsx
```

## 035-testing-chakra-ui-components.jsx

```jsx
import { ChakraProvider, Button, defaultSystem } from "@chakra-ui/react"
import { render, screen } from "@testing-library/react"
import { expect, test } from "vitest"

function SaveButton() {
  return <Button onClick={() => {}}>Save changes</Button>
}

test("renders an accessible save action", () => {
  render(
    <ChakraProvider value={defaultSystem}>
      <SaveButton />
    </ChakraProvider>,
  )
  expect(screen.getByRole("button", { name: "Save changes" })).toBeTruthy()
})
```

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 035, inspect the result described below and interact with every trigger, field, or control.

The test checks the action through its role and accessible name, independent of Chakra's generated class names.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Write tests for a labelled form field and a dialog trigger. Assert the dialog opens, Escape closes it, and focus returns appropriately.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Selecting elements by generated Emotion class names. Those are implementation details and can change after a refactor.
- Testing only that a component renders. Assert the user-visible result of clicking, typing, submitting, or dismissing.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="nextjs-server-components-and-ssr.md">034 - Next.js, Server Components, and SSR</a></td>
      <td><a href="../lessons/035-testing-chakra-ui-components.md">Chapter lesson</a></td>
      <td><a href="../qnas/035-testing-chakra-ui-components.md">Chapter Q&amp;A</a></td>
      <td><a href="performance-and-styling-architecture.md">036 - Performance and styling architecture</a></td>
    </tr>
  </tbody>
</table>
