# 030 - Composition, Chakra factory, and asChild Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind composition, chakra factory, and aschild?

Chakra composition lets applications style custom elements and compose Chakra triggers with router links. The asChild pattern merges behavior and props with a child element when its semantics are appropriate.

## 2. Which API should I learn first?

`chakra factory, asChild, Link, polymorphism, component props`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Use asChild to preserve the real element semantics of a router link or custom button. Use the chakra factory for a custom element that needs the system styling API.

## 4. What state and accessibility detail matters most?

Composition merges props and event handlers. The underlying child still determines native semantics, focusability, and whether a ref can reach the DOM. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Wrapping an interactive element inside another interactive element. Preserve one focusable control and one coherent semantic role.

## 6. How can I practice it?

Compose a Chakra-styled router link and inspect its rendered HTML, accessible name, focus state, and navigation behavior. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. What problem does asChild solve?

It lets a component compose its behavior and styles onto a child element, preserving the child's native or router-specific semantics.

## 8. When should I use the chakra factory?

Use it to create a custom component that participates in Chakra's styling system. Avoid it when a standard Chakra component already expresses the pattern.

## 9. What must a custom child support?

It must accept and forward relevant props, event handlers, and refs to the rendered element so composition and focus behavior work.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="slot-recipes-and-multi-part-components.md">029 - Slot recipes and multi-part components</a></td>
      <td><a href="../lessons/030-composition-chakra-factory-and-aschild.md">Chapter lesson</a></td>
      <td><a href="../examples/030-composition-chakra-factory-and-aschild.md">Chapter example</a></td>
      <td><a href="presence-animation-and-transitions.md">031 - Presence, animation, and transitions</a></td>
    </tr>
  </tbody>
</table>
