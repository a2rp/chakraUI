# 037 - Migration from Chakra UI v2 to v3

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Migration from Chakra UI v2 to v3.
- Identify the main API: `@chakra-ui/codemod upgrade, createSystem, ChakraProvider value, compound components`.
- Choose an appropriate use case: Use the official codemod to accelerate a migration, then review every transform and run type checks and interaction tests.
- Avoid the main implementation risks: Treating codemod completion as proof of a correct migration. Automated transforms cannot decide product semantics or discover every custom wrapper.

## Core idea

Chakra UI v3 changes provider setup, theming, compound component APIs, color mode, and many component props. Migrations should be planned as a sequence of codemod-assisted transformations followed by manual review.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `@chakra-ui/codemod upgrade, createSystem, ChakraProvider value, compound components`.

The v2 and v3 APIs are not interchangeable. Keep examples version-labelled and verify each migrated component against the installed package.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

```jsx
# Preview the codemod changes first
npx @chakra-ui/codemod upgrade --dry

# Update the core packages after reviewing the plan
npm uninstall @chakra-ui/icons @emotion/styled framer-motion
npm install @chakra-ui/react@latest @emotion/react@latest

# Then migrate the provider, theme, and compound component APIs.
# Run the project's typecheck and interaction tests after each group.
```

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Use the official codemod to accelerate a migration, then review every transform and run type checks and interaction tests.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Treating codemod completion as proof of a correct migration. Automated transforms cannot decide product semantics or discover every custom wrapper.
- Combining version migration with unrelated redesign work. Separate mechanical changes from intentional behavior changes to simplify review.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Chakra UI v3 changes provider setup, theming, compound component APIs, color mode, and many component props. Migrations should be planned as a sequence of codemod-assisted transformations followed by manual review. Remember the API boundary: @chakra-ui/codemod upgrade, createSystem, ChakraProvider value, compound components. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Run the codemod in dry mode on a copy, review generated changes, migrate one component family, and record manual follow-ups.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="036-performance-and-styling-architecture.md">036 - Performance and styling architecture</a></td>
      <td><a href="../qnas/037-migration-from-chakra-ui-v2-to-v3.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/037-migration-from-chakra-ui-v2-to-v3.md">Chapter example</a></td>
      <td><a href="038-production-design-system-and-maintenance.md">038 - Production design system and maintenance</a></td>
    </tr>
  </tbody>
</table>
