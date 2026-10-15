# LeiKa Search Tool

Eigenständige Webanwendung zum Nachschlagen von Verwaltungsleistungen im Leistungskatalog der öffentlichen Verwaltung (LeiKa). Die Suche greift auf die öffentliche API des FIM-Portals zu und zeigt Leistungsschlüssel, URNs und Links zu den zugehörigen Leistungen an.

## Funktionen

- Volltextsuche nach Leistungsbezeichnung oder LeiKa-Schlüssel
- Ergebnislisten mit jeweils 20 Leistungen und Seitennavigation
- Anzeige der LeiKa-ID und der URN im Format `urn:de:fim:leika:leistung:<Leistungsschlüssel>`
- Kopieren der URN per Schaltfläche
- Automatischer Abbruch überholter Suchanfragen bei Eingabeänderungen
- Responsive Darstellung und automatische Anpassung an das helle oder dunkle Systemdesign
- Beschriftete Bedienelemente, Tastaturbedienung und Statusmeldungen für assistive Technologien

## Verwendung

Voraussetzungen sind ein aktueller Browser mit aktiviertem JavaScript und eine Internetverbindung zur FIM-API. Ein Build, ein Paketmanager und zusätzliche Bibliotheken sind nicht erforderlich.

Die Datei `leika.html` herunterladen und direkt im Browser öffnen, beispielsweise per Doppelklick.

1. Eine Leistungsbezeichnung oder einen LeiKa-Schlüssel eingeben.
2. Die Suche startet automatisch nach einer Eingabepause von 400 Millisekunden.
3. Bei Bedarf zwischen Ergebnisseiten wechseln.
4. Die URN anklicken, um sie zu kopieren, oder den Leistungstitel im FIM-Portal öffnen.

Ob die Zwischenablagefunktion beim direkten Öffnen verfügbar ist, hängt vom Browser und dessen Berechtigungen ab. Falls das Kopieren nicht möglich ist, kann die URN manuell markiert und kopiert werden.

## Datenquelle

Die Anwendung verwendet den Endpunkt `https://fimportal.de/api/v0/leistung-steckbriefe` mit den Parametern `fts_query`, `order_by=relevance`, `offset` und `limit=20`. Der verwendete API-Pfad und die Suchabläufe orientieren sich an der LeiKa-Seite des `fc-toolportal`.

Suchbegriffe werden direkt vom Browser an das FIM-Portal übertragen. Die Anwendung betreibt keinen eigenen Backenddienst und speichert keine Suchhistorie. Verfügbarkeit, Aktualität der Daten und browserseitiger Zugriff hängen von der öffentlichen API ab.

## Repository-Struktur

| Datei | Inhalt |
| --- | --- |
| `leika.html` | Vollständige Anwendung mit HTML, CSS und JavaScript |
| `README.md` | Verwendung und Datenquelle |
| `LICENSE.txt` | Lizenztext der EUPL 1.2 |

## Lizenz

Dieses Projekt steht unter der EUPL 1.2. Der vollständige Lizenztext befindet sich in [LICENSE.txt](LICENSE.txt).
