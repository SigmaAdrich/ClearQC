<div align="center">

# ✦ ClearQC

**Quantenchemie auf deinem eigenen Computer**

[📥 Download](https://github.com/SigmaAdrich/ClearQC/releases/latest) · [🐛 Fehler melden](https://github.com/SigmaAdrich/ClearQC/issues)

**[中文](README.md) · [English](README.en.md) · Deutsch · [日本語](README.ja.md)**

</div>

---

## Was ist das hier?

Hast du dich jemals gefragt — **wie sieht ein Molekül wirklich aus? Wie sind seine Elektronen verteilt? Warum bricht diese Bindung, aber nicht jene?**

Diese Fragen lassen sich theoretisch mit der Quantenmechanik berechnen — genau das macht die „Quantenchemie" oder „Computerchemie".

Traditionell erfordert eine solche Berechnung jedoch:

- Einen Linux-Server einrichten
- Eingabedateien über die Kommandozeile schreiben lernen
- Lange Warteschlangen in Job-Schedulern
- Ausgabedateien manuell kopieren und Graphen von Hand erstellen

Diese Arbeitsweise hat eine sehr steile Lernkurve — viele Studierende geben auf, bevor sie überhaupt angefangen haben.

**ClearQC hat das Ziel, all diese Hürden zu beseitigen.**

Sag der Software einfach, welches Molekül du berechnen möchtest — tippe zum Beispiel „Coffein" oder „Benzol" — klicke auf einen Button, und nach wenigen Minuten siehst du:

- Die dreidimensionale Struktur des Moleküls
- Gesamtenergie und Atomladungsverteilung
- Visualisierung der Grenzorbitale (HOMO / LUMO)
- IR- oder UV-Vis-Absorptionsspektrum (wenn du die entsprechende Aufgabe gewählt hast)

**Alles läuft lokal auf deinem Windows-PC. Keine Internetverbindung für die Berechnungen notwendig, kein Konto erforderlich, keine Python-Kenntnisse nötig.**

---

## Was kann Quantenchemie überhaupt berechnen?

Falls dir „Quantenchemie" abstrakt klingt, hier sind konkrete Beispiele:

**🔬 Geometrieoptimierung**
Ausgehend von einer groben Startstruktur sucht der Computer die stabilste 3D-Form des Moleküls — die Konfiguration mit der niedrigsten Energie. Stell es dir vor wie eine gespannte Feder, die in ihre natürliche Gleichgewichtslage zurückschnappt.

**⚡ Grenzorbitale (HOMO / LUMO)**
HOMO steht für „Highest Occupied Molecular Orbital" (höchstes besetztes Molekülorbital), LUMO für „Lowest Unoccupied Molecular Orbital" (niedrigstes unbesetztes Molekülorbital). Diese beiden Orbitale bestimmen, wo ein Molekül bei einer Reaktion Elektronen abgibt oder aufnimmt — also seine chemische Reaktivität. ClearQC stellt sie als anschauliche 3D-Isoflächen dar.

**🌈 UV-Vis-Absorptionsspektrum (TD-DFT)**
Warum absorbiert Benzol im UV-Bereich? Warum haben Farbstoffe eine Farbe? Angeregte-Zustands-Rechnungen (TD-DFT) sagen vorher, welche Lichtwellenlängen ein Molekül absorbiert — direkt vergleichbar mit experimentellen UV-Vis-Spektrometerdaten.

**📳 Infrarotspektrum (IR)**
Chemische Bindungen schwingen wie Federn bei bestimmten Frequenzen. Eine Frequenzanalyse sagt vorher, wo IR-Absorptionsbanden erscheinen — direkt vergleichbar mit dem, was ein IR-Spektrometer im Labor misst.

**🧪 Mulliken-Ladungen**
Zeigt, wie viel überschüssige Ladung jedes Atom trägt — hilfreich zum Verständnis von Polarität, Wasserstoffbrückenbindungen und nukleophilen/elektrophilen Reaktionszentren.

---

## Screenshots

> *(Screenshots folgen demnächst)*

---

## Funktionen

| Funktion | Beschreibung |
|----------|-------------|
| Molekülbibliothek | Name eingeben (Deutsch, Englisch oder IUPAC) → Autovervollständigung → Berechnung starten |
| Datei-Import | XYZ-, PDB-, MOL/SDF- oder Gaussian-GJF-Dateien per Drag & Drop |
| Einzelpunktenergie | Elektronische Energie für eine gegebene Geometrie berechnen |
| Geometrieoptimierung | Stabilste Molekülstruktur automatisch finden |
| Frequenzanalyse | Schwingungsfrequenzen berechnen und IR-Spektrum erzeugen |
| Angeregte Zustände (TD-DFT) | Lichtabsorption berechnen und UV-Vis-Spektrum erzeugen |
| Lösungsmitteleffekte | Implizite Solvatation (PCM) für Wasser, DMSO, Methanol und 5 weitere |
| 3D-Visualisierung | Kugel-Stab-Modell + HOMO/LUMO/Elektronendichte-Isoflächen |
| KI-Interpretation | KI-Modell anschließen für automatische Ergebnis-Erklärung oder Fehlerdiagnose |
| Export | Ergebnisse als JSON oder CSV exportieren |
| Sprachen | 中文 / English / Deutsch / 日本語 |
| Hell-/Dunkel-Modus | Augenschonend |

---

## Systemanforderungen

ClearQC unterstützt derzeit nur **Windows 10 / 11 (64-Bit)**.

Außerdem muss **WSL 2** (Windows-Subsystem für Linux 2) aktiviert sein. WSL 2 ist eine eingebaute Windows-Funktion, die es Windows ermöglicht, Linux-Programme auszuführen — ClearQCs Berechnungsmodul (PySCF) läuft in dieser Linux-Umgebung. **Du musst Linux überhaupt nicht kennen**; ClearQC erledigt alles automatisch.

### WSL 2 aktivieren

1. Öffne PowerShell **als Administrator** (im Startmenü nach „PowerShell" suchen → Rechtsklick → Als Administrator ausführen)
2. Führe folgenden Befehl aus:
   ```
   wsl --install
   ```
3. Warte, bis die Installation abgeschlossen ist, und **starte deinen Computer neu**

Nach dem Neustart ist WSL 2 bereit. Bei Problemen hilft die [offizielle Microsoft-Dokumentation](https://learn.microsoft.com/de-de/windows/wsl/install).

### Hardware-Empfehlungen

| | Minimum | Empfohlen |
|--|---------|-----------|
| RAM | 4 GB | 8 GB oder mehr |
| Speicherplatz | 600 MB | 1 GB+ (für temporäre Berechnungsdateien) |
| CPU | Beliebig x64 | Mehr Kerne = schnellere Berechnungen |

---

## Download & Installation

Lade die neueste Version von der [Releases-Seite](https://github.com/SigmaAdrich/ClearQC/releases/latest) herunter.

Es gibt zwei Installationspakete:

**📦 Offline-Installer (empfohlen für Erstnutzer)**
Dateiname enthält `offline`, ~135 MB. Das Berechnungsmodul ist bereits enthalten — herunterladen, doppelklicken, fertig. **Keine Internetverbindung notwendig.**

**📦 Online-Installer (bei guter Internetverbindung)**
Dateiname enthält `online`, ~14 MB. Der Installer selbst ist klein, aber beim **ersten Start wird das ~120 MB große Berechnungsmodul heruntergeladen** (Internetverbindung erforderlich). Danach ist keine Verbindung mehr nötig.

> **Nicht sicher, welchen du nehmen sollst?** Nimm den Offline-Installer — der funktioniert immer.

### Installationsschritte

1. Lade die `.exe`-Datei herunter
2. Doppelklick zum Starten. Windows zeigt möglicherweise eine Sicherheitswarnung an („Windows hat deinen Computer geschützt"). Klicke auf **Weitere Informationen → Trotzdem ausführen**
3. Folge dem Installationsassistenten
4. Starte **ClearQC** über das Startmenü oder die Desktop-Verknüpfung
5. **Beim ersten Start** importiert die App automatisch die WSL-Berechnungsumgebung — das dauert etwa 30–60 Sekunden. Bitte warte
6. Sobald die Hauptoberfläche erscheint, kann es losgehen!

---

## Schnellstart in 5 Minuten

**Schritt 1: Molekülnamen eingeben**

Tippe im Chat-Eingabefeld unten links `/compute caffeine` und drücke Enter.

Die App sucht Coffein in der eingebauten Molekülbibliothek und zeigt eine **Berechnungskarte** im Chat-Panel.

**Schritt 2: Parameter einstellen**

Die Karte verwendet bereits empfohlene Standardwerte (B3LYP / def2-SVP — gute Balance aus Geschwindigkeit und Genauigkeit). Klicke auf **Adjust** für weitere Optionen:

- **Methode**: HF (schnell, aber weniger genau) oder B3LYP (empfohlene DFT-Methode)
- **Präzision**: Fast / Balanced / Accurate
- **Aufgabe**: Einzelpunkt (SP) / Optimierung (Opt) / Frequenz (Freq) / Angeregte Zustände
- **Lösungsmittel**: Für Simulationen in Lösung ein Lösungsmittel auswählen

Beim ersten Versuch einfach alles bei den Standardwerten lassen.

**Schritt 3: Compute klicken**

Klicke auf den grünen **Compute**-Button. Die Statusleiste rechts zeigt den Berechnungsfortschritt.

Ein kleines Molekül wie Coffein benötigt bei Balanced-Präzision etwa 1–3 Minuten.

**Schritt 4: Ergebnisse ansehen**

Nach Abschluss der Berechnung erscheint eine Ergebniskarte mit:

- Gesamtenergie (in Hartree)
- Konvergenzstatus
- Mulliken-Atomladungen
- Berechnungszeit

Das rechte Panel zeigt gleichzeitig die 3D-Struktur. Mit dem Dropdown-Menü kannst du zwischen **HOMO, LUMO und Elektronendichte**-Isoflächen wechseln.

**Schritt 5 (optional): KI-Erklärung**

Die Ergebniskarte hat unten einen **AI Explain**-Button. Wenn du einen KI-Endpunkt konfiguriert hast (Einstellungen → KI-Konfiguration), wird nach dem Klicken eine verständliche Erklärung der Ergebnisse generiert.

---

## Häufige Fragen

**F: Die App öffnet sich nicht oder meldet, WSL wurde nicht gefunden?**
A: Stelle sicher, dass WSL 2 gemäß der obigen Anleitung aktiviert ist, und starte den PC neu.

**F: Der erste Start bleibt bei „Berechnungsumgebung wird importiert" hängen?**
A: Das ist normal — der WSL-Import dauert je nach Festplattengeschwindigkeit 30–60+ Sekunden. Bitte warten; Fenster nicht schließen.

**F: Berechnung schlägt fehl?**
A: Häufigste Ursache ist eine falsche Ladungs- oder Spin-Einstellung (z.B. ein Kation berechnen ohne die Ladung auf +1 zu setzen). Klicke auf **AI Diagnose** auf der Ergebniskarte für eine automatische Diagnose.

**F: Welche Dateiformate werden unterstützt?**
A: XYZ, PDB, MOL/SDF und Gaussian GJF/COM können direkt ins Fenster gezogen werden.

**F: Berechnungen sind sehr langsam?**
A: Quantenchemische Berechnungen sind rechenintensiv. Größere Moleküle, größere Basissätze und komplexere Aufgaben dauern länger. Beginne mit Balanced-Präzision und Einzelpunktenergie (SP).

**F: Wird Mac oder Linux unterstützt?**
A: Derzeit nicht. Nur Windows 10/11. Mac/Linux-Support ist nicht geplant.

---

## Feedback & Support

Fehler gefunden oder eine Idee für neue Funktionen? Erstelle ein Issue auf der [Issues-Seite](https://github.com/SigmaAdrich/ClearQC/issues).

---

## Lizenz

© 2025 SigmaAdrich. All rights reserved.