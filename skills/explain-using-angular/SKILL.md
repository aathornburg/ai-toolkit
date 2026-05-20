Name: explain-using-angular

Purpose
-------
Provide mappings and inline-comment guidance that explain code written in
JavaScript/TypeScript (especially React) using Angular concepts and
terminology (components, templates, dependency injection, lifecycle hooks).

When to use
-----------
- Source code is a web frontend (React, TSX/JSX) and the user requests an
  Angular-oriented explanation or analogies.

Behavior
--------
- Detect component files, contexts, hooks, and routing code.
- Produce short inline comments that show Angular equivalents (e.g., map
  `useEffect` -> `ngOnInit`/`ngOnChanges`, React Context -> Angular
  Services + DI).
- Provide a short section with higher-level parallels (routing, state
  management, forms). Keep changes read-only until user approves a patch.

Examples
--------
- "Annotate `web/src/App.tsx` mapping React Router usage to Angular
  Router equivalents."
