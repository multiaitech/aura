# Reference

## Sidebar labels

These are the exact labels in Aura's sidebar:

- History
- Project
- Model Hub
- Orchestrator
- Pipeline
- Modules
- User MCP
- Automation Trail
- Documentation
- System Log
- Checkpoint

## Status lights

Aura uses small coloured dots. Their meaning depends on what they belong to.

**Harness (Model Hub, Harness tab)**

- Green - ACP or a verified bridge is ready. The role can be delegated to.
- Yellow - only a CLI fallback exists. It works, but Aura gets one final answer per call and the role has no memory of earlier steps.
- Red - no usable bridge, or a non-interactive CLI. It must not be assigned to a role.

**MCP (User MCP)**

- Grey - registered but not tested. A new connection always starts here.
- Green - the health test passed and the integration is active.
- Red - the health test failed and the connection stays off.

The test runs only when you click the light.

**Roles (Pipeline)**

Each role has an on/off switch and a status area. A role with no model bound shows **No model yet**. A role you switch off is never delegated to.

## AuraData

AuraData sits next to the executable, so each installation keeps its own state.

- `settings.json` - application settings, including role bindings
- `aura-workspace.json` - the workspace registry
- `agents/` - agent registry
- `browser/` - in-app browser state; screenshots are in `browser/captures/`
- `browser-external/` - external browser integration data
- `checkpoints/` - checkpoint snapshots used for rollback
- `database/` - internal database files
- `documentation/` - the markdown files shown in the Documentation panel
- `documents/` - user documents
- `history/` - chat history
- `lesson_learned/` - Lesson Learned records
- `logs/` - `system.jsonl` and related logs
- `mcp/` - MCP connection configuration
- `memory/` - long-term memory records
- `no-project/` - sessions that are not attached to a project
- `pipeline-checkpoints/` - pipeline-level rollback snapshots
- `projects/` - project workspaces
- `semantic_index/` - search index
- `worklog/` - session notes

## Security model

- **Single user, per instance** - one Aura never coordinates with another Aura instance, even on the same account.
- **Immutable core** - the shell, the permission gate, the checkpoint system, the System Log and the credential vault cannot be modified by a user, an extension or an agent.
- **Encrypted vault** - API keys are stored encrypted and shown masked.
- **Permission gate** - any folder outside the project needs your approval.
- **Default-deny egress** - outbound network access is denied unless a host has been approved.
- **Read-only System Log** - reading the log never grants authority to change core state.

## Updates

1. Aura reads `https://multiaitech.com/api/v1/aura/version`.
2. It downloads the installer for that version.
3. It verifies the file's SHA-256 against the manifest.
4. It installs only if the hash matches.

Current version: 0.2.70.

## Common first-run problems

### A role shows "No model yet"

No model is bound to that role.

1. Open **Pipeline** and pick the role.
2. Choose an API or Local model and press **Set**, or press **Set** on a harness row.
3. Press **Save**.

### A harness light is yellow or red

Yellow means only a CLI fallback exists: the harness is installed but Aura cannot stream its steps. Red means the harness is missing, interactive-only, or has no usable bridge.

Re-run **Scan Local Harnesses** in **Builder Adapter**, confirm the harness is installed and logged in outside Aura, and use an API or Local model for that role if it stays red.

### A local engine does not answer

The engine is not running, or it listens on a port other than the default.

1. Start the engine yourself and confirm it is listening (Ollama 11434, LM Studio 1234, llama.cpp 8080, Jan 1337, vLLM 8000, Text Generation WebUI 5000).
2. Open **Model Hub**, switch to **Local**, then the **Runtime** tab.
3. Press **Load**, then **Test**.

If the engine cannot be started, use the GGUF folder route instead: **+ Add Local** and pick the folder with your `.gguf` files.

### An update is not offered

1. Confirm the machine can reach multiaitech.com.
2. Check `logs/system.jsonl` for a version-check error.
3. Restart Aura and check again.

If the manifest reports a version equal to the installed one, there is nothing to install yet.

## Related documents

- [Getting Started](getting-started.md)
- [Models](models.md)
- [Features](features.md)
