# 020 - Images, icons, and file upload Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Build a file picker that explains accepted formats, displays the selected filename, and retains a useful error if the image preview fails.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    020-images-icons-and-file-upload.jsx
```

## 020-images-icons-and-file-upload.jsx

```jsx
import { useState } from "react"
import { Button, Image, Stack, Text } from "@chakra-ui/react"

export function LogoPreview() {
  const [src, setSrc] = useState("/brand-mark.png")
  return (
    <Stack gap="3">
      <Image
        src={src}
        alt="Company logo"
        maxW="12rem"
        onError={() => setSrc("/fallback-logo.png")}
      />
      <Text color="fg.muted">Previewing the selected logo.</Text>
      <Button variant="outline" onClick={() => setSrc("/brand-mark.png")}>
        Reset preview
      </Button>
    </Stack>
  )
}
```

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 020, inspect the result described below and interact with every trigger, field, or control.

The image has meaningful alt text and falls back when loading fails. In production, the selected file must also be validated and uploaded safely.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Build a file picker that explains accepted formats, displays the selected filename, and retains a useful error if the image preview fails.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Assuming Chakra includes every icon set. Install and import an icon library explicitly, then label icon-only controls.
- Treating accept or client-side file checks as security. The server must validate file type, size, and contents.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="cards-avatars-badges-and-lists.md">019 - Cards, avatars, badges, and lists</a></td>
      <td><a href="../lessons/020-images-icons-and-file-upload.md">Chapter lesson</a></td>
      <td><a href="../qnas/020-images-icons-and-file-upload.md">Chapter Q&amp;A</a></td>
      <td><a href="accordion-and-collapsible-content.md">021 - Accordion and collapsible content</a></td>
    </tr>
  </tbody>
</table>
