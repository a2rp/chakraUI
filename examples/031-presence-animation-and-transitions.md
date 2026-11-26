# 031 - Presence, animation, and transitions Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Animate a dismissible status panel with a short enter/exit effect. Add a reduced-motion alternative and verify content still works without motion.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    031-presence-animation-and-transitions.jsx
```

## 031-presence-animation-and-transitions.jsx

```jsx
import { useState } from "react"
import { Button, Presence, Stack } from "@chakra-ui/react"

export function AnimatedNotice() {
  const [open, setOpen] = useState(false)
  return (
    <Stack align="start" gap="3">
      <Button onClick={() => setOpen((value) => !value)}>Toggle notice</Button>
      <Presence
        present={open}
        animationName={{ _open: "fade-in", _closed: "fade-out" }}
        animationDuration="moderate"
      >
        <div role="status">Your changes are saved.</div>
      </Presence>
    </Stack>
  )
}
```

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 031, inspect the result described below and interact with every trigger, field, or control.

The notice appears and exits with CSS motion while its visible state remains controlled by the disclosure state.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Animate a dismissible status panel with a short enter/exit effect. Add a reduced-motion alternative and verify content still works without motion.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Animating every element because motion is available. Excess movement can distract or harm users with vestibular sensitivities.
- Removing content immediately when an exit animation is expected. Presence must remain mounted long enough to complete the transition.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="030-composition-chakra-factory-and-aschild.md">030 - Composition, Chakra factory, and asChild</a></td>
      <td><a href="../lessons/031-presence-animation-and-transitions.md">Chapter lesson</a></td>
      <td><a href="../qnas/031-presence-animation-and-transitions.md">Chapter Q&amp;A</a></td>
      <td><a href="032-accessibility-keyboard-interaction-and-rtl.md">032 - Accessibility, keyboard interaction, and RTL</a></td>
    </tr>
  </tbody>
</table>
