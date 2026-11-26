# 019 - Cards, avatars, badges, and lists Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind cards, avatars, badges, and lists?

Content components group related information and communicate identity or status. Card, Avatar, Badge, and List expose composable parts so layout and semantics remain explicit.

## 2. Which API should I learn first?

`Card.Root, Card.Header, Card.Body, Avatar.Root, Avatar.Fallback, Badge, List`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Use a Card for a related content unit, Avatar for a person or entity, Badge for compact status, and semantic lists for repeated items.

## 4. What state and accessibility detail matters most?

These components primarily structure content. Choose semantic headings and list elements based on the document meaning rather than the visual appearance. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Using Badge as the only status signal when meaning depends on color. Include readable text or an icon with an accessible name.

## 6. How can I practice it?

Build a team member card with an avatar fallback, role text, status badge, and a semantic list of skills. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. Should Card.Root be interactive?

Only make the whole card interactive when the entire content has one clear action and the resulting link or button semantics remain valid.

## 8. What belongs in Avatar.Fallback?

Provide initials or a name-derived fallback so identity remains visible when an image is unavailable.

## 9. Can a Badge communicate status by color alone?

Avoid that. Include status text so the meaning remains available without relying only on color perception.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="018-form-validation-and-react-hook-form.md">018 - Form validation and React Hook Form</a></td>
      <td><a href="../lessons/019-cards-avatars-badges-and-lists.md">Chapter lesson</a></td>
      <td><a href="../examples/019-cards-avatars-badges-and-lists.md">Chapter example</a></td>
      <td><a href="020-images-icons-and-file-upload.md">020 - Images, icons, and file upload</a></td>
    </tr>
  </tbody>
</table>
