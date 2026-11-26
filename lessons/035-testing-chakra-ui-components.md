# 035 - Testing Chakra UI components

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Testing Chakra UI components.
- Identify the main API: `@testing-library/react, user-event, getByRole, ChakraProvider wrapper`.
- Choose an appropriate use case: Test key interactions, accessible names, errors, and state transitions. Keep a small number of browser tests for portal, focus, and layout behavior.
- Avoid the main implementation risks: Selecting elements by generated Emotion class names. Those are implementation details and can change after a refactor.

## Core idea

Test user-visible behavior rather than Chakra's internal class names. Testing Library queries by role, label, and visible text produce tests that survive styling and markup refactors.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `@testing-library/react, user-event, getByRole, ChakraProvider wrapper`.

Wrap tests with the same provider and custom system used by the app. Portals may render outside the initial container but remain queryable through screen.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

```jsx
import { ChakraProvider, Button, defaultSystem } from "@chakra-ui/react"
import { render, screen } from "@testing-library/react"
import userEvent from "@testing-library/user-event"

function SaveButton() {
  return <Button onClick={() => {}}>Save changes</Button>
}

test("renders an accessible save action", () => {
  render(
    <ChakraProvider value={defaultSystem}>
      <SaveButton />
    </ChakraProvider>,
  )
  expect(screen.getByRole("button", { name: "Save changes" })).toBeInTheDocument()
})
```

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Test key interactions, accessible names, errors, and state transitions. Keep a small number of browser tests for portal, focus, and layout behavior.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Selecting elements by generated Emotion class names. Those are implementation details and can change after a refactor.
- Testing only that a component renders. Assert the user-visible result of clicking, typing, submitting, or dismissing.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Test user-visible behavior rather than Chakra's internal class names. Testing Library queries by role, label, and visible text produce tests that survive styling and markup refactors. Remember the API boundary: @testing-library/react, user-event, getByRole, ChakraProvider wrapper. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Write tests for a labelled form field and a dialog trigger. Assert the dialog opens, Escape closes it, and focus returns appropriately.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="nextjs-server-components-and-ssr.md">034 - Next.js, Server Components, and SSR</a></td>
      <td><a href="../qnas/035-testing-chakra-ui-components.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/035-testing-chakra-ui-components.md">Chapter example</a></td>
      <td><a href="performance-and-styling-architecture.md">036 - Performance and styling architecture</a></td>
    </tr>
  </tbody>
</table>
