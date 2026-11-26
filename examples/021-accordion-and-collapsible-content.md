# 021 - Accordion and collapsible content Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Create a frequently asked questions section with stable item values. Decide whether multiple items can remain open and test keyboard toggling.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    021-accordion-and-collapsible-content.jsx
```

## 021-accordion-and-collapsible-content.jsx

```jsx
import { Accordion } from "@chakra-ui/react"

export function Questions() {
  return (
    <Accordion.Root multiple collapsible>
      <Accordion.Item value="billing">
        <Accordion.ItemTrigger>
          When will I be charged?
          <Accordion.ItemIndicator />
        </Accordion.ItemTrigger>
        <Accordion.ItemContent>
          <Accordion.ItemBody>Your plan renews on the date shown in billing settings.</Accordion.ItemBody>
        </Accordion.ItemContent>
      </Accordion.Item>
      <Accordion.Item value="cancel">
        <Accordion.ItemTrigger>
          Can I cancel at any time?
          <Accordion.ItemIndicator />
        </Accordion.ItemTrigger>
        <Accordion.ItemContent>
          <Accordion.ItemBody>Yes. Access continues through the paid period.</Accordion.ItemBody>
        </Accordion.ItemContent>
      </Accordion.Item>
    </Accordion.Root>
  )
}
```

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 021, inspect the result described below and interact with every trigger, field, or control.

Each stable item value identifies its content, and multiple sections may remain open under the selected policy.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Create a frequently asked questions section with stable item values. Decide whether multiple items can remain open and test keyboard toggling.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Using an accordion to hide essential content users need to compare at once. Consider showing content directly when scanning matters.
- Providing trigger text that is vague or omitting a visible expanded-state affordance.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="images-icons-and-file-upload.md">020 - Images, icons, and file upload</a></td>
      <td><a href="../lessons/021-accordion-and-collapsible-content.md">Chapter lesson</a></td>
      <td><a href="../qnas/021-accordion-and-collapsible-content.md">Chapter Q&amp;A</a></td>
      <td><a href="tabs-steps-and-navigation.md">022 - Tabs, steps, and navigation</a></td>
    </tr>
  </tbody>
</table>
