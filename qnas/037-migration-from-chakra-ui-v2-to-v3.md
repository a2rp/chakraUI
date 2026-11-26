# 037 - Migration from Chakra UI v2 to v3 Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind migration from chakra ui v2 to v3?

Chakra UI v3 changes provider setup, theming, compound component APIs, color mode, and many component props. Migrations should be planned as a sequence of codemod-assisted transformations followed by manual review.

## 2. Which API should I learn first?

`@chakra-ui/codemod upgrade, createSystem, ChakraProvider value, compound components`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Use the official codemod to accelerate a migration, then review every transform and run type checks and interaction tests.

## 4. What state and accessibility detail matters most?

The v2 and v3 APIs are not interchangeable. Keep examples version-labelled and verify each migrated component against the installed package. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Treating codemod completion as proof of a correct migration. Automated transforms cannot decide product semantics or discover every custom wrapper.

## 6. How can I practice it?

Run the codemod in dry mode on a copy, review generated changes, migrate one component family, and record manual follow-ups. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. What does the v3 codemod handle?

The official codemod automates many renames, prop changes, imports, and compound-component transformations. Review its report and follow up manually.

## 8. Can a v2 theme be passed as the v3 provider value?

No. Convert theme customization to the v3 system model using createSystem and defineConfig.

## 9. Which v2 color-mode APIs should I expect to change?

Several old Chakra hooks and script components were removed or moved to next-themes-based snippets. Follow the current migration guide rather than copying v2 setup.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="036-performance-and-styling-architecture.md">036 - Performance and styling architecture</a></td>
      <td><a href="../lessons/037-migration-from-chakra-ui-v2-to-v3.md">Chapter lesson</a></td>
      <td><a href="../examples/037-migration-from-chakra-ui-v2-to-v3.md">Chapter example</a></td>
      <td><a href="038-production-design-system-and-maintenance.md">038 - Production design system and maintenance</a></td>
    </tr>
  </tbody>
</table>
