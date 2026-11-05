# Models - Three Executor Paths

Every role in Aura runs on exactly one executor: an API model, a local model, or a harness. The three paths are interchangeable per role. Aura never rebinds a role's executor on its own, and never overrides the model configured inside a harness - that stays your choice.

## API path

Bring your own key. Keys are stored in Aura's encrypted vault and displayed masked after you save them.

### Built-in providers

**Chat and text**

- OpenCode Go - https://opencode.ai/zen/go/v1
- OpenCode Zen - https://opencode.ai/zen/v1
- OpenRouter - https://openrouter.ai/api/v1
- FreeLLMAPI - https://freellmapi.co/v1
- DeepSeek - https://api.deepseek.com
- Qwen via Alibaba Model Studio - https://dashscope-intl.aliyuncs.com/compatible-mode/v1
- Z.ai GLM - https://api.z.ai/api/paas/v4
- Kimi Moonshot - https://api.moonshot.ai/v1
- Claude Anthropic - https://api.anthropic.com/v1
- ChatGPT OpenAI API - https://api.openai.com/v1
- Grok xAI - https://api.x.ai/v1
- Mistral AI - https://api.mistral.ai/v1
- Agnes free API hub - https://apihub.agnes-ai.com/v1
- NVIDIA NIM - https://integrate.api.nvidia.com/v1
- Cloudflare Workers AI - needs your account ID inside the base URL
- HuggingFace Inference - https://router.huggingface.co/v1
- Groq - https://api.groq.com/openai/v1
- Cerebras - https://api.cerebras.ai/v1
- Google Gemini - https://generativelanguage.googleapis.com/v1beta/openai
- OpenAI Local Proxy - 127.0.0.1:10531, no key needed
- 9Router local router - 127.0.0.1:20128, uses its own key from its dashboard

**Image** - Stability AI, Replicate, OpenAI DALL-E 3, Pollinations (keyless).

**Video** - Luma Dream Machine, Runway, Pika.

**Search** - Brave Search, used by the agent web-search tool rather than as a chat model.

Chat roles do not use image or video models yet.

### Custom endpoints

Any OpenAI-compatible endpoint can be added, so a brand-new AI service works without waiting for an Aura update. In the **custom** tab of the API screen, fill in Name, Base URL and Auth style, then press **+ Add endpoint**. Aura appends `/models` when loading and `/chat/completions` when chatting, so include the version segment your gateway needs (for example `.../v1`).

## Local path

No API key, no network traffic, full privacy. Two routes.

### Runtime route

Aura talks to an engine that is already running on your machine.

- Ollama - port 11434
- LM Studio - port 1234
- llama.cpp llama-server - port 8080
- Jan - port 1337
- vLLM - port 8000
- Text Generation WebUI - port 5000

Start the engine, open **Model Hub**, switch to **Local**, then the **Runtime** tab, press **Load**, then **Test**.

### GGUF folder route

Open **Model Hub**, switch to **Local**, press **+ Add Local** and choose a folder holding `.gguf` files. Aura scans the folder and lists the models it finds. No engine process is needed for this route.

## Harness path

### What a harness is

A harness is a full coding agent with its own file access: Codex, Claude Code, OpenCode, KiloCode, Qwen Code, Cursor, Gemini CLI and others. Aura drives it as a role executor and reads its output.

**Important:** Aura cannot stop a harness from writing files, even when the harness is bound to an advisory role such as Reviewer, Security or Tester. Only the role instruction and prompt restrain it. For write isolation, keep harnesses on coder roles.

### Discovery

1. Open **Model Hub**, switch to **Harness**, and open **Builder Adapter**.
2. Press **Scan Local Harnesses**. Discovery only - Aura never starts a harness by itself.
3. Aura lists what is installed and usable on the machine.

Recognized harness ids: `codex`, `claude-code`, `opencode`, `kilocode`, `qwen` (Qwen Code), `jcode`, `prime-agent`, `pi` (Pi coding agent), `cursor`, `gemini-cli`, `copilot`, `mimocode`, `freebuff`, `bravecode`, `codebuddy` (bins `codebuddy`, `cbc`, `codebuddy-code`), plus a custom ACP harness.

### Status lights

- **Green** - ACP or a verified bridge is ready. Delegate normally.
- **Yellow** - a CLI fallback exists. Aura bridges it through the harness's headless CLI and returns one final answer per call, so the role has no memory of earlier steps. Recheck before relying on it.
- **Red** - no usable bridge, or a non-interactive CLI. It must not be assigned to a role.

Aura never changes the model configured inside a harness. If a harness needs a different model, change it in that harness's own configuration.

## Leader on a harness

When the Leader itself runs on a harness, Aura bridges orchestration through structured intent blocks. The Leader emits a request to write todos or to delegate to a specialist, Aura parses it, and Aura executes it with the same guards as a native API or local Leader - including the rule that todos must be written before a delegation. There is no silent bypass, and anything outside the allowed actions is rejected.

## Choosing a path

- **Local** - maximum privacy, offline work, no per-token cost.
- **API** - the strongest models, and the simplest setup for a single role.
- **Harness** - reuse a coding agent you already pay for, best on coder roles.

For advisory roles (Reviewer, Security, Tester) prefer API or Local, so a harness cannot write files while it is only supposed to read.
