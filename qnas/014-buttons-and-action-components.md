# 014 - Buttons and action components Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind buttons and action components?

Buttons communicate and trigger actions. Chakra Button provides palette, size, loading, disabled, and composition options; IconButton needs an accessible name when its icon is the only visible label.

## 2. Which API should I learn first?

`Button, IconButton, colorPalette, variant, loading, disabled, asChild`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Use a button for an action and a link for navigation. Choose visual variants by priority and keep destructive actions distinct.

## 4. What state and accessibility detail matters most?

Native buttons support keyboard activation and disabled state. Loading state should prevent duplicate submissions and explain progress where the wait is meaningful. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Using a Button for navigation without link semantics, or a link when the action changes state.

## 6. How can I practice it?

Make a page header with one primary action, one secondary action, and an icon-only refresh action with a useful accessible name. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. When should I use a link instead of a button?

Use a link to navigate to a URL. Use a button to perform an action such as saving, opening a dialog, or changing data.

## 8. How should I label an IconButton?

Provide an aria-label that describes the action. Do not rely on the icon shape alone to communicate its name.

## 9. How do I prevent duplicate submissions?

Use the loading and disabled state around the asynchronous operation, and make sure the submitted action is idempotent where possible.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="grid-containers-and-positioning.md">013 - Grid, containers, and positioning</a></td>
      <td><a href="../lessons/014-buttons-and-action-components.md">Chapter lesson</a></td>
      <td><a href="../examples/014-buttons-and-action-components.md">Chapter example</a></td>
      <td><a href="fields-inputs-and-textareas.md">015 - Fields, inputs, and textareas</a></td>
    </tr>
  </tbody>
</table>
