# 032 - Accessibility, keyboard interaction, and RTL Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind accessibility, keyboard interaction, and rtl?

Accessible Chakra interfaces combine semantic elements, visible labels, sufficient contrast, keyboard support, and logical focus. Direction-aware layout props and locale providers help interfaces adapt to right-to-left languages.

## 2. Which API should I learn first?

`Field labels, aria-label, _focusVisible, dir, LocaleProvider, logical CSS properties`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Prefer native semantics and component defaults, then test keyboard and assistive technology flows. Use logical properties for layouts that must support both directions.

## 4. What state and accessibility detail matters most?

Chakra provides patterns but cannot infer the correct accessible name, reading order, contrast, or translation. Those remain product and content decisions. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Removing focus outlines without a replacement. Keyboard users need to see which control is active.

## 6. How can I practice it?

Audit one form and one menu using keyboard only. Add a visible focus treatment, then switch the container direction and check reading and layout order. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. Does an accessible component remove the need for testing?

No. Test names, keyboard behavior, focus, contrast, zoom, and real task completion with the app's content and surrounding layout.

## 8. Why use logical properties?

Properties such as paddingInlineStart follow writing direction, so they adapt to RTL without separate left/right overrides.

## 9. Should aria-label always be added?

No. Prefer a visible label when possible. Add aria-label when a control has no visible text name, such as a clearly identified icon-only action.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="031-presence-animation-and-transitions.md">031 - Presence, animation, and transitions</a></td>
      <td><a href="../lessons/032-accessibility-keyboard-interaction-and-rtl.md">Chapter lesson</a></td>
      <td><a href="../examples/032-accessibility-keyboard-interaction-and-rtl.md">Chapter example</a></td>
      <td><a href="033-typescript-and-type-generation.md">033 - TypeScript and type generation</a></td>
    </tr>
  </tbody>
</table>
