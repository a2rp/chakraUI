# 002 - Installation and project setup Q&A

These answers use Chakra UI v3 APIs. Check the installed package version when applying them to a project.

## 1. What is the core idea behind installation and project setup?

A Chakra project needs a React application, the Chakra package, and its Emotion runtime dependency. Current v3 installation guidance requires Node.js 20 or newer; verify framework peer dependencies against the versions already installed.

## 2. Which API should I learn first?

`@chakra-ui/react, @emotion/react, npm install, Vite or Next.js`. Start with the smallest documented composition, then add state or variants only when the task needs them.

## 3. When should I use this pattern?

Add Chakra to an existing React app when its framework and React versions meet the package peer requirements. Choose one package manager and keep the lockfile committed.

## 4. What state and accessibility detail matters most?

Installation is a build-time project change. The provider and component usage happen at runtime in the React tree. Preserve semantic labels and keyboard behavior as you customize the visual structure.

## 5. What mistake should I check for in review?

Installing the obsolete v2 package set or relying on an old tutorial. v3 uses @chakra-ui/react and @emotion/react; older examples may include packages no longer required.

## 6. How can I practice it?

Add Chakra UI to a fresh Vite React app, record the Node and React versions, and render one Button inside ChakraProvider. Compare the result with the corresponding example file and test it with keyboard input where the pattern is interactive.

## 7. Which packages are needed for a manual v3 setup?

Install @chakra-ui/react and @emotion/react. Use the framework's existing React and React DOM packages if compatible, and consult current peer requirements before changing them.

## 8. What Node.js version should I use?

The current Chakra installation guide lists Node.js 20.x as the minimum. Check the official guide again when upgrading because minimum tool versions can change.

## 9. Do I need the Chakra CLI?

No. The CLI can add project-local component snippets and generate token types, but the core package can be set up manually.

## Chapter navigation

<table width="100%">
  <thead>
    <tr><th>Previous Q&amp;A</th><th>Chapter lesson</th><th>Chapter example</th><th>Next Q&amp;A</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="001-introduction-to-chakra-ui-v3.md">001 - Introduction to Chakra UI v3</a></td>
      <td><a href="../lessons/002-installation-and-project-setup.md">Chapter lesson</a></td>
      <td><a href="../examples/002-installation-and-project-setup.md">Chapter example</a></td>
      <td><a href="003-providers-snippets-and-framework-integration.md">003 - Providers, snippets, and framework integration</a></td>
    </tr>
  </tbody>
</table>
