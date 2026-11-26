# 018 - Form validation and React Hook Form Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Create a sign-up form with a registered email input, a controlled Select, field-level errors, and an async submit state.

## Assumptions and prerequisites

- `@chakra-ui/react`, `@emotion/react`, and `react-hook-form`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    018-form-validation-and-react-hook-form.jsx
```

## 018-form-validation-and-react-hook-form.jsx

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

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 018, inspect the result described below and interact with every trigger, field, or control.

React Hook Form validates the registered field, Field renders the error state, and the submit button communicates an in-flight request.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Create a sign-up form with a registered email input, a controlled Select, field-level errors, and an async submit state.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Validating only in JSX and accepting invalid data at the server. Client validation improves feedback but does not replace server-side validation.
- Using Controller for every plain input. Register native-compatible inputs directly and reserve Controller for controlled widgets.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="017-select-combobox-and-autocomplete.md">017 - Select, Combobox, and Autocomplete</a></td>
      <td><a href="../lessons/018-form-validation-and-react-hook-form.md">Chapter lesson</a></td>
      <td><a href="../qnas/018-form-validation-and-react-hook-form.md">Chapter Q&amp;A</a></td>
      <td><a href="019-cards-avatars-badges-and-lists.md">019 - Cards, avatars, badges, and lists</a></td>
    </tr>
  </tbody>
</table>
