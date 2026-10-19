# AthenaHQ for Devin

Connect Devin to AthenaHQ to analyze brand visibility, share of voice, mentions,
citations, rankings, and competitors across AI search platforms.

## Connection

The plugin connects to AthenaHQ's hosted MCP server:

```text
https://api.athenahq.ai/api/mcp
```

Sign in with your AthenaHQ account when Devin prompts you to connect, then choose
your organization. The plugin uses OAuth; no API key or client secret belongs in
the manifest. Account analytics and write tools follow your existing access and
role permissions. Writes use the dashboard's validation and audit logging, and
some actions consume credits or permanently delete data.

See the [MCP documentation](https://docs.athenahq.ai/api-reference/mcp) for available
tools, permissions, and API-key setup for clients that require it.

## Try it

- "Use AthenaHQ to list the websites I can access."
- "Compare our share of voice with competitors over the latest available month."
- "Which sources are AI assistants citing about our brand?"

## Install before marketplace publication

In Devin Cloud, open **Customize → Plugins → Add plugin → Upload .zip** and upload
a zip containing this directory's contents, including `.devin-plugin/plugin.json`.
Start a new session, connect your AthenaHQ account, and ask Devin to list your
websites. Confirm that it calls `list_websites` successfully.

With the Devin CLI, install this directory locally, then start a session:

```bash
devin plugins install --local /absolute/path/to/devin-plugin
devin
```

## Marketplace contribution

This directory is the distribution package for
[CognitionAI/devin-marketplace](https://github.com/CognitionAI/devin-marketplace).
Copy its contents to `plugins/athenahq/` in a checkout of that repository, then add
`"./plugins/athenahq"` to `optionalPlugins` in the marketplace's
`.devin-plugin/plugin.json`.

Run the marketplace's checks:

```bash
python3 scripts/validate.py --fix
python3 scripts/validate.py --fetch
```

Before submitting, complete the Devin installation and `list_websites` tool call
above, as required by the marketplace's
[contribution guide](https://github.com/CognitionAI/devin-marketplace/blob/main/.agents/skills/adding-a-plugin/SKILL.md).
Opening a pull request accepts the marketplace's
[Contributor License Agreement](https://github.com/CognitionAI/devin-marketplace/blob/main/CLA.md).
