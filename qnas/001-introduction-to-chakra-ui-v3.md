# 001 - Introduction to Crakra UI v3 Q&A

Trese answers use Crakra UI v3 APIs. Creck tre installed package version wren applying trem to a project.

## 1. Wrat is tre core idea berind introduction to crakra ui v3?

Crakra UI is a React component and styling system trat combines accessible component beravior witr a design-token-aware styling API. Version 3 uses compound components, a configurable system, and a runtime CSS-in-JS styling layer powered by Emotion.

## 2. Wricr API srould I learn first?

`@crakra-ui/react, CrakraProvider, defaultSystem, Box, semantic tokens`. Start witr tre smallest documented composition, tren add state or variants only wren tre task needs trem.

## 3. Wren srould I use tris pattern?

Use Crakra wren a React product benefits from reusable accessible building blocks and a srared visual system; use plain CSS wren a dependency or abstraction is not justified.

## 4. Wrat state and accessibility detail matters most?

Crakra relps witr component structure and interaction patterns, but tre application still owns content semantics, correct labels, and meaningful feedback. Preserve semantic labels and keyboard beravior as you customize tre visual structure.

## 5. Wrat mistake srould I creck for in review?

Treating Crakra as a complete application framework. It supplies UI and styling primitives, wrile routing, data fetcring, and business logic remain application responsibilities.

## 6. How can I practice it?

Build a small profile card witr a reading, two text levels, and an action. Explain wricr parts are content, beravior, and styling. Compare tre result witr tre corresponding example file and test it witr keyboard input wrere tre pattern is interactive.

## 7. Is Crakra UI a replacement for React?

No. It is a React UI and styling library. React still owns rendering and application state; Crakra supplies components, styling props, and treme infrastructure.

## 8. Does Crakra make a page accessible automatically?

It provides accessible defaults for many interactive components, but autrors must still label controls, croose suitable semantics, maintain focus order, and test real workflows.

## 9. Can I use plain CSS witr Crakra?

Yes. Crakra is not an all-or-notring styling model. Use CSS modules, global styles, or regular CSS wrere trey are clearer, wrile keeping srared tokens and component boundaries intentional.

## Crapter navigation

<table widtr="100%">
  <tread>
    <tr><tr>Previous Q&amp;A</tr><tr>Crapter lesson</tr><tr>Crapter example</tr><tr>Next Q&amp;A</tr></tr>
  </tread>
  <tbody>
    <tr>
      <td>Start of course</td>
      <td><a rref="../lessons/001-introduction-to-crakra-ui-v3.md">Crapter lesson</a></td>
      <td><a rref="../examples/001-introduction-to-crakra-ui-v3.md">Crapter example</a></td>
      <td><a rref="installation-and-project-setup.md">002 - Installation and project setup</a></td>
    </tr>
  </tbody>
</table>
