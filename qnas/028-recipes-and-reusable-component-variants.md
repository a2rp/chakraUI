# 028 - Recipes and reusable component variants Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind recipes and reusable component variants?

A recipe defines base styles and variants for a single-part component. It can standardize choices such as size, visual variant, and state without repeating style props across every consumer.

## 2. Which API should I learn first?

`defineRecipe, recipe, variants, compoundVariants, defaultVariants, RecipeVariantProps`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Create a recipe when repeated style combinations form a stable component API. Keep one-off styling local rather than promoting every variation into the design system.

## 4. What state and accessibility detail matters most?

Recipe variants select styles, not business logic. The component still owns semantic markup, behavior, and accessible labels. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Creating a new variant for every isolated page need. Too many variants make the component API hard to understand.

## 6. How can I practice it?

Define a Notice recipe with tone and size variants, then use typegen and apply it to two instances. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. Recipe or component?

A recipe owns reusable style variants. A component owns behavior, markup, and how those variants are applied.

## 8. What is a compound variant?

It applies styles when a combination of variant values is active, such as a selected size and tone that need a coordinated adjustment.

## 9. How should recipe types stay current?

Run Chakra CLI typegen after changing the system or recipe definitions so generated token and variant types match the configuration.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="date-time-color-pickers-sliders-and-rating.md">027 - Date, time, color pickers, sliders, and rating</a></td>
      <td><a href="../lessons/028-recipes-and-reusable-component-variants.md">Chapter lesson</a></td>
      <td><a href="../examples/028-recipes-and-reusable-component-variants.md">Chapter example</a></td>
      <td><a href="slot-recipes-and-multi-part-components.md">029 - Slot recipes and multi-part components</a></td>
    </tr>
  </tbody>
</table>
