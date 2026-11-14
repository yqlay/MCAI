# MCAI

A Minecraft server AI assistant with a genuine in-game terminal.

This repository hosts release assets, user documentation and issue reports.
MCAI development source and private development history are not published here.

## Downloads and setup

Download [MCAI 0.4.0-alpha.1](https://github.com/yqlay/MCAI/releases/tag/v0.4.0-alpha.1).
Checksums and license notices accompany the installation packages.
Use the file for your exact Minecraft version and loader. The current release
family is **0.4.0-alpha.1**, for **Windows x64**.

- Java: 1.12.2 Forge; 1.20.1, 1.21.1 and 26.3 Fabric or Forge.
- Bedrock: a separate local BDS, behavior pack and native Windows companion.
- Bring your own compatible model API. No model subscription or API key is included.

Read [installation](INSTALL.md), [capabilities and limits](CAPABILITIES.md),
[support](SUPPORT.md) and [third-party notices](THIRD-PARTY.md).

## What MCAI does

Describe a task in natural language. The Agent can inspect Minecraft state,
execute authorized commands, build from structured files and check results.
Sessions, planning, recurring tasks and subagents are available through an
adapted Codex CLI in a real Windows HwndTerminal/ConPTY interface. World actions
use server APIs and commands, without an AI player entity.

Press F8 to open or hide MCAI, F6 for Home and F7 for Settings. Configure API
connections and your selected models in Settings. Hiding the terminal does not
stop server tasks or loops.

## Credits and disclosure

MCAI adapts OpenAI Codex and Microsoft Windows Terminal. Bundled components retain
their own licenses and notices. AI coding agents contributed substantially to
the integration, tests and documentation; generative AI is also a runtime feature.

MCAI is not an official OpenAI, Microsoft or Mojang product. This repository does
not imply approval or availability on another mod distribution platform.
