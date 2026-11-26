# Chakra UI Practical Notes

A structured, hands-on guide to Chakra UI for building accessible React interfaces. The course follows the v3 system and compound-component APIs, with migration notes for v2 projects.

## Scope and version

The examples target Chakra UI v3.38.0, the latest stable release verified on 2026-11-26. Chakra v3 uses a configurable styling system and currently uses Emotion at runtime. APIs, framework support, and Node requirements can change; check the package version in your project before copying version-sensitive code.

Chakra UI is a component and styling library, not a router or application framework. These notes focus on its provider, design tokens, style props, component patterns, forms, overlays, accessibility, TypeScript, server rendering, testing, and production maintenance.

## Learning outcomes

By following the roadmap, you will learn to:

- Set up Chakra UI in an existing React application and provide a shared system.
- Compose v3 components from their documented parts and manage controlled state.
- Use style props, breakpoints, tokens, semantic tokens, recipes, and slot recipes.
- Build accessible forms, selection widgets, overlays, navigation, and feedback.
- Integrate Chakra with TypeScript, Next.js, testing tools, and form libraries.
- Recognize version differences and plan a safe Chakra UI v2 to v3 migration.

## Prerequisites

- Familiarity with JavaScript, React, JSX, props, state, and component composition.
- Basic HTML, CSS, responsive design, and accessibility concepts.
- Node.js 20 or newer per the current installation guidance, a package manager, and an existing React app.
- TypeScript is helpful for the type-generation chapter but is not required for the early chapters.

## Quick guides

- [Chakra UI summary](chakraUI-summary.md)
- [Chakra UI keywords and concepts](chakraUI-keywords.md)

## Getting started

For a manual v3 setup, install Chakra and Emotion in an existing compatible React project:

```sh
npm install @chakra-ui/react @emotion/react
```

Wrap the app in the provider using the default system:

```jsx
import { ChakraProvider, defaultSystem } from "@chakra-ui/react"

export function AppProvider({ children }) {
  return <ChakraProvider value={defaultSystem}>{children}</ChakraProvider>
}
```

The CLI can add editable project-local snippets for patterns such as color mode or a toaster:

```sh
npx @chakra-ui/cli snippet add
```

Choose either the manual provider composition or a generated project snippet and inspect the generated code. Check the official framework requirements and peer dependencies for your installed package version.

## How to use these notes

1. Read the lesson to understand the component model, styling decisions, and limitations.
2. Use the matching Q&A to review edge cases, migration differences, and practical decisions.
3. Mount the matching example in a configured React app and adapt it to a real interface.
4. Test keyboard behavior, labels, focus, loading, and error states for interactive examples.

## Repository structure

- `lessons/` contains the chapter explanations.
- `qnas/` contains chapter questions and answers.
- `examples/` contains practical, app-mounted examples.
- `chakraUI-summary.md` provides a topic-wide review.
- `chakraUI-keywords.md` indexes Chakra concepts and APIs.
- `LICENSE` contains the repository's MIT license.

## Course roadmap

| No. | Lesson | Q&A | Example |
| ---: | --- | --- | --- |
| 001 | [Introduction to Chakra UI v3](lessons/001-introduction-to-chakra-ui-v3.md) | [Open Q&A](qnas/001-introduction-to-chakra-ui-v3.md) | [Open example](examples/001-introduction-to-chakra-ui-v3.md) |
| 002 | [Installation and project setup](lessons/002-installation-and-project-setup.md) | [Open Q&A](qnas/002-installation-and-project-setup.md) | [Open example](examples/002-installation-and-project-setup.md) |
| 003 | [Providers, snippets, and framework integration](lessons/003-providers-snippets-and-framework-integration.md) | [Open Q&A](qnas/003-providers-snippets-and-framework-integration.md) | [Open example](examples/003-providers-snippets-and-framework-integration.md) |
| 004 | [Component anatomy, compound APIs, and state](lessons/004-component-anatomy-compound-apis-and-state.md) | [Open Q&A](qnas/004-component-anatomy-compound-apis-and-state.md) | [Open example](examples/004-component-anatomy-compound-apis-and-state.md) |
| 005 | [Style props and token-aware styling](lessons/005-style-props-and-token-aware-styling.md) | [Open Q&A](qnas/005-style-props-and-token-aware-styling.md) | [Open example](examples/005-style-props-and-token-aware-styling.md) |
| 006 | [Responsive and conditional styles](lessons/006-responsive-and-conditional-styles.md) | [Open Q&A](qnas/006-responsive-and-conditional-styles.md) | [Open example](examples/006-responsive-and-conditional-styles.md) |
| 007 | [Design tokens and CSS variables](lessons/007-design-tokens-and-css-variables.md) | [Open Q&A](qnas/007-design-tokens-and-css-variables.md) | [Open example](examples/007-design-tokens-and-css-variables.md) |
| 008 | [Custom system and theme configuration](lessons/008-custom-system-and-theme-configuration.md) | [Open Q&A](qnas/008-custom-system-and-theme-configuration.md) | [Open example](examples/008-custom-system-and-theme-configuration.md) |
| 009 | [Semantic tokens and color palettes](lessons/009-semantic-tokens-and-color-palettes.md) | [Open Q&A](qnas/009-semantic-tokens-and-color-palettes.md) | [Open example](examples/009-semantic-tokens-and-color-palettes.md) |
| 010 | [Color modes and dark mode](lessons/010-color-modes-and-dark-mode.md) | [Open Q&A](qnas/010-color-modes-and-dark-mode.md) | [Open example](examples/010-color-modes-and-dark-mode.md) |
| 011 | [Typography and text styles](lessons/011-typography-and-text-styles.md) | [Open Q&A](qnas/011-typography-and-text-styles.md) | [Open example](examples/011-typography-and-text-styles.md) |
| 012 | [Layout primitives: Box, Flex, and Stack](lessons/012-layout-primitives-box-flex-and-stack.md) | [Open Q&A](qnas/012-layout-primitives-box-flex-and-stack.md) | [Open example](examples/012-layout-primitives-box-flex-and-stack.md) |
| 013 | [Grid, containers, and positioning](lessons/013-grid-containers-and-positioning.md) | [Open Q&A](qnas/013-grid-containers-and-positioning.md) | [Open example](examples/013-grid-containers-and-positioning.md) |
| 014 | [Buttons and action components](lessons/014-buttons-and-action-components.md) | [Open Q&A](qnas/014-buttons-and-action-components.md) | [Open example](examples/014-buttons-and-action-components.md) |
| 015 | [Fields, inputs, and textareas](lessons/015-fields-inputs-and-textareas.md) | [Open Q&A](qnas/015-fields-inputs-and-textareas.md) | [Open example](examples/015-fields-inputs-and-textareas.md) |
| 016 | [Checkbox, radio, and switch controls](lessons/016-checkbox-radio-and-switch-controls.md) | [Open Q&A](qnas/016-checkbox-radio-and-switch-controls.md) | [Open example](examples/016-checkbox-radio-and-switch-controls.md) |
| 017 | [Select, Combobox, and Autocomplete](lessons/017-select-combobox-and-autocomplete.md) | [Open Q&A](qnas/017-select-combobox-and-autocomplete.md) | [Open example](examples/017-select-combobox-and-autocomplete.md) |
| 018 | [Form validation and React Hook Form](lessons/018-form-validation-and-react-hook-form.md) | [Open Q&A](qnas/018-form-validation-and-react-hook-form.md) | [Open example](examples/018-form-validation-and-react-hook-form.md) |
| 019 | [Cards, avatars, badges, and lists](lessons/019-cards-avatars-badges-and-lists.md) | [Open Q&A](qnas/019-cards-avatars-badges-and-lists.md) | [Open example](examples/019-cards-avatars-badges-and-lists.md) |
| 020 | [Images, icons, and file upload](lessons/020-images-icons-and-file-upload.md) | [Open Q&A](qnas/020-images-icons-and-file-upload.md) | [Open example](examples/020-images-icons-and-file-upload.md) |
| 021 | [Accordion and collapsible content](lessons/021-accordion-and-collapsible-content.md) | [Open Q&A](qnas/021-accordion-and-collapsible-content.md) | [Open example](examples/021-accordion-and-collapsible-content.md) |
| 022 | [Tabs, steps, and navigation](lessons/022-tabs-steps-and-navigation.md) | [Open Q&A](qnas/022-tabs-steps-and-navigation.md) | [Open example](examples/022-tabs-steps-and-navigation.md) |
| 023 | [Menus, popovers, tooltips, and hover cards](lessons/023-menus-popovers-tooltips-and-hover-cards.md) | [Open Q&A](qnas/023-menus-popovers-tooltips-and-hover-cards.md) | [Open example](examples/023-menus-popovers-tooltips-and-hover-cards.md) |
| 024 | [Dialogs, drawers, and alert dialogs](lessons/024-dialogs-drawers-and-alert-dialogs.md) | [Open Q&A](qnas/024-dialogs-drawers-and-alert-dialogs.md) | [Open example](examples/024-dialogs-drawers-and-alert-dialogs.md) |
| 025 | [Alerts, toasts, progress, and loading states](lessons/025-alerts-toasts-progress-and-loading-states.md) | [Open Q&A](qnas/025-alerts-toasts-progress-and-loading-states.md) | [Open example](examples/025-alerts-toasts-progress-and-loading-states.md) |
| 026 | [Tables and data display](lessons/026-tables-and-data-display.md) | [Open Q&A](qnas/026-tables-and-data-display.md) | [Open example](examples/026-tables-and-data-display.md) |
| 027 | [Date, time, color pickers, sliders, and rating](lessons/027-date-time-color-pickers-sliders-and-rating.md) | [Open Q&A](qnas/027-date-time-color-pickers-sliders-and-rating.md) | [Open example](examples/027-date-time-color-pickers-sliders-and-rating.md) |
| 028 | [Recipes and reusable component variants](lessons/028-recipes-and-reusable-component-variants.md) | [Open Q&A](qnas/028-recipes-and-reusable-component-variants.md) | [Open example](examples/028-recipes-and-reusable-component-variants.md) |
| 029 | [Slot recipes and multi-part components](lessons/029-slot-recipes-and-multi-part-components.md) | [Open Q&A](qnas/029-slot-recipes-and-multi-part-components.md) | [Open example](examples/029-slot-recipes-and-multi-part-components.md) |
| 030 | [Composition, Chakra factory, and asChild](lessons/030-composition-chakra-factory-and-aschild.md) | [Open Q&A](qnas/030-composition-chakra-factory-and-aschild.md) | [Open example](examples/030-composition-chakra-factory-and-aschild.md) |
| 031 | [Presence, animation, and transitions](lessons/031-presence-animation-and-transitions.md) | [Open Q&A](qnas/031-presence-animation-and-transitions.md) | [Open example](examples/031-presence-animation-and-transitions.md) |
| 032 | [Accessibility, keyboard interaction, and RTL](lessons/032-accessibility-keyboard-interaction-and-rtl.md) | [Open Q&A](qnas/032-accessibility-keyboard-interaction-and-rtl.md) | [Open example](examples/032-accessibility-keyboard-interaction-and-rtl.md) |
| 033 | [TypeScript and type generation](lessons/033-typescript-and-type-generation.md) | [Open Q&A](qnas/033-typescript-and-type-generation.md) | [Open example](examples/033-typescript-and-type-generation.md) |
| 034 | [Next.js, Server Components, and SSR](lessons/034-nextjs-server-components-and-ssr.md) | [Open Q&A](qnas/034-nextjs-server-components-and-ssr.md) | [Open example](examples/034-nextjs-server-components-and-ssr.md) |
| 035 | [Testing Chakra UI components](lessons/035-testing-chakra-ui-components.md) | [Open Q&A](qnas/035-testing-chakra-ui-components.md) | [Open example](examples/035-testing-chakra-ui-components.md) |
| 036 | [Performance and styling architecture](lessons/036-performance-and-styling-architecture.md) | [Open Q&A](qnas/036-performance-and-styling-architecture.md) | [Open example](examples/036-performance-and-styling-architecture.md) |
| 037 | [Migration from Chakra UI v2 to v3](lessons/037-migration-from-chakra-ui-v2-to-v3.md) | [Open Q&A](qnas/037-migration-from-chakra-ui-v2-to-v3.md) | [Open example](examples/037-migration-from-chakra-ui-v2-to-v3.md) |
| 038 | [Production design system and maintenance](lessons/038-production-design-system-and-maintenance.md) | [Open Q&A](qnas/038-production-design-system-and-maintenance.md) | [Open example](examples/038-production-design-system-and-maintenance.md) |

## Course status

The roadmap defines the course structure. Each chapter is represented by a lesson, Q&A, and example file with matching numbering and names.

## License

This repository is distributed under the license in [LICENSE](LICENSE).
