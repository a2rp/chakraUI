# 033 - TypeScript and type generation Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind typescript and type generation?

Chakra's TypeScript definitions provide component props and token-aware types. When a custom system introduces new tokens or recipes, CLI type generation can synchronize the app's generated types with that configuration.

## 2. Which API should I learn first?

`@chakra-ui/react types, RecipeVariantProps, strictTokens, @chakra-ui/cli typegen`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Use TypeScript to catch invalid props and model component contracts. Enable strictTokens when the team is ready to use the configured system consistently.

## 4. What state and accessibility detail matters most?

Types improve development-time feedback but do not validate runtime data or guarantee that a browser renders the intended result. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Changing theme tokens but not regenerating types. The editor can otherwise report missing values or offer stale completions.

## 6. How can I practice it?

Add a custom token and a recipe variant, run typegen, then use the generated variant type in a reusable component prop. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. What does typegen do?

It generates TypeScript definitions from the configured system so custom tokens and recipes can participate in editor suggestions and type checking.

## 8. When should I enable strictTokens?

Enable it when the design system is established and the team is ready to reject unregistered values in token-aware style props.

## 9. Do TypeScript types validate API responses?

No. Validate external data at runtime before treating it as a typed application value.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="accessibility-keyboard-interaction-and-rtl.md">032 - Accessibility, keyboard interaction, and RTL</a></td>
      <td><a href="../lessons/033-typescript-and-type-generation.md">Chapter lesson</a></td>
      <td><a href="../examples/033-typescript-and-type-generation.md">Chapter example</a></td>
      <td><a href="nextjs-server-components-and-ssr.md">034 - Next.js, Server Components, and SSR</a></td>
    </tr>
  </tbody>
</table>
