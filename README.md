# skills

Dieses Repository sammelt wiederverwendbare Skills und spezialisierte Agenten für KI-Entwicklungswerkzeuge. **arc42 Architect** erstellt, ergänzt und prüft Softwarearchitektur-Dokumentation nach arc42. **System Analyst** klärt fachliche Anforderungen, schreibt und prüft Use Cases und gleicht sie mit dem Code ab.

## Zielplattformen

- GitHub Copilot (CLI und VS Code)
- Codex
- OpenCode

## Installation

Du kannst **arc42 Architect** (`arc42-architect`) und **System Analyst** (`system-analyst`) einzeln oder gemeinsam aus dem [GitHub-Repository Mehtrick/skills](https://github.com/Mehtrick/skills) installieren.

Wenn du den Marktplatz bereits als `skills-local` eingebunden hast, deinstalliere zuerst die Plugins aus dieser Quelle und entferne den alten Marktplatz. Folge dann der Anleitung für deine Plattform.

System Analyst enthält ab Version `0.2.0` den Skill `grill-with-docs`. Er klärt offene fachliche Entscheidungen anhand bestehender Use Cases, des Glossars und des Codes und hält fest, welche Use-Case-Schritte und Akzeptanzkriterien sich daraus ergeben.

### GitHub Copilot

Du brauchst Git-Zugriff auf GitHub und eine Copilot-Version mit Unterstützung für Agent Plugins 1.0.

**Copilot CLI**

Füge den Marktplatz einmal hinzu und führe den Installationsbefehl für jedes gewünschte Plugin aus.

```sh
copilot plugin marketplace add Mehtrick/skills
copilot plugin install arc42-architect@mehtrick-skills
copilot plugin install system-analyst@mehtrick-skills
```

**VS Code**

1. Wähle Copilot als Agent und öffne **Chat: Open Customizations**.
2. Wähle **Browse → Configure Marketplaces → Add Marketplace** und gib `https://github.com/Mehtrick/skills.git` ein.
3. Installiere `arc42-architect`, `system-analyst` oder beide aus dem Marktplatz `mehtrick-skills`.

Öffne zur Prüfung eine neue Sitzung im Zielprojekt und wähle den Agenten über `/agent` in der CLI oder in der Agentenauswahl von VS Code. Bitte **arc42 Architect** um eine arc42-Gliederung oder **System Analyst**, mit `grill-with-docs` eine offene Entscheidung zu einem Use Case zu klären.

[GitHub Copilot CLI – Plugins installieren](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/plugins-finding-installing) · [VS Code – Agent Plugins](https://code.visualstudio.com/docs/agent-customization/agent-plugins)

### Codex

Du brauchst die Codex CLI mit Plugin-Unterstützung sowie Git-Zugriff auf GitHub.

Füge den Marktplatz einmal hinzu und führe den Installationsbefehl für jedes gewünschte Plugin aus.

```sh
codex plugin marketplace add https://github.com/Mehtrick/skills.git --ref main
codex plugin add arc42-architect@mehtrick-skills
codex plugin add system-analyst@mehtrick-skills
```

Nach dem Hinzufügen des Marktplatzes findest du **arc42 Architect** und **System Analyst** auch in Codex Desktop unter **Plugins → Mehtrick Skills**. Einen bereits eingerichteten Marktplatz aktualisierst du mit `codex plugin marketplace upgrade mehtrick-skills`.

Öffne zur Prüfung einen neuen Chat im Zielprojekt. Bitte mit `$arc42-architect:arc42-architect` um eine arc42-Gliederung oder mit `$system-analyst:grill-with-docs` um die Klärung einer offenen Entscheidung zu einem Use Case.

[Codex – Git-Marktplätze hinzufügen](https://developers.openai.com/plugins/build/plugins#add-a-marketplace-from-the-cli)

### OpenCode

Du brauchst OpenCode 2, Git-Zugriff auf GitHub und Bash. Führe den Block im Stammverzeichnis des Zielprojekts aus. Lass in `packages` die Namen der Pakete stehen, die du installieren möchtest. Führe denselben Block für Updates erneut aus.

```bash
(
  set -e
  packages=(arc42-architect system-analyst)
  skills_download="$(mktemp -d)"
  trap 'rm -rf -- "$skills_download"' EXIT
  git clone --depth 1 --branch main https://github.com/Mehtrick/skills.git "$skills_download"
  mkdir -p .opencode/agents .opencode/skills
  for package in "${packages[@]}"; do
    package_dir="$skills_download/plugins/$package"
    cp "$package_dir/profiles/opencode/$package.md" .opencode/agents/
    cp -R "$package_dir/skills/." .opencode/skills/
  done
)
```

Starte zur Prüfung OpenCode im Zielprojekt und wähle den installierten Agenten als primären Agenten. Bitte `arc42-architect` um eine arc42-Gliederung oder `system-analyst`, mit `@grill-with-docs` eine offene Entscheidung zu einem Use Case zu klären.

[OpenCode – Agenten](https://opencode.ai/docs/agents/) · [OpenCode – Skills](https://opencode.ai/docs/skills/)

## Inspiration und Skill-Quellen

Matt Pococks Sammlung ist eine Inspiration für den Aufbau dieses Repositories. Sein `grill-with-docs` ist die Vorlage für die auf Use Cases zugeschnittene Variante in System Analyst. [mattpocock/skills](https://github.com/mattpocock/skills) · [grill-with-docs](https://github.com/mattpocock/skills/tree/main/skills/engineering/grill-with-docs)
