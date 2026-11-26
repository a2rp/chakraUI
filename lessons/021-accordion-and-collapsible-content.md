# 021 - Accordion and collapsible content

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Accordion and collapsible content.
- Identify the main API: `Accordion.Root, Accordion.Item, ItemTrigger, ItemContent, Collapsible.Root, open`.
- Choose an appropriate use case: Use Accordion for a set of related questions or sections; use Collapsible for one optional region in a page.
- Avoid the main implementation risks: Using an accordion to hide essential content users need to compare at once. Consider showing content directly when scanning matters.

## Core idea

Accordion groups related expandable sections, while Collapsible controls one disclosure region. Compound parts expose triggers and content while preserving expanded state and keyboard behavior.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `Accordion.Root, Accordion.Item, ItemTrigger, ItemContent, Collapsible.Root, open`.

Accordion state can be controlled or uncontrolled. The trigger communicates expanded state and activates the associated content with keyboard input.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

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

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Use Accordion for a set of related questions or sections; use Collapsible for one optional region in a page.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Using an accordion to hide essential content users need to compare at once. Consider showing content directly when scanning matters.
- Providing trigger text that is vague or omitting a visible expanded-state affordance.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Accordion groups related expandable sections, while Collapsible controls one disclosure region. Compound parts expose triggers and content while preserving expanded state and keyboard behavior. Remember the API boundary: Accordion.Root, Accordion.Item, ItemTrigger, ItemContent, Collapsible.Root, open. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Create a frequently asked questions section with stable item values. Decide whether multiple items can remain open and test keyboard toggling.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="images-icons-and-file-upload.md">020 - Images, icons, and file upload</a></td>
      <td><a href="../qnas/021-accordion-and-collapsible-content.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/021-accordion-and-collapsible-content.md">Chapter example</a></td>
      <td><a href="tabs-steps-and-navigation.md">022 - Tabs, steps, and navigation</a></td>
    </tr>
  </tbody>
</table>
