# 027 - Date, time, color pickers, sliders, and rating Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Create a date range filter and a volume slider with a numeric entry alternative. Document the value format sent to the API.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    027-date-time-color-pickers-sliders-and-rating.jsx
```

## 027-date-time-color-pickers-sliders-and-rating.jsx

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

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 027, inspect the result described below and interact with every trigger, field, or control.

The slider constrains a value from 0 to 100 and provides keyboard adjustment. A precise numeric input can be added for users who need exact entry.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Create a date range filter and a volume slider with a numeric entry alternative. Document the value format sent to the API.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Treating formatted date strings as timezone-neutral instants. Separate a calendar date from a timestamp and define the timezone policy.
- Using a slider when precise numeric entry matters. Pair it with a NumberInput or another direct-entry path when precision is important.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="tables-and-data-display.md">026 - Tables and data display</a></td>
      <td><a href="../lessons/027-date-time-color-pickers-sliders-and-rating.md">Chapter lesson</a></td>
      <td><a href="../qnas/027-date-time-color-pickers-sliders-and-rating.md">Chapter Q&amp;A</a></td>
      <td><a href="recipes-and-reusable-component-variants.md">028 - Recipes and reusable component variants</a></td>
    </tr>
  </tbody>
</table>
