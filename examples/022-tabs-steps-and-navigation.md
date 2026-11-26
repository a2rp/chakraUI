# 022 - Tabs, steps, and navigation Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Create three settings tabs with stable values and corresponding content. Then sketch a multi-step setup flow and decide which state belongs in the URL.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    022-tabs-steps-and-navigation.jsx
```

## 022-tabs-steps-and-navigation.jsx

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

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 022, inspect the result described below and interact with every trigger, field, or control.

Selecting a trigger displays its matching panel, and the tab set uses one stable value per tab.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Create three settings tabs with stable values and corresponding content. Then sketch a multi-step setup flow and decide which state belongs in the URL.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Using tabs as a substitute for site navigation when each item represents a distinct route or page.
- Leaving tab values duplicated or panel content mismatched. Each trigger value must identify its own panel.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="021-accordion-and-collapsible-content.md">021 - Accordion and collapsible content</a></td>
      <td><a href="../lessons/022-tabs-steps-and-navigation.md">Chapter lesson</a></td>
      <td><a href="../qnas/022-tabs-steps-and-navigation.md">Chapter Q&amp;A</a></td>
      <td><a href="023-menus-popovers-tooltips-and-hover-cards.md">023 - Menus, popovers, tooltips, and hover cards</a></td>
    </tr>
  </tbody>
</table>
