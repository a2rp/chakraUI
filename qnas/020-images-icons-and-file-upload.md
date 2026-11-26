# 020 - Images, icons, and file upload Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind images, icons, and file upload?

Media and file controls combine browser APIs with Chakra presentation. Image displays native image content, icons are usually supplied by a separate icon library, and FileUpload provides an accessible composed file-selection experience.

## 2. Which API should I learn first?

`Image, Icon, FileUpload, lucide-react or react-icons, onError, accept`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Use image alt text according to purpose, decorative icons hidden from assistive technology, and file input constraints that match server validation.

## 4. What state and accessibility detail matters most?

The browser owns file selection and image loading. Chakra can style and compose these controls, but security validation and persistent storage belong to the application/server. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Assuming Chakra includes every icon set. Install and import an icon library explicitly, then label icon-only controls.

## 6. How can I practice it?

Build a file picker that explains accepted formats, displays the selected filename, and retains a useful error if the image preview fails. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. Does Chakra UI include an icon pack?

No. Use a chosen icon package such as lucide-react or react-icons, and wrap icons with Chakra Icon or an accessible button as needed.

## 8. Can accept on a file input validate security?

No. It guides the picker and improves UX. The server must independently validate type, size, and file contents.

## 9. How do I choose image alt text?

Describe the image's purpose when informative. Use empty alt text for purely decorative images so assistive technology can skip them.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="cards-avatars-badges-and-lists.md">019 - Cards, avatars, badges, and lists</a></td>
      <td><a href="../lessons/020-images-icons-and-file-upload.md">Chapter lesson</a></td>
      <td><a href="../examples/020-images-icons-and-file-upload.md">Chapter example</a></td>
      <td><a href="accordion-and-collapsible-content.md">021 - Accordion and collapsible content</a></td>
    </tr>
  </tbody>
</table>
