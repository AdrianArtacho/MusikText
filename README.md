# MusicXML Lyric Player

See it [in action](https://adrianartacho.github.io/MusikText/?file=MyBoat9.musicxml&tempo=200&bg=classroom.jpg).

Idee: [Veronika Humpel](https://www.musikschule-simmering.at/unterrichtsfaecher/elementares-musizieren/) ([Musikschule Simmering](https://www.musikschule-simmering.at/), Wien)

Ein einfacher browserbasierter Player für Gesangsmelodien im MusicXML-Format. Die Melodie wird abgespielt, während der Liedtext synchron in großen Rechtecken dargestellt wird.

---

Ein einfacher browserbasierter Player für Gesangsmelodien im MusicXML-Format. Die Melodie wird abgespielt, während der Liedtext synchron in großen Rechtecken dargestellt wird. Das Projekt ist für GitHub Pages geeignet und benötigt keinen Server.

## Export aus MuseScore

> Beispiel [MuseScore file](https://raw.githubusercontent.com/AdrianArtacho/MusikText/main/INPUT/MyBoat.mscz).

**Wichtig:** Die Partitur muss als **unkomprimierte `.musicxml`-Datei** exportiert werden.

**Datei → Exportieren → Uncompressed MusicXML (*.musicxml)**

Das komprimierte Format (`.mxl`) wird derzeit nicht unterstützt.

---

## Unterstützte MuseScore-Funktionen

### Liedtext

Normale Liedtexte werden automatisch erkannt.

Beispiel:

* My
* boat
* lies
* o-ver
* the
* o-cean

Mehrsilbige Wörter werden automatisch zusammengefügt:

* `o` + `ver` → `over`
* `o` + `cean` → `ocean`

---

### Alternative Texte

Mehrere Liedtextzeilen werden als Alternativen interpretiert.

Beispiel in MuseScore:

| Zeile 1 | Zeile 2 | Zeile 3 |
| ------- | ------- | ------- |
| boat    | knee    | house   |

Anzeige:

```
[boat]
 knee
 house
```

Durch Anklicken eines alternativen Textes wird dieser mit dem Haupttext vertauscht.

---

### Zeilenumbrüche (System Breaks)

Manuelle Zeilenumbrüche in MuseScore werden übernommen.

Verwendet dazu:

**Palette → Umbrüche & Zwischenräume → Systemumbruch**

Jede Zeile der Partitur wird als eigene Zeile von Rechtecken dargestellt.

---

### Farbige Notenköpfe

Die Farbe eines Notenkopfes wird auf das entsprechende Wort übertragen.

Beispiel:

* roter Notenkopf → roter Rahmen
* blauer Notenkopf → blauer Rahmen

Bei mehrsilbigen Wörtern wird die Farbe der ersten Silbe verwendet.

---

### Titel

Der Titel der Partitur wird automatisch übernommen.

Empfohlen:

**Datei → Partitureigenschaften**

oder

**Format → Stil → Titel**

Der Titel erscheint automatisch oberhalb der Rechtecke.

---

## URL-Parameter

Die Anwendung kann direkt über URL-Parameter gesteuert werden.

### MusicXML-Datei laden

```
?file=MyBoat9.musicxml
```

Die Datei wird im Ordner

```
INPUT/
```

gesucht.

---

### Hintergrundbild

```
?bg=classroom.jpg
```

Das Bild wird im Ordner

```
bg/
```

gesucht.

---

### Tempo

```
?tempo=120
```

Überschreibt das in der Partitur gespeicherte Tempo.

---

### Beispiel

```
?file=MyBoat9.musicxml&tempo=120&bg=classroom.jpg
```

---

## Bedienung

* **Play** startet die Wiedergabe.
* **Stop** stoppt die Wiedergabe.
* **Leertaste** startet bzw. stoppt die Wiedergabe.
* Beim ersten Start wird automatisch Vollbild aktiviert (sofern vom Browser erlaubt).
* **Loop** wiederholt die Wiedergabe endlos.

---

## Ordnerstruktur

```
index.html

INPUT/
    MyBoat9.musicxml
    Song2.musicxml

bg/
    classroom.jpg
    beach.jpg
```

---

## GitHub Pages

Das Projekt kann direkt über GitHub Pages betrieben werden. Es wird kein Server benötigt; alle Dateien werden vollständig im Browser verarbeitet.

---

## [📝ToDo](https://trello.com/c/IZXmK94t/152-humpel-musiktext)