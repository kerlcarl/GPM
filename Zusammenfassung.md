# Geschäftsprozessmanagement (GPM) — Prüfungszusammenfassung
**FHNW · BSc Wirtschaftsinformatik · FS26 · Dozent: Roman Brun**

> Diese Zusammenfassung deckt alle Vorlesungsthemen ab. Lernziele sind jeweils am Ende jedes Abschnitts markiert.

---

## Inhaltsverzeichnis
1. [Grundlagen: Was ist ein Geschäftsprozess?](#1-grundlagen)
2. [Geschäftsprozessmanagement (BPM)](#2-bpm)
3. [BPM-Lebenszyklus](#3-bpm-lebenszyklus)
4. [Prozessidentifikation](#4-prozessidentifikation)
5. [Prozesserhebung & Modellierung](#5-prozesserhebung)
6. [Strategische Prozessmodellierung mit BPMN](#6-strategische-bpmn)
7. [Operative Prozessmodellierung mit BPMN](#7-operative-bpmn)
8. [Modellierungskonventionen](#8-konventionen)
9. [DMN — Decision Model and Notation](#9-dmn)
10. [Qualitative Prozessanalyse](#10-qualitative-analyse)
11. [Quantitative Prozessanalyse & Simulation](#11-quantitative-analyse)
12. [Rollen im GPM](#12-rollen)
13. [Schnellübersicht: Formeln](#13-formeln)

---

## 1. Grundlagen

### Was ist ein Geschäftsprozess?

> „… eine abgegrenzte, meist arbeitsteilige Folge logisch verbundener Funktionen/Tätigkeiten mit einem definierten Beginn und Ende."

**Kernmerkmale:**
- Hat mindestens einen **Input** und einen **Output**
- Wird durch **Kunden** ausgelöst
- Hat ein definiertes **Ergebnis** (End-to-End)
- Hat häufig **wertschöpfenden Charakter**
- Beschreibt alle möglichen **Pfade** von Aktivitäten

**Bestandteile** (nach Dumas et al. 2021):
> „die Gesamtheit von zusammenhängenden Ereignissen, Aktivitäten und Entscheidungspunkten, an der eine Reihe von Akteuren und Objekten beteiligt sind, und die gemeinsam zu einem Ergebnis führen, das für mindestens einen Kunden einen Mehrwert darstellt."

### Typische Prozesstypen
| Prozesstyp | Englisch |
|---|---|
| Angebot-bis-Auftrag | Quote-to-Order |
| Auftrag-bis-Zahlungseingang | Order-to-Cash |
| Problem-bis-Lösung | Issue-to-Resolution |
| Antrag-bis-Bestätigung | Application-to-Approval |
| Bestellung-bis-Bezahlung | Purchase-to-Pay |

### Geschichte
- **Adam Smith** (1723–1790): Arbeitsteilung → 20 Nadeln/Person → 48.000 Nadeln/10 Personen
- **Frederick W. Taylor** (Taylorismus): Scientific Management, extreme Spezialisierung
- **Henry Ford / Mazda**: Entdeckung drastischer Effizienzunterschiede → Geburtsstunde des Prozessdenkens
  - Ford: 500 Mitarbeiter in der Kreditorenbuchhaltung → nach Prozessneugestaltung: 120 (−76%)
  - Einführung zentraler Datenbank statt papierbasiertem Abgleich von 3 Dokumenten
- **Hammer & Champy (1993)**: Business Process Reengineering (BPR) — radikales Neudenken

---

## 2. BPM

### Definition
> „Geschäftsprozessmanagement (BPM) ist die Gesamtheit von Methoden, Techniken und Werkzeugen zum Identifizieren, Erheben, Analysieren, Verbessern, Ausführen und Überwachen von Geschäftsprozessen, die das Ziel verfolgen, deren Leistung zu optimieren." *(Dumas et al. 2021)*

### Ganzheitlicher Ansatz
BPM muss …
- von der **Unternehmensführung** akzeptiert und gelebt werden
- in der **Strategie** der Organisation seinen Platz finden
- eine ideal angepasste **Aufbauorganisation** haben
- von allen Mitarbeitern akzeptiert werden (**Kultur**)

### 6 typische Missverständnisse
1. GPM ist nur in grossen Organisationen nötig
2. GPM benötigt hochanspruchsvolle Verfahren
3. GPM setzt Spezialisten voraus
4. GPM ist eine **technische** Disziplin ❌ (es ist ein **Managementansatz**)
5. GPM ist eine Wissenschaft
6. GPM löst alle Probleme

### Erwarteter Nutzen von BPM
| Kategorie | Beispiele |
|---|---|
| Höhere Produktivität | Schlanke Prozesse, Redundanzabbau |
| Höhere Kundenzufriedenheit | Geringere Fehlerkosten, schnelleres Angebot |
| Höhere Transparenz & Flexibilität | Schnelle Reaktion auf Marktänderungen |
| Höhere Sicherheit | Früherkennung von Schwachstellen |
| Höhere Wirtschaftlichkeit | Zielorientierte Steuerung mit KPIs |

---

## 3. BPM-Lebenszyklus

Der BPM-Lebenszyklus besteht aus 5 Phasen (nach Dumas et al.):

```
Prozessidentifikation → Prozesserhebung → Prozessanalyse → Prozessverbesserung → Prozessimplementierung
                                                ↑                                        |
                                                └──────── Prozessüberwachung ────────────┘
```

### Phasen im Detail

| Phase | Dumas | BOC (PMLC) | Camunda |
|---|---|---|---|
| **Identifikation** | Prozessarchitektur & Auswahl | Strategy | Automatisierungs-Scope |
| **Erhebung** | Ist-Prozess modellieren | Design & Documentation | Design (BPMN) |
| **Analyse** | Qualitativ + quantitativ | Analysis & Optimization | Machbarkeit, APIs |
| **Verbesserung** | Soll-Prozess (To-Be) | Was-wäre-wenn Szenarien | BPMN + technische Attribute |
| **Implementierung** | Change Management + IT | Implementation & Change | Deployment auf Workflow Engine |
| **Überwachung** | Conformance & Performance | KPI-Dashboards | Heatmaps, Error-Handling |

---

## 4. Prozessidentifikation

> „Systematische Definition der Geschäftsprozesse eines Unternehmens — Auswahl (Priorisierung) und Definition der Prozessarchitektur."

### Arten der Prozessidentifikation
| Ansatz | Beschreibung | Methode |
|---|---|---|
| **Individuell (I)** | Jedes Unternehmen hat eigene Prozesse | Strategie → Geschäftsmodell |
| **Allgemein (A)** | Grundlegende Prozesse in allen Unternehmen | Referenzmodelle |

### Referenzmodelle (allgemeine Prozessidentifikation)
| Modell | Einsatz |
|---|---|
| **APQC PCF** | Branchenneutrales Framework (5 Ebenen: Kategorie → Prozessgruppe → Prozess → Aktivität → Task) |
| **SCOR** | Supply Chain (Plan, Source, Make, Deliver, Return) / SCOR DS: Orchestrate, Plan, Order, Source, Transform, Fulfill, Return |
| **ITIL** | IT Service Management (Incident Management, Change Management, …) |
| **COBIT** | IT Governance |

### Prozesskategorien (nach Porter)
| Kategorie | Beschreibung | Merkmale |
|---|---|---|
| **Kernprozess** | Direkte Wertschöpfung | Wahrnehmbarer Kundennutzen, unternehmensspezifisch, nicht imitierbar |
| **Supportprozess** | Unterstützt Kernprozesse | Interne Kunden, kein direkter Kundennutzen, Outsourcing möglich |
| **Managementprozess** | Koordination & Steuerung | Strategische Ausrichtung, nicht operativ, sichert Existenzfähigkeit |

> **Faustformel:** „Sell stuff · Deliver stuff · Making sure you have stuff to sell and deliver" *(Geary Rummler)*

### Prozess-Checkliste
Bevor man einen Prozess aufnimmt, sind 5 Fragen zu prüfen:
1. **Ist es überhaupt ein Prozess?** (kein Projekt, keine Abteilung)
2. **Kann der Prozess kontrolliert werden?** (klare Geschäftsfälle, Wiederholung)
3. **Ist er wichtig genug?** (Kunde zahlt dafür, oder gesetzliche Pflicht)
4. **Ist der Umfang nicht zu gross?** (1:1-Beziehung zwischen Ereignis und Aktivitäten)
5. **Ist der Umfang nicht zu klein?** (mind. 3 Akteure nötig)

### Drei Arten von Beziehungen in der Prozesslandkarte
| Beziehung | Beschreibung |
|---|---|
| **Sequenz** | Logische & zeitliche Abfolge; Output → Input |
| **Zerlegung (Dekomposition)** | Prozess wird in Teilprozesse aufgeteilt (hierarchisch, meist Level 2+) |
| **Spezialisierung** | Varianten eines generischen Prozesses (z.B. Online-Bestellung vs. B2B-Bestellung) |

### Vorgehen: Prozesslandkarte erstellen
1. **Strategieanalyse**: Geschäftsmodell, Kunden, Ziele
2. **Hauptprozesse identifizieren (Level 1)**: End-to-End Kernprozesse, Führungs- & Supportprozesse
3. **Detaillierung (Level 2 & 3)**: Zerlegung, Sequenz, Spezialisierung
4. **Prozessprofil erstellen**: Prozessname, -ziel, KPIs, Verantwortliche, Schnittstellen
5. **Validierung**: Vollständigkeit & Konsistenz mit Management abgleichen

### Checkliste Prozesslandkarte
- Branche klar erkennbar?
- Kernprozesse identifiziert?
- Führungs- und Supportprozesse klar getrennt?
- Anzahl Unterebenen passend?

---

## 5. Prozesserhebung

### Modellarten
| # | Art | Beispiel |
|---|---|---|
| 1 | Physische Modelle | Architekturmodell, Prototypen |
| 2 | Text | Prozessdokumentation |
| 3 | Grafische Modelle | BPMN, UML |
| 4 | Mathematische Modelle | Formeln |

### Vergleich Dokumentationsformen
| Form | Vorteile | Nachteile |
|---|---|---|
| **Text** | Einfach zu erstellen | Ungenau, Rollen unklar, schwer analysierbar |
| **Tabelle** | Strukturierter | Keine Parallelität sichtbar |
| **Grafik ohne Notation** | Visuell | Interpretationsspielraum |
| **BPMN** | Standardisiert, eindeutig, automatisierbar | Lernkurve, Komplexität bei 50+ Symbolen |

### Ziele der Prozessmodellierung
- **Prozessstruktur**: Transparenz, Ist→Soll, Schulung
- **Prozessleistung**: KPIs (Zeit, Kosten, Qualität), Benchmarking
- **Prozessautomatisierung**: Workflow-Engine, System-Anbindung, Qualitätssicherung

---

## 6. Strategische BPMN

### Strategisch vs. Operativ
| | Strategisch | Operativ |
|---|---|---|
| **Frage** | Was & Warum | Wie |
| **Detailtiefe** | Abstrakt, kompakt | Detailliert, technisch |
| **Zielgruppe** | Führungskraft, Management | Process Participants, Process Analyst, Process Engineer |
| **Max. Elemente** | ~10 Flussobjekte, ~8 Artefakte, 1 A4 Seite | Vollständig |

### BPMN — Was ist das?
- **Business Process Model and Notation**
- Standard der OMG (Object Management Group)
- Verbindet Business und IT ("Brücke")
- Über 50 Symbole; 4 Diagrammtypen: Prozess-, Kollaborations-, Choreographie-, Konversationsdiagramme

### Basiselemente BPMN (strategisches Modell)

#### Pools & Lanes
- **Pool**: Container für einen Geschäftsprozess (= ein Teilnehmer)
- **Lane**: Unterteilung innerhalb eines Pools (Rolle, OE, System)
- Flussobjekte müssen immer **klar einer Lane** zugeordnet sein!

#### Aufgaben / Aktivitäten
- Aktivität: etwas wird getan
- Teilprozess: mit `[+]`-Symbol → Detail nicht sichtbar

#### Ereignisse
| Typ | Symbol | Beschreibung |
|---|---|---|
| **Startereignis** | Dünner Kreis | Löst Prozess aus |
| **Zwischenereignis** | Doppelter Kreis | Meilenstein, Zustand |
| **Endereignis** | Dicker Kreis | Prozessende |

#### Gateways (strategisch)
| Gateway | Symbol | Logik |
|---|---|---|
| **Exklusiv (XOR)** | X | Entweder … oder … (genau 1 Pfad) |
| **Parallel (AND)** | + | Alle Pfade gleichzeitig |

#### Verbindende Objekte
| Typ | Beschreibung |
|---|---|
| **Sequenzfluss** | Prozessabfolge |
| **Nachrichtenfluss** | Austausch zwischen Pools (gestrichelt) |
| **Assoziation** | Anbindung von Artefakten |

---

## 7. Operative BPMN

### Zusätzliche Konnektoren
| Konnektor | Beschreibung |
|---|---|
| **Standardfluss** | Wird durchlaufen, wenn alle anderen nicht zutreffen (NICHT der "normale" Pfad!) |
| **Bedingter Fluss** | Enthält Bedingung (selten verwendet) |
| **Datenassoziation** | Gerichtete Anbindung von Datenobjekten |

### Regeln für Pools & Lanes
- Externe Teilnehmer = **Black-box Pool**
- Nachrichtenfluss zwischen Pools: über **Nachrichtenfluss**
- **Kein** Nachrichtenfluss innerhalb eines Pools
- **Kein** Sequenzfluss über Pool-Grenzen
- Informationsfluss innerhalb Pool: über **Datenobjekte / Datenspeicher**

### Datenobjekte
| Typ | Beschreibung |
|---|---|
| **Datenobjekt** | E-Mails, Dokumente — temporär im Prozessfluss |
| **Datenspeicher** | Persistente Ablageorte (existieren unabhängig vom Prozess) |

### Alle Gateway-Typen
| Gateway | Kürzel | Logik | Verwendung |
|---|---|---|---|
| **Exklusiv (XOR)** | X | Genau 1 Pfad | Häufigste Entscheidung |
| **Parallel (AND)** | + | Alle Pfade | Parallelisierung |
| **Inklusiv (OR)** | O | 1 bis n Pfade | Wenn mehrere Optionen möglich |
| **Komplex** | * | Spezialfall (z.B. 2 von 3) | Selten, immer kommentieren |
| **Ereignisbasiert** | Sechseck | Erstes Ereignis entscheidet | Warten auf eines von mehreren Ereignissen |
| **Ereignisbasiert parallel** | Sechseck+ | Alle Ereignisse müssen eintreten | |

> **Inklusives Gateway**: Nur mit Bedacht einsetzen, da nicht immer eindeutig!

### Typisierung von Aufgaben
| Typ | Beschreibung | Relevanz |
|---|---|---|
| **Manuell** | Ohne Software (Kundengespräch, Ablage) | Technisch |
| **Benutzer** | Menschliche Tätigkeit, von Process Engine beauftragt | Technisch |
| **Senden** | Asynchrones Senden an Service/App | Technisch |
| **Empfangen** | Warten auf Nachricht | Technisch |
| **Service** | Automatisch durch Software, wartet auf Antwort | Technisch |
| **Skript** | Direkt von Process Engine | Technisch |
| **Geschäftsregel** | Externe Regelsammlung (→ DMN) | Technisch |

### Markierungen von Aufgaben
| Markierung | Beschreibung |
|---|---|
| **Schleife** | Wiederholung bis Bedingung erfüllt |
| **Mehrfach parallel** | Parallele Durchläufe, Anzahl bekannt |
| **Mehrfach sequenziell** | Sequenzielle Durchläufe |
| **Kompensation** | Rückgängig machen |

### Teilprozesse
| Typ | Beschreibung |
|---|---|
| **Normal** | Strukturierung/Übersichtlichkeit, wiederverwendbar |
| **Ad Hoc** | Aktivitäten in beliebiger Reihenfolge, mehrfach oder gar nicht |
| **Transaktion** | Ganz oder gar nicht (Abbruch-Ereignis nötig) |
| **Ereignis-Teilprozess** | Wird durch Ereignis ausgelöst, gepunktete Umrandung |

### Ereignis-Übersicht (vollständig)
| Ereignis | Start | Zwisch.(catch) | Zwisch.(throw) | Ende | Angeheftet |
|---|---|---|---|---|---|
| **Blanko** | Ja | Ja | Ja | Ja | — |
| **Nachricht** | Ja | Ja | Ja | Ja | Ja |
| **Timer** | Ja | Ja | — | — | Ja |
| **Bedingung** | Ja | Ja | — | — | Ja |
| **Signal** | Ja | Ja | Ja | Ja | Ja |
| **Fehler** | — | — | — | Ja | Ja (unterbrechend) |
| **Eskalation** | — | — | Ja | Ja | Ja (meist nicht-unterbr.) |
| **Kompensation** | — | — | Ja | Ja | Ja |
| **Terminierung** | — | — | — | Ja | — |
| **Link** | — | Ja | Ja | — | — |
| **Abbruch** | — | — | — | — | Ja (nur Transaktion) |

**Unterbrechend vs. Nicht-Unterbrechend (angeheftet):**
- **Unterbrechend**: Aktivität/Teilprozess wird abgebrochen → neuer Pfad
- **Nicht-Unterbrechend**: Aktivität läuft weiter → gestrichelte Kreislinien

### Kollaborationsdiagramm
- **Orchestrierung**: Prozess in einem Pool mit mehreren Lanes (Dirigent-Prinzip)
- **Kollaboration**: Mehrere Pools mit Nachrichtenflüssen dazwischen
  - Aufgeklappter Pool: vollständiger Prozess sichtbar
  - Zugeklappter Pool (Black-box): nur Ein-/Ausgangs-Nachrichtenflüsse sichtbar
- **Vorteil**: Übergabepunkte, Medienbrüche, Wartezeiten offenlegen

### BPMN Pro & Contra
| Pro | Contra |
|---|---|
| Standardisierte Sprache | Lücke zwischen Business & IT weiterhin möglich |
| Gemeinsame Sprache für alle Beteiligten | Komplexe Symbolpalette (Hemmschwelle) |
| Einfach & komplex anwendbar | Manche Tools haben eigene Validierungsregeln |

---

## 8. Modellierungskonventionen

### Ziele
> Einheitliche, leicht lesbare und leicht verständliche Modelle für heterogene Anwenderkreise.

**Ein «gutes» BPMN-Modell ist:**
- **Fehlerfrei**: BPMN-Spezifikation eingehalten
- **Klar**: Prozesslogik aus Diagramm allein ablesbar
- **Vollständig**: Start/Endzustände, externe Entitäten vorhanden
- **Konsistent**: Identisch strukturierte Modelle im Team

### Quellen für Konventionen
- **eCH-0074**: Grundsätze (Richtigkeit, Relevanz, Wirtschaftlichkeit, Klarheit, Vergleichbarkeit)
- **eCH-0158**: BPMN-Modellierungskonventionen für die öffentliche Verwaltung Schweiz
- Silver (2011): BPMN Method and Style
- Rücker & Freund (2019): Praxishandbuch BPMN 2.0

### Namenskonventionen
| Element | Schema | Beispiel |
|---|---|---|
| **Aufgabe** | [Objekt] + [Verb] | „Lebensmittel einkaufen" |
| **Ereignis** | [Objekt] + [passiviertes Verb] | „Hunger festgestellt" |
| **XOR-Gateway** | Frage | „Antrag genehmigt?" |
| **Ausgangspfad** | Antwort | „Ja" / „Nein" |

### Layout-Regeln
- **Primäre Richtung**: Links → Rechts (oder Oben → Unten)
- **Rückwärtspfeile**: Nur für Schleifen
- **Überlappungen vermeiden**: Kanten und Elemente nicht überlappen
- **Einheitliches Knicken**: Sequenz- und Nachrichtenflüsse einheitlich

### Regeln für Pools & Lanes
- **Black-box Pool** für externe Teilnehmer (Kunden, Partner)
- Kundenorientierte Prozesse: Start mit **Nachrichten-Startereignis**
- Prozess-Pool → Prozessname; Black-box Pool → Teilnehmername
- Aufgeklappter Pool: genau **ein vollständiger Prozess**
- Zugeklappter Pool: mind. ein ein-/ausgehender Nachrichtenfluss

### Start- und Endereignisse
- Immer modellieren! (Auslöser & Endzustand festhalten)
- Startereignis vorhanden → an **jedem** Pfadende ein Endereignis (und umgekehrt)
- **Ein Endereignis pro identischem Endzustand**

### Nachrichtenfluss & Ereignisse
- Nachrichtenfluss startet in **Aktivitäten** (nicht in auslösenden Ereignissen)
- Nachrichtenfluss endet in **eintretenden Ereignissen**

### Gateways
- Stellen nur **Logik** dar, keine Aktivität
- Nicht gleichzeitig zusammenführen **und** verzweigen
- XOR-Gateway immer mit **X-Marker** darstellen
- Zusammenführung verzweigter XOR-Pfade ist obligatorisch (eCH-0158), auf gleicher horizontaler Linie
  - Ausnahme 1: Pfad trifft auf Endereignis
  - Ausnahme 2: Kontrollschleife zurück

---

## 9. DMN

### Warum DMN?
- Wissensintensive Prozesse: Fachwissen sollte **vom Prozessmodell getrennt** sein
- BPMN: Aufgabentyp **Geschäftsregel** ist Verbindungspunkt zu DMN
- Prozedural (BPMN: Wie?) vs. Deklarativ (DMN: Was?)

**Vorteile der Trennung:**
- Einfachere Prozessmodelle
- Adäquatere Modelle für Entscheidungen
- Einfacheres Änderungsmanagement
- Wiederverwendung von Entscheidungsmodellen

### DMN — Überblick
> DMN = Decision Model and Notation (Standard der OMG, Version 1.5/2024)

**Zwei Hauptebenen:**
1. **Decision Requirements (DRD)** — Was wird entschieden?
2. **Decision Logic** — Wie wird entschieden? (v.a. Entscheidungstabellen)

### Decision Requirements Diagram (DRD)

#### Elemente
| Element | Form | Beschreibung |
|---|---|---|
| **Decision** | Rechteck | Entscheidung; kann in Teilentscheidungen zerlegt werden |
| **Decision Logic / Business Knowledge** | Abgerundetes Rechteck | Wiederverwendbares Regelwerk |
| **Input Data** | Oval | Eingabedaten von ausserhalb |
| **Knowledge Source** | Dokumentensymbol | Wissensquelle (Gesetze, Richtlinien, Erfahrung) |

#### Konnektoren
| Konnektor | Beschreibung |
|---|---|
| **Information Requirement** (solide Linie) | Welche Eingabe wird benötigt? |
| **Knowledge Requirement** (gestrichelte Linie) | Auf welchem Wissen basiert die Entscheidung? |
| **Authority Requirement** (gestrichelte + Kreis) | Abhängigkeit von Wissensquelle (informativ) |

### Decision Logic — Entscheidungstabellen

#### Aufbau
- **Eingabespalten**: Bedingungen — innerhalb einer Zeile UND-verknüpft
- **Ausgabespalten**: Ergebniswerte
- **Regeln (Zeilen)**: Kombination aus Bedingungen und Ergebnissen
- Mehrere Werte in einer Zelle = ODER-Verknüpfung (Komma)

#### FEEL-Syntax (Friendly Enough Expression Language)
| Operator | Beispiel |
|---|---|
| Vergleich | `>= 18`, `< 30000`, `<= 70` |
| Bereich | `[30000..50000]` |
| Komma = ODER | `"A","B"` |

### Hit Policies (Trefferrichtlinien)
| Policy | Kürzel | Beschreibung | Mehrfach? |
|---|---|---|---|
| **Unique** | U | Genau eine Regel trifft zu | Nein |
| **Any** | A | Mehrere Regeln, alle mit gleichem Ergebnis | Nein |
| **Priority** | P | Mehrere Regeln → Ergebnis mit höchster Priorität | Nein |
| **First** | F | Mehrere Regeln → erste zutreffende Regel gewinnt | Nein |
| **Output Order** | O | Ergebnisse nach Ausgabeprioritäten sortiert | Ja |
| **Rule Order** | R | Ergebnisse nach Regelreihenfolge sortiert | Ja |
| **Collect** | C | Alle Ergebnisse; Aggregation: Summe/Min/Max/Anzahl | Ja |

> **Prüfungstipp**: Häufig verwendet sind **Unique (U)** und **First (F)**. First erlaubt Überlappungen — Regeln werden von oben nach unten geprüft.

---

## 10. Qualitative Prozessanalyse

> „Die 'künstlerische' Seite der Prozessanalyse" — kein festes Vorgehen, aber erprobte Techniken.

### Wertschöpfungsanalyse

**Drei Kategorien:**

| Kategorie | Kürzel | Kriterien | Beispiele |
|---|---|---|---|
| **Wertschöpfend** | WS | Kunde zahlt dafür; Qualitätsreduktion bemerkt | Bewerbung bewerten, Lieferdatum bestätigen |
| **Geschäftswertschöpfend** | GWS | Nötig für Einnahmen / Compliance / Risikominimierung | Bonität prüfen, Vollständigkeit prüfen |
| **Nicht wertschöpfend** | NWS | Alles andere | Weiterleiten, Warten, Fehlerkorrektur |

**Vorgehen:**
1. Prozessaktivitäten in Schritte zerlegen (vor/während/nach Aktivität)
2. Schritte klassifizieren (WS / GWS / NWS)

> **Ziel**: NWS-Anteile erkennen und reduzieren.

### Waste-Analyse (Muda)
Basiert auf Toyota Production System (Taiichi Ohno, 1970er). Muda = japanisch für Verschwendung.

**Drei übergeordnete Kategorien:**

#### MOVE
| Typ | Beschreibung |
|---|---|
| **Transport** | Bewegung von Materialien/Dokumenten — Reduzierung anstreben |
| **Bewegung** | Prozessteilnehmer bewegen sich zwischen Maschinen/Orten |

#### HOLD
| Typ | Beschreibung |
|---|---|
| **Bestand (Work-in-Process)** | Volles Materiallager, überfüllter E-Mail-Eingang |
| **Warten** | Aktivität wartet auf Verfügbarkeit eines Teilnehmers |

#### OVERDOE
| Typ | Beschreibung |
|---|---|
| **Fehler** | Aktivitäten zur Fehlerkorrektur |
| **Überbearbeitung** | Unnötiger Perfektionismus, Aufgaben die sich als überflüssig erweisen |
| **Überproduktion** | Prozessinstanzen ohne Mehrwert (z.B. Angebote, die abgelehnt werden) |

### Ursachenanalyse (Root Cause Analysis)

#### Ursache-Wirkungs-Diagramm (Ishikawa / Fishbone)
**Die 6 M's:**
| M | Beschreibung |
|---|---|
| **Messung** | Falsche Berechnungen, Messverfahren |
| **Material** | Rohstoffe, Daten als Input |
| **Maschine** | Technologie, Systemabstürze, fehlende Funktionen |
| **Milieu** | Umfeld: Kunden, Lieferanten, Konkurrenz (ausserhalb Kontrolle) |
| **Mensch** | Qualifikationen, Konflikte, Motivation |
| **Methode** | Arbeitsweisen, Prozesse, Strukturen |

**Vorgehen:**
1. Hauptproblem definieren (Fischkopf)
2. Einflussgrössen festlegen (6 M's oder angepasst)
3. Haupt- und Nebenursachen formulieren
4. Ursachen einordnen

#### 5-Why-Methodik
- Frage so lange „Warum?", bis die eigentliche Ursache gefunden ist
- Fünf ist eine **Daumenregel** für die Analysetiefe
- **Nachteil**: Oft gibt es mehrere Hauptursachen (→ Kombination mit Ishikawa empfohlen)

**Empfohlene Reihenfolge:**
1. Ishikawa → breite Ursachensammlung
2. Daten prüfen & priorisieren
3. 5-Why → Tiefenanalyse der Hauptursache

### Optimierungsansätze
| Ansatz | Beschreibung |
|---|---|
| **Business Reengineering** | Radikaler Neuanfang — keine Optimierung bestehender Abläufe |
| **Prozessoptimierung / Restrukturierung** | Wesentliche Verbesserung: Durchlaufzeit ↓, Qualität ↑ |

---

## 11. Quantitative Prozessanalyse & Simulation

### Was ist eine Simulation?
> „Nachahmung eines dynamischen Prozesses in einem Modell, um zu Erkenntnissen zu gelangen, die auf die Wirklichkeit übertragbar sind." (VDI 3633)

- Prozess wird **n-mal** durchlaufen; Zufallsgenerator entscheidet bei Entscheidungen
- 1:1-Übertragung auf Realität **nicht** möglich → Ergebnisse müssen interpretiert werden
- Mehr Durchläufe → Ergebnisse nähern sich theoretischen Werten an (Würfel-Analogie)

**Typische Fragestellungen:**
- Ist meine Prozessalternative besser als der Ist-Prozess?
- Wie verhalten sich Prozesse unter geänderter Auftragslast?
- Wie sind Prozesslaufzeiten und Wartezeiten?
- Wie ist die Auslastung von Mitarbeitern und Maschinen?
- Was kosten meine Prozesse?

### Zeitattribute
| Attribut | Kürzel | Beschreibung |
|---|---|---|
| **Wartezeit** | WZ | Liegt im Eingang, noch nicht geöffnet |
| **Bearbeitungszeit** | BZ | Aktive Bearbeitung |
| **Liegezeit** | LZ | Fertig, aber noch nicht weitergeleitet |
| **Transportzeit** | TZ | Weiterleitung / Systemrouting |

### Durchlaufzeit (DLZ)
> **DLZ = Summe aller** Bearbeitungszeiten + Wartezeiten + Liegezeiten + Transportzeiten

Messbar auf: Gesamtprozess, Teilprozess, Aktivität

### Weitere Analysemöglichkeiten (in ADONIS)
| Analyse | Beschreibung |
|---|---|
| **Activity Based Costing (ABC)** | Kosten- und zeitintensive Aktivitäten identifizieren |
| **Kapazitätsanalyse** | Personalbedarf und -kosten ermitteln |
| **Endereignis & Pfade** | Kosten unterschiedlicher Endergebnisse, Pfadvisualisierung |
| **Was-wäre-wenn-Analyse** | Szenarien vergleichen |

---

## 12. Rollen im GPM

| Rolle | Beschreibung |
|---|---|
| **Process Owner** | Strategische Verantwortung; genehmigt Budget |
| **Process Manager** | Operative Verantwortung; berichtet an Process Owner |
| **Process Analyst** | Unterstützt Process Manager; BPMN-Experte; Brückenbauer Business↔IT |
| **Process Engineer** | Setzt SOLL-Prozess technisch um |
| **Process Participants** | Führen die Prozesse aus; erbringen Wertschöpfung |
| **CPO** (Chief Process Officer) | Gesamtverantwortung für alle Prozesse |
| **Process Steering Board** | Obere Führungskräfte (Grosse Unternehmen) |
| **Prozessauditor** | Unabhängige Prüfung von Prozessen |

> „Die wichtigste Qualifikation eines Process Analyst ist nicht das Senden, sondern das **Empfangen**."

---

## 13. Formeln — Schnellübersicht

### Prozessfragment 1: Sequenz

```
DDZ_Pro = DDZ_1 + DDZ_2 + ... + DDZ_n
```

**Beispiel:** 5 + 2 + 4 = **11 min**

---

### Prozessfragment 2.1: Entscheidung (XOR)

```
DDZ_Pro = Summe(DZ_A × p_A)
```

**Beispiel:** 5×1,0 + 2×0,6 + 3×0,4 = **7,4 min**

---

### Prozessfragment 2.2: Verschachtelte Entscheidung

```
H_A = Produkt aller p auf dem Pfad vom Start bis zu A
DDZ_Pf = DZ_A × H_A
DDZ_Pro = Summe aller DDZ_Pf
```

**Beispiel:**
- A: 5 × 1 = 5,00
- B: 2 × (0,6 × 0,6) = 0,72
- C: 4 × (0,4 × 0,6) = 0,96
- D: 1 × (0,6 × 0,4) = 0,24
- E: 3 × (0,4 × 0,4) = 0,48
- **Gesamt: 7,4 min**

---

### Prozessfragment 3: Schleife

```
DDZ_Pf = DZ_A × 1/(1 - p)
```

**Beispiel:** p = 0,2; DZ = 5 min → 5 × 1/0,8 = **6,25 min**

**Schleife mit Ausweichaktivität B (nicht immer ausgeführt):**
```
DDZ_Pro = DZ_A × 1/(1-p) + DZ_B × 1/(1-p) - DZ_B
```
**Beispiel:** A=5, B=2, p=0,2 → 6,25 + 2,5 − 2 = **6,75 min**

---

### Prozessfragment 4: Parallelität (AND)

```
DDZ_Pf = max(DZ_1, ..., DZ_n)
```

**Einfaches Beispiel:** 5 + max(2, 1) = **7 min**

**Parallelität + Entscheidung (korrekt):**
```
DDZ_Pf = Summe über alle Kombinationen: max(DZ_Pfad1, DZ_Pfad2) × (H_Pfad1 × H_Pfad2)
```
Alle Kombinationen aufzählen! (B&D, B&E, C&D, C&E …)

---

## Prüfungstipps

### Häufige Prüfungsthemen
1. **BPMN-Modell lesen/erstellen** — Gateways, Ereignisse, Pools korrekt einsetzen
2. **Prozesskategorien** — Kern/Support/Management korrekt einordnen & begründen
3. **BPM-Lebenszyklus** — Phasen nennen & beschreiben
4. **DMN-Entscheidungstabellen** — Hit Policies unterscheiden, Tabelle lesen & erstellen
5. **Qualitative Analyse** — WS/GWS/NWS klassifizieren, Ishikawa anwenden
6. **Quantitative Analyse** — Durchlaufzeit berechnen (alle 4 Prozessfragmente!)
7. **Modellierungskonventionen** — Fehler in BPMN-Modellen finden

### Typische Stolperfallen
- **XOR-Gateway ohne X-Marker** → nicht konventionskonform
- **Sequenzfluss über Pool-Grenzen** → verboten
- **Nachrichtenfluss innerhalb eines Pools** → verboten; Datenobjekte verwenden
- **Standardfluss als „normaler Pfad"** verstehen → falsch! Er ist der Ausweichpfad
- **Parallelität**: DDZ = Durchschnitt statt Maximum → falsch
- **Schleife**: DDZ vergessen durch 1/(1-p) zu dividieren
- **Ereignistypen** verwechseln: Fehler ist immer unterbrechend; Eskalation meist nicht-unterbrechend

### Kurzformeln auf einen Blick
| Fragment | Formel |
|---|---|
| Sequenz | `Summe aller DDZ` |
| Entscheidung | `Summe(DZ × p)` |
| Verschachtelt | `Summe(DZ × H)` wobei `H = Produkt aller p auf dem Pfad` |
| Schleife | `DZ / (1 - p)` |
| Parallelität | `max(DZ_1, ..., DZ_n)` |

---

*Zusammenfassung erstellt aus den Vorlesungsunterlagen von Roman Brun, FHNW BSc WI FS26.*  
*Quellen: Dumas et al. (2021), Rücker & Freund (2019), Silver (2011), eCH-0158, APQC PCF, SCOR DS, VDI 3633*
