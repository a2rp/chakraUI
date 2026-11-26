# 015 - Fields, inputs, and textareas Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind fields, inputs, and textareas?

Form controls need labels, helper text, error feedback, and predictable value behavior. In v3, Field composes these concerns around Input, Textarea, or another control.

## 2. Which API should I learn first?

`Field.Root, Field.Label, Field.HelperText, Field.ErrorText, Input, Textarea`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Use a visible label for each control. Use placeholder for an example or hint, never as the only accessible name.

## 4. What state and accessibility detail matters most?

Field.Root shares required, invalid, disabled, and read-only state with its parts. The actual input still needs name and form integration when submitting native form data. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Relying on placeholder text as a persistent label. It disappears during input and is less reliable for accessibility.

## 6. How can I practice it?

Build an email field with a visible label, helper text, required indication, and an error message that appears after validation. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. Is placeholder an acceptable replacement for a label?

No. Use a visible label. Placeholder text disappears when users type and should only supply an example or short hint.

## 8. Where should invalid state be set?

Set invalid on Field.Root and render Field.ErrorText so the visual state, field context, and explanatory message agree.

## 9. Can Input submit a native form?

Yes. Give it a name and place it in a form; native form submission requires named successful controls.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="014-buttons-and-action-components.md">014 - Buttons and action components</a></td>
      <td><a href="../lessons/015-fields-inputs-and-textareas.md">Chapter lesson</a></td>
      <td><a href="../examples/015-fields-inputs-and-textareas.md">Chapter example</a></td>
      <td><a href="016-checkbox-radio-and-switch-controls.md">016 - Checkbox, radio, and switch controls</a></td>
    </tr>
  </tbody>
</table>
