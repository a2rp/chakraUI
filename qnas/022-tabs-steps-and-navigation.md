# 022 - Tabs, steps, and navigation Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind tabs, steps, and navigation?

Tabs switch among related panels within one page. Steps communicate progress through a sequence. Navigation links move between locations, so these patterns should not be conflated merely because they share a horizontal visual shape.

## 2. Which API should I learn first?

`Tabs.Root, Tabs.List, Tabs.Trigger, Tabs.Content, Steps.Root, Link`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Use tabs for peer content panels, a step indicator for a sequential workflow, and links for navigation to separate destinations.

## 4. What state and accessibility detail matters most?

Tabs use roving keyboard focus and activate panels according to configured activation behavior. Steps describe progress but do not validate a form automatically. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Using tabs as a substitute for site navigation when each item represents a distinct route or page.

## 6. How can I practice it?

Create three settings tabs with stable values and corresponding content. Then sketch a multi-step setup flow and decide which state belongs in the URL. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. Should tabs change the URL?

For in-page peer panels, local tab state is enough. If panels are navigable destinations or should be shareable, use links or configure router navigation intentionally.

## 8. How should tab values be chosen?

Use stable unique strings that match each panel. Avoid array indexes when panels can be reordered.

## 9. Do Steps validate the current form step?

No. Steps present workflow progress. The application must validate data and decide whether users may proceed.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="accordion-and-collapsible-content.md">021 - Accordion and collapsible content</a></td>
      <td><a href="../lessons/022-tabs-steps-and-navigation.md">Chapter lesson</a></td>
      <td><a href="../examples/022-tabs-steps-and-navigation.md">Chapter example</a></td>
      <td><a href="menus-popovers-tooltips-and-hover-cards.md">023 - Menus, popovers, tooltips, and hover cards</a></td>
    </tr>
  </tbody>
</table>
