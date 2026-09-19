# Können-Leiter

Sieben Stufen. Sie sind **kein Lehrplan zum Abarbeiten**, sondern eine Landkarte: sie sagt, wo
Louis gerade steht, welches Werkzeug als nächstes natürlich dazukommt, und welche Projekte dieses
Werkzeug tragen können.

So wird sie benutzt:

- **Louis' Projekt entscheidet, nicht die Stufe.** Bringt er auf Stufe 2 ein Vasen-Projekt mit
  (eigentlich Stufe 6), wird die Vase gebaut – nur eben in Etappen, und die Kurven-Werkzeuge werden
  dort eingeführt, wo die Vase sie braucht. Die Leiter wird dann übersprungen, nicht das Projekt.
- **Pro Etappe ein neues Werkzeug.** Was in "Neu" steht, ist der Vorrat für mehrere Etappen, nicht
  für eine.
- **"Sitzt, wenn"** ist die Frage, die Louis am Ende der Sitzung gestellt wird. Antwortet er
  richtig, ist die Stufe durch. Antwortet er nicht, wird das Werkzeug im nächsten Projekt einfach
  nochmal gebraucht – ohne es zur Lektion zu erklären.

Hotkeys hier nur als Erinnerung. Die verbindliche Liste steht im Skill `plasticity`.

---

## Stufe 0 – Einrichtung

Einmalig, bevor irgendwas gebaut wird: Einheit auf Millimeter, Rastergröße, Testquader
**20 × 20 × 20 mm** nachmessen. Die drei Schritte stehen im Skill `plasticity`, Abschnitt 5.

**Sitzt, wenn:** `Ctrl+=` an seinem Testquader **20** anzeigt.

---

## Stufe 1 – Von der Skizze zum Körper

**Neu:** Mittel-Rechteck und Mittelkreis (Center Rectangle / Center Circle), Extrudieren (`E`),
Maßeingabe mit `Tab`, Ansichten umschalten (`Numpad 7` / `3` / `1`), Abstand messen (`Ctrl+=`),
Grundkörper direkt setzen (Eck-Quader, Zylinder).

Das ist die Stufe, auf der die **Maßeingabe mit `Tab`** zur Gewohnheit werden muss. Wer hier mit
der Maus "ungefähr" zieht, kämpft auf allen weiteren Stufen mit schiefen Maßen.

**Sitzt, wenn:** Louis einen Quader **40 × 25 × 8 mm** ohne Anleitung baut und nachmisst.

**Projekte – Funktion:** Distanzstück (Zylinder Ø 12 × 6 mm), Unterlegplatte für ein wackelndes
Möbel, Grundplatte für einen späteren Halter.
**Projekte – Deko:** Untersetzer **90 × 90 × 6 mm**, Rohling für ein Namensschild, ein Stapel aus
drei versetzten Quadern als Objekt.

**Passender Design-Happen:** Das Modul – alle Maße als Vielfache einer Grundeinheit.

---

## Stufe 2 – Material wegnehmen

**Neu:** Boolesch (`Q`) mit Abziehen, Werkzeugkörper bauen und vorher duplizieren (`Shift`+`D`),
Bohrungen, Aussparungen, Verschieben (`G`) zum Positionieren.

Hier lernt Louis den wichtigsten Arbeitsstil in Plasticity: **Abzieh-Körper vor dem Boolean
duplizieren und ausblenden.** Plasticity hat keinen parametrischen Baum – wer den Werkzeugkörper
wegwirft, baut die Bohrung beim nächsten Änderungswunsch neu.

**Sitzt, wenn:** Louis sagen kann, wie er eine fertige Bohrung von **3,4 auf 4,2 mm** ändert.

**Projekte – Funktion:** Wandhalter mit zwei Schraublöchern, Kopfhörerhaken für die
Schreibtischkante, Handy-Ständer, Kabelklemme.
**Projekte – Deko:** Stiftehalter mit Löchern in verschiedenen Durchmessern, Teelichthalter,
Untersetzer mit durchbrochenem Muster.

**Passender Design-Happen:** Toleranz-Denken – welches Maß ist kritisch, welches darf wandern.

---

## Stufe 3 – Zeichenebenen und Symmetrie

**Neu:** Fläche auswählen (`3`) und zur Zeichenebene machen (`Space` / `Shift`+`Space`), Spiegeln
(`Alt`+`X`), Verbinden (`J`), Drehen (`R`).

Die Stufe, die am meisten Frust wegnimmt. Fast jedes "meine Kurve liegt schief im Raum" löst sich
damit, dass vorher die richtige Fläche zur Zeichenebene gemacht wird.

**Sitzt, wenn:** Louis eine Bohrung in eine **schräge** Fläche setzen kann, ohne dass sie schief
durchgeht.

**Projekte – Funktion:** Gehäuse-Grundform mit Anschlüssen auf verschiedenen Seiten, Hakenleiste
mit drei gespiegelten Haken, zweiarmiger Halter.
**Projekte – Deko:** symmetrische Schale, Buchstütze, Objekt mit Muster auf mehreren Seiten.

**Passender Design-Happen:** Symmetrie mit einem Bruch.

---

## Stufe 4 – Kanten fertig machen

**Neu:** Verrundung (`B`) für Rundungen **und** Fasen, Radien-Hierarchie, richtige Reihenfolge
(Kanten immer **zuletzt**), Fase statt Rundung an der Bettkante.

Der Punkt, an dem Louis' Teile aufhören, wie Rohlinge auszusehen. Gleichzeitig die häufigste
Fehlerquelle: Verrundungen machen spätere Booleans instabil, deshalb kommen sie am Ende.

**Sitzt, wenn:** Louis erklären kann, warum eine **1 mm** Fase unten am Druckbett besser ist als
eine **1 mm** Rundung.

**Projekte – Funktion:** Drehknopf, Werkzeuggriff, Griffschale für eine Schublade.
**Projekte – Deko:** weich verrundete Schale, Seifenspender-Deckel, Briefbeschwerer.

**Passender Design-Happen:** Fase oder Rundung – und die Radien-Hierarchie.

---

## Stufe 5 – Hohl und zweiteilig

**Neu:** Aushöhlen (Hollow), Verdicken (Thicken), Seite versetzen (Offset Face), Passungen mit
Spiel, Deckel und Gegenstück.

Ab hier baut Louis Dinge, die **zusammengehören**. Das Thema der Stufe ist nicht ein Werkzeug,
sondern **Spiel**: zwei gedruckte Teile mit identischem Maß passen nie – der Spalt wird gezeichnet,
nicht erhofft.

**Sitzt, wenn:** Louis für einen aufsteckbaren Deckel von selbst Spiel einplant und die Zahl
begründen kann.

**Projekte – Funktion:** Elektronik-Gehäuse mit Deckel, Dose mit Steckdeckel, Batteriefach,
Ersatz-Abdeckung für ein kaputtes Teil.
**Projekte – Deko:** hohle Vase mit gleichmäßiger Wand, Übertopf, Dose mit Schiebedeckel.

**Passender Design-Happen:** Gleichmäßige Wandstärke – und die Schattennut.

---

## Stufe 6 – Kurven und runde Formen

**Neu:** Linie (`Shift`+`A`) und Kurven zeichnen, Trimmen (`T`), Kurve versetzen (`O`), Rotieren
(Revolve), Loft (`L`), Rohr (`P`), Sweep (`Shift`+`P`).

Die Stufe für alles, was nicht aus Quadern besteht. **Rotieren** ist der beste Einstieg: eine
halbe Profillinie, um die Achse gedreht – damit entstehen Vasen, Knöpfe und Griffe mit sehr wenig
Zeichnerei.

**Sitzt, wenn:** Louis ein Profil zeichnet und weiß, ob er es rotieren, loften oder sweepen muss.

**Projekte – Funktion:** ergonomischer Griff nach seiner Handmaß-Messung, Schlauchadapter zwischen
zwei Durchmessern, Trichter.
**Projekte – Deko:** Vase mit eigenem Profil, Lampenschirm, Sockel für eine gedruckte Figur,
Kerzenhalter.

**Passender Design-Happen:** Ergonomie in Zahlen – und Detail-Dichte.

---

## Stufe 7 – Schauflächen

**Neu:** Flächenübergänge und ihre Qualität (G0/G1/G2), Material festlegen (`M`), Render-Ansicht,
Export-Toleranz fein einstellen.

Diese Stufe braucht er nur für Objekte, die **angeschaut** werden – Deko, Renders, Geschenke. Für
Funktionsteile ist sie überflüssig, und das gehört dazugesagt.

**Sitzt, wenn:** Louis an einem Reflex auf seinem Modell erkennt, ob ein Übergang glatt
durchläuft oder eine Lichtkante hat.

**Projekte – Deko:** ein Objekt von Stufe 4–6 nochmal auf Schaufläche-Qualität bringen und
rendern.

**Passender Design-Happen:** Warum billige Teile billig aussehen – Flächenstetigkeit.
