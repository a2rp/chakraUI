# Chakra UI Keywords and Concepts

A quick index to current Chakra UI v3 concepts and APIs. Chakra UI is a React component library, so this file indexes component names, props, configuration APIs, and styling concepts rather than JavaScript reserved words.

## Version and package names

- `@chakra-ui/react`: core Chakra UI component and styling package.
- `@emotion/react`: runtime styling dependency used by the current Chakra UI release.
- `@chakra-ui/cli`: project tooling for snippets, codemods, and type generation.
- `next-themes`: color-mode provider dependency used by current project snippets.
- `react-icons`, `lucide-react`: optional third-party icon libraries; not included by the Chakra core package.
- Chakra UI v3: compound component APIs and system-based theming.
- Chakra UI v2: earlier API with different provider, theme, and component contracts.

## Application setup

- `ChakraProvider`: supplies a Chakra system to descendants.
- `defaultSystem`: the built-in styling system.
- `createSystem`: creates a system from a base config and custom config.
- `defaultConfig`: starting config for a custom system.
- `defineConfig`: types and defines system configuration.
- `Provider`: often a project-local wrapper that composes ChakraProvider with other providers.
- `snippet add`: CLI command that adds editable component source snippets.
- `typegen`: CLI command that generates types from a custom system.
- `strictTokens`: config option that enforces configured token use in typed styles.
- `preflight`: CSS reset configuration.
- `globalCss`: global style configuration.
- `cssVarsRoot`, `cssVarsPrefix`: CSS variable placement and prefix configuration.

## Component anatomy and state

- `Root`: root part of a compound component and its shared state context.
- `Trigger`: control that opens, closes, or selects content.
- `Content`: panel or content region connected to an interaction.
- `Item`: selectable item with a stable value.
- `Positioner`: floating-layout wrapper.
- `Portal`: renders a layer outside its local DOM ancestor.
- `HiddenInput`: native form integration part for custom controls.
- `value`: controlled state supplied by a parent.
- `defaultValue`: initial state for an uncontrolled component.
- `onValueChange`: callback for a value change.
- `open`, `defaultOpen`, `onOpenChange`: controlled, initial, and change state for disclosure components.
- Controlled component: parent owns state and updates it in callbacks.
- Uncontrolled component: component manages state after an initial default.

## Styling and design-system APIs

- Style props: CSS-like props such as `p`, `bg`, `color`, `gap`, `borderRadius`.
- `css`: advanced CSS object escape hatch.
- `_hover`, `_focusVisible`, `_dark`: conditional style selectors.
- Responsive object: styles keyed by breakpoints such as `{ base: ..., md: ... }`.
- Token: named primitive design value.
- Semantic token: named design role such as `bg.subtle`, `fg.muted`, or `border`.
- CSS variable: browser custom property emitted for theme values.
- `system.token()`: access a raw token value.
- `system.token.var()`: access a token CSS variable.
- `colorPalette`: selects a component recipe's coordinated palette.
- `textStyle`: applies a named typographic style.
- `layerStyle`: applies a named reusable style layer.
- `animationStyle`: applies a named animation style.

## Layout and content components

- `Box`: general styleable container.
- `Flex`: one-dimensional flex layout.
- `Stack`, `HStack`, `VStack`: gap-based child layout.
- `Grid`, `GridItem`, `SimpleGrid`: CSS Grid patterns.
- `Container`: centered, width-constrained content.
- `Center`: centering layout primitive.
- `Heading`, `Text`: semantic text components.
- `Card`: related content composition.
- `Avatar`: identity and image fallback.
- `Badge`: compact status or category.
- `List`: semantic list structure.
- `Image`: image element with Chakra styling props.

## Forms and selection

- `Field.Root`: label, helper, required, and invalid context for a control.
- `Field.Label`, `Field.HelperText`, `Field.ErrorText`: field parts.
- `Input`, `Textarea`, `NativeSelect`: familiar form controls.
- `Checkbox.Root`: independent choice.
- `RadioGroup.Root`: one selected option in a group.
- `Switch.Root`: immediate on/off setting.
- `Select.Root`: list selection widget.
- `Combobox.Root`: input with a selectable collection.
- `createListCollection`: creates structured item data for collection-based widgets.
- `NumberInput`, `Slider`, `Rating`: numeric or evaluative controls.
- `DateInput`, `DatePicker`, `ColorPicker`, `FileUpload`: specialized controls.
- React Hook Form `register`: connect native-compatible fields.
- React Hook Form `Controller`: connect controlled components.

## Disclosure, navigation, and feedback

- `Accordion.Root`: group of expandable sections.
- `Collapsible.Root`: one expandable region.
- `Tabs.Root`: switch among related panels.
- `Steps.Root`: communicate progress through a sequence.
- `Menu.Root`: command menu.
- `Popover.Root`: interactive floating content.
- `Tooltip.Root`: brief descriptive help.
- `HoverCard.Root`: supplementary preview.
- `Dialog.Root`: focused dialog layer.
- `Drawer.Root`: dialog-like side panel.
- `Alert.Root`: persistent inline message.
- `Progress.Root`: determinate or indeterminate progress.
- `Skeleton`: visual placeholder for loading content.
- toaster snippet: app-owned transient notification composition.
- `Presence`: presence and enter/exit transition coordination.

## Theme customization

- `defineRecipe`: define base and variants for a single-part component.
- `defineSlotRecipe`: define styles across named component parts.
- `variants`: named style choices.
- `compoundVariants`: style choices applied to combinations of variants.
- `defaultVariants`: defaults for recipe variants.
- `RecipeVariantProps`: infer a recipe's variant types.
- `useRecipe`, `useSlotRecipe`: consume recipe definitions.
- Type generation: synchronize custom tokens and recipes with TypeScript definitions.

## Composition, accessibility, and framework integration

- `chakra()`: create a Chakra-styled custom element.
- `as`: select a rendered element when the component API supports it.
- `asChild`: compose a component's behavior and props onto its child.
- `aria-label`: accessible name for a control without visible text.
- `_focusVisible`: keyboard-visible focus styling.
- Logical CSS properties: start/end layout properties that adapt to writing direction.
- RTL: right-to-left layout direction.
- React Server Component: server-rendered React component without client interactivity.
- Client boundary: region that uses browser APIs, event handlers, or React state.
- Hydration: attaching client behavior to server-rendered markup.
- Portal: rendering overlay content outside the local DOM subtree.

## Legacy v2 terms to recognize

These names appear in older tutorials and should not be copied directly into a v3 project without checking the migration guide:

- `extendTheme`, v2 `theme` provider prop, `ColorModeScript`, `useColorModeValue`.
- `isOpen`, `isDisabled`, `isInvalid`, `colorScheme`, `spacing`.
- `Modal`, `AccordionButton`, `TabList`, `TabPanel`, `StackItem`.
- `@chakra-ui/icons`, `@chakra-ui/next-js`, `@emotion/styled`.

These are migration recognition terms, not a claim that every name is unavailable in every compatibility path. Confirm against the installed version.
