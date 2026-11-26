# Chakra UI Summary

A topic-wide review of Chakra UI, focused on the v3 system and component APIs used throughout this repository.

## 1. What Chakra UI provides

Chakra UI is a React component and styling library. It supplies accessible component patterns, style props, design tokens, and configurable recipes. React remains responsible for application rendering and state; the application remains responsible for routing, data, business rules, validation, and product content.

The current v3 line uses Emotion at runtime and is evolving its styling architecture in phases. Do not treat future roadmap items as already-shipped APIs. Examples in these notes target v3.38.0 as verified on 2026-11-26.

## 2. Installation and provider

For a compatible React project, install:

```sh
npm install @chakra-ui/react @emotion/react
```

Provide the default or custom system near the application root:

```jsx
import { ChakraProvider, defaultSystem } from "@chakra-ui/react"

export function Provider({ children }) {
  return <ChakraProvider value={defaultSystem}>{children}</ChakraProvider>
}
```

The current installation guidance requires Node.js 20.x or newer. Check peer requirements and framework setup for the exact package version. The CLI can add editable snippets for common app compositions, such as color mode and toaster.

## 3. Component composition and state

Many v3 components use compound APIs:

```jsx
<Tabs.Root defaultValue="profile">
  <Tabs.List>
    <Tabs.Trigger value="profile">Profile</Tabs.Trigger>
    <Tabs.Trigger value="security">Security</Tabs.Trigger>
  </Tabs.List>
  <Tabs.Content value="profile">Profile settings</Tabs.Content>
  <Tabs.Content value="security">Security settings</Tabs.Content>
</Tabs.Root>
```

- Use `defaultValue` for ordinary uncontrolled initial state.
- Use `value` and the documented change callback for controlled state.
- Preserve required parts, stable item values, semantic labels, and keyboard behavior.
- Use a native element or simpler component when a custom interaction adds no value.

## 4. Styling, tokens, and responsive design

Style props express CSS-like values through Chakra's system:

```jsx
<Box
  bg="bg.subtle"
  color="fg"
  p={{ base: "4", md: "6" }}
  _focusVisible={{ outline: "2px solid", outlineColor: "blue.500" }}
/>
```

Use responsive values for presentation, not JavaScript resize state. Prefer shared tokens for colors, spacing, typography, and radii. Primitive tokens represent raw values; semantic tokens represent roles such as surfaces, foregrounds, borders, and focus rings. Semantic tokens are generally easier to adapt across color modes.

## 5. Theming and recipes

A custom v3 system combines a base config and a custom config:

```tsx
import { createSystem, defaultConfig, defineConfig } from "@chakra-ui/react"

const config = defineConfig({
  theme: {
    tokens: {
      colors: {
        brand: { 500: { value: "#176B87" } },
      },
    },
  },
})

export const system = createSystem(defaultConfig, config)
```

Use `defineRecipe` for variants on one styled root and `defineSlotRecipe` for coordinated styles on several named parts. Promote patterns when repeated product intent is clear. Run CLI type generation after custom token or recipe changes when typed system values are used.

## 6. Forms and feedback

- Use a visible label for every control; a placeholder is a hint, not a label.
- Compose fields with `Field.Root`, `Field.Label`, `Field.HelperText`, and `Field.ErrorText`.
- Select checkboxes, radio groups, and switches according to the choice semantics.
- Use NativeSelect for simple platform-native choices; use Select or Combobox when custom presentation or search is needed.
- Chakra provides control and presentation patterns, not domain validation. Validate again on the server.
- Use persistent alerts for important errors, toasts for brief status, and progress only when the reported value is meaningful.

## 7. Overlays and navigation

Choose each pattern by behavior:

- Menu: a list of commands.
- Popover: interactive floating content.
- Tooltip: brief noninteractive description.
- Dialog: focused prompt or task.
- Drawer: side-positioned dialog-like content.
- Tabs: related content panels on one page.
- Links: navigation to another location.

Keep focus entry, keyboard traversal, Escape behavior, focus return, accessible naming, and portal placement in mind. Do not build a tooltip that contains interactive controls.

## 8. Accessibility and internationalization

Accessible interfaces preserve semantic HTML, visible labels, contrast, focus visibility, keyboard interaction, useful error messages, and logical reading order. Use logical CSS properties for layouts that support RTL and provide translated labels and messages. Chakra defaults help, but the full page still requires keyboard and assistive-technology review.

## 9. TypeScript, Next.js, and testing

- Chakra types validate component props at development time; they do not validate runtime data.
- Typegen synchronizes configured token and recipe types.
- Keep server-rendered data and static composition on the server where practical; isolate event handlers and state in client components.
- Use Testing Library role and label queries rather than generated CSS class names.
- Test the visible result and behavior: opening, closing, selecting, submitting, validation, focus, and error handling.

## 10. Performance and maintenance

Measure rendering and bundle size before optimizing. Use CSS for responsive presentation rather than React resize listeners. Split optional heavy views when profiling supports it. Chakra's current runtime styling architecture and roadmap are version-sensitive; verify current release notes before making performance assumptions.

## 11. Chakra v2 to v3

The major upgrade changed provider and theme configuration, component composition, state props, color mode, and several package names. The official codemod can perform many transformations, but review its output and follow with type checks, interaction tests, and manual accessibility review. Keep migration changes separate from unrelated redesign work.

## Review checklist

- Does every control have a useful accessible name?
- Are visual state and keyboard state both clear?
- Are tokens semantic and shared where reuse is real?
- Are controlled values updated from their callbacks?
- Do error and loading states explain what users can do?
- Are framework, Node, React, and Chakra versions compatible?
- Have important interactions been checked in a browser and with keyboard navigation?
