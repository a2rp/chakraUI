# 023 - Menus, popovers, tooltips, and hover cards

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Menus, popovers, tooltips, and hover cards.
- Identify the main API: `Menu.Root, Popover.Root, Tooltip.Root, HoverCard.Root, Portal, positioning`.
- Choose an appropriate use case: Choose the pattern from the content's task and interaction, not from its visual shape. Use a tooltip only for brief noninteractive help.
- Avoid the main implementation risks: Putting buttons or form controls inside a tooltip. Use a popover or dialog for interactive content.

## Core idea

Floating components position content near a trigger but communicate different semantics. Menus expose commands, popovers host interactive content, tooltips offer short descriptions, and hover cards reveal supplementary previews.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `Menu.Root, Popover.Root, Tooltip.Root, HoverCard.Root, Portal, positioning`.

Floating components coordinate focus, dismissal, and positioning. Portals change DOM placement but should not break accessible naming or focus management.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

```jsx
import { Menu } from "@chakra-ui/react"

export function ProjectActions() {
  return (
    <Menu.Root>
      <Menu.Trigger>Project actions</Menu.Trigger>
      <Menu.Positioner>
        <Menu.Content>
          <Menu.Item value="rename">Rename project</Menu.Item>
          <Menu.Item value="archive">Archive project</Menu.Item>
        </Menu.Content>
      </Menu.Positioner>
    </Menu.Root>
  )
}
```

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Choose the pattern from the content's task and interaction, not from its visual shape. Use a tooltip only for brief noninteractive help.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Putting buttons or form controls inside a tooltip. Use a popover or dialog for interactive content.
- Making a menu item navigate without link semantics, or failing to support keyboard navigation and dismissal.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Floating components position content near a trigger but communicate different semantics. Menus expose commands, popovers host interactive content, tooltips offer short descriptions, and hover cards reveal supplementary previews. Remember the API boundary: Menu.Root, Popover.Root, Tooltip.Root, HoverCard.Root, Portal, positioning. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Build an actions menu with descriptive item labels and a separate help tooltip. Test opening, Escape dismissal, and keyboard traversal.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="tabs-steps-and-navigation.md">022 - Tabs, steps, and navigation</a></td>
      <td><a href="../qnas/023-menus-popovers-tooltips-and-hover-cards.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/023-menus-popovers-tooltips-and-hover-cards.md">Chapter example</a></td>
      <td><a href="dialogs-drawers-and-alert-dialogs.md">024 - Dialogs, drawers, and alert dialogs</a></td>
    </tr>
  </tbody>
</table>
