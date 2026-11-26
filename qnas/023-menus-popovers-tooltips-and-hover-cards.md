# 023 - Menus, popovers, tooltips, and hover cards Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind menus, popovers, tooltips, and hover cards?

Floating components position content near a trigger but communicate different semantics. Menus expose commands, popovers host interactive content, tooltips offer short descriptions, and hover cards reveal supplementary previews.

## 2. Which API should I learn first?

`Menu.Root, Popover.Root, Tooltip.Root, HoverCard.Root, Portal, positioning`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Choose the pattern from the content's task and interaction, not from its visual shape. Use a tooltip only for brief noninteractive help.

## 4. What state and accessibility detail matters most?

Floating components coordinate focus, dismissal, and positioning. Portals change DOM placement but should not break accessible naming or focus management. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Putting buttons or form controls inside a tooltip. Use a popover or dialog for interactive content.

## 6. How can I practice it?

Build an actions menu with descriptive item labels and a separate help tooltip. Test opening, Escape dismissal, and keyboard traversal. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. Tooltip or popover for extra content?

Use a tooltip for short, noninteractive descriptive help. Use a popover when content contains controls, longer content, or user interaction.

## 8. What belongs in a menu?

Commands or actions associated with a trigger. Use menu item semantics and keep labels clear about the action.

## 9. Why can a portal affect overlays?

Portals render outside the local DOM subtree to escape clipping and stacking contexts. Ensure focus and theme context remain correct.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="022-tabs-steps-and-navigation.md">022 - Tabs, steps, and navigation</a></td>
      <td><a href="../lessons/023-menus-popovers-tooltips-and-hover-cards.md">Chapter lesson</a></td>
      <td><a href="../examples/023-menus-popovers-tooltips-and-hover-cards.md">Chapter example</a></td>
      <td><a href="024-dialogs-drawers-and-alert-dialogs.md">024 - Dialogs, drawers, and alert dialogs</a></td>
    </tr>
  </tbody>
</table>
