# 004 - Component anatomy, compound APIs, and state

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Component anatomy, compound APIs, and state.
- Identify the main API: `Component.Root, Component.Trigger, Component.Content, value/defaultValue, onValueChange`.
- Choose an appropriate use case: Choose compound components when an interaction needs multiple coordinated elements or custom markup. Use a simple component when it already expresses the desired interaction.
- Avoid the main implementation risks: Omitting a required part such as a hidden input or item value. Compound APIs make more structure visible, but each documented part still has a role.

## Core idea

Many Chakra v3 interactive components expose a Root and named parts such as Trigger, Content, and Item. The parts make structure explicit while sharing state and accessibility behavior through their compound context.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `Component.Root, Component.Trigger, Component.Content, value/defaultValue, onValueChange`.

Uncontrolled state starts from defaultValue and is managed internally. Controlled state comes from value and must be updated in the matching callback.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

```jsx
import { Accordion } from "@chakra-ui/react"

export function ShippingQuestion() {
  return (
    <Accordion.Root collapsible>
      <Accordion.Item value="shipping">
        <Accordion.ItemTrigger>
          How long does shipping take?
          <Accordion.ItemIndicator />
        </Accordion.ItemTrigger>
        <Accordion.ItemContent>
          <Accordion.ItemBody>Most orders arrive within five business days.</Accordion.ItemBody>
        </Accordion.ItemContent>
      </Accordion.Item>
    </Accordion.Root>
  )
}
```

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Choose compound components when an interaction needs multiple coordinated elements or custom markup. Use a simple component when it already expresses the desired interaction.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Omitting a required part such as a hidden input or item value. Compound APIs make more structure visible, but each documented part still has a role.
- Controlling a widget with value while also expecting defaultValue to control later updates. Use defaultValue for initial state or value plus its change callback for controlled state.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Many Chakra v3 interactive components expose a Root and named parts such as Trigger, Content, and Item. The parts make structure explicit while sharing state and accessibility behavior through their compound context. Remember the API boundary: Component.Root, Component.Trigger, Component.Content, value/defaultValue, onValueChange. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Compose one Accordion item and one Tabs group. Label each part and identify which state is owned internally versus supplied by React.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="003-providers-snippets-and-framework-integration.md">003 - Providers, snippets, and framework integration</a></td>
      <td><a href="../qnas/004-component-anatomy-compound-apis-and-state.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/004-component-anatomy-compound-apis-and-state.md">Chapter example</a></td>
      <td><a href="005-style-props-and-token-aware-styling.md">005 - Style props and token-aware styling</a></td>
    </tr>
  </tbody>
</table>
