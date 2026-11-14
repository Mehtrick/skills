# Hinweise für KI-Agenten

Dieses Repository dient als gemeinsame Quelle für wiederverwendbare Skills, Agenten und ergänzende Konfigurationen. Die Inhalte sollen über die jeweiligen Plugin- oder Erweiterungsmechanismen in KI-Entwicklungswerkzeuge eingebunden werden können. GitHub Copilot, Codex und OpenCode sind die vorrangigen Zielplattformen.

## Mitarbeit am Repository

- Verfasse alle Skills auf Englisch, einschließlich der Beispiele und der mitgelieferten Anleitungen.
- Setze in Skills und Agenten keine festen Pfade im Zielrepository voraus. Suche zuerst im Zielrepository anhand seiner Anweisungen, Dokumentation, Konfiguration und vorhandenen Dateien. Wenn die Quelldatei oder der Ablageort nach der Suche unklar ist, frage vor der Änderung gezielt nach. Führe bekannte Projektpfade ausdrücklich als Beispiele auf. Verlinke mitgelieferte Plugin-Ressourcen relativ und prüfe, dass die Links auch nach der Installation auflösbar sind.
- Plane die Installation von Anfang an mit. Berate den Repository-Verantwortlichen bei neuen oder wesentlich geänderten Skills, Agenten und Integrationen zur Installationsgranularität. Frage vor der Umsetzung, welche Einheiten separat installierbar sein sollen, etwa einzelne Skills, ein Agent mit seinen Skills oder ein thematisches Paket. Erläutere die Auswirkungen auf Abhängigkeiten, Updates und die Zielplattformen. Greife die Entscheidung erneut auf, wenn sich der Zuschnitt oder die Abhängigkeiten ändern.
- Pflege gemeinsame Inhalte möglichst an einer Stelle. Ergänze werkzeugspezifische Konfigurationen dort, wo die jeweilige Integration sie benötigt.
- Prüfe bei Änderungen an einer Integration die benötigten Formate, Pfade und Ladeverfahren anhand der offiziellen Dokumentation des Zielwerkzeugs.
- Halte den Abschnitt „Installation“ in der README bei jeder Änderung an verfügbaren Skills, Agenten, Plugins oder ihren Installationswegen aktuell. Dokumentiere pro separat installierbarer Einheit das Zielwerkzeug, die Voraussetzungen, die Installationsschritte und eine kurze Funktionsprüfung. Kennzeichne geplante Installationswege als solche.
- Verwende „Installationspaket“ als plattformübergreifenden Begriff für gemeinsam installierte Inhalte. Verwende „Plugin“, wenn das Zielwerkzeug dafür seinen Plugin-Mechanismus nutzt.
