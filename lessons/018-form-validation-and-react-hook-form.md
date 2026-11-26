# 018 - Form validation and React Hook Form

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Form validation and React Hook Form.
- Identify the main API: `Field.Root invalid, Field.ErrorText, react-hook-form register, Controller, handleSubmit`.
- Choose an appropriate use case: Use native validation for simple forms. Add React Hook Form when many fields, complex validation, or controlled widgets make a dedicated form model valuable.
- Avoid the main implementation risks: Validating only in JSX and accepting invalid data at the server. Client validation improves feedback but does not replace server-side validation.

## Core idea

Chakra Field handles visual and accessible field feedback, while a form library handles values, validation lifecycle, and submission state. Keep one source of truth for each input's value and error.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `Field.Root invalid, Field.ErrorText, react-hook-form register, Controller, handleSubmit`.

The form library owns values and validation state. Chakra Field displays that state; it does not perform validation by itself.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

```jsx
import { Button, Field, Input, Stack } from "@chakra-ui/react"
import { useForm } from "react-hook-form"

export function ContactForm() {
  const { register, handleSubmit, formState: { errors, isSubmitting } } = useForm()
  const onSubmit = async (values) => console.log(values)

  return (
    <form onSubmit={handleSubmit(onSubmit)} noValidate>
      <Stack gap="4">
        <Field.Root invalid={Boolean(errors.email)}>
          <Field.Label>Email</Field.Label>
          <Input type="email" {...register("email", { required: "Enter an email address" })} />
          <Field.ErrorText>{errors.email?.message}</Field.ErrorText>
        </Field.Root>
        <Button type="submit" loading={isSubmitting}>Send</Button>
      </Stack>
    </form>
  )
}
```

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Use native validation for simple forms. Add React Hook Form when many fields, complex validation, or controlled widgets make a dedicated form model valuable.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Validating only in JSX and accepting invalid data at the server. Client validation improves feedback but does not replace server-side validation.
- Using Controller for every plain input. Register native-compatible inputs directly and reserve Controller for controlled widgets.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Chakra Field handles visual and accessible field feedback, while a form library handles values, validation lifecycle, and submission state. Keep one source of truth for each input's value and error. Remember the API boundary: Field.Root invalid, Field.ErrorText, react-hook-form register, Controller, handleSubmit. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Create a sign-up form with a registered email input, a controlled Select, field-level errors, and an async submit state.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="select-combobox-and-autocomplete.md">017 - Select, Combobox, and Autocomplete</a></td>
      <td><a href="../qnas/018-form-validation-and-react-hook-form.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/018-form-validation-and-react-hook-form.md">Chapter example</a></td>
      <td><a href="cards-avatars-badges-and-lists.md">019 - Cards, avatars, badges, and lists</a></td>
    </tr>
  </tbody>
</table>
