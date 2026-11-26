# 031 - Presence, animation, and transitions

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Presence, animation, and transitions.
- Identify the main API: `Presence, present, animationName, animationStyle, keyframes`.
- Choose an appropriate use case: Animate state changes when motion clarifies cause and effect. Respect reduced-motion preferences and keep the interface usable without animation.
- Avoid the main implementation risks: Animating every element because motion is available. Excess movement can distract or harm users with vestibular sensitivities.

## Core idea

Presence coordinates whether conditional content is mounted and applies CSS-based enter and exit animation styles. CSS animation keeps visual transitions separate from state and avoids adding animation work to business logic.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `Presence, present, animationName, animationStyle, keyframes`.

The application controls whether content is present; Presence coordinates mount and exit timing. Motion is presentational and should not hide important state changes.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

```jsx
import { Button, Presence, Stack, useDisclosure } from "@chakra-ui/react"

export function AnimatedNotice() {
  const disclosure = useDisclosure()
  return (
    <Stack align="start" gap="3">
      <Button onClick={disclosure.open}>Show notice</Button>
      <Presence
        present={disclosure.open}
        animationName={{ _open: "fade-in", _closed: "fade-out" }}
        animationDuration="moderate"
      >
        <div role="status">Your changes are saved.</div>
      </Presence>
    </Stack>
  )
}
```

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Animate state changes when motion clarifies cause and effect. Respect reduced-motion preferences and keep the interface usable without animation.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Animating every element because motion is available. Excess movement can distract or harm users with vestibular sensitivities.
- Removing content immediately when an exit animation is expected. Presence must remain mounted long enough to complete the transition.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Presence coordinates whether conditional content is mounted and applies CSS-based enter and exit animation styles. CSS animation keeps visual transitions separate from state and avoids adding animation work to business logic. Remember the API boundary: Presence, present, animationName, animationStyle, keyframes. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Animate a dismissible status panel with a short enter/exit effect. Add a reduced-motion alternative and verify content still works without motion.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="030-composition-chakra-factory-and-aschild.md">030 - Composition, Chakra factory, and asChild</a></td>
      <td><a href="../qnas/031-presence-animation-and-transitions.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/031-presence-animation-and-transitions.md">Chapter example</a></td>
      <td><a href="032-accessibility-keyboard-interaction-and-rtl.md">032 - Accessibility, keyboard interaction, and RTL</a></td>
    </tr>
  </tbody>
</table>
