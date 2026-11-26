# 022 - Tabs, steps, and navigation

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Tabs, steps, and navigation.
- Identify the main API: `Tabs.Root, Tabs.List, Tabs.Trigger, Tabs.Content, Steps.Root, Link`.
- Choose an appropriate use case: Use tabs for peer content panels, a step indicator for a sequential workflow, and links for navigation to separate destinations.
- Avoid the main implementation risks: Using tabs as a substitute for site navigation when each item represents a distinct route or page.

## Core idea

Tabs switch among related panels within one page. Steps communicate progress through a sequence. Navigation links move between locations, so these patterns should not be conflated merely because they share a horizontal visual shape.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `Tabs.Root, Tabs.List, Tabs.Trigger, Tabs.Content, Steps.Root, Link`.

Tabs use roving keyboard focus and activate panels according to configured activation behavior. Steps describe progress but do not validate a form automatically.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

```jsx
import { Tabs } from "@chakra-ui/react"

export function SettingsTabs() {
  return (
    <Tabs.Root defaultValue="profile">
      <Tabs.List>
        <Tabs.Trigger value="profile">Profile</Tabs.Trigger>
        <Tabs.Trigger value="security">Security</Tabs.Trigger>
      </Tabs.List>
      <Tabs.Content value="profile">Update your profile details.</Tabs.Content>
      <Tabs.Content value="security">Manage sign-in preferences.</Tabs.Content>
    </Tabs.Root>
  )
}
```

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Use tabs for peer content panels, a step indicator for a sequential workflow, and links for navigation to separate destinations.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Using tabs as a substitute for site navigation when each item represents a distinct route or page.
- Leaving tab values duplicated or panel content mismatched. Each trigger value must identify its own panel.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Tabs switch among related panels within one page. Steps communicate progress through a sequence. Navigation links move between locations, so these patterns should not be conflated merely because they share a horizontal visual shape. Remember the API boundary: Tabs.Root, Tabs.List, Tabs.Trigger, Tabs.Content, Steps.Root, Link. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Create three settings tabs with stable values and corresponding content. Then sketch a multi-step setup flow and decide which state belongs in the URL.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="accordion-and-collapsible-content.md">021 - Accordion and collapsible content</a></td>
      <td><a href="../qnas/022-tabs-steps-and-navigation.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/022-tabs-steps-and-navigation.md">Chapter example</a></td>
      <td><a href="menus-popovers-tooltips-and-hover-cards.md">023 - Menus, popovers, tooltips, and hover cards</a></td>
    </tr>
  </tbody>
</table>
