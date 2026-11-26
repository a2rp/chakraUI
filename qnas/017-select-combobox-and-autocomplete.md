# 017 - Select, Combobox, and Autocomplete Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind select, combobox, and autocomplete?

Selection widgets range from native selects to searchable comboboxes. Chakra's compound Select and Combobox components use a collection to define options and expose explicit parts for input, trigger, list, and selected value.

## 2. Which API should I learn first?

`NativeSelect, Select.Root, Combobox.Root, createListCollection, collection`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Prefer NativeSelect for a simple form choice that benefits from platform behavior. Use Select for a styled list and Combobox when users need text search or typeahead.

## 4. What state and accessibility detail matters most?

Collection items pair stable values with human-readable labels. Controlled widgets use value and onValueChange; the collection is data, not rendered JSX itself. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Choosing a custom popup for a small static list without a real need. Native controls often provide strong platform accessibility and mobile behavior.

## 6. How can I practice it?

Create a framework picker with a searchable collection. Add an empty state, a clear label, and a selected value that can be submitted. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. When is NativeSelect enough?

Use NativeSelect for ordinary fixed choices when platform-native behavior is acceptable and search or rich option content is unnecessary.

## 8. What is a collection?

A collection is structured option data with stable values and labels. Chakra's selection components use it to coordinate items and interaction state.

## 9. Is a Combobox always an autocomplete?

A combobox combines an input with a selectable popup. Autocomplete describes a suggestion behavior that can be configured on top of that interaction.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="016-checkbox-radio-and-switch-controls.md">016 - Checkbox, radio, and switch controls</a></td>
      <td><a href="../lessons/017-select-combobox-and-autocomplete.md">Chapter lesson</a></td>
      <td><a href="../examples/017-select-combobox-and-autocomplete.md">Chapter example</a></td>
      <td><a href="018-form-validation-and-react-hook-form.md">018 - Form validation and React Hook Form</a></td>
    </tr>
  </tbody>
</table>
