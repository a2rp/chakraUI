# 027 - Date, time, color pickers, sliders, and rating

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Date, time, color pickers, sliders, and rating.
- Identify the main API: `DateInput, DatePicker, ColorPicker, Slider, NumberInput, Rating`.
- Choose an appropriate use case: Use a specialized picker when its value model and interaction help users complete the task. Keep native or simpler input alternatives in mind for constrained environments.
- Avoid the main implementation risks: Treating formatted date strings as timezone-neutral instants. Separate a calendar date from a timestamp and define the timezone policy.

## Core idea

Specialized controls model structured values such as dates, ranges, colors, and ratings. Their compound APIs expose segments, labels, hidden inputs, and keyboard behavior that plain text inputs would otherwise have to recreate.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `DateInput, DatePicker, ColorPicker, Slider, NumberInput, Rating`.

These widgets expose structured values and specialized keyboard interaction. Integrate them with forms through their supported hidden input or controlled value APIs.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

```jsx
import { Slider, Stack, Text } from "@chakra-ui/react"

export function VolumeControl() {
  return (
    <Stack gap="3" maxW="sm">
      <Text id="volume-label">Volume</Text>
      <Slider.Root defaultValue={[40]} min={0} max={100} aria-labelledby="volume-label">
        <Slider.Control>
          <Slider.Track><Slider.Range /></Slider.Track>
          <Slider.Thumb index={0} />
        </Slider.Control>
      </Slider.Root>
      <Text color="fg.muted">Use arrow keys for fine adjustment.</Text>
    </Stack>
  )
}
```

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Use a specialized picker when its value model and interaction help users complete the task. Keep native or simpler input alternatives in mind for constrained environments.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Treating formatted date strings as timezone-neutral instants. Separate a calendar date from a timestamp and define the timezone policy.
- Using a slider when precise numeric entry matters. Pair it with a NumberInput or another direct-entry path when precision is important.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Specialized controls model structured values such as dates, ranges, colors, and ratings. Their compound APIs expose segments, labels, hidden inputs, and keyboard behavior that plain text inputs would otherwise have to recreate. Remember the API boundary: DateInput, DatePicker, ColorPicker, Slider, NumberInput, Rating. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Create a date range filter and a volume slider with a numeric entry alternative. Document the value format sent to the API.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="026-tables-and-data-display.md">026 - Tables and data display</a></td>
      <td><a href="../qnas/027-date-time-color-pickers-sliders-and-rating.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/027-date-time-color-pickers-sliders-and-rating.md">Chapter example</a></td>
      <td><a href="028-recipes-and-reusable-component-variants.md">028 - Recipes and reusable component variants</a></td>
    </tr>
  </tbody>
</table>
