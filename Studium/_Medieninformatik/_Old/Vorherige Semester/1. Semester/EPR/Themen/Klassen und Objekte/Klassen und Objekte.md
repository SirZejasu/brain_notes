#Themen 
#EPR
#Medieninformatik 

---
# Quellen
[[Skript - Klassen und Objekte]]

# Definition Klasse
----
Klassen sind Baupläne für erzeugte Objekte.

---
Eine Klasse enthält den Aufbau eines Objekts sowie Methoden, die das Objekt selbst ausführen können.

## Aufbau einer Klasse
- Statische Methoden sind Klassenmethoden.
- Klassenvariablen
	- Definiert durch static.
- Konstruktoren
	- Wird verwendet, um Objekte zu erzeugen.
	- Name ist gleich der Klasse.
- Get-Methoden
- Instanz-Methoden

## Konstruktor
Diese Methode innerhalb einer Klasse ist wichtig, da hierdurch neue Objekte beim Aufruf der Klasse erzeugt werden können.

### Vorlesung
#### Erzeugen eines neuen Objekts durch den Konstruktor
![[Pasted image 20221130151436.png]]
![[Pasted image 20221130151713.png]]


### Aufbau eines Konstruktors
- Variable desselben Typs der Klasse
- Erzeugung eines Objekts
	- Durch die Zuweisung zu einer Variable
	- Aufruf durch den Operator "new"
- Instanzvariablen

#### Abschnitt aus Code-Beispiel
```java
-- Konstruktor innerhalb der Klasse von "RechteckTest" --
    /*
     * Variable des Typs Rechteck deklarieren. Die Variable kann durch Zuweisungen mit Objekten der
     * Klasse Rechteck belegt werden.
     */
    Rechteck r;

    /*
     * Der Variablen r ein Rechteck-Objekt zuweisen.
     */
    r = new Rechteck(2.5, 1.5);
```

### Code Beispiel
#### Rechteck Test


## Instanzmethoden
----
Instanzmethoden sind Methoden in einer Klasse, die von Objekten der selben Klasse ausgeführt werden. 

---

### Sonstiges
- Werden ohne den Modifikator static deklariert.
- Aufgerufen durch Objekt.Methodenname (Parameter)
- Instanzmethoden können auch verwendet werden, um den Zustand eines Objekts zu verändern. Der Return-Wert kann von typ void sein.

## Instanzvariablen
----
Instanzvariablen sind nicht-statische Variablen einer Klasse. Bei jedem Erzeugen eines Objekts bzw. einer Instanz wird diese Variable dem Objekt vererbt.

---

### Code Beispiel
#### Beispielcode einer Instanzmethode, der nur den Zustand eines Objekts verändern soll
![[Pasted image 20221130163559.png]]
#### Code Abschnitt
```java
/**
   * Veranschaulicht Zugriffe auf Instanzmethoden der Klasse Rechteck.
   */
  public static void testeInstanzmethoden() {

    /*
     * Rechteck erzeugen und einer Variablen zuweisen.
     */
    Rechteck r = new Rechteck(1, 2, 3, 4);

    /*
     * Instanzmethode zur Berechnung der Fläche aufrufen.
     */
    System.out.println(r.gibFlaeche());

    /*
     * Hat die Instanzmethode einen anderen Ergebnistyp als void, handelt es sich bei dem Aufruf um
     * einen Ausdruck, der insbesondere innerhalb anderer Ausdrücke verwendet werden kann.
     */
    System.out.println(2 * r.gibFlaeche() + 3);

    /*
     * Der Objektausdruck vor dem Punkt muss keine Variable sein. Es ist jeder Ausdruck erlaubt, der
     * ein entsprechendes Objekt als Wert liefert. Aber: Typen müssen beachtet werden! Hat der
     * Objektausdruck den Typ T (wobei T eine Klasse ist), dann sind nur Instanzmethoden rechts vom
     * Punkt (.) zulässig, die in der Klasse T bekannt sind. Dies heißt zunächst, die
     * Instanzmethoden müssen in der Klasse T definiert sein.
     */
    System.out.println(2 * (new Rechteck(1, 2, 3, 4)).gibFlaeche() + 3);

    /*
     * Aufruf der Methode um festzustellen, ob Rechteck einen Punkt enthält.
     */
    System.out.println(r.enthaeltPunkt(new Punkt(1.5, 3.5)));

    /*
     * Aufruf der Methode zum Verschieben eines Rechtecks. Beachte: bei diesem Aufruf handelt es
     * sich nicht um einen Ausdruck, da die Instanzmethode keinen Ergebnistyp besitzt.
     */
    System.out.println(r.gibAlsString());
    r.verschiebe(2, 5);
    System.out.println(r.gibAlsString());

    /*
     * Zweites Rechteck erzeugen. Instanzmethode aufrufen, um daraus und dem Rechteck in der
     * Variablen r die Rechteckhülle zu erzeugen.
     */
    Rechteck r2 = new Rechteck(3.5, 4.5, 4.5, 9.5);
    Rechteck huelle = r.erzeugeHuelle(r2);
    System.out.println(huelle.gibAlsString());
  }
```


### Vorlesung
![[Pasted image 20221130160823.png]]

# Definition Objekte
----
Objekte werden aus Klassen erzeugt und sollen im Programm Objekte aus der realen darstellen. Objekte sind also strukturierte Daten.

---
Objekte werden durch Konstruktoren in Klassen erzeugt. Objekte haben neben den Bauplan eigene, individuelle Methoden und Variablenwerte.

## Aufbau eines Objekts
- Alle Werte und Methoden aus der Klasse als Vorlage
- Individuelle Werte und Methoden
- Eigene Identität
	- Operatoren == und != vergleichen die Identität von Objekten
- Instanzvariablen
	- Zugriff durch Objektname.Instanzvariable

# SC aus Vorlesung
## Punkt
```java

/**
 * Ein Objekt dieser Klasse repräsentiert einen Punkt in einer 2D-Ebene.
 */
public class Punkt {

  /**
   * Horizontale Koordinate dieses Punkts.
   */
  private double x;

  /**
   * Vertikale Koordinate dieses Punkts.
   */
  private double y;

  /**
   * Erzeugt einen Punkt mit den angegebenen Koordinaten.
   *
   * @param x horizontale Koordinate dieses Punkts
   * @param y vertikale Koordinate dieses Punkts
   */
  public Punkt(double x, double y) {

    this.x = x;
    this.y = y;
  }

  /**
   * Gibt an, ob der übergebene Punkt rechts unterhalb von diesem Punkt liegt.
   *
   * @param punkt Punkt, für den geprüft wird, ob er rechts unterhalb von diesem Punkt liegt.
   * @return {@code true} genau dann, wenn der übergebene Punkt rechts unterhalb von diesem Punkt
   *         liegt. Als rechts bzw. unterhalb wird auch gewertet, wenn beide Punkte dieselbe
   *         horizontale bzw. vertikale Koordinate besitzen.
   */
  public boolean istRechtsUnterhalb(Punkt punkt) {

    return (this.x <= punkt.x) && (this.y <= punkt.y);
  }

  /**
   * Liefert die horizontale Koordinate dieses Punkts.
   *
   * @return horizontale Koordinate dieses Punkts.
   */
  public double gibX() {

    return this.x;
  }

  /**
   * Liefert die vertikale Koordinate dieses Punkts.
   *
   * @return vertikale Koordinate dieses Punkts.
   */
  public double gibY() {

    return this.y;
  }

  /**
   * Verschiebt diesen Punkt um das angegebene Maß in horizontaler und vertikaler Richtung.
   *
   * @param xVerschiebung Verschiebung in horizontaler Richtung; durch Wert größer 0 wird nach
   *                      rechts verschoben
   * @param yVerschiebung Verschiebung in vertikaler Richtung; durch Wert größer 0 wird nach unten
   *                      verschoben
   */
  public void verschiebe(double xVerschiebung, double yVerschiebung) {

    this.x = this.x + xVerschiebung;
    this.y = this.y + yVerschiebung;
  }

  /**
   * Liefert einen Punkt, der gegenüber diesem Punkt das angegebene Maß in horizontaler und
   * vertikaler Richtung verschoben ist.
   *
   * @param xVerschiebung Verschiebung in horizontaler Richtung
   * @param yVerschiebung Verschiebung in vertikaler Richtung
   * @return neuer Punkt, der gegenüber diesem Punkt verschoben ist
   */
  public Punkt gibVersetztenPunkt(double xVerschiebung,
          double yVerschiebung) {

    return new Punkt(x + xVerschiebung, y + yVerschiebung);
  }

  /**
   * Liefert eine textuelle Darstellung dieses Punkts.
   *
   * @return textuelle Darstellung im Format (x, y)
   */
  public String gibAlsString() {

    return "(" + this.x + ", " + this.y + ")";
  }
}
```



## Rechteck
```java

/**
 * Ein Objekt dieser Klasse repräsentiert ein Rechteck in einer 2D-Ebene. Die
 * Seiten des Rechtecks liegen parallel bzw. senkrecht zur horizontalen und
 * vertikalen Koordinaten-Achse.
 */
public class Rechteck {

  /**
   * Ursprung, d.h. linke obere Ecke dieses Rechtecks.
   */
  private Punkt ursprung;

  /**
   * Breite dieses Rechtecks.
   */
  private double breite;

  /**
   * Höhe dieses Rechtecks.
   */
  private double hoehe;

  /**
   * Erzeugt ein Rechteck, dessen Breite und Höhe 0 ist. Der Ursprung des Rechtecks ist der Punkt
   * (0, 0).
   */
  public Rechteck() {

    this.ursprung = new Punkt(0, 0);
    this.breite = 0;
    this.hoehe = 0;

  }

  /**
   * Erzeugt ein Rechteck mit der angegebenen Breite und Höhe. Der Ursprung liegt bei (0, 0).
   *
   * @param breite Breite dieses Rechtecks
   * @param hoehe  Höhe dieses Rechtecks
   */
  public Rechteck(double breite, double hoehe) {

    this.ursprung = new Punkt(0, 0);
    this.breite = breite;
    this.hoehe = hoehe;
  }

  /**
   * Erzeugt ein Rechteck mit den angegebenen Koordinaten.
   *
   * @param x      horizontaler Ursprung dieses Rechtecks
   * @param y      vertikaler Ursprung dieses Rechtecks
   * @param breite Breite dieses Rechtecks
   * @param hoehe  Höhe dieses Rechtecks
   */
  public Rechteck(double x, double y, double breite, double hoehe) {

    this.ursprung = new Punkt(x, y);
    this.breite = breite;
    this.hoehe = hoehe;
  }

  /**
   * Prüft, ob der übergebene Punkt innerhalb dieses Rechtecks oder auf dessen Begrenzungslinien
   * liegt.
   *
   * @param punkt Punkt
   * @return {@code true} genau dann, wenn der Punkt innerhalb dieses Rechtecks oder auf seinen
   *         Begrenzungslinien liegt
   */
  public boolean enthaeltPunkt(Punkt punkt) {

    return (this.ursprung.gibX() <= punkt.gibX()
            && punkt.gibX() <= this.ursprung.gibX() + this.breite
            && this.ursprung.gibY() <= punkt.gibY()
            && punkt.gibY() <= this.ursprung.gibY() + this.hoehe);

    /*
     * so geht's auch:
     */
    // Punkt eckpunkt = ursprung.gibVersetztenPunkt(this.breite,
    //                                              this.hoehe);
    // return (this.ursprung.istRechtsUnterhalb(punkt)
    //         && punkt.istRechtsUnterhalb(eckpunkt));
  }

  /**
   * Liefert die Fläche dieses Rechtecks.
   *
   * @return Fläche dieses Rechtecks
   */
  public double gibFlaeche() {

    return this.breite * this.hoehe;
  }

  /**
   * Vergrößert dieses Rechteck um den angegebenen Faktor.
   *
   * @param faktor Faktor, um den das Rechteck vergrößert wird
   */
  public void vergroessere(double faktor) {

    this.breite = faktor * this.breite;
    this.hoehe = faktor * this.hoehe;
  }

  /**
   * Verschiebt dieses Rechteck um das angegebene Mass in horizontaler und vertikaler Richtung.
   *
   * @param xVerschiebung Verschiebung in horizontaler Richtung; durch Wert größer 0 wird nach
   *                      rechts verschoben
   * @param yVerschiebung Verschiebung in vertikaler Richtung; durch Wert größer 0 wird nach unten
   *                      verschoben
   */
  public void verschiebe(int xVerschiebung, int yVerschiebung) {

    this.ursprung.verschiebe(xVerschiebung, yVerschiebung);
  }

  /**
   * Liefert das kleinste Rechteck, das dieses und das übergebene Rechteck umhüllt. Beide Rechtecke
   * bleiben unverändert.
   *
   * @param rechteck ein Rechteck
   * @return kleinstes Rechteck, das dieses Rechteck und {@code rechteck} umhüllt
   */
  public Rechteck erzeugeHuelle(Rechteck rechteck) {

    /*
     * Minimale und maximale horizontale und vertikale Koordinaten beider Rechtecke bestimmen.
     */
    double xMin = Math.min(this.ursprung.gibX(), rechteck.ursprung.gibX());
    double yMin = Math.min(this.ursprung.gibY(), rechteck.ursprung.gibY());

    double xMax = Math.max(this.ursprung.gibX() + this.breite,
            rechteck.ursprung.gibX() + rechteck.breite);
    double yMax = Math.max(this.ursprung.gibY() + this.hoehe,
            rechteck.ursprung.gibY() + rechteck.hoehe);

    return new Rechteck(xMin, yMin, xMax - xMin, yMax - yMin);
  }

  /**
   * Liefert eine textuelle Repräsentation dieses Rechtecks.
   *
   * @return textuelle Repräsentation dieses Rechtecks mit Angabe seiner Koordinaten
   */
  public String gibAlsString() {

    return "Rechteck (Ursprung = "
            + this.ursprung.gibAlsString()
            + ", Breite = " + this.breite
            + ", Höhe = " + this.hoehe + ")";
  }

  /**
   * Veranschaulicht Zugriffe auf Instanzvariablen der Klasse Rechteck.
   *
   * @param args wird nicht verwendet
   */
  public static void main(String[] args) {

    /*
     * Variablen deklarieren, die in den folgenden Testanweisungen benötigt werden.
     */
    Rechteck r1;
    Rechteck r2;

    r1 = new Rechteck(1, 2, 3, 4);

    /*
     * Instanzvariable dieses Rechtecks in Ausdrücken verwenden. Wichtig: der Zugriff auf *private*
     * Instanzvariablen einer Klasse ist nur aus Methoden dieser Klasse möglich. Der Programm, der
     * hier gezeigt wird, wäre z.B. in der Klasse RechteckTest nicht möglich.
     */
    System.out.println(r1.breite);
    System.out.println((r1.breite + r1.hoehe) / 2);

    /*
     * Instanzvariablen dieses Rechtecks Werte zuweisen.
     */
    r1.breite = 4.5;
    System.out.println(r1.breite);

    /*
     * Zuweisung an Instanzvariable hat Effekt nur für genau das Objekt, dessen Variable man
     * anspricht.
     */
    r1 = new Rechteck(1.5, 1);
    r2 = new Rechteck(2.5, 2);
    r1.breite = 15.5;
    r2.breite = 10.3;
    System.out.println(r1.breite);  // Ausgabe: 15.5
    System.out.println(r2.breite);  // Ausgabe 10.3

    /*
     * Ähnlicher Code, aber mit "Seiteneffekt". Beachte: zwei Variablen können dasselbe Objekt
     * enthalten.
     */
    r1 = new Rechteck(1.5, 1);
    r2 = new Rechteck(2.5, 2);
    r1.breite = 15.5;
    r2 = r1;
    r2.breite = 10.3;
    System.out.println(r2.breite);  // Ausgabe 10.3
    System.out.println(r1.breite);  // Ausgabe auch 10.3!

    /*
     * Der Objektausdruck vor dem Punkt muss keine Variable sein. Es ist jeder Ausdruck erlaubt, der
     * ein entsprechendes Objekt als Wert liefert. Aber: Typen müssen beachtet werden! Hat der
     * Objektausdruck den Typ T (wobei T eine Klasse ist), dann sind nur Instanzvariablen rechts vom
     * Punkt (.) zulässig, die in der Klasse T bekannt sind. Dies heißt zunächst, die
     * Instanzvariablen müssen in der Klasse T definiert sein.
     */
    System.out.println((new Rechteck(1, 2, 3, 4)).breite);
  }
}

```


## Rechteck-Test
```java

/**
 * Diese Klasse dient dazu, Konstruktoren und Methoden der Klasse Rechteck zu
 * testen und deren Funktionsweise zu veranschaulichen.
 */
public class RechteckTest {

  /**
   * Veranschaulicht die Funktionsweise der Konstruktoren der Klasse Rechteck.
   */
  public static void testeKonstruktoren() {

    /*
     * Variable des Typs Rechteck deklarieren. Die Variable kann durch Zuweisungen mit Objekten der
     * Klasse Rechteck belegt werden.
     */
    Rechteck r;

    /*
     * Der Variablen r ein Rechteck-Objekt zuweisen.
     */
    r = new Rechteck(2.5, 1.5);

    /*
     * Dasselbe mit dem anderen Konstruktor. Der alte Inhalt der Variablen r wird überschrieben.
     */
    r = new Rechteck(1.5, 2, 3, 4);

    /*
     * Der Aufruf eines Konstruktors ist ein Ausdruck. Dieser Ausdruck kann innerhalb anderer
     * Ausdrücke verwendet werden, hier z.B. innerhalb des Aufrufs der println-Methode verwendet.
     * Wenn Sie diesen Code ausführen, sehen Sie, dass die Ausgabe "komisch" aussieht. Wir werden in
     * OPR den Grund dafür kennenlernen.
     */
    System.out.println(new Rechteck(1, 2, 3, 4));

    /*
     * Versuch, einen Konstruktor mit zu wenigen Parametern aufzurufen.
     */
    // r = new Rechteck(1);
  }

  /**
   * Veranschaulicht Zugriffe auf Instanzmethoden der Klasse Rechteck.
   */
  public static void testeInstanzmethoden() {

    /*
     * Rechteck erzeugen und einer Variablen zuweisen.
     */
    Rechteck r = new Rechteck(1, 2, 3, 4);

    /*
     * Instanzmethode zur Berechnung der Fläche aufrufen.
     */
    System.out.println(r.gibFlaeche());

    /*
     * Hat die Instanzmethode einen anderen Ergebnistyp als void, handelt es sich bei dem Aufruf um
     * einen Ausdruck, der insbesondere innerhalb anderer Ausdrücke verwendet werden kann.
     */
    System.out.println(2 * r.gibFlaeche() + 3);

    /*
     * Der Objektausdruck vor dem Punkt muss keine Variable sein. Es ist jeder Ausdruck erlaubt, der
     * ein entsprechendes Objekt als Wert liefert. Aber: Typen müssen beachtet werden! Hat der
     * Objektausdruck den Typ T (wobei T eine Klasse ist), dann sind nur Instanzmethoden rechts vom
     * Punkt (.) zulässig, die in der Klasse T bekannt sind. Dies heißt zunächst, die
     * Instanzmethoden müssen in der Klasse T definiert sein.
     */
    System.out.println(2 * (new Rechteck(1, 2, 3, 4)).gibFlaeche() + 3);

    /*
     * Aufruf der Methode um festzustellen, ob Rechteck einen Punkt enthält.
     */
    System.out.println(r.enthaeltPunkt(new Punkt(1.5, 3.5)));

    /*
     * Aufruf der Methode zum Verschieben eines Rechtecks. Beachte: bei diesem Aufruf handelt es
     * sich nicht um einen Ausdruck, da die Instanzmethode keinen Ergebnistyp besitzt.
     */
    System.out.println(r.gibAlsString());
    r.verschiebe(2, 5);
    System.out.println(r.gibAlsString());

    /*
     * Zweites Rechteck erzeugen. Instanzmethode aufrufen, um daraus und dem Rechteck in der
     * Variablen r die Rechteckhülle zu erzeugen.
     */
    Rechteck r2 = new Rechteck(3.5, 4.5, 4.5, 9.5);
    Rechteck huelle = r.erzeugeHuelle(r2);
    System.out.println(huelle.gibAlsString());
  }

  /**
   * Veranschaulicht die Identität von Objekten.
   */
  public static void testeIdentitaet() {

    /*
     * Zwei Rechtecke erzeugen und verschiedenen Variablen zuweisen.
     */
    Rechteck r1 = new Rechteck(1, 2, 3, 4);
    Rechteck r2 = new Rechteck(1, 2, 3, 4);

    /*
     * Testausgabe, um Identität der Werte beider Variablen festzustellen.
     */
    System.out.println(r1 == r2);

    /*
     * Wert der Variablen r1 der Variablen r2 zuweisen.
     *
     * Zur Sprachregelung: ein Wert meint immer das Ergebnis der Auswertung eines Ausdrucks. Es muss
     * sich nicht um nummerische Werte handeln.
     */
    r2 = r1;

    /*
     * Testausgabe, um Identität der Werte beider Variablen festzustellen.
     */
    System.out.println(r1 == r2);
  }

  /**
   * Führt die Testmethoden aus und stellt die Testergebnisse auf dem Bildschirm dar.
   *
   * @param args wird nicht verwendet
   */
  public static void main(String[] args) {

//    testeKonstruktoren();
    testeInstanzmethoden();
//    testeIdentitaet();
  }
}

```