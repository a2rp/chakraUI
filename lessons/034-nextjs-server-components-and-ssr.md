# 034 - Next.js, Server Components, and SSR

> Chakra UI v3.38.0 context, current as of 2026-11-26. Confirm the installed package version before applying version-sensitive APIs.

## Learning goals

After this lesson, you should be able to:

- Explain the purpose and boundaries of Next.js, Server Components, and SSR.
- Identify the main API: `ChakraProvider, Next.js App Router, React Server Components, client boundary, hydration`.
- Choose an appropriate use case: Use server components for data loading and static page composition; place client boundaries around interactive state and event handlers.
- Avoid the main implementation risks: Adding use client to the entire app without a need. This expands the client bundle and reduces server component opportunities.

## Core idea

Chakra UI v3 supports server-rendered React and Next.js App Router patterns, but interactive Chakra components depend on client-side React capabilities. Keep data and static composition on the server where possible, and isolate interactive state in client boundaries.

A useful way to learn a component library is to separate three questions: what behavior the component provides, how its parts communicate, and which design tokens style it. Chakra's API helps connect these layers, but it does not replace product decisions about content, validation, routing, or data ownership.

In v3, examples are organized around the current compound component and system APIs. Older tutorials may show a single component with many nested exports, v2 theme helpers, or a different provider contract. Treat version labels as part of the example, not as optional decoration.

## API and behavior

The relevant surface for this topic is `ChakraProvider, Next.js App Router, React Server Components, client boundary, hydration`.

Chakra component support does not mean every Chakra component is a server component. Interactive hooks require a client boundary; static rendering can still occur on the server.

For controlled usage, pass a value from the owning React state and update it from the component's change callback. For uncontrolled usage, provide an initial default and let the component manage ordinary interaction state. Do not provide both approaches unless the API explicitly needs both.

## Example

The following focused component demonstrates the core idea:

```jsx
// app/providers.tsx
"use client"

import { ChakraProvider, defaultSystem } from "@chakra-ui/react"

export function Providers({ children }: { children: React.ReactNode }) {
  return <ChakraProvider value={defaultSystem}>{children}</ChakraProvider>
}

// app/layout.tsx
import { Providers } from "./providers"

export default function RootLayout({ children }: { children: React.ReactNode }) {
  return <html lang="en"><body><Providers>{children}</Providers></body></html>
}
```

Keep the data and business rules in application code. Use Chakra for the documented composition and styling behavior, and confirm less common props against the installed version's TypeScript definitions.

## When to use this pattern

Use server components for data loading and static page composition; place client boundaries around interactive state and event handlers.

If the UI needs custom behavior beyond the documented component contract, start from the simplest semantic HTML structure that meets the need. Add Chakra composition only when it makes the behavior, consistency, or accessibility easier to maintain.

## Common mistakes

- Adding use client to the entire app without a need. This expands the client bundle and reduces server component opportunities.
- Assuming browser-only APIs or color-mode state are identical during server rendering and hydration.

A quick review checklist:

- Does the markup communicate the same meaning as the visible design?
- Can keyboard users reach and operate the control?
- Are text, focus, disabled, error, and loading states understandable without color alone?
- Are repeated values represented by a shared token or variant where that improves consistency?

## Recap

Chakra UI v3 supports server-rendered React and Next.js App Router patterns, but interactive Chakra components depend on client-side React capabilities. Keep data and static composition on the server where possible, and isolate interactive state in client boundaries. Remember the API boundary: ChakraProvider, Next.js App Router, React Server Components, client boundary, hydration. Keep the behavior and semantics explicit, and choose the smallest reusable abstraction that supports the task.

## Practice task

Create a Next.js root provider, render a static Chakra heading from a server page, and move one interactive dialog into a client component.

## Further review

Compare your implementation with the matching Q&A and example files. Verify the API in Chakra UI v3 documentation when the installed minor version differs from the version named in this lesson.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous lesson</th><th>Chapter Q&amp;A</th><th>Chapter example</th><th>Next lesson</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="typescript-and-type-generation.md">033 - TypeScript and type generation</a></td>
      <td><a href="../qnas/034-nextjs-server-components-and-ssr.md">Chapter Q&amp;A</a></td>
      <td><a href="../examples/034-nextjs-server-components-and-ssr.md">Chapter example</a></td>
      <td><a href="testing-chakra-ui-components.md">035 - Testing Chakra UI components</a></td>
    </tr>
  </tbody>
</table>
