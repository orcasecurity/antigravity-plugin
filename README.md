<p align="center">
  <img src="assets/logo.png" alt="Orca Security" width="96" />
</p>

<h1 align="center">Orca Security Plugin for Antigravity</h1>

<p align="center">Cloud security context from Orca, inside your Antigravity agent.</p>

<p align="center">
  <a href="LICENSE"><img alt="License: MIT" src="https://img.shields.io/badge/license-MIT-blue.svg" /></a>
  <img alt="Antigravity plugin" src="https://img.shields.io/badge/Antigravity-plugin-0080FF" />
</p>

## What it does

Connects Antigravity's agent to the [Orca Security MCP server](https://orca.security/mcp-server/), so it can triage alerts, explore assets and attack paths, query your cloud inventory, track compliance, and search cloud detection events using live data from your Orca account.

## Requirements

- An Orca Security account
- The Antigravity App or the `agy` CLI

## Install

**Antigravity CLI** (recommended)

```bash
agy plugin install https://github.com/orcasecurity/antigravity-plugin
```

Verify with `agy plugin list`.

**Manual**

Clone the repo into the global plugins folder:

```bash
git clone https://github.com/orcasecurity/antigravity-plugin ~/.gemini/config/plugins/orca-security
```

To scope the plugin to one project, clone it into that workspace's `.agents/plugins/` folder instead. The plugin then shows under **Customizations** > **Installed**.

<details>
<summary>Manual MCP setup (without the plugin)</summary>

If you prefer not to install the plugin, add the server to `~/.gemini/config/mcp_config.json`:

```json
{
  "mcpServers": {
    "orca-security": {
      "serverUrl": "https://mcp.orcasecurity.io"
    }
  }
}
```

In the Antigravity IDE you can open the same file from the agent panel: **...** > **MCP Servers** > **Manage MCP Servers** > **View raw config**.

</details>

## Sign in

The plugin uses OAuth and needs no configuration, so it installs enabled. When its MCP server first connects, Antigravity prompts you to sign in with your Orca account in the browser. No client ID or secret is needed.

If you need to sign in again, go to **Customizations** > **Installed** > **MCP Servers** and click **Authenticate**.

## Try it

- Show my top critical alerts in Orca
- Which attack paths lead to my most sensitive assets?
- What is my compliance status for CIS AWS Foundations?

## What's in this repo

```
.
├── plugin.json        Plugin manifest
├── mcp_config.json    Orca MCP server definition
├── assets/logo.png    Plugin logo
├── SECURITY.md        How to report vulnerabilities
└── LICENSE            MIT license
```

## Privacy

[Orca Security Privacy Policy](https://orca.security/privacy-policy/)

## Support

- **Email:** support@orca.security
- **Docs:** https://docs.orcasecurity.io/docs/mcp-integration

## Security

To report a vulnerability, see [SECURITY.md](SECURITY.md).

## License

[MIT](LICENSE)
