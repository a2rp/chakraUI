# 036 - Performance and styling architecture Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind performance and styling architecture?

Chakra v3 currently uses Emotion at runtime while its long-term styling direction evolves toward a zero-runtime model in phases. Optimize based on measurements, keep component trees focused, and avoid work that duplicates what CSS can do.

## 2. Which API should I learn first?

`Emotion runtime, bundle analyzer, direct imports, CSS variables, memoization`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Profile before optimizing. Use CSS for responsive presentation and reserve React state for behavior; split heavy features when measurements show meaningful bundle cost.

## 4. What state and accessibility detail matters most?

Styling runtime and bundle trade-offs depend on the installed Chakra version and build. The official docs describe the current direction; do not assume future architecture has shipped. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Memoizing every component before profiling. It adds complexity and can obscure state flow without a measurable gain.

## 6. How can I practice it?

Measure an app route, identify one expensive render or imported package, make one evidence-based change, and record before/after results. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. Is Chakra zero-runtime today?

Current installation documentation says Chakra uses Emotion at runtime and describes zero-runtime styling as a phased long-term direction. Verify release notes before relying on a future change.

## 8. Should I memoize all Chakra components?

No. Measure first. Many performance issues come from data, expensive work, or bundle size rather than style props alone.

## 9. How do I reduce initial bundle cost?

Use direct imports, inspect production chunks, defer optional heavy views, and avoid importing large packages for a small feature.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="testing-chakra-ui-components.md">035 - Testing Chakra UI components</a></td>
      <td><a href="../lessons/036-performance-and-styling-architecture.md">Chapter lesson</a></td>
      <td><a href="../examples/036-performance-and-styling-architecture.md">Chapter example</a></td>
      <td><a href="migration-from-chakra-ui-v2-to-v3.md">037 - Migration from Chakra UI v2 to v3</a></td>
    </tr>
  </tbody>
</table>
