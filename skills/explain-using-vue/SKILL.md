Name: explain-using-vue

Purpose
-------
Explain JavaScript/TypeScript frontend code by mapping idioms to Vue
(2/3) concepts: options vs composition API, reactive refs, lifecycle
hooks, and single-file component structure.

When to use
-----------
- Source is a React or general JS frontend and the user prefers Vue-based
  analogies or example snippets.

Behavior
--------
- Detect function components, hooks, and stateful logic.
- Suggest Vue equivalents (composition API `setup()`, `ref`, `reactive`),
  map lifecycle hooks (e.g., `useEffect` -> `onMounted`/`watch`).
