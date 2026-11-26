# 032 - Accessibility, keyboard interaction, and RTL

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Accessibility, keyboard interaction, and RTL.
- Identify the main API: `Field labels, aria-label, _focusVisible, dir, LocaleProvider, logical CSS properties`.
- Choose an appropriate use case: Prefer native semantics and component defaults, then test keyboard and assistive technology flows. Use logical properties for layouts that must support both directions.
- Avoid the main implementation risks: Removing focus outlines without a replacement. Keyboard users need to see which control is active.

## Core idea

Accessible Chakra interfaces combine semantic elements, visible labels, sufficient contrast, keyboard support, and logical focus. Direction-aware layout props and locale providers help interfaces adapt to right-to-left languages.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `Field labels, aria-label, _focusVisible, dir, LocaleProvider, logical CSS properties`.

Chakra provides patterns but cannot infer the correct accessible name, reading order, contrast, or translation. Those remain product and content decisions.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

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

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Prefer native semantics and component defaults, then test keyboard and assistive technology flows. Use logical properties for layouts that must support both directions.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Removing focus outlines without a replacement. Keyboard users need to see which control is active.
- Using physical left/right margins and borders throughout an RTL interface when logical start/end properties express the intended direction.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Accessible Chakra interfaces combine semantic elements, visible labels, sufficient contrast, keyboard support, and logical focus. Direction-aware layout props and locale providers help interfaces adapt to right-to-left languages. Remember the API boundary: Field labels, aria-label, _focusVisible, dir, LocaleProvider, logical CSS properties. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Audit one form and one menu using keyboard only. Add a visible focus treatment, then switch the container direction and check reading and layout order.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="031-presence-animation-and-transitions.md">031 - Presence, animation, and transitions</a></td>
      <td><a href="../qnas/032-accessibility-keyboard-interaction-and-rtl.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/032-accessibility-keyboard-interaction-and-rtl.md">Chapter example</a></td>
      <td><a href="033-typescript-and-type-generation.md">033 - TypeScript and type generation</a></td>
    </tr>
  </tbody>
</table>
