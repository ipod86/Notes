# 📝 Self-Hosted Notiz-Tool

Ein schlankes, schnelles und vollständig selbstgehostetes Web-Notizbuch. Es kombiniert die Leichtigkeit von Markdown mit mächtigen Features wie einem integrierten Skizzenblock, Kontaktverwaltung, Push-Erinnerungen, Live-Synchronisation und automatischen Backups – angetrieben von einer robusten SQLite-Datenbank und verpackt in einem einzigen, einfach zu installierenden Bash-Skript.

## ✨ Features

Das Notiz-Tool bietet eine Vielzahl an Funktionen, die es zu einer vollwertigen, selbstgehosteten Notiz- und Wissensdatenbank machen:

### 🛡️ Sicherheit & Multi-Device
* **Multi-Instanz fähig:** Komfortables Setup-Skript zum Anlegen, Updaten und Löschen beliebig vieler unabhängiger Instanzen auf einem Server.
* **Passwortschutz:** Optionaler Zugriffsschutz für die gesamte Instanz.
* **Brute-Force-Schutz:** Intelligente IP-Sperre bei zu vielen fehlerhaften Login-Versuchen.
* **Kollisions-Schutz (Locking):** Sperrt Notizen für andere Geräte/Tabs, während sie von jemandem bearbeitet werden, um unbeabsichtigtes Überschreiben zu verhindern.
* **Browser-Navigation:** Vollständige Unterstützung für Zurück/Vorwärts im Browser. Jede Notiz erhält eine eigene URL, die als Lesezeichen gespeichert oder geteilt werden kann.

### 📊 Dashboard
* **Startseite mit Übersicht:** Dashboard zeigt auf einen Blick: Anzahl aller Notizen, offene Aufgaben, angepinnte Notizen, überfällige und anstehende Termine (mit relativen Zeitangaben wie "morgen", "in 3 Tagen"), zuletzt hochgeladene Medien und zuletzt bearbeitete Notizen.

### 🔔 Benachrichtigungen & Aufgaben
* **Push-Benachrichtigungen (Webhooks):** Sende zeitgesteuerte Erinnerungen an dein Smartphone (z.B. via ntfy.sh) oder als formatierte Nachricht an Discord (unterstützt GET und POST mit JSON-Payload).
* **To-Do Dashboard:** Eine zentrale Übersicht aller offenen und erledigten Checkboxen aus allen Notizen.

### 📝 Editor & Inhalte
* **Markdown-Support:** Umfangreiche Formatierungen (Fett, Kursiv, Durchgestrichen, Farbiger Text, Tabellen, Zitate, Spoiler-Blöcke, Code-Blöcke mit Syntax-Highlighting, Trennlinien).
* **Intelligente Listen:** Bullet-Points, nummerierte Listen und Checkboxen werden beim Drücken von Enter automatisch fortgesetzt. Nummern zählen automatisch hoch. Bei leerem Eintrag + Enter wird der Listenpunkt entfernt.
* **Tab-Einrückung:** Tab/Shift+Tab zum Ein- und Ausrücken von Text und verschachtelten Listen direkt im Editor.
* **Drag & Drop Uploads:** Bilder und Dateien einfach in den Textbereich ziehen.
* **Skizzen-Block:** Integriertes Zeichen-Tool mit Stift, Textmarker und Radiergummi für handschriftliche Notizen.
* **Verlinkungen (Mentions):** Tippe `@`, um blitzschnell andere Notizen im Text zu verlinken. Rückverweise werden automatisch angezeigt.
* **Sprachnotiz:** Sprachaufnahmen direkt in der App aufnehmen und abspielen.

### 👤 Kontakte
* **Kontaktverwaltung:** Kontakte mit Name, Mobil- und Festnetznummer, E-Mail, Firma, Adresse, eigenem Bild und Notizfeld anlegen und verwalten.
* **Kontakte in Notizen einfügen:** Über den Toolbar-Button eine Kontakt-Kachel in die Notiz einbetten. Klick auf einen eingefügten Kontakt öffnet direkt das Bearbeitungsformular.
* **Lösch-Sicherheit:** Wird ein Kontakt gelöscht, erscheint in allen Notizen, in denen er eingefügt war, ein Hinweis „Kontakt gelöscht".

### 🏷️ Tags & Organisation
* **Tags mit Farben:** Tags erstellen, bearbeiten und löschen – jeweils mit frei wählbarer Farbe und Name.
* **Tag-Filter:** Filterleiste in der Sidebar zum Filtern des Notizbaums. Mehrere Tags gleichzeitig auswählbar (ODER-Verknüpfung). Dynamisches Overflow-Handling: passt sich automatisch an die Sidebar-Breite an.
* **Tags pro Notiz:** Über das Notiz-Menü (⋮) beliebig viele Tags einer Notiz zuweisen. Farbige Tag-Chips in der Notizansicht und farbige Punkte im Baummenü.
* **Anpinnen:** Notizen als Favoriten markieren. Angepinnte Notizen erscheinen im Dashboard.

### 📋 Vorlagen
* **Notiz als Vorlage speichern:** Über das Notiz-Menü (⋮) die aktuelle Notiz als wiederverwendbare Vorlage sichern.
* **Aus Vorlage erstellen:** Beim Anlegen neuer Notizen eine vorhandene Vorlage als Grundlage wählen.
* **Vorlagen verwalten:** Übersicht aller gespeicherten Vorlagen mit Löschmöglichkeit.

### 🌍 Freigaben & Verwaltung
* **Öffentliche Freigabe-Links:** Generiere Lese-Links für einzelne Notizen, um sie mit Leuten ohne Account zu teilen.
* **Versionsverlauf (Historie):** Jeder Speichervorgang wird gesichert. Kehre jederzeit zu einer alten Version einer Notiz zurück. Beim Wiederherstellen einer alten Version wird die aktuelle Version automatisch als neuer Verlaufseintrag gesichert.
* **Notiz duplizieren:** Erstelle eine Kopie der aktuellen Notiz inklusive aller Tags über das Notiz-Menü (⋮).
* **Papierkorb:** Gelöschte Notizen landen im Papierkorb und können samt Unterstruktur wiederhergestellt werden. Notizen die gerade bearbeitet werden, sind vor dem Löschen geschützt.
* **Medien-Manager:** Übersicht aller hochgeladenen Dateien mit Vorschau, Download, Verknüpfungs-Info und Löschen. Beim Löschen eines Mediums erscheint in den Notizen ein Hinweis „Medium gelöscht".
* **Automatisches Sortieren:** Notizen lassen sich auf Knopfdruck alphabetisch ordnen (Ordner stehen immer oben).
* **Backup & Restore:** Vollautomatische nächtliche Backups, die direkt über die Web-Oberfläche heruntergeladen oder wiederhergestellt werden können.

### 🎨 Darstellung
* **Dark & Light Mode:** Theme jederzeit umschaltbar über die Einstellungen.
* **Akzentfarbe:** Frei wählbare Akzentfarbe für die gesamte Benutzeroberfläche.

## 🔒 Sicherheit für den Online-Betrieb

Das Tool ist für den öffentlichen Internet-Betrieb gehärtet. Folgende Maßnahmen sind bereits eingebaut:

| Maßnahme | Details |
|---|---|
| **Security Headers** | `X-Frame-Options`, `X-Content-Type-Options`, `CSP`, `Referrer-Policy`, `HSTS` (bei HTTPS) |
| **Session-Cookies** | `HttpOnly`, `SameSite=Strict`, optional `Secure` (bei HTTPS) |
| **Brute-Force-Schutz** | IP-Sperre nach 5 Fehlversuchen, 5 min Sperrzeit |
| **SSRF-Schutz** | Webhook-URLs werden gegen private/lokale IP-Ranges geprüft |
| **Upload-Whitelist** | Nur explizit erlaubte Dateitypen werden akzeptiert (siehe FAQ) |
| **Path-Traversal-Schutz** | Backup-Archive werden auf unsichere Pfade geprüft |
| **XSS-Schutz** | DOMPurify sanitisiert alle geteilten Notizen vor dem Rendern |
| **Fehler-Handling** | Keine Stack-Traces im HTTP-Response — Fehler nur im Server-Log |
| **Proxy-Unterstützung** | ProxyFix für korrektes IP-Handling hinter nginx/Cloudflare |

### Empfohlene Produktionsumgebung

Für den Betrieb im Internet wird empfohlen:
- **Reverse Proxy** (nginx oder Caddy) mit HTTPS/TLS davor schalten
- **Passwortschutz** in den App-Einstellungen aktivieren
- Env-Variable `HTTPS=true` im systemd-Service setzen (aktiviert `Secure`-Flag auf Session-Cookies)

```ini
# In /etc/systemd/system/notizen-INSTANZ.service unter [Service]:
Environment="HTTPS=true"
```

Wenn **kein** Reverse Proxy vorgeschaltet ist, sollte der ProxyFix deaktiviert werden:

```ini
Environment="BEHIND_PROXY=0"
```

---

## 🚀 Installation

Das Tool wird über ein interaktives Setup-Skript installiert. Es richtet die Python-Umgebung (Flask), alle Verzeichnisse, die SQLite-Datenbank sowie die systemd-Services und Cronjobs automatisch ein.

**Voraussetzungen:** Ein Linux-Server (z. B. Ubuntu/Debian) und Root-Rechte.

### Step-by-Step

**1. Skript herunterladen und ausführen:**

```bash
wget -O setup_notes_sqlite.sh https://raw.githubusercontent.com/ipod86/Notes/main/setup_notes_sqlite.sh && chmod +x setup_notes_sqlite.sh && sudo ./setup_notes_sqlite.sh
```

Das Skript fragt interaktiv nach Instanzname, Port und Backup-Optionen.

**2. Für ein Update bestehender Instanzen:**

```bash
sudo ./setup_notes_sqlite.sh
```

Dann Option `[2]` wählen. Alle Instanzen werden aktualisiert, die Datenbank und Uploads bleiben erhalten.

## ❓ FAQ

### Welche Dateitypen kann ich hochladen?

Es ist eine umfangreiche Whitelist erlaubter Dateitypen eingebaut. Standardmäßig sind folgende Typen erlaubt:

| Kategorie | Erlaubte Endungen |
|---|---|
| **Bilder** | jpg, jpeg, png, gif, webp, svg, bmp, ico, tiff, tif, avif, heic, heif |
| **Audio** | mp3, wav, ogg, m4a, flac, aac, opus, wma, aiff |
| **Video** | mp4, webm, mov, avi, mkv, ogv, m4v, 3gp |
| **Dokumente** | pdf, txt, md, doc, docx, xls, xlsx, ppt, pptx, odt, ods, odp, rtf, csv |
| **Archive** | zip, tar, gz, 7z, rar, bz2 |
| **Strukturierter Text / Code** | json, xml, yaml, yml, toml, ini, cfg, conf, log, sql |
| **Kalender / Kontakte** | ics, vcf |

### Wie kann ich einen neuen Dateityp hinzufügen?

Öffne die Datei `app/app.py` und suche die Konstante `ALLOWED_EXTENSIONS` (ganz oben in der Datei, nach den Imports). Füge dort die gewünschte Dateiendung in **Kleinbuchstaben ohne Punkt** hinzu:

```python
ALLOWED_EXTENSIONS = {
    # Images
    'jpg', 'jpeg', 'png', ...
    # Mein neuer Typ
    'stl',   # <-- einfach hinzufügen
}
```

Anschließend das Update einspielen:

```bash
sudo ./setup_notes_sqlite.sh  # Option [2] wählen
```

> **Wichtig:** Füge niemals ausführbare Dateitypen hinzu (z. B. `py`, `sh`, `php`, `exe`, `js`, `html`). Diese könnten bei einer Fehlkonfiguration des Webservers serverseitig ausgeführt werden und ein erhebliches Sicherheitsrisiko darstellen.

### Warum werden manche Dateinamen nach dem Upload umbenannt?

Aus Sicherheitsgründen wird jeder Upload unter einem zufälligen UUID-Dateinamen gespeichert. Der Originalname ist in der Datenbank hinterlegt und wird beim Download wiederhergestellt. Das verhindert Path-Traversal-Angriffe durch präparierte Dateinamen.

### Wie aktiviere ich HTTPS / sichere Cookies?

Das Tool selbst liefert kein HTTPS. Empfohlen wird ein Reverse Proxy davor (z. B. nginx mit Certbot oder Caddy). Sobald HTTPS aktiv ist, trage in der systemd-Service-Datei ein:

```ini
Environment="HTTPS=true"
```

Damit wird das `Secure`-Flag auf dem Session-Cookie gesetzt, sodass er nicht über unverschlüsselte Verbindungen übertragen werden kann.

---

## 📖 Verwendete Open-Source-Bibliotheken & Ressourcen

* **[Flask](https://flask.palletsprojects.com/) & [SQLite](https://www.sqlite.org/):** Web-Framework für das Python-Backend und lokale relationale Datenbank.
* **[SortableJS](https://sortablejs.github.io/Sortable/):** Drag-and-Drop-Funktionalität für die Strukturierung des Notizbaums.
* **[Highlight.js](https://highlightjs.org/):** Syntax-Highlighting für Code-Blöcke innerhalb der Notizen.
* **[Material Design Icons](https://pictogrammers.com/library/mdi/):** Die in der Benutzeroberfläche verwendeten SVG-Icons entstammen der Pictogrammers-Bibliothek.
* **[DOMPurify](https://github.com/cure53/DOMPurify):** XSS-Sanitizer für geteilte Notizen in der Share-Ansicht.

<!-- Last updated via Claude Code: 2026-03-22 -->
