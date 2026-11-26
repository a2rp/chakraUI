# 016 - Checkbox, radio, and switch controls

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Checkbox, radio, and switch controls.
- Identify the main API: `Checkbox.Root, RadioGroup.Root, Switch.Root, checked, onCheckedChange, value`.
- Choose an appropriate use case: Choose the control that matches the decision: independent selection, one-of-many selection, or a persistent setting toggle.
- Avoid the main implementation risks: Using a switch for a choice that requires an explicit confirmation or submit step. A switch usually signals an immediate setting change.

## Core idea

Checkboxes support independent binary or multi-select choices, radio groups select one option from a set, and switches represent an immediate on/off setting. Chakra v3 exposes explicit compound parts for these controls.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `Checkbox.Root, RadioGroup.Root, Switch.Root, checked, onCheckedChange, value`.

Checkbox and switch expose checked state; radio groups expose a selected value. Controlled usage must update state in the associated change callback.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

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

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Choose the control that matches the decision: independent selection, one-of-many selection, or a persistent setting toggle.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Using a switch for a choice that requires an explicit confirmation or submit step. A switch usually signals an immediate setting change.
- Forgetting to provide a visible label or hidden native input part in a compound form control.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Checkboxes support independent binary or multi-select choices, radio groups select one option from a set, and switches represent an immediate on/off setting. Chakra v3 exposes explicit compound parts for these controls. Remember the API boundary: Checkbox.Root, RadioGroup.Root, Switch.Root, checked, onCheckedChange, value. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Build a notification preferences form with two independent checkboxes and one radio group for delivery frequency. Add labels and helper text.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="fields-inputs-and-textareas.md">015 - Fields, inputs, and textareas</a></td>
      <td><a href="../qnas/016-checkbox-radio-and-switch-controls.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/016-checkbox-radio-and-switch-controls.md">Chapter example</a></td>
      <td><a href="select-combobox-and-autocomplete.md">017 - Select, Combobox, and Autocomplete</a></td>
    </tr>
  </tbody>
</table>
