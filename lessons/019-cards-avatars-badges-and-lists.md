# 019 - Cards, avatars, badges, and lists

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Cards, avatars, badges, and lists.
- Identify the main API: `Card.Root, Card.Header, Card.Body, Avatar.Root, Avatar.Fallback, Badge, List`.
- Choose an appropriate use case: Use a Card for a related content unit, Avatar for a person or entity, Badge for compact status, and semantic lists for repeated items.
- Avoid the main implementation risks: Using Badge as the only status signal when meaning depends on color. Include readable text or an icon with an accessible name.

## Core idea

Content components group related information and communicate identity or status. Card, Avatar, Badge, and List expose composable parts so layout and semantics remain explicit.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `Card.Root, Card.Header, Card.Body, Avatar.Root, Avatar.Fallback, Badge, List`.

These components primarily structure content. Choose semantic headings and list elements based on the document meaning rather than the visual appearance.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

```jsx
import { Avatar, Badge, Card, Heading, List, Text } from "@chakra-ui/react"

export function MemberCard() {
  return (
    <Card.Root maxW="sm">
      <Card.Header>
        <Avatar.Root>
          <Avatar.Fallback name="Mina Chen" />
        </Avatar.Root>
        <Heading size="md" mt="3">Mina Chen</Heading>
      </Card.Header>
      <Card.Body>
        <Badge colorPalette="green">Available</Badge>
        <Text mt="3">Frontend engineer</Text>
        <List.Root mt="3">
          <List.Item>Design systems</List.Item>
          <List.Item>Accessibility</List.Item>
        </List.Root>
      </Card.Body>
    </Card.Root>
  )
}
```

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Use a Card for a related content unit, Avatar for a person or entity, Badge for compact status, and semantic lists for repeated items.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Using Badge as the only status signal when meaning depends on color. Include readable text or an icon with an accessible name.
- Rendering images without fallback or useful alt text. Identity should remain understandable when an image fails.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Content components group related information and communicate identity or status. Card, Avatar, Badge, and List expose composable parts so layout and semantics remain explicit. Remember the API boundary: Card.Root, Card.Header, Card.Body, Avatar.Root, Avatar.Fallback, Badge, List. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Build a team member card with an avatar fallback, role text, status badge, and a semantic list of skills.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="018-form-validation-and-react-hook-form.md">018 - Form validation and React Hook Form</a></td>
      <td><a href="../qnas/019-cards-avatars-badges-and-lists.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/019-cards-avatars-badges-and-lists.md">Chapter example</a></td>
      <td><a href="020-images-icons-and-file-upload.md">020 - Images, icons, and file upload</a></td>
    </tr>
  </tbody>
</table>
