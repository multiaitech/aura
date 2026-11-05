# Getting Started

This is the only page you must read to start using Aura. Everything else Aura offers is optional.

## Requirements

- Windows 10 or Windows 11, 64-bit.
- The Aura installer. No separate runtime, database or server is needed.

## Install

1. Download the installer from [multiaitech.com](https://multiaitech.com/download).
2. Run it and follow the wizard.
3. Launch Aura from the Start menu.

On first launch Aura creates an `AuraData/` folder next to the executable. Settings, logs and chat history live there.

## Connect one model

Every role runs on exactly one executor. Aura supports three executor paths and **one of them is enough to start**:

- **API** - a cloud provider you already use, with your own key.
- **Local** - a model on your own machine. No key, and nothing leaves the machine.
- **Harness** - a coding agent already installed and logged in on your machine.

### Path A: API key

1. Open **Model Hub** and switch to the **API** tab.
2. Pick a provider from the list. For your own gateway open the **custom** tab, fill in Name, Base URL and Auth style, then press **+ Add endpoint**.
3. Paste the API key. Providers that need no key say so on the form.
4. Press **Load Models** to fetch the model list. **Test Connection** checks reachability before you commit.
5. Tick the models you want and press **Save models**.

Keys are stored in Aura's encrypted vault and shown masked afterwards.

### Path B: Local

Two routes, equally supported.

**Runtime route** - the engine serves the model:

1. Start the engine yourself: Ollama (port 11434), LM Studio (port 1234), llama.cpp llama-server (port 8080), Jan (port 1337), vLLM (port 8000) or Text Generation WebUI (port 5000).
2. Open **Model Hub**, switch to **Local**, then the **Runtime** tab.
3. Press **Load**, then **Test**.

**GGUF folder route** - Aura reads the model files directly:

1. Open **Model Hub** and switch to **Local**.
2. Press **+ Add Local** and choose the folder that holds your `.gguf` files.

Neither route needs an API key.

### Path C: Harness

A harness is a full coding agent (Codex, Claude Code, OpenCode, KiloCode, Qwen Code and others) that Aura can drive as a role executor.

1. Install and log in to the harness yourself, outside Aura.
2. Open **Model Hub**, switch to **Harness**, and open **Builder Adapter**.
3. Press **Scan Local Harnesses**. This is discovery only - Aura never starts a harness by itself.
4. Read the status light before binding: green means ready, yellow means only a CLI fallback exists, red means it cannot be assigned to a role.

A harness has its own file access. See [models.md](models.md) before binding one to an advisory role.

## Bind the model to the Leader

1. Open **Pipeline** and pick the **Leader** role.
2. In the model picker, choose the API or Local model and press **Set**, or press **Set** on a harness row.
3. Press **Save**. The footer states that selections are saved directly to the role.

A role with no model shows **No model yet**.

## First chat

Open the chat, type a request and send it. The Leader reads the intent, plans the work, and either answers itself or hands the work to a specialist.

## What you do not need

None of the following is required to start: MCP servers, modules, skills, projects, a second model, or a harness. Aura works with one model and the Leader.

## If something looks wrong

- A role shows **No model yet**: no model is bound to it.
- A harness light is yellow or red: the bridge is not ready. Use an API or Local model for that role instead.
- A local engine does not answer: the engine is not running, or it listens on a different port.

More in [reference.md](reference.md).
