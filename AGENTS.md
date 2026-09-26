# Repository agent guide

## Repository workflow and completion

`src/hatch/` is the CLI, `backend/` the separate Hatchling backend, with tests/docs/environments defined alongside `hatch.toml`. Use Python 3.10+ and Hatch environments. CI runs `hatch fmt --check`, `hatch run types:check`, and `hatch test --python <installed-version>` with coverage/randomization options. Scope iteration checks while retaining required matrix gates.

Docs validation uses `hatch run docs:build-check`; theme/environment dependencies may be required. `python -m build backend` builds Hatchling separately. Environment creation/type checking downloads tools and downstream tests build third-party packages; inspect selected targets. Docs ci-build and package/distribution releases are publication actions.

Continue the authorized change through relevant validation and repair of failures it causes; preserve unrelated work. Report checks actually run, commands only inspected, and exact missing prerequisites. Ask only when a material decision, missing authorization, or required input blocks progress; continue independent reversible work. Existing mandatory contribution and validation gates still apply.
