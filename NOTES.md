# Working conventions (from the user)

- **"侧边栏" means the sidebar column *and* the blocks/panels inside it.**
  When a request says "改侧边栏", it covers:
  - the column shell (`.…_sidebarCol`, background, radius, tilt, seams)
  - its inner blocks: session rows, workspace groups, new-session button,
    search field, the HUD panel, and the account/footer row.
  The same reading applies to the right dock (`[data-sidebar-right-panel]`)
  and the panels it hosts.

- Do not change unrelated surfaces (conversation, composer, settings) when the
  request names only one sidebar.

- Keep every rule scoped and reversible: if a selector does not match the
  running build, the surface must fall back to the host look instead of
  breaking (no half-rendered panels).

## Process rules (learned the hard way)

- **Do not add effects the user did not ask for.** No extra colouring, glow,
  hover states, or "nice to have" details without explicit confirmation first.
- When a request is ambiguous, propose the change in one or two lines and wait.
- Corner marks stay neutral grey at all times; selection is communicated by the
  orange bar only.
- Prefer removing a rule over adding a compensating one.
