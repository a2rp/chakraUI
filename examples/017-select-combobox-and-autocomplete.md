# 017 - Select, Combobox, and Autocomplete Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Create a framework picker with a searchable collection. Add an empty state, a clear label, and a selected value that can be submitted.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    017-select-combobox-and-autocomplete.jsx
```

## 017-select-combobox-and-autocomplete.jsx

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

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 017, inspect the result described below and interact with every trigger, field, or control.

The field filters a stable collection and lets users choose a framework by typing or navigating the options.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Create a framework picker with a searchable collection. Add an empty state, a clear label, and a selected value that can be submitted.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Choosing a custom popup for a small static list without a real need. Native controls often provide strong platform accessibility and mobile behavior.
- Rendering option labels without stable values or failing to synchronize selected state with the form.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="checkbox-radio-and-switch-controls.md">016 - Checkbox, radio, and switch controls</a></td>
      <td><a href="../lessons/017-select-combobox-and-autocomplete.md">Chapter lesson</a></td>
      <td><a href="../qnas/017-select-combobox-and-autocomplete.md">Chapter Q&amp;A</a></td>
      <td><a href="form-validation-and-react-hook-form.md">018 - Form validation and React Hook Form</a></td>
    </tr>
  </tbody>
</table>
