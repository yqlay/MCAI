# Install MCAI for Java Edition

MCAI runs a server-owned AI assistant and embeds a real Windows terminal in the
game. It requires **Windows x64**. The interface and built-in guides are English.
Use your own model API; the provider may charge for requests. No API key is included.

## Choose the matching file

Install one MCAI JAR for the exact game version and loader. Do not install Fabric
and Forge variants together. Minecraft, its loader and the game Java runtime
are separate prerequisites.

| Minecraft | Loader tested | Game Java | Additional required mod |
| --- | --- | --- | --- |
| 1.12.2 | Forge 14.23.5.2864 | 8, x64 | None |
| 1.20.1 | Fabric 0.19.5 | 17, x64 | Fabric API 0.92.12+1.20.1 |
| 1.20.1 | Forge 47.4.28 | 17, x64 | None |
| 1.21.1 | Fabric 0.19.5 | 21, x64 | Fabric API 0.116.17+1.21.1 |
| 1.21.1 | Forge 52.1.20 | 21, x64 | None |
| 26.3 | Fabric 0.20.1 | 25, x64 | Fabric API 0.165.0+26.3 |
| 26.3 | Forge 66.1.0 | 25, x64 | None |

These are tested combinations, not a promise that every other loader build or
third-party mod works. There is no Fabric 1.12.2 variant in this release family.
NeoForge, macOS and Linux are not supported by these Windows packages.

1. Close the game and stop the matching server before replacing mod files.
   Finish or explicitly pause Agent tasks and scheduled loops first.
2. Back up the existing game/server folder, including world, config and `mcai`.
   Keep backups on a disk you choose. Do not delete histories to update the mod.
3. Copy the matching JAR into that instance's `mods` folder. Remove the older
   MCAI JAR from `mods` so that only one MCAI version is loaded. Preserve it in
   the backup. Install the matching Fabric API separately on Fabric.
4. For multiplayer, use matching MCAI files on the Windows server and client.
   For singleplayer, install it in the client's game instance.
5. Start Minecraft normally. Join the intended world/server. The server owner
   must authorize players; installing the client alone does not grant authority.

The runtime is bundled. First initialization verifies and unpacks it into the
instance's MCAI storage, so first start takes longer than a warm start. Use a
reasonably short, writable local directory, for example `E:\Minecraft\server`.
Do not unpack the JAR manually or delete runtime folders while Agents are active.

## Connect a model

Open MCAI with **F8**, then **F7** for Settings. On an authorized local setup,
open **API connections → Add API**. Choose the endpoint's actual protocol,
enter its HTTPS base URL with the required API prefix, and save the key in the
settings form. For example, an OpenAI-compatible endpoint may require `/v1`.
Do not put keys in game chat, Agent prompts, screenshots or bug reports.

Fetch the model list when supported. Choose the models you want in **My models**;
you do not have to add every model the endpoint returns. A catalog response
does not prove generation or tool calling works. Run the connection test and a
small read-only request before asking the Agent to change a world. Tests and
Agent work can consume paid API tokens.

Use **Home → New session**, or continue a saved session. `/api` manages API
connections; `/model` selects from your saved models. Effort settings depend on
the selected model and provider's supported parameters. A provider that rejects
tools, images or reasoning settings does not gain them from a UI selection.

## Controls and task behavior

| Control | Action |
| --- | --- |
| F6 / `/home` | Open Home |
| F7 / `/settings` | Open Settings |
| F8 | Show or hide MCAI |
| Settings close button | Return to the page that opened Settings |
| `/resume` | Choose a saved session |
| `/plan` | Discuss and approve a plan before execution |
| `/goal` | Continue work toward an objective |
| `/loop` | Configure recurring work; inspect its status and stop it explicitly |

The open key can be changed in Minecraft's key bindings. Key conflicts, operating
system input methods and terminal shortcuts can have their own behavior. Hiding
the interface or closing a terminal attachment does **not** mean server tasks or
loops have stopped. Inspect the task/session status before repeating a request.

## Updates and recovery

Keep the complete `mcai` directory and the server configuration when updating
within a supported game version. Restore the backup as a set if rollback is
needed. This release does not provide cross-version Minecraft world conversion.
Never open the only copy of a newer world in an older Minecraft version.

If a terminal disconnects, return Home and reconnect to the same session. Check
whether the previous task was accepted before sending it again. A provider
timeout and a terminal disconnect are different failures; preserve the error
message and the task identity for diagnosis.

See [support](SUPPORT.md) for a useful bug report and [capabilities](CAPABILITIES.md)
for the differences between the Java ports and Bedrock companion.
