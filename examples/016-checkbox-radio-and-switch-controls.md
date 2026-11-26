# 016 - Checkbox, radio, and switch controls Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Build a notification preferences form with two independent checkboxes and one radio group for delivery frequency. Add labels and helper text.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    016-checkbox-radio-and-switch-controls.jsx
```

## 016-checkbox-radio-and-switch-controls.jsx

```jsx
import { Checkbox, Stack, Switch } from "@chakra-ui/react"

export function NotificationSettings() {
  return (
    <Stack gap="4">
      <Checkbox.Root defaultChecked>
        <Checkbox.HiddenInput />
        <Checkbox.Control />
        <Checkbox.Label>Email me product updates</Checkbox.Label>
      </Checkbox.Root>
      <Switch.Root>
        <Switch.HiddenInput />
        <Switch.Control />
        <Switch.Label>Enable weekly summary</Switch.Label>
      </Switch.Root>
    </Stack>
  )
}
```

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 016, inspect the result described below and interact with every trigger, field, or control.

Each preference is labeled and keyboard-operable. Checkbox and switch state can be submitted or controlled by React as the form requires.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Build a notification preferences form with two independent checkboxes and one radio group for delivery frequency. Add labels and helper text.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Using a switch for a choice that requires an explicit confirmation or submit step. A switch usually signals an immediate setting change.
- Forgetting to provide a visible label or hidden native input part in a compound form control.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="015-fields-inputs-and-textareas.md">015 - Fields, inputs, and textareas</a></td>
      <td><a href="../lessons/016-checkbox-radio-and-switch-controls.md">Chapter lesson</a></td>
      <td><a href="../qnas/016-checkbox-radio-and-switch-controls.md">Chapter Q&amp;A</a></td>
      <td><a href="017-select-combobox-and-autocomplete.md">017 - Select, Combobox, and Autocomplete</a></td>
    </tr>
  </tbody>
</table>
