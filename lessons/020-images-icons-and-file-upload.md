# 020 - Images, icons, and file upload

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Images, icons, and file upload.
- Identify the main API: `Image, Icon, FileUpload, lucide-react or react-icons, onError, accept`.
- Choose an appropriate use case: Use image alt text according to purpose, decorative icons hidden from assistive technology, and file input constraints that match server validation.
- Avoid the main implementation risks: Assuming Chakra includes every icon set. Install and import an icon library explicitly, then label icon-only controls.

## Core idea

Media and file controls combine browser APIs with Chakra presentation. Image displays native image content, icons are usually supplied by a separate icon library, and FileUpload provides an accessible composed file-selection experience.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `Image, Icon, FileUpload, lucide-react or react-icons, onError, accept`.

The browser owns file selection and image loading. Chakra can style and compose these controls, but security validation and persistent storage belong to the application/server.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

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

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Use image alt text according to purpose, decorative icons hidden from assistive technology, and file input constraints that match server validation.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Assuming Chakra includes every icon set. Install and import an icon library explicitly, then label icon-only controls.
- Treating accept or client-side file checks as security. The server must validate file type, size, and contents.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Media and file controls combine browser APIs with Chakra presentation. Image displays native image content, icons are usually supplied by a separate icon library, and FileUpload provides an accessible composed file-selection experience. Remember the API boundary: Image, Icon, FileUpload, lucide-react or react-icons, onError, accept. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Build a file picker that explains accepted formats, displays the selected filename, and retains a useful error if the image preview fails.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="cards-avatars-badges-and-lists.md">019 - Cards, avatars, badges, and lists</a></td>
      <td><a href="../qnas/020-images-icons-and-file-upload.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/020-images-icons-and-file-upload.md">Chapter example</a></td>
      <td><a href="accordion-and-collapsible-content.md">021 - Accordion and collapsible content</a></td>
    </tr>
  </tbody>
</table>
