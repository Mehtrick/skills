# skills

Dieses Repository sammelt wiederverwendbare Skills, Agenten und ergänzende Konfigurationen für KI-Entwicklungswerkzeuge. Ziel ist es, diese Inhalte für mehrere Werkzeuge zu pflegen und über deren jeweilige Plugin- oder Erweiterungsmechanismen bereitzustellen.

## Zielplattformen

- GitHub Copilot
- Codex
- OpenCode

Diese drei Werkzeuge haben bei der Entwicklung der Integrationen Vorrang. Weitere KI-Tools können später ergänzt werden.

## Begriffe

- **Skill** bezeichnet einen wiederverwendbaren Arbeitsablauf mit einer `SKILL.md` und optionalen Vorlagen, Referenzen oder Skripten.
- **Agent** bezeichnet eine spezialisierte Rolle, etwa den Architektur-Agenten für arc42. Ein Agent kann mehrere Skills nutzen.
- **Installationspaket** bezeichnet eine Einheit, die gemeinsam installiert wird. Dafür verwenden wir den Begriff **Plugin**, wenn das Zielwerkzeug die Einheit über seinen Plugin-Mechanismus lädt.

## Installation

Installationsquelle für alle drei Werkzeuge ist das [GitHub-Repository Mehtrick/skills](https://github.com/Mehtrick/skills).

Das arc42-Paket enthält 14 Skills und drei Rollen. **arc42 Architect** (`arc42-architect`) führt den Dialog und erstellt oder bearbeitet die Dokumentation. **Architecture Explorer** (`arc42-explorer`) sammelt bei größeren Aufgaben Belege im Repository. **Architecture Reviewer** (`arc42-reviewer`) prüft den Entwurf. Die Spezialisten liefern Befunde an den Architekten.

### Codex · arc42 Architect

Das Paket enthält die Architektenrolle als Einstiegsskill und weitere Skills für einzelne arc42-Aufgaben. Der Agent sucht die Architekturdokumentation im Zielrepository und fragt bei unklaren Ablageorten nach.

**Voraussetzung** ist eine Codex CLI mit Plugin-Unterstützung und Git-Zugriff auf das GitHub-Repository.

1. Füge den Marktplatz über die GitHub-URL hinzu.

   ```sh
   codex plugin marketplace add https://github.com/Mehtrick/skills.git --ref main
   ```

2. Installiere **arc42 Architect** in Codex Desktop unter **Plugins** aus der Quelle **Skills Repository**. Alternativ installierst du es direkt über die CLI.

   ```sh
   codex plugin add arc42-architect@skills-local
   ```

3. Richte Explorer und Reviewer einmal im Zielprojekt ein. Führe dort den [GitHub-Installationsblock](#profile-und-skills-von-github-installieren) mit `arc42_client=codex` aus. Codex lädt die beiden TOML-Profile aus der Projektkonfiguration. Der Architekt ist über den Einstiegsskill im Plugin verfügbar.
4. Öffne einen neuen Chat im gewünschten Projekt und wähle `arc42-architect` über `$` im Eingabefeld. Verwende für die [Funktionsprüfung](#zusammenspiel-der-agenten-prüfen) einen Auftrag, der ausdrücklich um die beiden Subagenten bittet.

Für Updates aktualisierst du den Marktplatz mit `codex plugin marketplace upgrade skills-local` und führst die Plugin-Installation und den Installationsblock für die Profile erneut aus.

[Codex – Git-Marktplätze hinzufügen](https://developers.openai.com/plugins/build/plugins#add-a-marketplace-from-the-cli)

### GitHub Copilot · arc42 Architect

**Voraussetzung** ist Git-Zugriff auf GitHub und eine Copilot-Version mit Unterstützung für Agent Plugins 1.0. Der Plugin-Installationsweg ist ab Version `0.2.0` dieses Pakets verfügbar.

**Copilot CLI**

```sh
copilot plugin marketplace add Mehtrick/skills
copilot plugin install arc42-architect@skills-local
```

Prüfe die Installation mit `copilot plugin list`. Starte im Zielprojekt eine neue Sitzung, wähle **arc42 Architect** über `/agent` und führe die [Funktionsprüfung](#zusammenspiel-der-agenten-prüfen) aus. Aktualisiere das Paket mit `copilot plugin update arc42-architect@skills-local`.

**VS Code**

1. Wähle Copilot als Agent und öffne **Chat: Open Customizations**.
2. Öffne **Browse → Configure Marketplaces → Add Marketplace** und gib `https://github.com/Mehtrick/skills.git` ein.
3. Wähle den Marktplatz `skills-local` und installiere **arc42-architect**. Starte einen neuen Chat, wähle **arc42 Architect** in der Agentenauswahl und führe die [Funktionsprüfung](#zusammenspiel-der-agenten-prüfen) aus.

Wenn du die arc42-Skills bereits als Dateien eingebunden hast, entferne diese Kopien nach dem Wechsel, damit jede Skill-ID nur einmal geladen wird.

[GitHub Copilot CLI – Plugins installieren](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/plugins-finding-installing) · [VS Code – Agent Plugins](https://code.visualstudio.com/docs/agent-customization/agent-plugins)

### OpenCode · arc42 Architect

**Voraussetzung** ist Git-Zugriff auf GitHub sowie OpenCode 2 mit Unterstützung für Agenten und Skills.

1. Führe den [GitHub-Installationsblock](#profile-und-skills-von-github-installieren) mit `arc42_client=opencode` aus. Er kopiert die drei Agentenprofile und alle Skills in das Zielprojekt.
2. Starte OpenCode im Zielprojekt, wähle `arc42-architect` als primären Agenten und führe die [Funktionsprüfung](#zusammenspiel-der-agenten-prüfen) aus.

[OpenCode – Agenten](https://opencode.ai/docs/agents/) · [OpenCode – Skills](https://opencode.ai/docs/skills/)

### Profile und Skills von GitHub installieren

Führe den Block mit Git und Bash (z. B. WSL oder Git Bash) im Stammverzeichnis deines Zielprojekts aus. Für Codex kopiert er die beiden Subagentenprofile. Für OpenCode kopiert er alle drei Profile sowie die Skills mit ihren Vorlagen und Referenzen. Er verwendet den Stand von `main` auf GitHub.

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

Zum Aktualisieren der kopierten Dateien führst du denselben Block erneut aus. Sichere vorher eigene Änderungen an den Profilen und Skills.

### Zusammenspiel der Agenten prüfen

Starte im Zielprojekt mit dem Architekten und verwende diesen Auftrag:

> Entwirf eine arc42-Gliederung für dieses Repository. Starte zuerst `arc42-explorer`, um belegt zu klären, welche Bausteine und externen Schnittstellen es gibt. Lass anschließend `arc42-reviewer` den Entwurf unabhängig prüfen. Warte auf beide Ergebnisse, markiere offene Fragen und gib den Entwurf im Chat aus.

Prüfe, ob beide Subagenten gestartet werden und ihre Befunde in den Entwurf einfließen. Für kleinere Änderungen kann der Architekt den passenden Fachskill direkt einsetzen.

### Architekturindex und AsciiDoc

`.agents/architecture.md` im Zielrepository ist die gemeinsame Referenz für Ablageorte, Vorlagen und Konventionen pro System. Alle arc42-Rollen und Fachskills lesen sie zuerst. Bei fehlenden oder veralteten Einträgen ermittelt der Explorer die für den Auftrag benötigten Pfade. Bei mehreren plausiblen Orten klärt der Architekt die Auswahl mit dir. Wenn der Auftrag Dateiänderungen umfasst, speichert er die bestätigten Einträge. Der Index wächst mit der Arbeit an den tatsächlich benötigten Kapiteln.

Du kannst die Einrichtung gezielt prüfen. Bitte den Architekten in einem Zielprojekt ohne Index, den Explorer nach der bestehenden ADR-Ablage suchen und den Index dafür anlegen zu lassen. Bei einer zweiten ADR-Aufgabe sollte der Agent den bestätigten Pfad aus dem Index verwenden.

Neue arc42-Dokumentation verwendet AsciiDoc (`.adoc`). Wähle beim offiziellen Download die Dokumentsprache und **AsciiDoc**. Das Projekt übernimmt die Abschnitte, die es braucht. [Offizielle arc42-Vorlage](https://arc42.org/download/)

Die [AGENTS.md](AGENTS.md) beschreibt, wie KI-Agenten an diesem Repository mitarbeiten sollen.

## Inspiration und Skill-Quellen

Matt Pococks Skill-Sammlung ist eine Inspiration für den Aufbau und die Verteilung dieses Repositories und eine externe Quelle für wiederverwendbare Skills, etwa für Anforderungsklärung, Domänenmodellierung und testgetriebene Entwicklung. [mattpocock/skills](https://github.com/mattpocock/skills)
