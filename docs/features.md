# Features

A short reference for what Aura does. Each section is a summary, not a manual.

## Modes and pipelines

- **Chat** - the Leader answers with its own model. This is the everyday mode.
- **Consensus** - several models answer independently and the Orchestrator synthesizes the result.
- **Debate** - a pro team and a contra team argue, and the Leader rules.
- **Coding Team** - the Leader coordinates coder, reviewer, security and tester roles in a fixed pipeline.

The active mode decides who is allowed to work. In Chat the Leader does everything itself. In Coding Team the Leader coordinates and the specialists do the work.

## Roles and switches

Roles live under **Pipeline**. Each has an on/off switch and a status area, and a role with no model shows **No model yet**.

Leader, Frontend, Backend, Coder (a single unified coder), Reviewer, Security, Tester, Documentation, Orchestrator.

A role switched off is your decision: Aura never delegates to it and never substitutes another agent for it. A role that fails at runtime is a technical problem, and Aura reports it rather than swapping a model behind your back.

## Leader duties

- **Final gate** - reads every specialist report, decides what is acceptable, and routes fixes back to the right role.
- **Auto-failover** - when a role's executor is down, an equivalent executor of the same specialty can take over. Roles you switched off are never replaced.
- **Conflict arbitration** - when two roles touch the same file, the Leader decides the order and the outcome.
- **Hybrid messaging** - roles can send operational messages, and the Leader always reads them.

## Modules and schedules

A module is a recurring activity assembled from MCP integrations plus sub-services, and each sub-service may have its own executor AI. A module can carry an optional schedule: every 30 minutes, hourly, every 24 hours, or daily at 09:00.

A module is still a bundle of integrations and sub-services without conditional step chaining, and the scheduler is early-stage.

## MCP connections

Connections live under **User MCP**, each with its own light.

A newly registered MCP starts with its light off and grey. The real health test runs only when you click the light: green means it passed and the integration is active, red means it failed and stays off.

## Skills

Skills change a role's system prompt and therefore how it behaves.

PonyTail (minimal code, anti over-engineering), Code Reviewer (logic, edge cases, API contracts), Security Checker (OWASP audit with false-positive filtering), Software Tester (coverage matrix, TDD), STORM Research (multi-perspective research), Fable Brain (decisive, evidence-based collaboration), Code Research Protocol (research before changing code), Review Discipline (evidence-first review output).

Some skills use web search without an API key. Skills are enabled per role in **Pipeline**.

## Documentation panel

**Documentation** is a flat set of markdown files with optional front-matter (title, covers, updated_by, project, kind).

The Documentation role owns the panel. While that role is active, every turn that changes project files must be handed to it, and read-only turns are exempt. The panel reads the folder next to the running executable, so each installation has its own documentation.

## Lesson Learned

Opt-in. Records are kept locally first, and uploaded only after the server accepts them. Lessons are graded Gold, Silver or Bronze, and the grading for coding lessons differs from the grading for Consensus.

## Automation Trail and intent

Every model writes one sentence of intent before each step, and that line appears before the action runs. If a model jumps straight to a tool, Aura fills in a readable line such as "Reading src/main.rs" or "Running: cargo test".

Only observable actions are shown. Hidden reasoning is never displayed, and tool arguments and results are available by clicking the step.

## In-app browser

Leader-only, built on WebView2. Ten tools:

- `browser_open` - navigate to a URL
- `browser_snapshot` - element list for the current page
- `browser_read` - page text
- `browser_click` - click an element
- `browser_type` - type into a field
- `browser_history` - navigation history
- `browser_screenshot` - save the page as a PNG
- `browser_eval` - run JavaScript in the page
- `browser_cdp` - raw Chrome DevTools Protocol escape hatch
- `browser_tabs` - list, open, select and close tabs

Each action passes a three-tier permission check with a 300 second approval timeout. Screenshots are saved as PNG files under `AuraData/browser/captures` and reach the model as a file path, not as an image.

## Telegram connector

The Telegram Aura Connector is built in, not a module. It handles pairing, slash commands, session binding, the mid-turn message queue and the replies.

## Checkpoints

A checkpoint snapshots `settings.json` and `aura-workspace.json`. Aura takes one before updates, factory reset, rollback and risky module changes, so a run can be restored to a known-good state.

## Projects and code panel

**Project** organizes the workspace and exposes the code panel for the files you are working on. Aura's own core stays immutable; project files live in the project folder you approve.
