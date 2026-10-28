# Veo3 AI for Codex

The Codex plugin marketplace for [Veo3 AI](https://www.veo3ai.io). It ships one plugin, [`veo3ai`](plugins/veo3ai),
which connects Codex to your Veo3 AI canvas so you can make images, videos, music and edits from a Codex task.

| Install name | Display name | MCP server | Version |
| --- | --- | --- | --- |
| `veo3ai` | Veo3 AI | `https://www.veo3ai.io/mcp` | `1.0.0` |

The plugin is a remote HTTP MCP server. It holds no client ID, keys or local server: Codex registers itself and
signs you in through the server's OAuth metadata, and every person signs in with their own Veo3 AI account.

## Install

### Let Codex do it

Paste this into a Codex task:

```text
Install the Veo3 AI plugin so I can create images and videos here.

1. Add the marketplace: run `codex plugin marketplace add veo3-ai/marketplace --ref main`
2. Install the plugin: run `codex plugin add veo3ai@veo3ai`
3. In a new task, sign in to my Veo3 AI account when asked

Tell me when it's ready to start creating.
```

### Or run it yourself

```bash
codex plugin marketplace add veo3-ai/marketplace --ref main
codex plugin add veo3ai@veo3ai
```

Then start a new Codex task and sign in to Veo3 AI when Codex asks (or from the MCP connections list). The
repository is public, so no GitHub sign-in is needed.

## Use

Ask in plain words, for example:

- "Show my Veo3 AI projects"
- "Make an 8-second product video from this photo with Veo3 AI"
- "Write a 30-second story and turn it into a multi-shot video on my Veo3 AI canvas"

Only starting a generation spends credits. Codex tells you what a run costs before it starts, and failed runs are
refunded automatically. You can see and disconnect connected apps at
[veo3ai.io/connected-apps](https://www.veo3ai.io/connected-apps).

## Update

```bash
codex plugin marketplace upgrade veo3ai
codex plugin add veo3ai@veo3ai
```

Start a new Codex task afterwards. Before sign-in the server answers `401` with `WWW-Authenticate: Bearer`, and both
OAuth well-known endpoints answer `200`; that is expected.

## Uninstall

```bash
codex plugin remove veo3ai
codex plugin marketplace remove veo3ai
```
