# 017 - Select, Combobox, and Autocomplete

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Select, Combobox, and Autocomplete.
- Identify the main API: `NativeSelect, Select.Root, Combobox.Root, createListCollection, collection`.
- Choose an appropriate use case: Prefer NativeSelect for a simple form choice that benefits from platform behavior. Use Select for a styled list and Combobox when users need text search or typeahead.
- Avoid the main implementation risks: Choosing a custom popup for a small static list without a real need. Native controls often provide strong platform accessibility and mobile behavior.

## Core idea

Selection widgets range from native selects to searchable comboboxes. Chakra's compound Select and Combobox components use a collection to define options and expose explicit parts for input, trigger, list, and selected value.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `NativeSelect, Select.Root, Combobox.Root, createListCollection, collection`.

Collection items pair stable values with human-readable labels. Controlled widgets use value and onValueChange; the collection is data, not rendered JSX itself.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

```jsx
import { Combobox, createListCollection } from "@chakra-ui/react"

const frameworks = createListCollection({
  items: [
    { label: "React", value: "react" },
    { label: "Vue", value: "vue" },
    { label: "Svelte", value: "svelte" },
  ],
})

export function FrameworkPicker() {
  return (
    <Combobox.Root collection={frameworks}>
      <Combobox.Label>Framework</Combobox.Label>
      <Combobox.Control>
        <Combobox.Input placeholder="Search frameworks" />
        <Combobox.Trigger />
      </Combobox.Control>
      <Combobox.Positioner>
        <Combobox.Content>
          {frameworks.items.map((item) => (
            <Combobox.Item key={item.value} item={item}>
              <Combobox.ItemText />
            </Combobox.Item>
          ))}
        </Combobox.Content>
      </Combobox.Positioner>
    </Combobox.Root>
  )
}
```

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Prefer NativeSelect for a simple form choice that benefits from platform behavior. Use Select for a styled list and Combobox when users need text search or typeahead.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Choosing a custom popup for a small static list without a real need. Native controls often provide strong platform accessibility and mobile behavior.
- Rendering option labels without stable values or failing to synchronize selected state with the form.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Selection widgets range from native selects to searchable comboboxes. Chakra's compound Select and Combobox components use a collection to define options and expose explicit parts for input, trigger, list, and selected value. Remember the API boundary: NativeSelect, Select.Root, Combobox.Root, createListCollection, collection. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Create a framework picker with a searchable collection. Add an empty state, a clear label, and a selected value that can be submitted.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="016-checkbox-radio-and-switch-controls.md">016 - Checkbox, radio, and switch controls</a></td>
      <td><a href="../qnas/017-select-combobox-and-autocomplete.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/017-select-combobox-and-autocomplete.md">Chapter example</a></td>
      <td><a href="018-form-validation-and-react-hook-form.md">018 - Form validation and React Hook Form</a></td>
    </tr>
  </tbody>
</table>
