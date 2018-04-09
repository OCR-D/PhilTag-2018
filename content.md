layout: true
  
<div class="my-header"></div>

<div class="my-footer">
  <table>
    <tr>
      <td>PhilTag 2018</td>
      <td style="text-align:right"><a href="https://www.dwds.de">Neues von OCR-D</a></td>
    </tr>
  </table>
</div>

---

class: title-slide

# Neues von OCR-D  

| Kay-Michael Würzner |
|:-------------------:|
| [wuerzner@bbaw.de](mailto:wuerzner@bbaw.de) |

---

# Überblick

- OCR-D-Framework (Konstantin Baierer, Volker Hartmann, Clemens Neudecker)
- OCR-D-Ground-Truth (Matthias Boenig)
- Training mit Tesseract 4 (Uwe Springmann)

---

# OCR-D

- DFG-gefördertes Koordinierungsprojekt
   + Ziele:
        * Verbesserung von OCR-Methoden für historische Drucke (16. - 19. Jh.)
        * technische Vorbereitung der Volltextdigitalisierung der in den VDs (16, 17, 18) verzeichneten Drucke
   + Laufzeit:
        * September 2015 - Oktober 2018 (Verlängerung beantragt)
   + Ablauf:
        1. Identifikation technischer und wissenschaftlicher Bedarfe
        2. Konzeption und Formulierung einer Ausschreibung für Modulprojekte (MPs) zu deren Bearbeitung
        3. Entwicklung einer Koordinierungsstruktur
        4. Betreuung der MPs
        5. Integration der MP-Entwicklungen in einen produktiven Workflow

---

# Modulprojektphase

- Modulprojektphase seit 01/2018
    + acht Modulprojekte in sechs inhaltlichen Bereichen
    + Bildvorverarbeitung:
        * *Bildoptimierung* (DFKI Kaiserslautern)
    + Layouterkennung:
        * *Layouterkennung* (DFKI Kaiserslautern)
        * *Weiterentwicklung LAREX* (JMU Würzburg)
    + Textoptimierung:
        * *Tesseract im OCR-D-Workflow* (UB Mannheim)
        * *Unüberwachte Nachkorrektur mit neuronalen Netzen und FSTs* (Uni Leipzig)
        * *Automatische Nachkorrektur mit PoCoTo* (LMU München)
    + OCR-Training:
        * *Modellrepositorium und automatische Schriftarterkennung* (FAU Erlangen, JGU Mainz, Uni Leipzig)
    + Langzeitarchivierung:
        * *Langzeitarchiv für historische Drucke* (SUB Göttingen)

---

# Framework

- Ziel:
    1. Integration der Ergebnisse der Modulprojekte
        * wohldefinierte Schnittstellen
        * etablierte Austauschformate
    2. Komplettierung mit Infrastrukturkomponenten zur Orchestrierung bzw. Ausbau zum vollwertigen Workflow
        * *Apache Taverna* als Workflowengine
        * File-Cache
        * Formatkonvertierungen
        * *Forschungsdatenrepositorium*
- Referenz:
    + https://github.com/OCR-D/pyocrd/
        * Workflow auf Basis vorhandener OpenSource-Komponenten (im Aufbau)
        * Spielwiese für Entwickler
        * Illustration der Schnittstellen

---

# Formate

- Grundlagen:
    + Fokus für die Verarbeitung von Anfang an: **Massendigitalisierung**
    + Dokumentation und Beispiele: https://github.com/OCR-D/spec/
    + METS als Austauschformat
        * `FileSection` für Referenzen auf Quell- und (Zwischen-)Ergebnisdateien
        * `USE`-Attribute zur Kenntlichmachung
    + METS für Ergebnisse auf **Dokumentebene**
        * `structMap TYPE=logical` für Dokumentstruktur
    + PAGE für Ergebnisse auf **Seitenebene**
    + JSON für **Parameterübergabe** und **Interfacebeschreibung**
    + ALTO als **Exportformat** (verlustbehaftet!)

---

# Warum METS

- Standardarbeitsformat in **Bibliotheken** und DFG-Richtlinien
- Standardausgabeformat von **Digitalisierungsdienstleistern**
- Anschluss an Präsentations-, Archiv- und Katalogsysteme
- umfangreicher Satz an Meta- und Primärdatenfeldern
- **Anschlusspunkt** an vorhandene Digitalisierungsworkflows
