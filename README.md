# PAMLite

### Leichtgewichtige Privileged-Access-Management-Lösung für sichere RDP-Zugriffe

PAMLite ist eine Open-Source-Plattform zur zentralen Verwaltung und Protokollierung von RDP-Zugriffen auf Windows-Server.

Ziel des Projekts ist es, kleinen und mittleren Unternehmen (KMU) eine einfache Alternative zu komplexen und kostenintensiven Privileged-Access-Management-Systemen (PAM) bereitzustellen.

Anstatt dass Administratoren direkt von ihrem Arbeitsplatz auf Server zugreifen, erfolgt der Zugriff über ein zentrales Webportal. Alle Verbindungen werden zentral verwaltet, protokolliert und nachvollziehbar dokumentiert.

---

## Funktionen

* Zentrales Webportal
* Sichere RDP-Verbindungen über Apache Guacamole
* Verwaltung von Servern
* Benutzeranmeldung und Authentifizierung
* Protokollierung von Sitzungen
* Suchfunktion für Server
* Zentrale Verwaltung von Zugangsdaten
* Open Source und Self-Hosted

---

## Warum PAMLite?

In vielen Unternehmen werden Server noch direkt über RDP administriert. Dabei kommen häufig lokale Administrator-Konten oder gemeinsam genutzte Zugangsdaten zum Einsatz.

Dies führt zu verschiedenen Problemen:

* Passwörter werden zwischen mehreren Personen geteilt
* Administrator-Passwörter werden lokal gespeichert
* Es fehlt eine zentrale Übersicht über Zugriffe
* Aktivitäten können nur schwer nachvollzogen werden
* Sicherheitsrichtlinien lassen sich nur eingeschränkt umsetzen

PAMLite schafft eine zentrale Zugriffsebene zwischen Administratoren und Servern. Dadurch werden privilegierte Zugriffe besser kontrolliert, dokumentiert und verwaltet.

---

## Architektur

```text
Administrator
      |
      v
+----------------------+
|       PAMLite        |
|      Webportal       |
+----------+-----------+
           |
           |
           +-------------------+
           |                   |
           v                   v
+----------------+    +----------------+
|   Datenbank    |    | Apache         |
|                |    | Guacamole      |
+----------------+    +-------+--------+
                              |
                              |
                              v
                     +----------------+
                     | Windows Server |
                     |    (RDP)       |
                     +----------------+
```

### Ablauf

1. Der Benutzer meldet sich am PAMLite-Webportal an.
2. Der gewünschte Server wird ausgewählt.
3. PAMLite übergibt die Verbindungsinformationen an Apache Guacamole.
4. Guacamole baut die RDP-Verbindung zum Zielserver auf.
5. Die Sitzung wird protokolliert.
6. Der Benutzer arbeitet über die bereitgestellte Verbindung auf dem Zielsystem.

---

## Verwendete Technologien

### Frontend

* HTML
* Bootstrap

### Backend

* Python
* Flask

### Datenbank

* SQLite (Standard)
* MariaDB/MySQL (optional)

### Remote-Zugriff

* Apache Guacamole

### Betriebssystem

* Ubuntu Server

---

## Hardware-Anforderungen

### PAMLite-Server

Empfohlene Mindestanforderungen:

* 4 CPU-Kerne
* 8 GB RAM
* 120 GB SSD
* Ubuntu Server 24.04 LTS

### Guacamole-Server

Empfohlene Mindestanforderungen:

* 2 CPU-Kerne
* 4 GB RAM
* 60 GB SSD
* Ubuntu Server 24.04 LTS

### Zielserver

* Windows Server 2022 oder neuer
* Aktivierter RDP-Dienst

---

## Installation

Die Installationsanleitung befindet sich im Ordner:

```text
/docs/installation.md
```

---

## Dokumentation

| Datei              | Beschreibung            |
| ------------------ | ----------------------- |
| installation.md    | Installationsanleitung  |
| configuration.md   | Konfigurationsanleitung |
| architecture.md    | Technische Architektur  |
| troubleshooting.md | Fehlerbehebung          |

---

## Geplante Erweiterungen

* Rollen- und Berechtigungskonzept
* Active-Directory-Anbindung
* Multi-Faktor-Authentifizierung (MFA)
* Sitzungsaufzeichnung
* Verschlüsselter Passwort-Tresor
* REST-API

---

## Lizenz

Dieses Projekt steht unter der MIT-Lizenz.

---

## Entwickler

Entwickelt im Rahmen einer Projektarbeit im Bereich Plattformentwicklung.

**PAMLite – Sichere Zugriffe. Einfach verwaltet.**
