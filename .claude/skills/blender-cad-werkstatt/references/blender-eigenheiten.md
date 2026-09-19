# Blenders Eigenheiten – die Fallen beim maßhaltigen Arbeiten

Hier steht, was schiefgeht, wenn man Blender wie ein CAD behandelt. **Wenn etwas unerklärlich
schiefläuft, zuerst hier nachsehen** – in neun von zehn Fällen steht die Ursache auf dieser Seite.

Alle Millimeterwerte gelten für Louis' Prusa: 0,4 mm Düse, 0,2 mm Schichthöhe, PLA.

---

## 1. Die Einheiten-Falle

*Scene Properties → Units*: **Unit System** auf *Metric*, **Length** auf *Millimeters*.

Ohne das denkt Blender in Metern. Ein Würfel mit „2" Kantenlänge ist dann **2 Meter**, und beim
Export landet irgendetwas im Slicer, nur nicht das Gewünschte.

**Unit Scale** bleibt auf **1.0**. Es ist verlockend, hier 0.001 einzutragen – das führt aber zu
Folgeproblemen bei Physik, Modifiern und Addons. Der saubere Weg ist: Unit Scale bei 1 lassen und
die Anzeige auf Millimeter stellen.

**Die Probe:** Ein Standard-Würfel (`Shift`+`A` → *Mesh* → *Cube*) muss unter `N` → *Item* →
*Dimensions* **2000 mm** anzeigen (Blenders Standardwürfel ist 2 Einheiten groß). Genau deshalb
gehört zum Anfang jedes Projekts das Setzen der Maße, nicht das Übernehmen der Vorgaben.

## 2. Das verschwindende Werkstück (Clip Start)

Kleine Teile werden beim Heranzoomen abgeschnitten oder verschwinden ganz. Kein Fehler im Modell –
die Kamera schneidet zu früh.

**Fix:** `N` → Reiter *View* → **Clip Start** von **0.1 m** auf **1 mm** stellen (oder 0,1 mm bei
sehr kleinen Teilen). Gehört zur Einrichtung, einmalig pro Datei.

Ein zu kleiner Wert kostet Tiefengenauigkeit und lässt Flächen flackern – **1 mm** ist für Teile
in Handgröße der richtige Kompromiss.

## 3. Skalieren lügt (Apply Scale)

Wird ein Objekt im Objektmodus mit `S` skaliert, ändert sich nur ein **Anzeige-Faktor** – das Mesh
darunter behält seine alten Maße. Sichtbar wird das erst später, und dann heftig:

- **Bevel** macht auf einer Achse breitere Fasen als auf der anderen.
- **Solidify** erzeugt ungleiche Wandstärken.
- Der Export bringt teils die falsche Größe mit.

**Fix:** `Ctrl`+`A` → *Scale*. Danach steht im `N`-Panel unter *Scale* überall **1.000**.

**Regel:** Nach jedem Skalieren im Objektmodus Scale anwenden – spätestens, bevor ein Modifier
dazukommt. Besser noch: gar nicht skalieren, sondern Maße direkt unter *Dimensions* eintippen.

## 4. Runde Formen sind Vielecke

Ein Zylinder mit 32 Segmenten ist ein 32-Eck. Wie weit das vom echten Kreis abweicht, lässt sich
ausrechnen: **Abweichung = Radius × (1 − cos(180°/Segmente))**.

Praktisch heißt das, für eine im Druck unsichtbare Abweichung (unter **0,05 mm**):

| Radius | Durchmesser | Segmente |
|---|---|---|
| 5 mm | Ø 10 | **24** |
| 10 mm | Ø 20 | **32** |
| 25 mm | Ø 50 | **48** |
| 50 mm | Ø 100 | **64** |

Blenders Vorgabe von 32 Segmenten passt also für kleine Teile und wird bei großen Rundungen zu
grob. Umgekehrt sind 128 Segmente an einer 6-mm-Bohrung nur unnötig schwere Dateien.

**Bohrungen sind zusätzlich enger, als sie aussehen.** Blender legt den Radius auf die **Ecken**
des Vielecks – zwischen den Ecken ist das Loch schmaler. Bei Ø 8,4 mm mit 32 Segmenten fehlen rund
**0,08 mm** am nutzbaren Durchmesser. Zusammen mit der Schrumpfung beim Druck wird aus einem
M3-Durchgangsloch schnell ein zu enges. **Also: Bohrungen 0,1 mm großzügiger zeichnen als in
Plasticity, oder die Segmentzahl erhöhen.**

## 5. Shade Smooth täuscht

*Shade Smooth* lässt ein grobes Mesh am Bildschirm glatt aussehen – es verändert nur die
Beleuchtung, **kein einziges Polygon kommt dazu**. Der Drucker bekommt trotzdem das Vieleck.

**Das ist die häufigste Enttäuschung:** am Bildschirm rund, im Druck facettiert. Wer Rundungen
beurteilen will, schaltet auf *Shade Flat* oder aktiviert das Drahtgitter-Overlay.

## 6. Wasserdicht (Manifold)

Der Slicer braucht einen geschlossenen Körper: **jede Kante an genau zwei Flächen**. Eine Kante
mit nur einer Fläche ist ein Loch, eine mit drei ist eine Überschneidung.

Solche Fehler entstehen unsichtbar – ein misslungener Boolean, eine gelöschte Fläche, ein
gespiegeltes Teil ohne verschmolzene Mittelnaht. Deshalb die **Mesh-Probe** mit der 3D-Print
Toolbox nach heiklen Schritten und immer vor dem Export.

Die drei häufigsten Ursachen, in dieser Reihenfolge prüfen:

1. **Doppelte Punkte** – im Bearbeitungsmodus alles auswählen (`A`), dann `M` → *By Distance*.
   Der Klassiker nach Spiegeln.
2. **Innenflächen**, die beim Boolean übrig blieben.
3. **Offene Ränder** nach dem Löschen von Flächen.

## 7. Normalen zeigen nach außen

Jede Fläche hat eine Vorder- und eine Rückseite. Zeigen einzelne nach innen, hält der Slicer diese
Stellen für Hohlräume und druckt Unsinn.

**Sichtbar machen:** Overlays → *Face Orientation*. Blau ist richtig, **rot ist falsch herum**.
**Fix:** im Bearbeitungsmodus alles auswählen, `Shift`+`N` (*Recalculate Outside*).

Tritt gern nach Booleans und nach dem Import fremder Modelle auf.

## 8. Ngons sind die Boolean-Killer

Ein **Ngon** ist eine Fläche mit mehr als vier Ecken. Blender kommt damit zurecht – Booleans oft
nicht. Große Ngons an der Schnittstelle sind die häufigste Ursache für zerfetzte Ergebnisse.

Wenn ein Boolean misslingt:

1. **Solver** von *Fast* auf **Exact** stellen (im Modifier).
2. **Bündige Flächen vermeiden:** Liegen zwei Flächen exakt aufeinander, weiß der Algorithmus
   nicht, wohin. Den Abzieh-Körper **0,01 mm** überstehen lassen – derselbe Trick wie in Plasticity.
3. Ngons an der Schnittstelle vorher unterteilen.

**Und wie in Plasticity gilt:** Abzieh-Körper nicht löschen. Als Modifier stehen lassen und den
Werkzeugkörper ausblenden (Augensymbol) – dann lässt sich die Bohrung später noch ändern.

## 9. Die Modifier-Reihenfolge entscheidet

Der Stack wird **von oben nach unten** abgearbeitet. Dieselben Modifier in anderer Reihenfolge
ergeben etwas anderes. Bewährt für Bauteile:

```
1. Mirror      (Spiegeln – früh, damit alles Weitere auf beiden Hälften wirkt)
2. Array       (Wiederholungen)
3. Boolean     (Löcher, Aussparungen)
4. Bevel       (Fasen – NACH dem Boolean, sonst zerschneidet der Boolean die Fasen)
5. Solidify    (Wandstärke)
6. Weighted Normal  (Glättung, ganz zuletzt)
```

**Die wichtigste Zeile davon: Bevel nach Boolean.** Das entspricht der Plasticity-Regel
„Verrundungen kommen zuletzt" – aus demselben Grund.

## 10. Was beim Export passiert

**STL kennt keine Einheiten.** Die Datei enthält nur Zahlen; der Slicer nimmt an, es seien
Millimeter. Stimmen die Blender-Einheiten, passt es – sonst kommt das Teil um Faktor 1000 daneben.

- **3MF ist die bessere Wahl**, wenn der Slicer es annimmt: Es speichert Einheiten mit und kann
  mehrere Teile samt Anordnung enthalten.
- **Modifier werden beim Export angewendet**, aber nur die, die auch im Viewport aktiv sind. Ein
  Modifier, der nur fürs Rendern eingeschaltet ist, fehlt in der Datei.
- **Vor dem Export:** Mesh-Probe, Maßprobe unter *Dimensions*, und prüfen, ob das Teil mit seiner
  Standfläche auf **Z = 0** steht.
