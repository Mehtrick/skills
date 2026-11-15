# Hinweise für KI-Agenten

Dieses Repository dient als gemeinsame Quelle für wiederverwendbare Skills, Agenten und ergänzende Konfigurationen. Die Inhalte sollen über die jeweiligen Plugin- oder Erweiterungsmechanismen in KI-Entwicklungswerkzeuge eingebunden werden können. GitHub Copilot, Codex und OpenCode sind die vorrangigen Zielplattformen.

## Mitarbeit am Repository

- Verfasse alle Skills auf Englisch, einschließlich der Beispiele und der mitgelieferten Anleitungen.
- Setze in Skills und Agenten keine festen Pfade im Zielrepository voraus. Suche zuerst im Zielrepository anhand seiner Anweisungen, Dokumentation, Konfiguration und vorhandenen Dateien. Wenn die Quelldatei oder der Ablageort nach der Suche unklar ist, frage vor der Änderung gezielt nach. Führe bekannte Projektpfade ausdrücklich als Beispiele auf. Verlinke mitgelieferte Plugin-Ressourcen relativ und prüfe, dass die Links auch nach der Installation auflösbar sind.
- Plane die Installation von Anfang an mit. Berate den Repository-Verantwortlichen bei neuen oder wesentlich geänderten Skills, Agenten und Integrationen zur Installationsgranularität. Frage vor der Umsetzung, welche Einheiten separat installierbar sein sollen, etwa einzelne Skills, ein Agent mit seinen Skills oder ein thematisches Paket. Erläutere die Auswirkungen auf Abhängigkeiten, Updates und die Zielplattformen. Greife die Entscheidung erneut auf, wenn sich der Zuschnitt oder die Abhängigkeiten ändern.
- Pflege gemeinsame Inhalte möglichst an einer Stelle. Ergänze werkzeugspezifische Konfigurationen dort, wo die jeweilige Integration sie benötigt.
- Prüfe bei Änderungen an einer Integration die benötigten Formate, Pfade und Ladeverfahren anhand der offiziellen Dokumentation des Zielwerkzeugs.
- Beschreibe in der README den aktuellen Funktions- und Installationsstand. Einzelne Änderungen, Versionshistorie und versionsbezogene Umstellungen gehören in die Veröffentlichungsnotizen.
- Halte den Abschnitt „Installation“ in der README bei jeder Änderung an verfügbaren Skills, Agenten, Plugins oder ihren Installationswegen aktuell. Dokumentiere pro separat installierbarer Einheit das Zielwerkzeug, die Voraussetzungen, die Installationsschritte und eine kurze Funktionsprüfung. Kennzeichne geplante Installationswege als solche.
- Verwende das GitHub-Repository als Installationsquelle. Dokumentiere für Codex das Hinzufügen des Marktplatzes über die GitHub-URL. Installationsanleitungen sollen keinen bereits vorhandenen lokalen Checkout dieses Repositories voraussetzen.
- Verwende „Installationspaket“ als plattformübergreifenden Begriff für gemeinsam installierte Inhalte. Verwende „Plugin“, wenn das Zielwerkzeug dafür seinen Plugin-Mechanismus nutzt.

## Plugin-Versionierung

Jedes Plugin hat eine eigene Versionsnummer im Format `MAJOR.MINOR.PATCH`. Sie steht im Feld `version` des Plugin-Manifests. Für das arc42-Paket steht sie im gemeinsamen `plugin.json` und im Codex-Kompatibilitätsmanifest `.codex-plugin/plugin.json`. Wenn dasselbe Paket mehrere Manifeste mit einem Versionsfeld hat, halte deren Versionen synchron.

- **Patch** für kompatible Korrekturen und Anpassungen am Paket, etwa präzisere Skill-Anweisungen, reparierte Vorlagen oder ein neues Logo (`0.1.0` → `0.1.1`).
- **Minor** für kompatible Erweiterungen, etwa einen zusätzlichen Skill oder eine neue optionale Funktion (`0.1.0` → `0.2.0`).
- **Major** für inkompatible Änderungen ab `1.0.0`, etwa das Entfernen oder Umbenennen eines Skills, neue Pflichtvoraussetzungen oder ein geändertes dokumentiertes Ausgabeformat. Während der Entwicklung unter `0.x` kennzeichnet ein Minor-Sprung auch inkompatible Änderungen. Weise in diesem Fall ausdrücklich darauf hin und beschreibe die nötige Umstellung.

1. Vergleiche die Paketänderung mit dem zuletzt veröffentlichten Stand auf GitHub. Erhöhe die Version jedes betroffenen Plugins vor der Veröffentlichung auf `main` im selben Änderungssatz wie den Paketinhalt. Bei mehreren Änderungen zählt die höchste nötige Stufe. Änderungen ausschließlich an der Repository-Dokumentation brauchen keine neue Plugin-Version.
2. Prüfe den Paketinhalt, die Versionsfelder und die mitgelieferten Ressourcen. Teste beim betroffenen Zielwerkzeug die Installation und bei einer neuen Version auch den Wechsel vom vorherigen Stand. Für Codex aktualisierst du dazu den Git-Marktplatz mit `codex plugin marketplace upgrade mehtrick-skills` und prüfst die installierte Version sowie den betroffenen Skill oder das geänderte Asset.
3. Veröffentliche nur auf Auftrag. Beschreibe bei einer Veröffentlichung die Änderung und gegebenenfalls den Umstellungsweg. Falls ein Git-Tag benötigt wird, verwende `<plugin-name>-v<version>`, etwa `arc42-architect-v0.2.0`. Veröffentliche spätere Änderungen unter einer neuen Version und lasse vorhandene Tags auf ihrem ursprünglichen Commit.

Siehe [Semantic Versioning](https://semver.org/) und [Codex-Dokumentation zu Git-Marktplätzen](https://developers.openai.com/plugins/build/plugins#add-a-marketplace-from-the-cli).
