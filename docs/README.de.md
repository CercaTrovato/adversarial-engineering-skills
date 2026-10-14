# Adversarial Engineering Skills

**Den Plan hinterfragen. Änderungen prüfen. Das Ergebnis belegen.**

[English](../README.md) · Deutsch · [Alle Sprachen](../README.md)

Ein Skill für das Engineering-Management mit Coding-Agenten: drei Qualitätsprüfungen mit nachvollziehbaren Belegen. Die prüfende Instanz nennt konkrete Fehlerpfade. Der verantwortliche Agent behebt die Probleme oder begründet ihre Zurückweisung anhand von Belegen.

## Drei Prüfungen

1. **Plan**: Vor wesentlicher Implementierung Randbedingungen, API- und Datenverträge, Berechtigungen, Zustandswechsel, übersehene Verbraucher und unnötige Komplexität prüfen.
2. **Änderung**: Nach einem zusammenhängenden Arbeitspaket und vor dem Merge den tatsächlichen Diff und das betroffene Verhalten prüfen. Bei Bedarf eine Sicherheitsprüfung ergänzen.
3. **Abnahme**: Vor einer Fertigmeldung Aussagen durch aktuelle Ausführungsergebnisse oder eine Prüfung der Artefakte belegen. Ungeprüfte Bereiche offenlegen.

Kleine Änderungen brauchen kleine Prüfungen; riskante Änderungen unabhängige Perspektiven und einzeln prüfbare Pakete. Selbstprüfung wird ausdrücklich gekennzeichnet und ersetzt keine vorgeschriebene unabhängige Prüfung. Offene Blocker verhindern das Bestehen der jeweiligen Prüfung. Der Skill erteilt keine Erlaubnis für Deployment oder Veröffentlichung.

## Installation

Mit Git und Node.js/npm im Zielprojekt ausführen:

```sh
npx skills add CercaTrovato/adversarial-engineering-skills --skill adversarial-engineering
```

Agenten interaktiv auswählen oder `-a claude-code`, `-a codex` beziehungsweise `-a cursor` ergänzen. `--copy` vermeidet symbolische Links; `-g` installiert auf Benutzerebene. Weitere Agenten, manuelle Installation und Entfernung stehen in der [Installationsanleitung](INSTALL.md). Die Unterstützung richtet sich nach der aktuellen Liste der Skills CLI, nicht nach einem vollständigen Funktionstest aller Agenten durch dieses Projekt.

## Verwendung

> Verwende adversarial-engineering für diese Änderung. Hinterfrage vor der Implementierung den Plan, prüfe danach den Diff und belege vor der Fertigmeldung die Abnahmekriterien. Nenne den Umgang mit jedem Befund, die Belege und die Grenzen der Prüfung.

Für eine reine Prüfung ergänzen: „Keine Dateien ändern.“ Nachprüfungen auf korrigierte Befunde beschränken; weiterhin gültige Prüfungen nicht wiederholen. Weitere Durchläufe brauchen neue Belege oder eine wesentlich überarbeitete Lösung.

Die [englische SKILL.md](../skills/adversarial-engineering/SKILL.md) ist maßgeblich; diese Seite erläutert Konzept und Installation. Der Skill garantiert keine Fehlerfreiheit und erzwingt keine CI-Sperren. Siehe [Validierung](VALIDATION.md), [Beiträge](../CONTRIBUTING.md) und [MIT-Lizenz](../LICENSE). Muttersprachliche Korrekturen sind willkommen.
