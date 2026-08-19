📱 WhatsApp Status Saver & Manager

Ein Python-basiertes Skript auf Selenium-Basis zum automatischen Speichern von WhatsApp-Statusmedien (Fotos und Videos) in voller Auflösung. Das Tool enthält zudem eine integrierte Auto-Update-Funktion über GitHub.
🚀 Features

    Kein Qualitätsverlust: Speichert Videos als MP4 direkt aus dem Browser-Memory und Bilder über das Canvas Element in voller Auflösung (filtert unscharfe Thumbnails automatisch heraus).

    Kein Chrome-Download-Dialog: Medien werden direkt per Base64 exportiert und lokal abgespeichert.

    Session-Persistence: Kein erneutes Scannen des QR-Codes bei jedem Start (nutzt ein lokales User-Data-Verzeichnis).

    Integriertes Auto-Update: Prüft automatisch auf GitHub nach neuen Versionen (version.json) und aktualisiert den Code bei Bedarf selbstständig.

🛠️ Voraussetzungen & Installation
1. Python & Abhängigkeiten

Stelle sicher, dass Python 3.8+ installiert ist. Installiere Selenium über das Terminal:
Bash

pip install selenium

2. Chrome Driver & Browser

    Stelle sicher, dass chromedriver.exe im selben Ordner wie die Python-Dateien liegt.

    Passe ggf. den Pfad zu deiner Chrome.exe in der Datei config.py an.

📁 Projektstruktur
Plaintext

├── config.py           # Pfade, Chrome-Optionen & GitHub Update-URLs
├── update_checker.py   # Logik für Versionsprüfungen & automatische Downloads
├── main.py             # Hauptmenü, Selenium-Steuerung & Saver-Logik
├── version.json        # Lokale Versionsdatei
└── chromedriver.exe    # Selenium Webdriver

📖 Bedienungsanleitung

    Programm starten:
    Bash

    python main.py

    Login durchführen:

        Wähle im Hauptmenü die Option 1 (Status Saver starten).

        Scanne beim ersten Start den WhatsApp QR-Code.

    Status speichern:

        Öffne in WhatsApp Web einen gewünschten Status (Bild oder Video).

        Drücke im Terminal s + ENTER. Das Medium wird automatisch im Ordner gespeichert.

    Beenden:

        Drücke q + ENTER, um den Saver-Modus zu verlassen.

💡 Tipps & Tricks

    Thumbnail-Problem vermeiden: Das Skript ist darauf ausgelegt, Bilder erst nach dem vollständigen Laden der vollen Auflösung abzugreifen. Warte 1–2 Sekunden, bis das Bild im WhatsApp-Status scharf dargestellt wird, bevor du s drückst.

    Auto-Updates einrichten:

        Wenn du deinen Code auf GitHub anpasst, erhöhe einfach die Version in der version.json auf GitHub (z. B. auf "1.0.1").

        Beim Ausführen von Punkt 4 (Version anzeigen & Updaten) im Menü lädt das Skript die aktuelle main.py automatisch herunter.

    Session zurücksetzen: Falls der WhatsApp-Login nicht mehr funktioniert oder hakt, lösche einfach den Ordner whatsapp_session/ im Projektverzeichnis und scanne den QR-Code neu.
