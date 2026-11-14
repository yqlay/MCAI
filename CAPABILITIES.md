# Capabilities and limits

MCAI is a server assistant. It uses server APIs and commands, rather than moving
an AI player entity. The adapted Codex Agent can plan, use tools, inspect feedback,
run workspace programs and delegate work when the selected model supports it.

| Area | Available behavior | Limit to state in the listing |
| --- | --- | --- |
| World inspection and commands | Read registered world state and execute authorized server operations | An installed client does not grant server permission |
| Structured building | JSON scenes, region capture, native state validation and retained jobs | Unknown mod behavior needs discovery and verification |
| Building styles | Editable Chinese, modern and medieval examples and components | Design aids, not a guarantee of visual quality |
| Multi-state blocks | Native state and coupled-part handling, transforms and verification | Runtime/neighbor changes remain actual game behavior |
| Java projections | JSON and Litematica workflows, subject to each native version's data | No promise of arbitrary cross-version NBT conversion |
| Agent tools | Native workspace execution, subagents and MCP world tools | Model/provider services and sandbox permissions still apply |
| Python / local compilers | Bundled Python; other compilers may be used through native tools when installed and allowed | No bundled C++ compiler or every-library guarantee |
| Sessions and modes | Session restoration, Plan, execution, Goal, BTW and recurring Loop work | Closing the front end does not stop background work |
| Native terminal | Microsoft HwndTerminal/ConPTY, transparent composition and display settings | Windows x64; representative device/IME checks, not all hardware |
| Camera / WorldEdit | Capability discovery reports actual availability | Unavailable adapters on the new ports are not advertised as working |
| Forge machine operations | Registry/command-based features where implemented | Atomic machine-transfer parity is not claimed |
| Bedrock | Local Windows BDS bridge and native companion | Separate manual setup; no remote pairing or Java NBT/general projection parity |

The exact tested game/loader versions are in [installation](INSTALL.md). Runtime
capability feedback takes priority over a generic tool name. Optional workflows
and examples help the Agent; they do not remove the user's ability to request a
different method. World edits, commands and generated programs can have lasting
effects, so the operator should grant access only to trusted players.

## Data and network behavior

MCAI stores conversations, job receipts, settings and files locally under its
instance storage. Requests send the relevant conversation and tool context to
the model endpoint selected by the operator. If images or files are included in
a request, their contents may also reach that endpoint. Provider retention and
charges are governed by that provider, not by the mod hosting site.

The bundled native programs run as child processes. Native execution and file
access use the current session's sandbox and ownership rules. Shared materials
and skills are deliberate shared inputs; another private player's/session's
files are not meant to become implicit context. Authorized tools can write world
state and session files. A listing must disclose these capabilities clearly.

No external model service, subscription, API balance or universal model quality
is included with the mod. Network search/download capabilities also depend on
the selected service and network access. Do not claim that every compatible API
implements every Codex capability.
