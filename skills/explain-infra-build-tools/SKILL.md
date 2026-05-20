Name: explain-infra-build-tools

Purpose
-------
Detect and explain build/bundler/infra tools (Vite, Webpack, Rollup,
esbuild, Parcel). Provide comparisons, migration notes, and config
locations.

When to use
-----------
- Repo contains `vite.config.*`, `webpack.config.*`, `rollup.config.*`,
  or package scripts referencing these tools.

Behavior
--------
- Explain role of the tool, common plugin models, dev vs prod differences,
  and provide a short migration checklist when switching tools.

Examples
--------
- "Compare Vite vs Webpack for this repo and list 5 migration concerns."
