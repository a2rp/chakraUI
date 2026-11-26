# 004 - Component anatomy, compound APIs, and state Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind component anatomy, compound apis, and state?

Many Chakra v3 interactive components expose a Root and named parts such as Trigger, Content, and Item. The parts make structure explicit while sharing state and accessibility behavior through their compound context.

## 2. Which API should I learn first?

`Component.Root, Component.Trigger, Component.Content, value/defaultValue, onValueChange`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Choose compound components when an interaction needs multiple coordinated elements or custom markup. Use a simple component when it already expresses the desired interaction.

## 4. What state and accessibility detail matters most?

Uncontrolled state starts from defaultValue and is managed internally. Controlled state comes from value and must be updated in the matching callback. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Omitting a required part such as a hidden input or item value. Compound APIs make more structure visible, but each documented part still has a role.

## 6. How can I practice it?

Compose one Accordion item and one Tabs group. Label each part and identify which state is owned internally versus supplied by React. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. Why does v3 use compound components?

They make the interactive structure explicit and let applications arrange documented parts while the component manages shared state and accessibility behavior.

## 8. When should state be controlled?

Control a component when another part of the app must set, observe, reset, or synchronize its value. Otherwise, defaultValue is usually simpler.

## 9. Can I omit the ItemIndicator?

Often yes if the visual affordance is supplied another way, but follow the component's documented required parts and ensure users can still discover the interaction.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="003-providers-snippets-and-framework-integration.md">003 - Providers, snippets, and framework integration</a></td>
      <td><a href="../lessons/004-component-anatomy-compound-apis-and-state.md">Chapter lesson</a></td>
      <td><a href="../examples/004-component-anatomy-compound-apis-and-state.md">Chapter example</a></td>
      <td><a href="005-style-props-and-token-aware-styling.md">005 - Style props and token-aware styling</a></td>
    </tr>
  </tbody>
</table>
