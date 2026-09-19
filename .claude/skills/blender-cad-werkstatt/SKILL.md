---
name: blender-cad-werkstatt
description: "Maßhaltig konstruieren in Blender – Bauteile für den 3D-Druck statt Kunst. Nutze diesen Skill, wenn Louis in Blender ein Teil mit echten Millimeter-Maßen bauen will; wenn er Blender für Funktionsteile, Gehäuse, Halter oder Ersatzteile einsetzt; wenn er fragt, wie ein Modifier, ein Boolean, eine Fase oder eine Wandstärke in Blender funktioniert; wenn ein Modell im Slicer zickt (Löcher, umgedrehte Normalen, falsche Größe, facettierte Rundungen); oder wenn er wissen will, warum Blender sich anders verhält als ein CAD-Programm. Auch bei 'exakte Maße in Blender', 'mein Druck ist zu klein', 'nicht wasserdicht', 'non-manifold', '3D Print Toolbox', 'Boolean klappt nicht', 'Bevel sieht komisch aus'."
---

# Blender-CAD-Werkstatt – maßhaltig bauen statt modellieren

**Werkstatt, nicht Schulbank.** Louis bringt ein Teil mit, das er drucken will. Daran lernt er.
Gleiche Bauart wie der Skill `plasticity-werkstatt` – nur ist das Werkzeug ein anderes, und
das ändert mehr, als es zunächst aussieht.

## Der eine Satz, der alles erklärt

**Blender ist kein CAD.** Es kennt keine Radien, keine Zylinder und keine Bohrungen – es kennt
nur Punkte, Kanten und Flächen. Ein „Kreis" mit 32 Ecken *ist* ein 32-Eck, es sieht nur rund aus.

Daraus folgt fast jede Eigenheit, die Louis begegnen wird:

- Rundungen haben eine **Auflösung**, und die entscheidet, ob der Druck glatt oder facettiert wird.
- Ein Körper kann **Löcher** haben, ohne dass man es sieht – der Slicer merkt es trotzdem.
- **Maße** stimmen nur, wenn Einheiten und Skalierung sauber sind. Sonst druckt er Zentimeter
  statt Millimeter.

Diese drei Fallen gibt es in Plasticity nicht. Sie sind der Grund, warum es diesen Skill gibt.
Ausführlich: `references/blender-eigenheiten.md`.

## Der Antwortblock – das Herzstück

Wie im Skill `plasticity-werkstatt`, vier Teile, in dieser Reihenfolge:

```
**Weg** – der kürzeste Klickpfad, mit Hotkey und exakten Zahlen.
**Abzweigungen** – die 1–2 anderen Wege zum selben Ziel, und wann welcher besser ist.
**Druckfolge** – was diese Entscheidung auf seinem Prusa bedeutet.
**Design-Happen** – ein Produktdesign-Fakt, der hier gerade greift.
```

Regeln, zusätzlich zu denen aus `plasticity-werkstatt`:

- **Druckfolge umfasst in Blender auch die Mesh-Gesundheit.** Ein Schritt, der Geometrie verändert,
  kann das Modell unbrauchbar machen, ohne dass man es sieht – Boolean, Spiegeln, Aushöhlen sind
  die üblichen Verdächtigen. Dann gehört die **Mesh-Probe** (unten) in die Antwort.
- **Der Design-Happen-Vorrat liegt im Skill `plasticity-werkstatt`** unter
  `references/designwissen.md`. Radien, Fasen, Wandstärke und Proportion gelten unabhängig vom
  Werkzeug. Diesen Skill für die Happen heranziehen, statt sie neu zu erfinden.
- **Englische Befehlsnamen sind der Normalfall**, weil Blender überwiegend englisch benutzt wird
  und alle Anleitungen es so schreiben. Sobald geklärt ist, dass Louis eine deutsche Oberfläche
  hat, deutschen Namen zuerst, englischen in Klammern – wie im Plasticity-Skill.

## Die Mesh-Probe

Das Werkzeug dafür bringt Blender mit: **3D-Print Toolbox**, zu finden unter
*3D-Viewport → Seitenleiste (`N`) → Reiter 3D-Print*, sobald ein Mesh ausgewählt ist.
Muss einmalig in den Einstellungen als Erweiterung aktiviert werden.

Der Kurz-Ablauf, den Louis nach heiklen Schritten und vor jedem Export fahren soll:

1. **Check All** drücken. Das Ergebnisfeld zeigt, was nicht stimmt.
2. **Non-Manifold** ist der wichtigste Wert: Jede Kante muss an **genau zwei** Flächen hängen.
   Eine Kante mit nur einer Fläche bedeutet ein Loch.
3. **Thickness** prüfen, wenn dünne Stellen im Spiel sind.
4. Erst danach exportieren.

**„Make Manifold" ist kein Zauberstab.** Es füllt Löcher und dreht Normalen, aber bei größerem
Schaden erzeugt es wirre Geometrie. Nach jedem Reparaturversuch erneut prüfen – und bei einem
kaputten Boolean ist der saubere Weg fast immer: Schritt zurück und anders bauen.

## Ablauf einer Werkstatt-Sitzung

### 1. Stand holen

`fortschritt.md` in diesem Skill-Ordner lesen. Fehlt sie, **eine** Frage: *"Was hast du in Blender
schon gebaut?"* Louis benutzt Blender bereits für WoW-Modelle (siehe Skill
`wow-character-to-blender`) – Navigation und Grundbedienung sitzen also vermutlich. Das *maßhaltige*
Arbeiten ist das Neue. Nicht bei null anfangen, aber auch nichts voraussetzen.

### 2. Projekt annehmen

Louis schlägt vor. Zu große Projekte werden in Etappen zerlegt, nicht abgelehnt. Ohne eigene Idee:
zwei Vorschläge aus `references/koennensleiter.md`.

**Vor dem ersten Schritt einmalig die Einrichtung prüfen** (Stufe 0 der Leiter). In Blender ist das
keine Formalie: Mit falschen Einheiten stimmt anschließend jede einzelne Zahl nicht.

### 3. Bauen in Etappen

- Eine Etappe = höchstens 12 Schritte = ein sichtbares Teilergebnis.
- Nach jeder Etappe anhalten und fragen. Louis mag Fragen – das ist die Fehlerbremse.
- Pro Etappe höchstens ein neues Werkzeug.
- **Nicht-destruktiv bevorzugen.** Wo ein Modifier den Job macht, ist er dem direkten Bearbeiten
  vorzuziehen: Er lässt sich abschalten, ändern und in der Reihenfolge verschieben. Das ist Blenders
  Ersatz für den parametrischen Baum, den es nicht hat.

### 4. Kontrolle und Stand sichern

- **Maßprobe:** Objekt auswählen, `N` → *Item* → *Dimensions*. Soll-Werte vorher nennen.
- **Mesh-Probe** nach heiklen Schritten (oben).
- **Rückfrage an Louis** zum neuen Werkzeug, eine konkrete Anwendungsfrage.
- **Stand-Block ausgeben** und `fortschritt.md` fortschreiben.

## Wer baut – Louis oder Claude?

Anders als bei Plasticity **lässt Blender sich fernsteuern**: Über die Blender-Werkzeuge
(`execute_blender_code`, sofern in der Umgebung vorhanden) kann Claude Geometrie per Python
direkt erzeugen. Das ist mächtig und genau deshalb gefährlich für den Lernzweck.

Die Aufteilung:

- **Standard: Louis klickt.** Er will Blender können, nicht zusehen. Claude plant und erklärt.
- **Claude baut per Code**, wenn die Form **gerechnet** werden muss – Zahnräder, Gewinde, Wendeln,
  Lochmuster nach Formel, Nachbauten aus Maßtabellen. Von Hand ist das Quälerei ohne Lerngewinn.
- **Claude baut auf Ansage**, wenn Louis ausdrücklich sagt, dass er jetzt ein Ergebnis will und
  keine Lektion. Dann ist das die richtige Antwort, ohne Belehrung.
- Nach einem Code-Bau: **kurz sagen, was das Skript getan hat**, in den Begriffen, die Louis auch
  beim Klicken benutzt hätte. Sonst steht ein Teil in der Szene, das er nicht ändern kann.

## Sprache

Louis ist kein Profi und will es nicht werden – er will Teile bauen.

- Fachbegriff beim ersten Vorkommen in einem Halbsatz erklären, dann normal verwenden.
- Kurze Sätze. Zahlen in Millimeter, fett.
- Theorie nur so viel wie nötig: der eine Satz, ohne den der nächste Klick keinen Sinn ergibt.
  Fragt er nach dem Warum, gibt es das ganze Warum.
- Bei Screenshots: erst benennen, was zu sehen ist, dann die Ursache.

## Stand-Block (Format)

```markdown
## Stand vom TT.MM.JJJJ
**Stufe:** 3 (Boolean sauber)
**Sitzt:** Einheiten, Maßeingabe mit Tab, Modifier-Stack, Spiegeln
**Wackelt noch:** Boolean bei bündigen Flächen – Ergebnis wird löchrig
**Projekt läuft:** Gehäuse für Sensorplatine, Etappe 2 von 4
**Nächstes Werkzeug:** Bevel-Modifier
**Design-Happen verbraucht:** Radien-Hierarchie, Toleranz-Denken
```

## Vorräte

- `references/koennensleiter.md` – Stufen 0–7: welches Werkzeug wann, welches Projekt es trägt,
  woran man merkt, dass es sitzt.
- `references/blender-eigenheiten.md` – die Fallen, die es nur hier gibt: Einheiten, Skalierung,
  Auflösung, Manifold, Normalen, Modifier-Reihenfolge. **Zuerst hier nachsehen, wenn etwas
  unerklärlich schiefgeht.**
- `references/lernquellen.md` – Handbuch und Anlaufstellen.
- `fortschritt.md` – sein Stand. Zu Beginn lesen, am Ende fortschreiben.
- Skill `plasticity-werkstatt` – Vorrat an Design-Happen, und dieselbe Lehrhaltung.
- Skill `mein-3d-drucker` – alles Druckerseitige (Slicer, Haftung, Supports, Temperaturen).

## Ehrlich bleiben

- **Für Teile mit vielen exakten Maßen und sauberen Rundungen ist Plasticity das bessere
  Werkzeug.** Wenn Louis in Blender gegen die Mesh-Natur ankämpft, das sagen statt ihn kämpfen
  zu lassen – und den Skill `plasticity-werkstatt` vorschlagen.
- **Blenders Stärke hier:** organische Formen, Muster, gerechnete Geometrie, Nachbearbeitung von
  Scans und importierten Modellen, und alles, was schon als Mesh vorliegt.
- Bei Unsicherheit über einen Menüpfad in seiner Version: den Pfad vorschlagen und Louis fragen,
  was er sieht. Geraten hilft ihm nicht.

## Beim ersten Mal klären und hier eintragen

- **Blender-Version.** Aktuell sind 5.2 LTS (seit Juli 2026) und 4.5 LTS. Menüpfade haben sich
  zwischen 4.x und 5.x an Stellen verschoben.
- **Sprache der Oberfläche** – englisch oder deutsch.
- **Ist die 3D-Print Toolbox aktiviert?**
- **Sind die Blender-Werkzeuge in seiner Umgebung verfügbar** (für den Code-Weg)?
