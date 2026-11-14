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

Nach dem Hinzufügen des Marktplatzes kannst du **arc42 Architect** auch in Codex Desktop unter **Plugins → Skills Repository** installieren. Falls der Marktplatz schon eingerichtet ist, aktualisiere ihn mit `codex plugin marketplace upgrade skills-local`. Ab Version `0.3.0` genügt für **arc42 Architect** die Plugin-Installation.

Öffne zur Prüfung einen neuen Chat im Zielprojekt. Bitte mit `$arc42-architect:arc42-architect` um eine arc42-Gliederung mit Quellen aus dem Repository und einen anschließenden Review des Entwurfs im Chat.

[Codex – Git-Marktplätze hinzufügen](https://developers.openai.com/plugins/build/plugins#add-a-marketplace-from-the-cli)

### OpenCode

Du brauchst OpenCode 2, Git-Zugriff auf GitHub und Bash. Führe den [Installationsblock](#arc42-architect-in-opencode-installieren) im Zielprojekt aus.

Starte zur Prüfung OpenCode im Zielprojekt, wähle `arc42-architect` als primären Agenten und bitte um eine arc42-Gliederung.

[OpenCode – Agenten](https://opencode.ai/docs/agents/) · [OpenCode – Skills](https://opencode.ai/docs/skills/)

### arc42 Architect in OpenCode installieren

Führe den Block mit Bash im Stammverzeichnis des Zielprojekts aus. Er kopiert das Architektenprofil und die 14 Skills. Führe ihn für Updates erneut aus.

```bash
(
  set -e
  arc42_download="$(mktemp -d)"
  trap 'rm -rf -- "$arc42_download"' EXIT
  git clone --depth 1 --branch main https://github.com/Mehtrick/skills.git "$arc42_download"
  arc42_package="$arc42_download/plugins/arc42-architect"
  mkdir -p .opencode/agents .opencode/skills
  cp "$arc42_package/profiles/opencode/arc42-architect.md" .opencode/agents/
  cp -R "$arc42_package/skills/." .opencode/skills/
)
```

### arc42 Architect von 0.2.0 auf 0.3.0 umstellen

Version `0.3.0` entfernt die Rollen `arc42-explorer` und `arc42-reviewer`. Formuliere bestehende Aufträge mit diesen Rollennamen so um, dass der Architekt selbst im Repository recherchiert oder den Entwurf prüft.

- **GitHub Copilot:** Aktualisiere das Plugin mit `copilot plugin update arc42-architect` oder über die Plugin-Verwaltung in VS Code.
- **Codex:** Aktualisiere den Marktplatz mit `codex plugin marketplace upgrade skills-local` und installiere das Plugin mit `codex plugin add arc42-architect@skills-local`. Falls du die alten Profile kopiert hast, kannst du `arc42-explorer.toml` und `arc42-reviewer.toml` aus deinem Agentenverzeichnis entfernen.
- **OpenCode:** Führe den [Installationsblock](#arc42-architect-in-opencode-installieren) erneut aus. Entferne die früher kopierten Profile `arc42-explorer.md` und `arc42-reviewer.md` aus `.opencode/agents/`, damit nur der Architekt geladen wird.

## Inspiration und Skill-Quellen

Matt Pococks Sammlung ist eine Inspiration für den Aufbau dieses Repositories und eine Quelle für weitere Skills, etwa zur Anforderungsklärung, Domänenmodellierung und testgetriebenen Entwicklung. [mattpocock/skills](https://github.com/mattpocock/skills)
