# 034 - Next.js, Server Components, and SSR Example

> This chapter uses Chakra UI v3.38.0 APIs. If your installed version differs, verify component parts and props before using the code.

## Goal

Create a Next.js root provider, render a static Chakra heading from a server page, and move one interactive dialog into a client component.

## Assumptions and prerequisites

- A Next.js App Router project, React, `@chakra-ui/react`, and `@emotion/react`.
- The host application already has a React entry point and a Chakra provider using `defaultSystem` or the custom system used by the project.
- The file below is a focused component example. Mount it from an existing route or app component; it is not a complete application scaffold.

## File structure

```text
src/
  examples/
    034-nextjs-server-components-and-ssr.jsx
```

## 034-nextjs-server-components-and-ssr.jsx

```jsx
// app/providers.tsx
"use client"

import type { ReactNode } from "react"
import { ChakraProvider, defaultSystem } from "@chakra-ui/react"

export function Providers({ children }: { children: ReactNode }) {
  return <ChakraProvider value={defaultSystem}>{children}</ChakraProvider>
}

// app/layout.tsx
import type { ReactNode } from "react"
import { Providers } from "./providers"

export default function RootLayout({ children }: { children: ReactNode }) {
  return <html lang="en"><body><Providers>{children}</Providers></body></html>
}
```

## Run and inspect

Start the host application with its existing development command, commonly `npm run dev`. Visit the route or page where you mounted the example. For chapter 034, inspect the result described below and interact with every trigger, field, or control.

The root layout provides Chakra context to the app. Server-rendered pages can use supported Chakra components, while stateful interactions belong inside client components.

## What to notice

- The API and composition are documented for Chakra UI v3, not copied from a v2 tutorial.
- The component remains responsible for its content, state, and application-specific behavior.
- When a code block shows only the topic-focused component, imports and host provider come from the configured application described above.

## Variations

Create a Next.js root provider, render a static Chakra heading from a server page, and move one interactive dialog into a client component.

Try this variation: change the content or data without changing the component's semantic role. Then test a narrow viewport, keyboard navigation, and an error or empty state when relevant.

## Common mistakes

- Adding use client to the entire app without a need. This expands the client bundle and reduces server component opportunities.
- Assuming browser-only APIs or color-mode state are identical during server rendering and hydration.

Check that the code's imports match the host project, that all values have stable keys where lists are rendered, and that controls have visible or programmatic labels.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous example</th><th>Chapter lesson</th><th>Chapter Q&amp;A</th><th>Next example</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="033-typescript-and-type-generation.md">033 - TypeScript and type generation</a></td>
      <td><a href="../lessons/034-nextjs-server-components-and-ssr.md">Chapter lesson</a></td>
      <td><a href="../qnas/034-nextjs-server-components-and-ssr.md">Chapter Q&amp;A</a></td>
      <td><a href="035-testing-chakra-ui-components.md">035 - Testing Chakra UI components</a></td>
    </tr>
  </tbody>
</table>
