# 029 - Slot recipes and multi-part components Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind slot recipes and multi-part components?

A slot recipe styles several named parts of one component, such as a field root, label, and input. It keeps related part styles coordinated while preserving the component's compound structure.

## 2. Which API should I learn first?

`defineSlotRecipe, slots, base, variants, useSlotRecipe, @chakra-ui/react/recipes`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Use slot recipes when several parts share variants or state. Use a single-part recipe when only one rendered element needs a style variant.

## 4. What state and accessibility detail matters most?

The slot recipe returns coordinated styles for each named part. Keep state and accessibility behavior in the component implementation rather than duplicating it in CSS. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Styling a slot that the component never renders or using a mismatched slot name. Keep recipe slots aligned with actual component anatomy.

## 6. How can I practice it?

Create a compact Field slot recipe with root, label, and helperText styles. Apply its styles to a controlled field and regenerate types. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. When is a slot recipe needed?

Use one when a component has multiple related parts whose styles vary together. A regular recipe is simpler for one styled root.

## 8. Do slots create DOM elements?

No. Slot names are style targets; the component composition still determines which elements render and how they behave.

## 9. Why use exact slot names?

The recipe and component must agree on slot identifiers. A mismatch means the intended style is never applied.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="recipes-and-reusable-component-variants.md">028 - Recipes and reusable component variants</a></td>
      <td><a href="../lessons/029-slot-recipes-and-multi-part-components.md">Chapter lesson</a></td>
      <td><a href="../examples/029-slot-recipes-and-multi-part-components.md">Chapter example</a></td>
      <td><a href="composition-chakra-factory-and-aschild.md">030 - Composition, Chakra factory, and asChild</a></td>
    </tr>
  </tbody>
</table>
