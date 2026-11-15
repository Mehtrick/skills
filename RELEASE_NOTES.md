# Veröffentlichungsnotizen

Diese Versionen enthalten eine inkompatible Änderung. Ersetze die bisherigen Skill-Namen in gespeicherten Prompts, Befehlen und eigenen Agent-Profilen anhand der Tabelle.

- `arc42-architect` 0.4.0 → 0.5.0
- `system-analyst` 0.3.0 → 0.4.0
- `software-developer` 0.2.0 → 0.3.0

- **Copilot CLI** führt das Update mit `copilot plugin update <plugin>` aus. [GitHub Copilot CLI – Plugins verwalten](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/plugins-finding-installing#manage-installed-plugins)
- **VS Code** aktualisiert installierte Plugins über **Chat: Update Plugins**. [VS Code – Plugins aktualisieren](https://code.visualstudio.com/docs/agent-customization/agent-plugins#_update-plugins)
- **Codex** aktualisiert die Plugins über `codex plugin marketplace upgrade mehtrick-skills`. Öffne anschließend einen neuen Chat. [Codex – Git-Marktplätze verwalten](https://developers.openai.com/plugins/build/plugins#add-a-marketplace-from-the-cli)
- **OpenCode** aktualisierst du mit dem [Installationsblock](README.md#opencode). Entferne anschließend die Verzeichnisse der zuvor aus diesem Repository installierten Skills unter `.opencode/skills/`, die in der Spalte „Bisher“ stehen.

| Plugin | Bisher | Neu |
| --- | --- | --- |
| `arc42-architect` | `arc42-architect` | `document-architecture` |
| `arc42-architect` | `arc42-introduction` | `document-architecture-introduction` |
| `arc42-architect` | `arc42-constraints` | `document-architecture-constraints` |
| `arc42-architect` | `arc42-context` | `document-system-context` |
| `arc42-architect` | `arc42-solution-strategy` | `document-solution-strategy` |
| `arc42-architect` | `arc42-building-blocks` | `document-building-blocks` |
| `arc42-architect` | `arc42-concept` | `document-crosscutting-concepts` |
| `arc42-architect` | `arc42-adr` | `create-adr` |
| `arc42-architect` | `arc42-quality-scenarios` | `write-quality-scenarios` |
| `arc42-architect` | `arc42-quality-tree` | `build-quality-tree` |
| `arc42-architect` | `arc42-risks` | `document-risks-and-debt` |
| `arc42-architect` | `arc42-glossary` | `maintain-glossary` |
| `arc42-architect` | `arc42-quality-review` | `review-architecture` |
| `system-analyst` | `system-analyst` | `analyze-requirements` |
| `system-analyst` | `grill-with-docs` | `clarify-business-decisions` |
| `system-analyst` | `use-case-write` | `write-use-case` |
| `system-analyst` | `use-case-review` | `review-use-case` |
| `system-analyst` | `use-case-code-check` | `verify-use-case-implementation` |
| `software-developer` | `developer` | `implement-feature` |
