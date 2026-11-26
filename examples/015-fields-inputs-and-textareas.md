# 015 - Fields, inputs, and textareas Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Build an email field with a visible label, helper text, required indication, and an error message that appears after validation.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    015-fields-inputs-and-textareas.jsx
```

## 015-fields-inputs-and-textareas.jsx

```jsx
import { Field, Input } from "@chakra-ui/react"

export function EmailField() {
  return (
    <Field.Root required>
      <Field.Label>Email address <Field.RequiredIndicator /></Field.Label>
      <Input name="email" type="email" autoComplete="email" />
      <Field.HelperText>We will only use this for account updates.</Field.HelperText>
    </Field.Root>
  )
}
```

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 015, inspect the result described below and interact with every trigger, field, or control.

The input has a visible label and helper text, and required state is communicated through Field.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Build an email field with a visible label, helper text, required indication, and an error message that appears after validation.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Relying on placeholder text as a persistent label. It disappears during input and is less reliable for accessibility.
- Setting invalid on the input without coordinating field context and a clear explanation of how to fix the value.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="buttons-and-action-components.md">014 - Buttons and action components</a></td>
      <td><a href="../lessons/015-fields-inputs-and-textareas.md">Chapter lesson</a></td>
      <td><a href="../qnas/015-fields-inputs-and-textareas.md">Chapter Q&amp;A</a></td>
      <td><a href="checkbox-radio-and-switch-controls.md">016 - Checkbox, radio, and switch controls</a></td>
    </tr>
  </tbody>
</table>
