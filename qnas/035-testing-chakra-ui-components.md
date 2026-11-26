# 035 - Testing Chakra UI components Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind testing chakra ui components?

Test user-visible behavior rather than Chakra's internal class names. Testing Library queries by role, label, and visible text produce tests that survive styling and markup refactors.

## 2. Which API should I learn first?

`@testing-library/react, user-event, getByRole, ChakraProvider wrapper`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Test key interactions, accessible names, errors, and state transitions. Keep a small number of browser tests for portal, focus, and layout behavior.

## 4. What state and accessibility detail matters most?

Wrap tests with the same provider and custom system used by the app. Portals may render outside the initial container but remain queryable through screen. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Selecting elements by generated Emotion class names. Those are implementation details and can change after a refactor.

## 6. How can I practice it?

Write tests for a labelled form field and a dialog trigger. Assert the dialog opens, Escape closes it, and focus returns appropriately. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. Why query by role?

Role queries align tests with the accessibility tree and verify that users can identify the control by its semantic role and name.

## 8. Should tests assert Chakra class names?

Usually no. Generated classes are styling implementation details. Assert visible output, state, and behavior instead.

## 9. How do I test a portal?

Use screen queries that search the document, then exercise focus, dismissal, and interactions in a browser-level test when environment behavior matters.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="034-nextjs-server-components-and-ssr.md">034 - Next.js, Server Components, and SSR</a></td>
      <td><a href="../lessons/035-testing-chakra-ui-components.md">Chapter lesson</a></td>
      <td><a href="../examples/035-testing-chakra-ui-components.md">Chapter example</a></td>
      <td><a href="036-performance-and-styling-architecture.md">036 - Performance and styling architecture</a></td>
    </tr>
  </tbody>
</table>
