# Design-Happen – Vorrat

Louis hat sich ausdrücklich *"ein paar Produktdesign-theoretische Fakten"* mitbestellt. Das ist der
vierte Teil des Antwortblocks.

## Auswahlregel

- **Einer pro Antwort.** Drei bis fünf Sätze. Zwei Happen in einer Antwort sind einer zu viel.
- **Nur wenn er gerade greift.** Der Happen muss sich auf das Teil beziehen, an dem Louis in
  diesem Moment arbeitet. Passt keiner, bleibt das Feld leer – ein Fakt, den er sofort anwenden
  kann, bleibt hängen; ein Fakt zum Auswendiglernen ist verschwendet.
- **Verbrauchte notieren** im Stand-Block unter *Design-Happen verbraucht*. Ein zweites Mal kommt
  derselbe Fakt nur noch **angewendet** ("wie bei der Radien-Hierarchie letztes Mal"), nicht
  nochmal erklärt.
- **Zahlen mitgeben.** "Achte auf Proportion" ist nutzlos. "Alle Radien als Vielfache von 2 mm" ist
  etwas, das er eintippen kann.
- Alle Millimeterwerte hier sind Richtwerte für **0,4 mm Düse, PLA**, seinen Prusa. Bei anderem
  Material laut sagen, dass die Zahl sich verschiebt.

---

## 1. Das Modul

Ein Teil wirkt stimmig, wenn seine Maße nicht zufällig sind. Der billigste Trick dafür: eine
Grundeinheit festlegen – bei kleinen Teilen **2 mm** – und alle Radien, Abstände, Stegbreiten und
Rücksprünge als Vielfache davon bauen. Radien also 2, 4, 6, 8 mm statt 1,7 und 3,4.

Das ersetzt Formgefühl durch eine Regel, und es macht das Teil nebenbei leichter zu ändern: alles
verschiebt sich in denselben Schritten. Profis nennen das Rastermaß.

## 2. Radien-Hierarchie

Zwei Regeln, die fast jede Verrundung richtig machen:

- **Je weiter außen eine Kante liegt, desto größer ihr Radius.** Die große Außenkante bekommt
  **4 mm**, die Kante der Aussparung darin **2 mm**, die kleine Fase am Detail **0,5 mm**. Gleiche
  Radien überall lassen ein Teil flach und beliebig wirken.
- **Bei verschachtelten Kanten gilt: Außenradius = Innenradius + Wandstärke.** Bei **2 mm** Wand
  und **3 mm** innen wird die Außenkante **5 mm**. Nur so bleibt die Wand überall gleich dick.
  Verletzt man das, wird die Wand an der Ecke dünner oder dicker – sichtbar und beim Druck
  ungünstig.

## 3. Fase oder Rundung

Beide nehmen die scharfe Kante weg, aber sie sagen etwas Unterschiedliches: Eine **Fase** wirkt
technisch, präzise, gemacht. Eine **Rundung** wirkt weich, handwerklich, anfassbar. Werkzeuge und
Gehäuse bekommen Fasen, Griffe und Deko Rundungen. Beides gemischt ohne System wirkt unentschlossen.

Praktisch wichtiger: **eine Kante ohne Behandlung sieht unfertig aus.** Eine durchgehende **0,5 mm**
Fase an allen Kanten, die nichts Besseres verdient haben, ist der billigste Weg, ein Teil "fertig"
aussehen zu lassen – und sie nimmt die Grate weg, an denen man sich beim gedruckten Teil kratzt.

## 4. Die Bettkante gehört der Fase

An der Kante, die auf dem Druckbett liegt, immer eine **0,5–1 mm** Fase, nie eine Rundung. Zwei
Gründe: Der Elefantenfuß – die leicht breitgedrückte erste Schicht – zerstört eine Rundung dort
ohnehin. Und eine Rundung läuft unten flach aus, was der Drucker als Überhang behandeln muss; eine
**45°** Fase druckt sauber ohne Stütze.

## 5. Die Schattennut

Wo zwei Teile aneinanderstoßen – Deckel auf Dose, Front auf Gehäuse – entsteht ein Spalt, und der
ist nie gleichmäßig. Der Trick aus dem Spritzguss: **die Fuge absichtlich zeichnen.** Eine Nut von
**1–2 mm** Breite und **0,5–1 mm** Tiefe rundherum an der Trennstelle.

Ein bewusster Schatten dort liest das Auge als Gestaltung. Ein unbewusster, ungleichmäßiger Spalt
liest es als Fehler. Beim Drucken ist das doppelt wertvoll, weil sich die Maßabweichung des Druckers
genau dort versteckt.

## 6. Gleichmäßige Wandstärke

Eine Wand, die überall gleich dick ist, sieht gekonnt aus **und** druckt besser. Dicke
Materialanhäufungen kühlen langsamer als ihre Umgebung und ziehen sich dabei zusammen – das ist die
Ursache von Verzug und Spannungsrissen. Deshalb: Volumen aushöhlen statt massiv lassen, und
Übergänge von dick auf dünn nicht abrupt, sondern über eine Schräge oder Rundung.

Richtwert für ihn: Wand mindestens **1,2 mm** (3 Bahnen), für tragende Teile **2 mm**, gleichmäßig.
Dafür ist **Aushöhlen** (Hollow) das richtige Werkzeug – nicht ein zweiter, kleinerer Körper zum
Abziehen, weil dessen Wandstärke an Ecken und Rundungen wandert.

## 7. Toleranz-Denken

Kein gedrucktes Maß trifft exakt. Deshalb zu jedem Teil **vorher** festlegen: welche zwei oder drei
Maße sind kritisch, und welche dürfen wandern.

Kritisch sind immer nur Maße, die an etwas anderes anschließen: Lochabstand zum Schraubmuster,
Innenmaß zum Bauteil, Steckmaß zum Gegenstück. Die Außenkontur darf fast immer **0,3 mm** daneben
liegen, ohne dass es jemand merkt. Wer alle Maße gleich wichtig nimmt, verliert Zeit an der falschen
Stelle.

Rechenwerte für seinen Drucker: Löcher **0,2–0,4 mm** größer zeichnen als gewünscht (M3-Durchgang
also **3,4 mm**), Steckpassungen mit **0,2–0,3 mm** Gesamtspiel, Presssitz **0,1 mm**.

## 8. Funktionsflächen zuerst

Die Reihenfolge, die verhindert, dass ein schönes Teil nicht passt: **zuerst die Flächen festlegen,
die etwas tun.** Die Auflagefläche, die Passfläche, die Schraubfläche, die Fläche, an der etwas
anliegt. Deren Maße stehen fest, sobald das Gegenstück gemessen ist.

Alles andere – Außenform, Radien, Proportion – wird **danach** darumherum gestaltet und darf sich
frei bewegen. Umgekehrt ist der klassische Anfängerfehler: die schöne Hülle steht, und dann passt
die Platine nicht hinein.

## 9. Symmetrie mit einem Bruch

Symmetrie beruhigt und ist in Plasticity halb so viel Arbeit (eine Hälfte bauen, `Alt`+`X`
spiegeln, `J` verbinden). Aber vollkommen symmetrisch wirkt steril.

Ein **einziger** bewusster Bruch macht ein Objekt interessant: eine Kabelöffnung, eine Beschriftung,
eine abgeschnittene Ecke. Genau einer. Zwei Brüche lesen sich als Zufall, und dann ist die Wirkung
der Symmetrie weg.

## 10. Ergonomie in Zahlen

Wenn etwas angefasst oder gedrückt wird, gibt es Maße, die man nicht schätzen muss (Richtwerte für
Erwachsene):

- **Fingerbreite:** 16–20 mm. Eine Griffmulde für einen Finger also mindestens **20 mm** breit.
- **Griff, den man mit ganzer Hand umfasst:** Ø **30–40 mm**, am angenehmsten um **35 mm**.
- **Fläche, die man gezielt drückt:** mindestens **10 mm** breit, Abstand zum Nachbarn **5 mm**.
- **Kantenradius, den man gern anfasst:** ab **2 mm**, ab **3 mm** wird es angenehm.
- **Daumenauflage:** rund **25 mm** Breite.

Das Bessere schlägt jede Tabelle: seine eigene Hand messen lassen. Bei Griffen ist ein Probedruck
von nur **20 mm** Höhe die günstigste Investition – Gefühl lässt sich nicht am Bildschirm prüfen.

## 11. Detail-Dichte und Ruhe

Ein Objekt wirkt hochwertig, wenn die Details **an einer Stelle konzentriert** sind und der Rest
ruhig bleibt. Alles überall gleichmäßig detailliert wirkt unruhig und billig – das ist der Grund,
warum billiges Plastikspielzeug überall Rillen, Stege und Muster hat.

Praktisch: eine Zone für Beschriftung, Textur und Details wählen, und mindestens eine große Fläche
bewusst leer lassen. Beim Drucken zahlt das doppelt, weil große ruhige Flächen mit weniger
Druckfehlern durchkommen als zerklüftete.

## 12. Die Fertigung gehört zum Entwurf

Die Form der Fertigungsart anzupassen ist kein Kompromiss, sondern der Beruf. Beim Druck heißt das:

- **45°-Regel.** Überhänge bis **45°** gehen ohne Stütze. Steiler → Teil anders ausrichten oder
  eine Stützschräge in die Form einbauen. Eine Form, die Stützen braucht, ist selten die schönste
  Lösung – die stützenfreie Variante ist meistens auch die ruhigere.
- **Schichtlinien nutzen, statt sie zu bekämpfen.** Wer bewusst waagerechte Rillen einplant, kriegt
  ein Teil, an dem die Schichtlinien wie Absicht aussehen.
- **Die Ausrichtung im Slicer beim Entwurf schon mitdenken.** Ein Teil, das auf der richtigen
  Fläche steht, braucht keine Stützen und ist in der Belastungsrichtung stabiler – gedruckte Teile
  brechen bevorzugt **zwischen** den Schichten.

## 13. Die schwebende Standfläche

Ein Objekt wirkt leichter, wenn es unten schmaler ist als sein Körper: ein Rücksprung von **1–2 mm**
rundherum, sodass die Standfläche im Schatten verschwindet. Dieselbe Idee wie bei Möbelsockeln.

Beim Druck hat dieser Rücksprung einen Haken: Er ist ein Überhang. Deshalb keine Kehle, sondern eine
**45° Fase** vom Rücksprung nach außen – dann wächst die Form stützenfrei nach oben und der
Schatteneffekt bleibt.

## 14. Warum billige Teile billig aussehen

Der Unterschied liegt fast immer in den **Übergängen zwischen Flächen**, und dafür gibt es drei
Stufen:

- **G0** – die Flächen treffen sich, es bleibt ein Knick. Sichtbare Kante.
- **G1** – der Knick ist weg, die Flächen laufen tangential ineinander. Aber die Krümmung springt,
  und das Auge sieht dort eine **Lichtkante**: eine feine helle Linie im Reflex.
- **G2** – auch die Krümmung geht stetig über. Der Reflex läuft ohne Sprung durch, und genau das
  liest man als "teuer".

Für Funktionsteile ist **G1** völlig ausreichend, und das macht eine normale Verrundung. Bei
Schauflächen lohnt die krümmungsstetige Variante – im Verrundungs-Dialog gibt es dafür eine Option.
Wie sie in seiner Version 2026.1 genau heißt, mit ihm zusammen im Dialog nachsehen, statt einen
Namen zu raten.

Der Test ohne Theorie: Modell drehen und den Glanzstreifen beobachten. Läuft er glatt durch, ist
der Übergang gut. Knickt oder blitzt er an der Verrundung, ist es G1.
