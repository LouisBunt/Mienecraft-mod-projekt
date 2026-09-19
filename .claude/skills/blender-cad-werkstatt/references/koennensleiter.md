# Können-Leiter – Blender für Bauteile

Acht Stufen als **Landkarte**, nicht als Lehrplan: Sie sagen, wo Louis steht und welches Werkzeug
als nächstes natürlich dazukommt. Sein Projekt entscheidet, nicht die Stufe – ein zu großes
Vorhaben wird zerlegt, nicht abgelehnt.

**Pro Etappe ein neues Werkzeug.** Was unter „Neu" steht, ist Vorrat für mehrere Etappen.

**"Sitzt, wenn"** ist die Frage am Sitzungsende. Antwortet er richtig, ist die Stufe durch. Sonst
wird das Werkzeug im nächsten Projekt einfach nochmal gebraucht – ohne es zur Lektion zu erklären.

---

## Stufe 0 – Einrichtung (nicht überspringen)

In Blender ist das keine Formalie. Mit falschen Einheiten stimmt danach keine einzige Zahl.

**Neu:** *Scene Properties → Units* auf Millimeter · **Clip Start** auf **1 mm** (`N` → *View*) ·
**3D-Print Toolbox** in den Einstellungen als Erweiterung aktivieren · das `N`-Panel und
*Item → Dimensions*.

Details und Begründung: `references/blender-eigenheiten.md`, Abschnitte 1 und 2.

**Sitzt, wenn:** Der Standardwürfel zeigt **2000 mm**, und Louis kann ihn auf **20 × 20 × 20 mm**
bringen.

---

## Stufe 1 – Exakte Maße statt Augenmaß

**Neu:** Grundkörper hinzufügen (`Shift`+`A`) und sofort im Panel unten links (`F9`) bemaßen ·
Maße unter `N` → *Item* → *Dimensions* eintippen · Verschieben mit Achse und Zahl
(`G` `Z` `10` `Enter`) · **Apply Scale** (`Ctrl`+`A` → *Scale*).

Die Stufe, auf der die Gewohnheit entstehen muss: **Zahl tippen, nicht ziehen.**

**Sitzt, wenn:** Louis erklären kann, warum nach dem Skalieren `Ctrl`+`A` nötig ist.

**Projekte – Funktion:** Distanzstück, Unterlegplatte, Grundplatte für einen späteren Halter.
**Projekte – Deko:** Untersetzer 90 × 90 × 6 mm, Namensschild-Rohling.

---

## Stufe 2 – Nicht-destruktiv: der Modifier-Stack

**Neu:** Was ein Modifier ist und warum er dem direkten Bearbeiten vorzuziehen ist ·
**Mirror** (Spiegeln) · **Array** (Wiederholung) · Reihenfolge im Stack verschieben ·
Modifier ein- und ausschalten.

Der Modifier-Stack ist Blenders Ersatz für den parametrischen Baum, den es nicht hat: abschaltbar,
änderbar, umsortierbar.

**Sitzt, wenn:** Louis eine Hälfte baut, spiegelt, und den Spiegel-Modifier nachträglich noch
verschieben kann, ohne neu anzufangen.

**Projekte – Funktion:** Hakenleiste mit gleichmäßigen Haken, zweiarmiger Halter.
**Projekte – Deko:** symmetrische Schale, Lochmuster-Untersetzer.

---

## Stufe 3 – Boolean, aber sauber

**Neu:** **Boolean**-Modifier mit *Difference* / *Union* / *Intersect* · Solver auf **Exact** ·
Werkzeugkörper ausblenden statt löschen · **0,01 mm Überstand** bei bündigen Flächen.

Hier lernt Louis die wichtigste Blender-Gewohnheit für Bauteile: **nach jedem Boolean die
Mesh-Probe.** Ein misslungener Boolean sieht oft normal aus und ist trotzdem kaputt.

**Sitzt, wenn:** Louis weiß, was er tut, wenn ein Boolean ein zerfetztes Ergebnis liefert
(Reihenfolge in `blender-eigenheiten.md`, Abschnitt 8).

**Projekte – Funktion:** Wandhalter mit Schraublöchern, Kabelhalter, Gehäuse mit Anschlussöffnung.
**Projekte – Deko:** Stiftehalter, Teelichthalter, Laternenschirm mit Durchbrüchen.

---

## Stufe 4 – Kanten: der Bevel-Modifier

**Neu:** **Bevel**-Modifier · *Amount* und *Segments* · *Limit Method* (Angle oder Weight) ·
*Clamp Overlap* · Platz im Stack: **nach dem Boolean**.

Eine Fase mit **1 Segment**, eine Rundung mit **3–5**. Mehr kostet nur Rechenzeit, ohne dass der
Drucker es abbilden könnte.

**Sitzt, wenn:** Louis erklären kann, warum der Bevel im Stack unter dem Boolean stehen muss.

**Projekte – Funktion:** Drehknopf, Werkzeuggriff, Griffschale.
**Projekte – Deko:** weich verrundete Schale, Briefbeschwerer.

---

## Stufe 5 – Wandstärke: Solidify

**Neu:** **Solidify**-Modifier · *Thickness*, *Offset*, *Even Thickness* · aus einer Fläche eine
Wand machen · Deckel und Gegenstück mit **Spiel**.

Thema der Stufe ist nicht das Werkzeug, sondern **Spiel**: Zwei gedruckte Teile mit identischem
Maß passen nie. Der Spalt wird gezeichnet, nicht erhofft – **0,2–0,3 mm** Gesamtspiel für eine
normale Steckverbindung.

**Sitzt, wenn:** Louis für einen aufsteckbaren Deckel von selbst Spiel einplant und die Zahl
begründen kann.

**Projekte – Funktion:** Elektronikgehäuse mit Deckel, Dose, Batteriefach, Ersatzabdeckung.
**Projekte – Deko:** hohle Vase mit gleichmäßiger Wand, Übertopf.

---

## Stufe 6 – Runde und gerechnete Formen

**Neu:** **Screw**-Modifier und **Spin** (das Blender-Gegenstück zum Rotieren) · Kurve plus
*Bevel Object* für Rohre und Profile · Segmentzahl bewusst wählen (Tabelle in
`blender-eigenheiten.md`, Abschnitt 4).

Hier wird der Code-Weg interessant: Zahnräder, Gewinde und Wendeln baut Claude per Python, weil
sie gerechnet werden müssen – von Hand ist das Quälerei ohne Lerngewinn.

**Sitzt, wenn:** Louis ein Profil zeichnet und weiß, ob er es rotieren, extrudieren oder an einer
Kurve entlangführen muss.

**Projekte – Funktion:** Schlauchadapter zwischen zwei Durchmessern, Trichter, ergonomischer Griff.
**Projekte – Deko:** Vase mit eigenem Profil, Kerzenhalter, Figurensockel.

---

## Stufe 7 – Druckfertig machen und fremde Modelle retten

**Neu:** 3D-Print Toolbox vollständig (*Check All*, *Thickness*, *Overhang*, *Intersections*) ·
Normalen prüfen und neu berechnen · doppelte Punkte verschmelzen · **Decimate** und **Remesh** für
importierte Modelle · Export als STL und 3MF.

Diese Stufe ist Blenders eigentliche Stärke gegenüber Plasticity: **alles, was schon als Mesh
vorliegt.** Heruntergeladene Modelle, Scans, und die WoW-Exporte, mit denen Louis ohnehin arbeitet.

**Sitzt, wenn:** Louis ein fremdes Modell aus dem Netz nimmt, die Fehler findet und es druckfertig
macht.

**Projekte:** ein heruntergeladenes Modell auf seinen Zweck anpassen; eine WoW-Figur aus dem
Export druckfertig machen (zusammen mit dem Skill `wow-character-to-blender`).
