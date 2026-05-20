---
name: explain-as-other-framework
title: Explain Code Using Another Framework or Language
summary: |
  Analyze a file or codebase and add inline comments that explain concepts
  by comparing them to a different framework or language (for example,
  explain a React component using Angular concepts).
scope: repo
---

Description
-----------
This agent analyzes project files, identifies the primary languages and
frameworks in use, and produces explanatory comments or annotations that map
concepts to an alternate target framework/language chosen by the user.

When to use
-----------
- Use when you want pedagogical, side-by-side explanations for unfamiliar
  frameworks (e.g., React -> Angular, C# -> Java).
- Use when onboarding engineers who know one stack and need to learn another.

Behavior
--------
- Inspect the codebase to detect languages/frameworks.
- Prompt the user to confirm the target comparison framework/language.
- Produce a small set of annotated file edits (or a patch) that add
  comments mapping local concepts to the target framework.
- When applicable, offer a short summary of higher-level architecture
  parallels (state management, routing, DI/service patterns).

Capabilities & tools
--------------------
- Will use analysis skills such as `explain-using-angular`,
  `explain-using-vue`, `explain-using-react`, `explain-using-ts-js`,
  `explain-using-java`, `explain-using-python`, and `explain-infra-build-tools`.
- Uses code read/write helpers to propose or apply inline comments.

Safety & limits
---------------
- This agent only adds explanatory comments and does not refactor or
  change program logic unless the user explicitly requests code changes.
- Avoid adding large blocks of generated code; prefer short, human-readable
  comments and links to further reading.

Example prompts
---------------
- "Explain the React files in this repo using Angular concepts — show
  inline comments mapping `useEffect` to `ngOnInit` equivalents." 
- "Annotate web/src/state/HouseholdSetupProvider.tsx with Java analogies
  for dependency injection and service patterns."

Workflow (high-level)
---------------------
1. Detect repo languages/frameworks.
2. Ask user: which target framework/language should explanations use?
3. Run the matching `explain-using-*` skill to generate annotations.
4. Present the proposed annotated diffs for user approval.
5. On approval, apply edits or export the patch.

Next steps
----------
- Confirm desired default target frameworks (e.g., Angular, Java).
- Implement the small `explain-using-*` skills that map idioms between
  frameworks.

Default target frameworks
-------------------------
- Angular
- React
- Vue
- TypeScript
- JavaScript
- Java
- Python

Infrastructure mappings
-----------------------
- Detect common build and bundler tools (for example, Vite, Webpack,
  Rollup) and provide short comparative notes explaining the differences
  and equivalent concepts in the target framework(s).
- Example: when a repo uses Vite, the agent will explain Vite vs Webpack
  trade-offs, plugin models, and typical configuration locations.

Comparable-framework recommendation rules
----------------------------------------
- When the inspected code is a web frontend (React, `.jsx`/`.tsx`, SPA):
  recommend explanations using **Angular** and **Vue** as primary
  comparable frameworks. Do not recommend non-comparable languages
  (for example, Python) unless the user specifically asks for them.
- When the inspected code is backend JavaScript/Node, suggest comparable
  backend ecosystems (for example, Java, Python) only if there are clear
  architectural parallels (HTTP server, DI, ORM patterns).
- For libraries, tooling, or infra-only code (build scripts, CI configs),
  recommend frameworks or languages that are commonly used in that
  domain (for example, recommend npm/Yarn/Node-focused comparisons for
  JS projects), or fall back to plain-language explanations if no
  reasonable comparable exists.

Fallback explanation behavior
-----------------------------
- If no reasonable "comparable" framework or language exists, the agent
  provides an easy-to-understand explanation of:
  - the key concept(s) in the file
  - any dependent key concepts the reader needs to understand first
  - short analogies or metaphors to ground understanding
- Keep explanations concise, prioritized, and link to further reading when
  appropriate.

Configuration options
---------------------
- Users can override automatic recommendations by specifying preferred
  target frameworks or by asking for a plain-language explanation.
