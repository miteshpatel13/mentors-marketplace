# Mentors Marketplace

A [Claude Code plugin marketplace](https://code.claude.com/docs/en/plugins/host-marketplace) — the catalog that lists Mentor plugins. It does not contain plugin source; each entry in `.claude-plugin/marketplace.json` points at the plugin's own repository, and Claude Code fetches the plugin from there at install time.

| Plugin | Source | Description |
|---|---|---|
| `engineering-mentor` | [miteshpatel13/engineering-mentor](https://github.com/miteshpatel13/engineering-mentor) | Production engineering standards, skills, agents, SOPs, security, testing, architecture, and development governance. |

## Install

In a Claude Code session:

```text
/plugin marketplace add miteshpatel13/mentors-marketplace
/plugin install engineering-mentor@mentors-marketplace
```

Or from a shell:

```bash
claude plugin marketplace add miteshpatel13/mentors-marketplace
claude plugin install engineering-mentor@mentors-marketplace
```

Machines without a GitHub SSH key can set `CLAUDE_CODE_PLUGIN_PREFER_HTTPS=1` so the clone uses HTTPS.

## Updates

A plugin's `version` in its own `.claude-plugin/plugin.json` decides when users receive a new copy — releases happen in the plugin repository, not here. Users pull them with:

```bash
claude plugin marketplace update mentors-marketplace
claude plugin update engineering-mentor@mentors-marketplace
```

## Maintaining the catalog

Validate after every change to `marketplace.json`:

```bash
claude plugin validate . --strict
```
