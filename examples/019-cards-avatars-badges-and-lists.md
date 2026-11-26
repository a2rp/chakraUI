# 019 - Cards, avatars, badges, and lists Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Build a team member card with an avatar fallback, role text, status badge, and a semantic list of skills.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    019-cards-avatars-badges-and-lists.jsx
```

## 019-cards-avatars-badges-and-lists.jsx

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

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 019, inspect the result described below and interact with every trigger, field, or control.

The card groups identity, availability, and skills. If the image is missing, the avatar fallback still communicates the person's name.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Build a team member card with an avatar fallback, role text, status badge, and a semantic list of skills.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Using Badge as the only status signal when meaning depends on color. Include readable text or an icon with an accessible name.
- Rendering images without fallback or useful alt text. Identity should remain understandable when an image fails.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="form-validation-and-react-hook-form.md">018 - Form validation and React Hook Form</a></td>
      <td><a href="../lessons/019-cards-avatars-badges-and-lists.md">Chapter lesson</a></td>
      <td><a href="../qnas/019-cards-avatars-badges-and-lists.md">Chapter Q&amp;A</a></td>
      <td><a href="images-icons-and-file-upload.md">020 - Images, icons, and file upload</a></td>
    </tr>
  </tbody>
</table>
