# 015 - Fields, inputs, and textareas

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Fields, inputs, and textareas.
- Identify the main API: `Field.Root, Field.Label, Field.HelperText, Field.ErrorText, Input, Textarea`.
- Choose an appropriate use case: Use a visible label for each control. Use placeholder for an example or hint, never as the only accessible name.
- Avoid the main implementation risks: Relying on placeholder text as a persistent label. It disappears during input and is less reliable for accessibility.

## Core idea

Form controls need labels, helper text, error feedback, and predictable value behavior. In v3, Field composes these concerns around Input, Textarea, or another control.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `Field.Root, Field.Label, Field.HelperText, Field.ErrorText, Input, Textarea`.

Field.Root shares required, invalid, disabled, and read-only state with its parts. The actual input still needs name and form integration when submitting native form data.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

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

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Use a visible label for each control. Use placeholder for an example or hint, never as the only accessible name.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Relying on placeholder text as a persistent label. It disappears during input and is less reliable for accessibility.
- Setting invalid on the input without coordinating field context and a clear explanation of how to fix the value.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Form controls need labels, helper text, error feedback, and predictable value behavior. In v3, Field composes these concerns around Input, Textarea, or another control. Remember the API boundary: Field.Root, Field.Label, Field.HelperText, Field.ErrorText, Input, Textarea. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Build an email field with a visible label, helper text, required indication, and an error message that appears after validation.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="buttons-and-action-components.md">014 - Buttons and action components</a></td>
      <td><a href="../qnas/015-fields-inputs-and-textareas.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/015-fields-inputs-and-textareas.md">Chapter example</a></td>
      <td><a href="checkbox-radio-and-switch-controls.md">016 - Checkbox, radio, and switch controls</a></td>
    </tr>
  </tbody>
</table>
