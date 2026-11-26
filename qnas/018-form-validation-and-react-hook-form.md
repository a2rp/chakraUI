# 018 - Form validation and React Hook Form Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind form validation and react hook form?

Chakra Field handles visual and accessible field feedback, while a form library handles values, validation lifecycle, and submission state. Keep one source of truth for each input's value and error.

## 2. Which API should I learn first?

`Field.Root invalid, Field.ErrorText, react-hook-form register, Controller, handleSubmit`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Use native validation for simple forms. Add React Hook Form when many fields, complex validation, or controlled widgets make a dedicated form model valuable.

## 4. What state and accessibility detail matters most?

The form library owns values and validation state. Chakra Field displays that state; it does not perform validation by itself. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Validating only in JSX and accepting invalid data at the server. Client validation improves feedback but does not replace server-side validation.

## 6. How can I practice it?

Create a sign-up form with a registered email input, a controlled Select, field-level errors, and an async submit state. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. Does Chakra validate form values?

No. Chakra supplies controls and field presentation. Use browser constraints, application logic, or a form library for value validation.

## 8. When should I use Controller?

Use Controller when a custom controlled component does not expose the native input contract expected by register.

## 9. Should the server repeat validation?

Yes. Client checks are for responsive feedback, but the server must validate and authorize submitted data independently.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="017-select-combobox-and-autocomplete.md">017 - Select, Combobox, and Autocomplete</a></td>
      <td><a href="../lessons/018-form-validation-and-react-hook-form.md">Chapter lesson</a></td>
      <td><a href="../examples/018-form-validation-and-react-hook-form.md">Chapter example</a></td>
      <td><a href="019-cards-avatars-badges-and-lists.md">019 - Cards, avatars, badges, and lists</a></td>
    </tr>
  </tbody>
</table>
