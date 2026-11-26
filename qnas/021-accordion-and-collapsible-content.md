# 021 - Accordion and collapsible content Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind accordion and collapsible content?

Accordion groups related expandable sections, while Collapsible controls one disclosure region. Compound parts expose triggers and content while preserving expanded state and keyboard behavior.

## 2. Which API should I learn first?

`Accordion.Root, Accordion.Item, ItemTrigger, ItemContent, Collapsible.Root, open`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Use Accordion for a set of related questions or sections; use Collapsible for one optional region in a page.

## 4. What state and accessibility detail matters most?

Accordion state can be controlled or uncontrolled. The trigger communicates expanded state and activates the associated content with keyboard input. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Using an accordion to hide essential content users need to compare at once. Consider showing content directly when scanning matters.

## 6. How can I practice it?

Create a frequently asked questions section with stable item values. Decide whether multiple items can remain open and test keyboard toggling. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. Accordion or Collapsible?

Use Accordion when several related sections share one disclosure pattern. Use Collapsible for one independently opened region.

## 8. What do multiple and collapsible mean?

multiple allows several items to remain open; collapsible allows the currently open item to close. Choose both behaviors intentionally.

## 9. Should essential information be hidden in an accordion?

If users need to compare it or it is critical for task completion, keep it visible or provide a clear way to discover it.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="images-icons-and-file-upload.md">020 - Images, icons, and file upload</a></td>
      <td><a href="../lessons/021-accordion-and-collapsible-content.md">Chapter lesson</a></td>
      <td><a href="../examples/021-accordion-and-collapsible-content.md">Chapter example</a></td>
      <td><a href="tabs-steps-and-navigation.md">022 - Tabs, steps, and navigation</a></td>
    </tr>
  </tbody>
</table>
