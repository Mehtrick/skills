# skills

Dieses Repository sammelt wiederverwendbare Skills und spezialisierte Agenten für KI-Entwicklungswerkzeuge. Die Inhalte werden zentral gepflegt und mit plattformspezifischen Konfigurationen zur Installation bereitgestellt. Das Installationspaket **arc42 Architect** hilft beim Erstellen, Ergänzen und Prüfen von Softwarearchitektur-Dokumentation nach arc42.

## Zielplattformen

- GitHub Copilot (CLI und VS Code)
- Codex
- OpenCode

## Installation

Alle Anleitungen installieren **arc42 Architect** aus dem [GitHub-Repository Mehtrick/skills](https://github.com/Mehtrick/skills).

### GitHub Copilot

Du brauchst Git-Zugriff auf GitHub und eine Copilot-Version mit Unterstützung für Agent Plugins 1.0.

**Copilot CLI**

```sh
copilot plugin marketplace add Mehtrick/skills
copilot plugin install arc42-architect@skills-local
```

**VS Code**

1. Wähle Copilot als Agent und öffne **Chat: Open Customizations**.
2. Wähle **Browse → Configure Marketplaces → Add Marketplace** und gib `https://github.com/Mehtrick/skills.git` ein.
3. Installiere `arc42-architect` aus dem Marktplatz `skills-local`.

Öffne zur Prüfung eine neue Sitzung im Zielprojekt. Wähle **arc42 Architect** über `/agent` in der CLI oder über die Agentenauswahl in VS Code und bitte um eine arc42-Gliederung.

[GitHub Copilot CLI – Plugins installieren](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/plugins-finding-installing) · [VS Code – Agent Plugins](https://code.visualstudio.com/docs/agent-customization/agent-plugins)

### Codex

Du brauchst die Codex CLI mit Plugin-Unterstützung sowie Git-Zugriff auf GitHub.

```sh
codex plugin marketplace add https://github.com/Mehtrick/skills.git --ref main
codex plugin add arc42-architect@skills-local
```

Nach dem Hinzufügen des Marktplatzes kannst du **arc42 Architect** auch in Codex Desktop unter **Plugins → Skills Repository** installieren. Für Explorer und Reviewer führe im Zielprojekt den [Installationsblock](#profile-und-skills-von-github-kopieren) mit `arc42_client=codex` aus.

Öffne zur Prüfung einen neuen Chat im Zielprojekt, wähle `$arc42-architect` und bitte um eine arc42-Gliederung unter Einbindung von `arc42-explorer` und `arc42-reviewer`.

[Codex – Git-Marktplätze hinzufügen](https://developers.openai.com/plugins/build/plugins#add-a-marketplace-from-the-cli)

### OpenCode

Du brauchst OpenCode 2, Git-Zugriff auf GitHub und Bash. Führe im Zielprojekt den [Installationsblock](#profile-und-skills-von-github-kopieren) mit `arc42_client=opencode` aus.

Starte zur Prüfung OpenCode im Zielprojekt, wähle `arc42-architect` als primären Agenten und bitte um eine arc42-Gliederung.

[OpenCode – Agenten](https://opencode.ai/docs/agents/) · [OpenCode – Skills](https://opencode.ai/docs/skills/)

### Profile und Skills von GitHub kopieren

Führe den Block mit Bash im Stammverzeichnis des Zielprojekts aus. Er kopiert für Codex die beiden Subagentenprofile und für OpenCode alle Profile und Skills.

```bash
(
  set -e
  arc42_client=opencode # Für Codex: codex
  arc42_download="$(mktemp -d)"
  trap 'rm -rf -- "$arc42_download"' EXIT
  git clone --depth 1 --branch main https://github.com/Mehtrick/skills.git "$arc42_download"
  arc42_package="$arc42_download/plugins/arc42-architect"
  case "$arc42_client" in
    codex)
      mkdir -p .codex/agents
      cp "$arc42_package"/profiles/codex/*.toml .codex/agents/
      ;;
    opencode)
      mkdir -p .opencode/agents .opencode/skills
      cp "$arc42_package"/profiles/opencode/*.md .opencode/agents/
      cp -R "$arc42_package/skills/." .opencode/skills/
      ;;
  esac
)
```

## Inspiration und Skill-Quellen

Matt Pococks Sammlung ist eine Inspiration für den Aufbau dieses Repositories und eine Quelle für weitere Skills, etwa zur Anforderungsklärung, Domänenmodellierung und testgetriebenen Entwicklung. [mattpocock/skills](https://github.com/mattpocock/skills)
