# 031 - Presence, animation, and transitions Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind presence, animation, and transitions?

Presence coordinates whether conditional content is mounted and applies CSS-based enter and exit animation styles. CSS animation keeps visual transitions separate from state and avoids adding animation work to business logic.

## 2. Which API should I learn first?

`Presence, present, animationName, animationStyle, keyframes`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Animate state changes when motion clarifies cause and effect. Respect reduced-motion preferences and keep the interface usable without animation.

## 4. What state and accessibility detail matters most?

The application controls whether content is present; Presence coordinates mount and exit timing. Motion is presentational and should not hide important state changes. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Animating every element because motion is available. Excess movement can distract or harm users with vestibular sensitivities.

## 6. How can I practice it?

Animate a dismissible status panel with a short enter/exit effect. Add a reduced-motion alternative and verify content still works without motion. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. What does Presence manage?

It coordinates conditional mounting and exit transitions so an element can animate out before it is removed.

## 8. Should every state change animate?

No. Motion should clarify change, remain brief, and respect reduced-motion preferences.

## 9. Is Presence a replacement for application state?

No. The application decides whether content is present; Presence handles the transition around that decision.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="composition-chakra-factory-and-aschild.md">030 - Composition, Chakra factory, and asChild</a></td>
      <td><a href="../lessons/031-presence-animation-and-transitions.md">Chapter lesson</a></td>
      <td><a href="../examples/031-presence-animation-and-transitions.md">Chapter example</a></td>
      <td><a href="accessibility-keyboard-interaction-and-rtl.md">032 - Accessibility, keyboard interaction, and RTL</a></td>
    </tr>
  </tbody>
</table>
