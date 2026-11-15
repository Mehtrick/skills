# skills

Dieses Repository sammelt wiederverwendbare Skills und spezialisierte Agenten für KI-Entwicklungswerkzeuge.

## Zielplattformen

- GitHub Copilot (CLI und VS Code)
- Codex
- OpenCode

## Skills

| Plugin | Skill | Was er tut | Erwartete Eingabe |
| --- | --- | --- | --- |
| arc42 Architect | [`document-architecture`](plugins/arc42-architect/skills/document-architecture/SKILL.md) | Erstellt, ergänzt oder prüft arc42-Dokumentation und benennt fehlende Belege. | System und gewünschte Kapitel oder Fragestellung. |
| arc42 Architect | [`document-architecture-introduction`](plugins/arc42-architect/skills/document-architecture-introduction/SKILL.md) | Dokumentiert Systemzweck, Qualitätsziele und Erwartungen der Stakeholder in Abschnitt 1. | Systemauftrag, Anforderungen und bekannte Stakeholder. |
| arc42 Architect | [`document-architecture-constraints`](plugins/arc42-architect/skills/document-architecture-constraints/SKILL.md) | Erfasst oder prüft verbindliche Rahmenbedingungen und ihre Architekturfolgen in Abschnitt 2. | Technische, organisatorische oder konventionsbedingte Vorgaben mit ihren Quellen. |
| arc42 Architect | [`document-system-context`](plugins/arc42-architect/skills/document-system-context/SKILL.md) | Beschreibt Systemgrenze, fachlichen Informationsaustausch und technische Schnittstellen in Abschnitt 3. | Systemumfang, externe Partner und bekannte Schnittstellen. |
| arc42 Architect | [`document-solution-strategy`](plugins/arc42-architect/skills/document-solution-strategy/SKILL.md) | Verknüpft Architekturprinzipien sowie Technologie- und Organisationsentscheidungen mit Qualitätszielen in Abschnitt 4. | Qualitätsziele, Rahmenbedingungen und relevante Architekturentscheidungen. |
| arc42 Architect | [`document-building-blocks`](plugins/arc42-architect/skills/document-building-blocks/SKILL.md) | Dokumentiert Bausteine, Verantwortlichkeiten und Schnittstellen in Abschnitt 5. | System- oder Bausteinname und relevante Code- oder Konfigurationsstellen. |
| arc42 Architect | [`document-crosscutting-concepts`](plugins/arc42-architect/skills/document-crosscutting-concepts/SKILL.md) | Erstellt oder überarbeitet Querschnittskonzepte in Abschnitt 8 und verknüpft sie mit ADRs. | Bausteinübergreifendes Thema, betroffene Bereiche und vorhandene Entscheidungen. |
| arc42 Architect | [`create-adr`](plugins/arc42-architect/skills/create-adr/SKILL.md) | Erstellt oder überarbeitet einen Architecture Decision Record (ADR) in Abschnitt 9. | Architekturentscheidung oder Entscheidungsfrage, Kontext und bekannte Alternativen. |
| arc42 Architect | [`write-quality-scenarios`](plugins/arc42-architect/skills/write-quality-scenarios/SKILL.md) | Formuliert messbare, priorisierte Qualitätsszenarien für Abschnitt 10. | Qualitätsziel oder konkreter Auslöser, erwartete Systemreaktion und Messgröße, soweit bekannt. |
| arc42 Architect | [`build-quality-tree`](plugins/arc42-architect/skills/build-quality-tree/SKILL.md) | Erstellt oder prüft einen durch Belege gestützten Qualitätsbaum in Abschnitt 10. | Vorhandene Qualitätsziele, Qualitätsszenarien und akzeptierte ADRs, soweit verfügbar. |
| arc42 Architect | [`document-risks-and-debt`](plugins/arc42-architect/skills/document-risks-and-debt/SKILL.md) | Erfasst oder aktualisiert Risiken und technische Schulden samt Auswirkungen, Maßnahmen und Status in Abschnitt 11. | Konkretes Risiko oder bestehende technische Schuld und bekannte Auswirkungen. |
| arc42 Architect | [`maintain-glossary`](plugins/arc42-architect/skills/maintain-glossary/SKILL.md) | Pflegt oder prüft Begriffe, Abkürzungen und Definitionen in Abschnitt 12. | Begriff, Abkürzung oder zu prüfendes Glossar mit relevantem Projektkontext. |
| arc42 Architect | [`review-architecture`](plugins/arc42-architect/skills/review-architecture/SKILL.md) | Prüft arc42-Dokumentation auf Belege, Konsistenz, Terminologie und Verweise. | Zu prüfende Kapitel oder Dokumente und verfügbare Referenzen. |
| System Analyst | [`analyze-requirements`](plugins/system-analyst/skills/analyze-requirements/SKILL.md) | Prüft fachliche Anforderungen anhand von Projektdokumentation, Code und Tests und koordiniert die Arbeit an Use Cases. | Fachliche Anforderung, Fragestellung oder Use-Case-Referenz. |
| System Analyst | [`ask-questions`](plugins/system-analyst/skills/ask-questions/SKILL.md) | Klärt eine unklare Anforderung mit gezielten Rückfragen. | Anforderung mit offenen Punkten und optionalem Projektkontext. |
| System Analyst | [`clarify-business-decisions`](plugins/system-analyst/skills/clarify-business-decisions/SKILL.md) | Klärt offene Entscheidungen anhand von Projektbelegen und leitet überprüfbare Änderungen an Use Cases ab. | Vorgeschlagener oder unklarer Geschäftsablauf und verfügbare Projektquellen. |
| System Analyst | [`write-use-case`](plugins/system-analyst/skills/write-use-case/SKILL.md) | Erstellt oder überarbeitet einen nummerierten AsciiDoc-Use-Case mit Änderungshistorie. | Fachliches Ziel und bekannte Regeln oder ein vorhandener Use Case mit Änderungswunsch. |
| System Analyst | [`review-use-case`](plugins/system-analyst/skills/review-use-case/SKILL.md) | Prüft Aufbau, Terminologie und fachliche Konsistenz eines Use Cases. | Use-Case-Entwurf oder Referenz auf den zu prüfenden Use Case. |
| System Analyst | [`verify-use-case-implementation`](plugins/system-analyst/skills/verify-use-case-implementation/SKILL.md) | Gleicht Abläufe und Geschäftsregeln mit Code und Tests ab und listet Abweichungen in einer Tabelle. | Use Case oder Use-Case-ID und Zugriff auf die Implementierung. |
| Developer | [`implement-feature`](plugins/software-developer/skills/implement-feature/SKILL.md) | Implementiert eine Anforderung testgetrieben und prüft Codequalität und Anforderungsabdeckung. | Use Case, Use-Case-ID oder direkt formulierte Anforderung. |
| Developer | [`diagnose-bug`](plugins/software-developer/skills/diagnose-bug/SKILL.md) | Ermittelt die wahrscheinliche Fehlerursache und reproduziert den Fehler mit einem Regressionstest. | Fehlerbericht mit beobachtetem und erwartetem Verhalten sowie bekannten Auslösern. |
| Developer | [`review-code-changes`](plugins/software-developer/skills/review-code-changes/SKILL.md) | Prüft Änderungen auf Codequalität, Sicherheit und Übereinstimmung mit Vorgaben und Anforderungen. | Diff, Pull Request oder Arbeitsstand und gegebenenfalls ein Vergleichsstand oder Anforderungen. |

## Installation

Du kannst **arc42 Architect** (`arc42-architect`), **System Analyst** (`system-analyst`) und **Developer** (`software-developer`) einzeln oder gemeinsam aus dem [GitHub-Repository Mehtrick/skills](https://github.com/Mehtrick/skills) installieren. Developer kann Use Cases aus dem Zielprojekt direkt lesen. Die Installation von System Analyst ist dafür optional.

### GitHub Copilot

Du brauchst Git-Zugriff auf GitHub und eine Copilot-Version mit Unterstützung für Agent Plugins 1.0.

**Copilot CLI**

Füge den Marktplatz einmal hinzu und führe den Installationsbefehl für jedes gewünschte Plugin aus.

```sh
copilot plugin marketplace add Mehtrick/skills
copilot plugin install arc42-architect@mehtrick-skills
copilot plugin install system-analyst@mehtrick-skills
copilot plugin install software-developer@mehtrick-skills
```

**VS Code**

1. Wähle Copilot als Agent und öffne **Chat: Open Customizations**.
2. Wähle **Browse → Configure Marketplaces → Add Marketplace** und gib `https://github.com/Mehtrick/skills.git` ein.
3. Installiere die gewünschten Plugins `arc42-architect`, `system-analyst` oder `software-developer` aus dem Marktplatz `mehtrick-skills`.

Öffne zur Prüfung eine neue Sitzung im Zielprojekt und wähle den Agenten über `/agent` in der CLI oder in der Agentenauswahl von VS Code. Bitte **arc42 Architect**, mit `document-architecture` eine arc42-Gliederung zu erstellen. Bitte **System Analyst**, mit `analyze-requirements` eine fachliche Anforderung zu klären. Gib **Developer** für `implement-feature` eine kleine Anforderung und prüfe, ob er vor der Implementierung einen aus dem erwarteten Grund fehlschlagenden Test ausführt.

[GitHub Copilot CLI – Plugins installieren](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/plugins-finding-installing) · [VS Code – Agent Plugins](https://code.visualstudio.com/docs/agent-customization/agent-plugins)

### Codex

Du brauchst die Codex CLI mit Plugin-Unterstützung sowie Git-Zugriff auf GitHub.

Füge den Marktplatz einmal hinzu und führe den Installationsbefehl für jedes gewünschte Plugin aus.

```sh
codex plugin marketplace add https://github.com/Mehtrick/skills.git --ref main
codex plugin add arc42-architect@mehtrick-skills
codex plugin add system-analyst@mehtrick-skills
codex plugin add software-developer@mehtrick-skills
```

Nach dem Hinzufügen des Marktplatzes findest du **arc42 Architect**, **System Analyst** und **Developer** auch in Codex Desktop unter **Plugins → Mehtrick Skills**. Einen bereits eingerichteten Marktplatz aktualisierst du mit `codex plugin marketplace upgrade mehtrick-skills`.

Öffne zur Prüfung einen neuen Chat im Zielprojekt. Bitte mit `$arc42-architect:document-architecture` um eine arc42-Gliederung und mit `$system-analyst:analyze-requirements` um die Klärung einer fachlichen Anforderung. Gib `$software-developer:implement-feature` eine kleine Anforderung und prüfe, ob Codex vor der Implementierung einen aus dem erwarteten Grund fehlschlagenden Test ausführt.

[Codex – Git-Marktplätze hinzufügen](https://developers.openai.com/plugins/build/plugins#add-a-marketplace-from-the-cli)

### OpenCode

Du brauchst OpenCode 2, Git-Zugriff auf GitHub und Bash. Führe den Block im Stammverzeichnis des Zielprojekts aus. Lass in `packages` die Namen der Pakete stehen, die du installieren möchtest. Führe denselben Block für Updates erneut aus. Bereinige bei Bedarf veraltete Dateien aus früheren Paketinstallationen im Zielprojekt.

```bash
(
  set -e
  packages=(arc42-architect system-analyst software-developer)
  skills_download="$(mktemp -d)"
  trap 'rm -rf -- "$skills_download"' EXIT
  git clone --depth 1 --branch main https://github.com/Mehtrick/skills.git "$skills_download"
  mkdir -p .opencode/agents .opencode/skills
  for package in "${packages[@]}"; do
    package_dir="$skills_download/plugins/$package"
    cp "$package_dir"/profiles/opencode/*.md .opencode/agents/
    cp -R "$package_dir/skills/." .opencode/skills/
  done
)
```

Starte zur Prüfung OpenCode im Zielprojekt und wähle den installierten Agenten als primären Agenten. Bitte `arc42-architect`, mit `@document-architecture` eine arc42-Gliederung zu erstellen, und `system-analyst`, mit `@analyze-requirements` eine fachliche Anforderung zu klären. Gib `developer` mit `@implement-feature` eine kleine Anforderung und prüfe, ob der Agent den Skill lädt und vor der Implementierung einen aus dem erwarteten Grund fehlschlagenden Test ausführt.

[OpenCode – Agenten](https://opencode.ai/docs/agents/) · [OpenCode – Skills](https://opencode.ai/docs/skills/)

## Inspiration und Skill-Quellen

Matt Pococks Sammlung ist eine Inspiration für den Aufbau dieses Repositories. Sein `grill-with-docs` ist die Vorlage für `clarify-business-decisions` in System Analyst. [mattpocock/skills](https://github.com/mattpocock/skills) · [grill-with-docs](https://github.com/mattpocock/skills/tree/main/skills/engineering/grill-with-docs)
