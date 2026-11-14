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

### Codex · arc42 Architect

Das Testpaket enthält die Architektenrolle als Einstiegsskill und weitere Skills für einzelne arc42-Aufgaben, etwa Kontextabgrenzung, ADRs und Qualitätsszenarien. Der Agent sucht die Architekturdokumentation im Zielrepository und fragt bei unklaren Ablageorten nach. Er übernimmt Sprache und Dateiformate des Zielprojekts. Für neue Dokumentation ist Markdown der Standard. Fünf AsciiDoc-Vorlagen liegen bei.

**Voraussetzung** ist ein lokaler Checkout dieses Repositories und eine Codex-Version mit Plugin-Unterstützung. Das Paket benötigt keine zusätzlichen Dienste.

1. Öffne das Repository in Codex Desktop. Starte die App neu, damit sie den [lokalen Marktplatz](.agents/plugins/marketplace.json) einliest.
2. Öffne **Plugins**, wähle die Quelle **Skills Repository** und installiere **arc42 Architect**.
3. Öffne einen neuen Chat im gewünschten Projekt. Wähle `arc42-architect` über `$` im Eingabefeld. Gib zum Beispiel ein: „Entwirf für einen internen Terminservice eine arc42-Gliederung. Der Service legt Termine an und versendet Erinnerungen. Markiere offene Architekturfragen und ändere keine Dateien.“ Der Entwurf sollte die arc42-Abschnitte abdecken und fehlende Angaben wie die Systemgrenze oder messbare Qualitätsziele sichtbar machen.

Mit einer Codex CLI, die `codex plugin add` unterstützt, kannst du das Paket aus dem Repository-Stamm ebenfalls installieren:

```sh
codex plugin marketplace add .
codex plugin add arc42-architect@skills-local
```

Die Installationswege für GitHub Copilot und OpenCode sind geplant.

Die [AGENTS.md](AGENTS.md) beschreibt, wie KI-Agenten an diesem Repository mitarbeiten sollen.
