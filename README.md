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

3. Öffne einen neuen Chat im gewünschten Projekt und wähle `arc42-architect` über `$` im Eingabefeld. Gib zum Beispiel ein: „Entwirf für einen internen Terminservice eine arc42-Gliederung. Der Service legt Termine an und versendet Erinnerungen. Markiere offene Architekturfragen und ändere keine Dateien.“ Der Entwurf sollte die arc42-Abschnitte abdecken und fehlende Angaben wie die Systemgrenze oder messbare Qualitätsziele sichtbar machen.

[Codex – Git-Marktplätze hinzufügen](https://developers.openai.com/plugins/build/plugins#add-a-marketplace-from-the-cli)

### GitHub Copilot · arc42-Skills

**Voraussetzung** ist Git-Zugriff auf GitHub und eine Copilot-Version mit Agent-Skill-Unterstützung, etwa Copilot CLI oder Copilot in VS Code.

1. Installiere die Skills von GitHub nach `.github/skills/` im Stammverzeichnis deines Zielprojekts. Verwende dazu die [GitHub-Installationsanleitung](#skills-von-github-installieren). Für die persönliche Nutzung über mehrere Projekte hinweg kannst du bei Copilot CLI und VS Code `~/.copilot/skills/` als Ziel verwenden.
2. Öffne das Zielprojekt in VS Code oder starte die Copilot CLI in dessen Stammverzeichnis. Starte einen neuen Chat. Wähle in VS Code `/arc42-architect` im Chat. In der Copilot CLI prüfst du mit `/skills`, ob `arc42-architect` verfügbar ist, und bittest Copilot anschließend, den Skill zu verwenden.
3. Gib zum Test den Terminservice-Auftrag aus dem Codex-Abschnitt ein. Der Skill sollte eine arc42-Gliederung mit offenen Architekturfragen liefern.

[GitHub Copilot CLI – Agent Skills](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/add-skills) · [VS Code – Agent Skills](https://code.visualstudio.com/docs/agent-customization/agent-skills)

### OpenCode · arc42-Skills

**Voraussetzung** ist Git-Zugriff auf GitHub und eine OpenCode-Version mit Skill-Unterstützung.

1. Installiere die Skills von GitHub nach `.opencode/skills/` im Stammverzeichnis deines Zielprojekts. Verwende dazu die [GitHub-Installationsanleitung](#skills-von-github-installieren). Für die persönliche Nutzung über mehrere Projekte hinweg kannst du das globale Skill-Verzeichnis unter deiner OpenCode-Konfiguration verwenden, standardmäßig `~/.config/opencode/skills/`.
2. Starte OpenCode im Zielprojekt und beginne einen neuen Chat. Bitte OpenCode, den Skill `arc42-architect` zu laden. In OpenCode-Versionen mit Skill-Erwähnungen kannst du `@arc42-architect` im Prompt verwenden. Der gewählte Agent braucht Zugriff auf den Skill.
3. Gib zum Test den Terminservice-Auftrag aus dem Codex-Abschnitt ein. Der Skill sollte eine arc42-Gliederung mit offenen Architekturfragen liefern.

[OpenCode – Skills](https://opencode.ai/docs/skills/)

### Skills von GitHub installieren

Führe den folgenden Block mit Git und Bash (z. B. WSL oder Git Bash) im Stammverzeichnis deines Zielprojekts aus. Wähle das Zielverzeichnis passend zu deinem Werkzeug. Der Befehl lädt den Stand von `main` aus GitHub in ein temporäres Verzeichnis und installiert alle Skill-Ordner gemeinsam. So bleiben Vorlagen und Querverweise verfügbar.

```bash
(
  set -e
  arc42_target=".github/skills" # Für OpenCode: .opencode/skills
  arc42_download="$(mktemp -d)"
  trap 'rm -rf -- "$arc42_download"' EXIT
  git clone --depth 1 --branch main https://github.com/Mehtrick/skills.git "$arc42_download"
  mkdir -p "$arc42_target"
  cp -R "$arc42_download/plugins/arc42-architect/skills/." "$arc42_target/"
)
```

Der Einstiegsskill liegt anschließend unter `<Zielverzeichnis>/arc42-architect/SKILL.md`. Zum Aktualisieren führst du denselben Block erneut aus. Sichere eigene Änderungen an installierten Skills vor der Aktualisierung.

Die [AGENTS.md](AGENTS.md) beschreibt, wie KI-Agenten an diesem Repository mitarbeiten sollen.
