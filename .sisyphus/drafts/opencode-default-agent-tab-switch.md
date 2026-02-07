# Draft: Add Default Agent To Tab Switch

## User Request (ZH)
- User wants the OpenCode default agent to be selectable via Tab switching, so they don't need to type `@build`.

## My Current Understanding
- Today: Omitting any `@agent` mention runs the default agent (likely `build`).
- UI/UX ask: include the default agent in the agent list/autocomplete/switcher so it can be selected via Tab.

## Assumptions (not yet confirmed)
- The user is using the OpenCode CLI/TUI input where Tab cycles agent mentions.
- Default agent is `build` and is currently hidden from the selectable list.

## Open Questions
- Which OpenCode client/UI is this (CLI/TUI, VSCode extension, web)?
- How should the option be labeled: `build`, `default (build)`, or `default` alias?
- Should selecting the default agent remove an explicit mention (i.e., revert to no `@...`), or insert `@build`?

## Acceptance Targets (draft)
- Tab switch list includes an explicit entry for the default agent.
- Selecting it behaves consistently (either inserts `@build` or clears mention and uses default routing).
- No behavior change when user types nothing (still uses default).
