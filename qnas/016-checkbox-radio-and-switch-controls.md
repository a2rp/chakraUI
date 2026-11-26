# 016 - Checkbox, radio, and switch controls Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind checkbox, radio, and switch controls?

Checkboxes support independent binary or multi-select choices, radio groups select one option from a set, and switches represent an immediate on/off setting. Chakra v3 exposes explicit compound parts for these controls.

## 2. Which API should I learn first?

`Checkbox.Root, RadioGroup.Root, Switch.Root, checked, onCheckedChange, value`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Choose the control that matches the decision: independent selection, one-of-many selection, or a persistent setting toggle.

## 4. What state and accessibility detail matters most?

Checkbox and switch expose checked state; radio groups expose a selected value. Controlled usage must update state in the associated change callback. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Using a switch for a choice that requires an explicit confirmation or submit step. A switch usually signals an immediate setting change.

## 6. How can I practice it?

Build a notification preferences form with two independent checkboxes and one radio group for delivery frequency. Add labels and helper text. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. Checkbox or radio: how do I choose?

Use checkboxes when options are independent. Use a radio group when exactly one value should be selected from a set.

## 8. When is a switch a good fit?

Use it for a setting that takes effect immediately and has a clear on/off meaning. Use a checkbox for a form choice that is saved later.

## 9. Why include HiddenInput?

The hidden input part connects the component's state to native forms and form libraries. Follow the component anatomy in the current docs.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="fields-inputs-and-textareas.md">015 - Fields, inputs, and textareas</a></td>
      <td><a href="../lessons/016-checkbox-radio-and-switch-controls.md">Chapter lesson</a></td>
      <td><a href="../examples/016-checkbox-radio-and-switch-controls.md">Chapter example</a></td>
      <td><a href="select-combobox-and-autocomplete.md">017 - Select, Combobox, and Autocomplete</a></td>
    </tr>
  </tbody>
</table>
