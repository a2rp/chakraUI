# 034 - Next.js, Server Components, and SSR Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind next.js, server components, and ssr?

Chakra UI v3 supports server-rendered React and Next.js App Router patterns, but interactive Chakra components depend on client-side React capabilities. Keep data and static composition on the server where possible, and isolate interactive state in client boundaries.

## 2. Which API should I learn first?

`ChakraProvider, Next.js App Router, React Server Components, client boundary, hydration`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Use server components for data loading and static page composition; place client boundaries around interactive state and event handlers.

## 4. What state and accessibility detail matters most?

Chakra component support does not mean every Chakra component is a server component. Interactive hooks require a client boundary; static rendering can still occur on the server. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Adding use client to the entire app without a need. This expands the client bundle and reduces server component opportunities.

## 6. How can I practice it?

Create a Next.js root provider, render a static Chakra heading from a server page, and move one interactive dialog into a client component. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. Do all Chakra components require use client?

No. Current Chakra documentation supports using Chakra components with React Server Components without adding the directive everywhere. Interactive hooks still need client components.

## 8. Where should the provider go in Next.js?

Compose it in a client provider component and include that component from the root layout so the server layout stays minimal.

## 9. What causes hydration mismatch with color mode?

The server may not know the same stored or system color preference as the browser. Prefer CSS semantic tokens and follow the current color-mode setup guidance.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="033-typescript-and-type-generation.md">033 - TypeScript and type generation</a></td>
      <td><a href="../lessons/034-nextjs-server-components-and-ssr.md">Chapter lesson</a></td>
      <td><a href="../examples/034-nextjs-server-components-and-ssr.md">Chapter example</a></td>
      <td><a href="035-testing-chakra-ui-components.md">035 - Testing Chakra UI components</a></td>
    </tr>
  </tbody>
</table>
