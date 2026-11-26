# 032 - Accessibility, keyboard interaction, and RTL Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Audit one form and one menu using keyboard only. Add a visible focus treatment, then switch the container direction and check reading and layout order.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    032-accessibility-keyboard-interaction-and-rtl.jsx
```

## 032-accessibility-keyboard-interaction-and-rtl.jsx

```jsx
import { Field, Input, Stack } from "@chakra-ui/react"

export function DirectionAwareForm() {
  return (
    <Stack dir="rtl" gap="4" maxW="sm">
      <Field.Root required>
        <Field.Label>البريد الإلكتروني</Field.Label>
        <Input type="email" autoComplete="email" />
        <Field.HelperText>أدخل عنوان البريد الإلكتروني</Field.HelperText>
      </Field.Root>
    </Stack>
  )
}
```

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 032, inspect the result described below and interact with every trigger, field, or control.

The field has a visible translated label and helper text, while the RTL direction flows through the container. Verify focus order with keyboard navigation.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Audit one form and one menu using keyboard only. Add a visible focus treatment, then switch the container direction and check reading and layout order.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Removing focus outlines without a replacement. Keyboard users need to see which control is active.
- Using physical left/right margins and borders throughout an RTL interface when logical start/end properties express the intended direction.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="031-presence-animation-and-transitions.md">031 - Presence, animation, and transitions</a></td>
      <td><a href="../lessons/032-accessibility-keyboard-interaction-and-rtl.md">Chapter lesson</a></td>
      <td><a href="../qnas/032-accessibility-keyboard-interaction-and-rtl.md">Chapter Q&amp;A</a></td>
      <td><a href="033-typescript-and-type-generation.md">033 - TypeScript and type generation</a></td>
    </tr>
  </tbody>
</table>
