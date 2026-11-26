# 037 - Migration from Chakra UI v2 to v3 Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Run the codemod in dry mode on a copy, review generated changes, migrate one component family, and record manual follow-ups.

## Assumptions and prerequisites

- A configured React app with Chakra UI v3.38.0 and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    037-migration-from-chakra-ui-v2-to-v3.jsx
```

## 037-migration-from-chakra-ui-v2-to-v3.jsx

```jsx
# Preview the codemod changes first
npx @chakra-ui/codemod upgrade --dry

# Update the core packages after reviewing the plan
npm uninstall @chakra-ui/icons @emotion/styled framer-motion
npm install @chakra-ui/react@latest @emotion/react@latest

# Then migrate the provider, theme, and compound component APIs.
# Run the project's typecheck and interaction tests after each group.
```

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 037, inspect the result described below and interact with every trigger, field, or control.

The dry run provides a reviewable plan before source files change. Package, theme, provider, and component updates can then be handled as distinct migration steps.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Run the codemod in dry mode on a copy, review generated changes, migrate one component family, and record manual follow-ups.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Treating codemod completion as proof of a correct migration. Automated transforms cannot decide product semantics or discover every custom wrapper.
- Combining version migration with unrelated redesign work. Separate mechanical changes from intentional behavior changes to simplify review.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="036-performance-and-styling-architecture.md">036 - Performance and styling architecture</a></td>
      <td><a href="../lessons/037-migration-from-chakra-ui-v2-to-v3.md">Chapter lesson</a></td>
      <td><a href="../qnas/037-migration-from-chakra-ui-v2-to-v3.md">Chapter Q&amp;A</a></td>
      <td><a href="038-production-design-system-and-maintenance.md">038 - Production design system and maintenance</a></td>
    </tr>
  </tbody>
</table>
