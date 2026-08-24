<div align="center">
  
# ENGRAI

### Character conversations that remember who they are.

A local-first, bring-your-own-model client for creating persistent characters,<br>
shaping how they behave, and carrying context across conversations.

[![Download the latest notarized DMG](https://img.shields.io/badge/Download-Latest_notarized_DMG-ff2d78?style=for-the-badge&logo=apple&logoColor=white)](https://github.com/va-desai-dev/ENGRAI/releases)

[![macOS 26+](https://img.shields.io/badge/macOS-26%2B-111111?logo=apple)](https://github.com/va-desai-dev/ENGRAI/releases)
![Apple notarized](https://img.shields.io/badge/Apple-notarized-2da44e)
![Bring your own key](https://img.shields.io/badge/models-bring_your_own_key-6f42c1)
![18+](https://img.shields.io/badge/age-18%2B-b42318)

**[Download for macOS](https://github.com/va-desai-dev/ENGRAI/releases)** · [Read the documentation](Documentation.docc/) · [Report an issue](https://github.com/va-desai-dev/ENGRAI/issues)

</div>

---

## Download for macOS

The current macOS build is distributed as a **Developer ID-signed and Apple-notarized DMG**.

1. Open [Releases](https://github.com/va-desai-dev/ENGRAI/releases) and choose the version marked **Latest**.
2. Download its `.dmg` file under **Assets**.
3. Open it and drag **ENGRAI** into **Applications**.
4. Launch ENGRAI and connect the model endpoint you want to use.

ENGRAI requires **macOS 26 or later**. You should not need to disable Gatekeeper, remove quarantine attributes, or use a security bypass. If macOS asks you to bypass a warning, delete that copy and download the DMG again from this repository.

### Verify your download

Ask Gatekeeper to validate the notarization ticket. You can also calculate the file's SHA-256 digest and compare it with a checksum in the release notes when one is provided:

```sh
shasum -a 256 ~/Downloads/ENGRAI-*.dmg
spctl --assess --type install --verbose=4 ~/Downloads/ENGRAI-*.dmg
```

Gatekeeper should report that the artifact is accepted and identify its source as a notarized Developer ID.

---

## What is ENGRAI?

ENGRAI is a native Apple-platform client for sustained, character-driven conversations with large language models. It is not a model or a hosted chat service. You bring the endpoint, model, and—when the provider requires it—your own API key.

The app turns structured character and persona settings into a predictable prompt, keeps durable session memories separate from recent chat history, and tracks how relationships change over time. The prompt system is documented so its behavior can be inspected instead of guessed at.

<p align="center">
  <img src="Screenshots/S1.jpg" alt="An ENGRAI character conversation" width="31%">
  &nbsp;
  <img src="Screenshots/S2.jpg" alt="ENGRAI character behavior controls" width="31%">
  &nbsp;
  <img src="Screenshots/S3.jpg" alt="ENGRAI session memory ledger" width="31%">
</p>

### Built around continuity

- **Detailed character construction** — shape identity, appearance, temperament, social behavior, priorities, voice, and other context through structured controls.
- **Session memory** — maintain a durable memory ledger for facts, preferences, boundaries, unresolved threads, and relationship continuity.
- **Relationships that evolve** — track directional alliance, romance, regard, and trust without allowing one dimension to invent another.
- **Group conversations** — preserve speaker-specific knowledge and relationships while withholding private interior context from other characters.
- **Inspectable prompting** — character traits, memories, scenes, personas, and final instructions enter the prompt in a published, deterministic order.

### Your models, your choice

ENGRAI can connect directly to:

- OpenAI-compatible APIs, including many hosted aggregators and local servers
- Anthropic's Messages API
- Google's Gemini API
- local endpoints such as Ollama, LM Studio, llama.cpp, and compatible servers

Chat, summarization, and image work can be assigned to different connections. Each connection keeps its own model name, endpoint, API format, and optional sampler overrides.

---

## Privacy by construction

ENGRAI has no developer-operated account system, API proxy, analytics service, advertising SDK, or content database. Requests travel directly from the app to the model provider or local endpoint you configure.

Your characters and conversations are local-first. If you enable iCloud synchronization, data may also be stored in your private CloudKit database. If you use a hosted model provider, the prompts and messages sent to that provider are governed by its retention and privacy policies; use a local endpoint when conversational content must remain on your own network.

API access is not bundled with the app. Any provider fees, limits, and acceptable-use rules come from the provider you choose.

---

## Connect a model

Create a connection in ENGRAI with:

| Setting | What to enter |
|---|---|
| **Format** | OpenAI, Anthropic, or Google |
| **Base URL** | The provider's API root, commonly ending in `/v1` |
| **Model name** | The provider's exact model identifier |
| **API key** | Your provider key; usually unnecessary for a local server |

For an OpenAI-compatible local server, a connection may look like:

```text
Format:     OpenAI
Base URL:   http://localhost:11434/v1
Model name: <the model served locally>
API key:    <blank>
```

Always use the endpoint and model identifier published by your provider. ENGRAI is provider-agnostic and does not endorse or supply access to any particular model.

---

## Documentation

The reference material in [`Documentation.docc`](Documentation.docc/) explains the system behind the interface:

| Guide | Covers |
|---|---|
| [Connecting API keys](Documentation.docc/Article.md) | Base URLs, model identifiers, authentication, hosted providers, and local inference engines |
| [Prompt builder guide](Documentation.docc/PromptBuilderGuide.md) | The human-readable prompt order, substitutions, group boundaries, and relationship tooling |
| [Prompt assembly reference](Documentation.docc/PromptAssemblyReference.md) | The detailed construction and provider-wrapping contract |
| [Slider reading reference](Documentation.docc/SliderReadingReference.md) | How structured character values become natural-language guidance |
| [Summarizer prompt reference](Documentation.docc/SummarizerPromptReference.md) | Memory-ledger updates and relationship deltas |
| [Terms of Service](Documentation.docc/Terms%26Services.md) | Eligibility, permitted use, privacy, limitations, and support |

---

## Important notes

- ENGRAI is strictly for adults aged **18 or older** and for lawful, fictional, creative use.
- Model output is probabilistic. Deterministic prompt assembly does not guarantee deterministic behavior from a provider or model.
- ENGRAI is not a substitute for medical, therapeutic, legal, financial, or other professional services.
- Back up information that matters to you. A developer-operated server copy does not exist and cannot be used to restore your data.

## Support

Use [GitHub Issues](https://github.com/va-desai-dev/ENGRAI/issues) for bugs, provider-compatibility problems, and documentation corrections. When reporting a connection issue, include the provider, API format, base URL form, model identifier, and full error text—but **never include your API key**.

Questions about the app may also be sent to [support@engrai.app](mailto:support@engrai.app).

Third-party components retain their respective licenses; see [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md).

<div align="center">

Copyright © 2026 Vedant Desai

</div>
