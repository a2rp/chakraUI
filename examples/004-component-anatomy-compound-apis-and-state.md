# 004 - Component anatomy, compound APIs, and state Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Compose one Accordion item and one Tabs group. Label each part and identify which state is owned internally versus supplied by React.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    004-component-anatomy-compound-apis-and-state.jsx
```

## 004-component-anatomy-compound-apis-and-state.jsx

```jsx
import { Accordion } from "@chakra-ui/react"

export function ShippingQuestion() {
  return (
    <Accordion.Root collapsible>
      <Accordion.Item value="shipping">
        <Accordion.ItemTrigger>
          How long does shipping take?
          <Accordion.ItemIndicator />
        </Accordion.ItemTrigger>
        <Accordion.ItemContent>
          <Accordion.ItemBody>Most orders arrive within five business days.</Accordion.ItemBody>
        </Accordion.ItemContent>
      </Accordion.Item>
    </Accordion.Root>
  )
}
```

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 004, inspect the result described below and interact with every trigger, field, or control.

The trigger toggles the associated content, and Chakra coordinates keyboard interaction and expanded state across the compound parts.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Compose one Accordion item and one Tabs group. Label each part and identify which state is owned internally versus supplied by React.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Omitting a required part such as a hidden input or item value. Compound APIs make more structure visible, but each documented part still has a role.
- Controlling a widget with value while also expecting defaultValue to control later updates. Use defaultValue for initial state or value plus its change callback for controlled state.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="003-providers-snippets-and-framework-integration.md">003 - Providers, snippets, and framework integration</a></td>
      <td><a href="../lessons/004-component-anatomy-compound-apis-and-state.md">Chapter lesson</a></td>
      <td><a href="../qnas/004-component-anatomy-compound-apis-and-state.md">Chapter Q&amp;A</a></td>
      <td><a href="005-style-props-and-token-aware-styling.md">005 - Style props and token-aware styling</a></td>
    </tr>
  </tbody>
</table>
