#Themen 
#EPR
#Medieninformatik 

---
# Quellen

# Definition
> [!question] Definition
> Hier kommt die Definition hin.



# Beispiele
## Baumknoten
```java

/**
 * Ein Baumknoten repräsentiert einen Knoten eines binären Suchbaums. Ebenso
 * repräsentiert er den durch diesen Knoten aufgespannten Baum. Ein Knoten
 * enthält als Inhalt eine Zeichenkette.
 */
public class Baumknoten {

  /**
   * Zeichen für Zeilenumbruch in Strings.
   */
  private static final char ZEILENUMBRUCH = '\n';

  /**
   * Einzelner Einrückungsschritt für Textdarstellung der Baum-Traversierung.
   */
  private static final String INDENT = "    ";

  /**
   * Inhalt dieses Knotens.
   */
  private String inhalt;

  /**
   * Linker Teilbaum dieses Knotens.
   */
  private Baumknoten linkerTeilbaum;

  /**
   * Rechter Teilbaum dieses Knotens.
   */
  private Baumknoten rechterTeilbaum;

  /**
   * Erzeugt einen neuen Baumknoten für den übergebenen Inhalt. Der Knoten ist ein Blatt.
   *
   * @param inhalt Wert, für den der Baumknoten erzeugt wird
   */
  public Baumknoten(String inhalt) {

    this.inhalt = inhalt;
    this.linkerTeilbaum = null;
    this.rechterTeilbaum = null;
  }

  /**
   * Liefert den Inhalt dieses Baumknotens.
   *
   * @return Inhalt dieses Baumknotens
   */
  public String gibInhalt() {

    return this.inhalt;
  }

  /**
   * Liefert den linken Teilbaum dieses Knotens.
   *
   * @return linker Teilbaum
   */
  public Baumknoten gibLinkenTeilbaum() {

    return this.linkerTeilbaum;
  }

  /**
   * Liefert den rechten Teilbaum dieses Knotens.
   *
   * @return rechter Teilbaum
   */
  public Baumknoten gibRechtenTeilbaum() {

    return this.rechterTeilbaum;
  }

  /**
   * Weist diesem Knoten einen linken Teilbaum zu.
   *
   * @param knoten Knoten, der linkes Kind dieses Knotens wird
   */
  public void setzeLinkenTeilbaum(Baumknoten knoten) {

    this.linkerTeilbaum = knoten;
  }

  /**
   * Weist diesem Knoten einen rechten Teilbaum zu.
   *
   * @param knoten Knoten, der rechtes Kind dieses Knotens wird
   */
  public void setzeRechtenTeilbaum(Baumknoten knoten) {

    this.rechterTeilbaum = knoten;
  }

  /**
   * Gibt die Inhalte der Inorder-Traversierung des Baums, der durch diesen Knoten aufgespannt wird,
   * zurück.
   *
   * @return Inhalte der Inorder-Traversierung, jeweils ein Knoteninhalt pro Zeile
   */
  public String gibInorderfolge() {

    return ((this.linkerTeilbaum == null)
            ? ""
            : this.linkerTeilbaum.gibInorderfolge() + ZEILENUMBRUCH)
            + this.inhalt
            + ((this.rechterTeilbaum == null)
                    ? ""
                    : ZEILENUMBRUCH + this.rechterTeilbaum.gibInorderfolge());
  }

  /**
   * Gibt die Inhalte der Preorder-Traversierung des Baums, der durch diesen Knoten aufgespannt
   * wird, zurück.
   *
   * @return Inhalte der Preorder-Traversierung, jeweils ein Knoteninhalt pro Zeile; Einrückung
   *         macht die Baumstruktur deutlich
   */
  public String gibPreorderfolge() {

    return gibPreorderfolge("");
  }

  /**
   * Durchläuft den Baum mit diesem Knoten als Wurzel in Preorder-Reihenfolge und liefert die
   * Preorder-Folge in eingerückter Form. Leere Bäume haben streng genommen eine leere
   * Preorder-Folge. Damit ersichtlich ist, wo sich im Baum leere Teilbäume befinden, wird für sie
   * der Text "(leer)" zurückgegeben.
   *
   * @param einrueckung Einrückung für diesen Knoten und seine Kinder
   */
  private String gibPreorderfolge(String einrueckung) {

    return (einrueckung + this.inhalt + ZEILENUMBRUCH)
            + ((this.linkerTeilbaum == null)
                    ? (INDENT + einrueckung + "(leer)")
                    : this.linkerTeilbaum.gibPreorderfolge(
                            INDENT + einrueckung))
            + ZEILENUMBRUCH
            + ((this.rechterTeilbaum == null)
                    ? (INDENT + einrueckung + "(leer)")
                    : this.rechterTeilbaum.gibPreorderfolge(
                            INDENT + einrueckung));
  }

  /**
   * Fügt dem Suchbaum mit diesem Knoten als Wurzel einen neuen Knoten für den übergebenen Wert
   * hinzu. Der Knoten wird so hinzugefügt, dass der Baum ein Suchbaum bleibt.
   *
   * @param wert Wert, der dem Baum hinzugefügt wird
   */
  public void fuegeHinzu(String wert) {

    if (wert.compareTo(this.inhalt) <= 0) {

      /*
       * Der Wert ist gleich dem Inhalt dieses Knotens oder liegt alphabetisch davor. Der Wert wird
       * im linken Teilbaum hinzugefügt.
       */
      if (this.linkerTeilbaum == null) {
        this.linkerTeilbaum = new Baumknoten(wert);
      } else {
        this.linkerTeilbaum.fuegeHinzu(wert);
      }

    } else {

      /*
       * Der Wert liegt alphabetisch hinter dem Inhalt dieses Knotens. Der Wert wird im rechten
       * Teilbaum hinzugefügt.
       */
      if (this.rechterTeilbaum == null) {
        this.rechterTeilbaum = new Baumknoten(wert);
      } else {
        this.rechterTeilbaum.fuegeHinzu(wert);
      }
    }
  }

  /**
   * Liefert den maximalen Inhalt aller Knoten des Suchbaums mit diesem Knoten als Wurzel.
   *
   * @return Maximaler Wert dieses Suchbaums
   */
  private String gibMaximalenWert() {

    return (this.rechterTeilbaum == null)
            ? this.inhalt
            : this.rechterTeilbaum.gibMaximalenWert();
  }

  /**
   * Entfernt aus dem Baum mit diesem Knoten als Wurzel den Knoten mit dem maximalen Inhalt.
   *
   * @return Baum ohne den Knoten mit maximalem Inhalt
   */
  private Baumknoten entferneMaximalenWert() {

    /*
     * Wurzelknoten nach dem Entfernen des Werts.
     */
    Baumknoten neueWurzel;

    if (this.rechterTeilbaum == null) {

      /*
       * Rechter Teilbaum ist leer. Wurzel enthält also maximalen Wert.
       */
      neueWurzel = this.linkerTeilbaum;

    } else {

      /*
       * Rechter Teilbaum ist nicht leer. Maximales Element ist also im rechten Teilbaum und wird
       * dort entfernt. Der resultierende Baum wird neuer rechter Teilbaum.
       */
      this.rechterTeilbaum = this.rechterTeilbaum.entferneMaximalenWert();
      neueWurzel = this;
    }

    return neueWurzel;
  }

  /**
   * Entfernt aus dem Suchbaum mit diesem Knoten als Wurzel den angegebenen Wert, sofern er im Baum
   * existiert.
   *
   * @param wert Wert, der aus dem Suchbaum entfernt wird (sofern er überhaupt existiert)
   * @return Baum nach Entfernen des Werts
   */
  public Baumknoten entferne(String wert) {

    /*
     * Wurzelknoten nach dem Entfernen des Werts.
     */
    Baumknoten neueWurzel = this;

    if ((wert.compareTo(this.inhalt) < 0)
            && (this.linkerTeilbaum != null)) {

      /*
       * Wert liegt alphabetisch vor dem Inhalt dieses Knotens. Das Entfernen wird im linken
       * Teilbaum durchgeführt.
       */
      this.linkerTeilbaum = this.linkerTeilbaum.entferne(wert);

    } else if ((wert.compareTo(this.inhalt) > 0)
            && (this.rechterTeilbaum != null)) {

      /*
       * Wert liegt alphabetisch hiner dem Inhalt dieses Knotens. Das Entfernen wird im rechten
       * Teilbaum durchgeführt.
       */
      this.rechterTeilbaum = this.rechterTeilbaum.entferne(wert);

    } else if (wert.equals(this.inhalt)) {

      /*
       * Wert ist gleich dem Inhalt dieses Knotens. Dieser Knoten wird entfernt.
       */
      if (this.rechterTeilbaum == null) {

        /*
         * Baum ohne diesen Knoten ist der linke Teilbaum, da der rechte leer ist.
         */
        neueWurzel = this.linkerTeilbaum;

      } else if (this.linkerTeilbaum == null) {

        /*
         * Baum ohne diesen Knoten ist der rechte Teilbaum, da der linke leer ist.
         */
        neueWurzel = this.rechterTeilbaum;

      } else {

        /*
         * Beide Teilbäume sind nicht leer. Der größte Inhalt des linken Teilbaums wird zum Inhalt
         * dieses Knotens. Der entsprechende Knoten aus dem linken Teilbaum wird entfernt.
         */
        this.inhalt = this.linkerTeilbaum.gibMaximalenWert();
        this.linkerTeilbaum
                = this.linkerTeilbaum.entferneMaximalenWert();
      }
    }

    return neueWurzel;
  }

  /**
   * Gibt an, ob der übergebene Wert im Baum enthalten ist.
   *
   * @param wert Wert, für den geprüft wird, ob er im Suchbaum enthalten ist
   * @return {@code true} genau dann, wenn der Wert enthalten ist
   */
  public boolean istEnthalten(String wert) {

    boolean istEnthalten;

    if (wert.compareTo(this.inhalt) < 0) {

      /*
       * Wert ist kleiner als Inhalt dieses Knotens. Falls Wert enthalten ist, ist er im linken
       * Teilbaum.
       */
      istEnthalten = (this.linkerTeilbaum != null)
              && linkerTeilbaum.istEnthalten(wert);

    } else if (wert.compareTo(this.inhalt) > 0) {

      /*
       * Wert ist größer als Inhalt dieses Knotens. Falls Wert enthalten ist, ist er im rechten
       * Teilbaum.
       */
      istEnthalten = (this.rechterTeilbaum != null)
              && rechterTeilbaum.istEnthalten(wert);

    } else {

      /*
       * Wert ist in diesem Knoten enthalten.
       */
      istEnthalten = true;
    }

    return istEnthalten;
  }
}

```

## BinaererSuchbaum
```java

/**
 * Ein Objekt dieser Klasse repräsentiert einen binären Suchbaum, dessen Knoten
 * Zeichenketten enthalten.
 */
public class BinaererSuchbaum {

  /**
   * Wurzelknoten dieses Suchbaums.
   */
  private Baumknoten wurzel;

  /**
   * Erzeugt einen leeren Suchbaum.
   */
  public BinaererSuchbaum() {

    this.wurzel = null;
  }

  // Traversierungen --------------------------------------------------------

  /**
   * Durchläuft die Knoten dieses Baums in Inorder-Reihenfolge und gibt deren Inhalt aus.
   *
   * @return Inhalte der Inorder-Traversierung, jeweils ein Knoteninhalt pro Zeile
   */
  public String gibInorderfolge() {

    return (this.wurzel == null)
            ? ""
            : this.wurzel.gibInorderfolge();
  }

  /**
   * Liefert die Preorder-Folge dieses Baums in eingerückter Form.
   *
   * @return Preorder-Folge in eingerückter Form mit einem Element pro Zeile
   */
  public String gibPreorderfolge() {

    return (this.wurzel == null)
            ? "(leer)"
            : this.wurzel.gibPreorderfolge();
  }

  /**
   * Gibt an, ob der übergebene Wert im Baum enthalten ist.
   *
   * @param wert Wert, für den geprüft wird, ob er im Suchbaum enthalten ist
   * @return {@code true} genau dann, wenn der Wert enthalten ist
   */
  public boolean istEnthalten(String wert) {

    /*
     * Wert ist enthalten, wenn Baum nicht leer ist und der durch die Wurzel aufgespannte Baum den
     * Wert enthält.
     */
    return (this.wurzel != null) && this.wurzel.istEnthalten(wert);
  }

  /**
   * Fügt dem Suchbaum einen neuen Knoten für den übergebenen Wert hinzu. Der Knoten wird so
   * hinzugefügt, dass der Baum ein Suchbaum bleibt.
   *
   * @param wert Wert, der dem Baum hinzugefügt wird
   */
  public void fuegeHinzuRekursiv(String wert) {

    if (this.wurzel == null) {

      /*
       * Baum ist leer. Ersten Knoten erzeugen.
       */
      this.wurzel = new Baumknoten(wert);

    } else {

      /*
       * Baum ist nicht leer. Wurzel bleibt beim Einfügen unverändert.
       */
      this.wurzel.fuegeHinzu(wert);
    }
  }

  /**
   * Fügt dem Suchbaum einen neuen Knoten für den übergebenen Wert hinzu. Der Knoten wird so
   * hinzugefügt, dass der Baum ein Suchbaum bleibt.
   *
   * @param wert Wert, der dem Baum hinzugefügt wird
   */
  public void fuegeHinzuIterativ(String wert) {

    /*
     * Blatt für übergebenen Wert erzeugen.
     */
    Baumknoten knoten = new Baumknoten(wert);

    /*
     * Baum von der Wurzel zu dem Knoten durchlaufen, an den der neue Knoten als Kind angefügt
     * werden muss.
     */

    /*
     * Enthält stets den Knoten, mit dem verglichen wird, ob der Wert rechts oder links davon
     * eingefügt werden muss.
     */
    Baumknoten aktuellerKnoten = this.wurzel;

    /*
     * Vorgänger des aktuellen Knotens. Enthält schließlich den Knoten, an dem der Knoten für den
     * einzufügenden Wert eingefügt wird.
     */
    Baumknoten vorgaenger = null;

    /*
     * Gibt an, ob beim Abstieg im Baum nach rechts verzweigt wurde. true genau dann, wenn nach
     * rechts verzweigt wurde. Wird benötigt, um am Ende entscheiden zu können, ob der neue Knoten
     * linkes oder rechtes Kind des Vorgängerknotens wird.
     */
    boolean nachRechtsVerzweigt = false;

    /*
     * Solange im Baum absteigen, wie noch kein Blatt erreicht ist.
     */
    while (aktuellerKnoten != null) {

      /*
       * Zum linken oder rechten Kind verzweigen. Aktueller Knoten wird dann zum Vorgänger dieses
       * Kindes.
       */
      vorgaenger = aktuellerKnoten;

      if (wert.compareTo(aktuellerKnoten.gibInhalt()) <= 0) {

        /*
         * Der einzufügende Wert ist kleiner oder gleich dem Inhalt des aktuellen Knotens. Der neue
         * Knoten muss im linken Teilbaum eingefügt werden.
         */
        nachRechtsVerzweigt = false;
        aktuellerKnoten = aktuellerKnoten.gibLinkenTeilbaum();

      } else {

        /*
         * Der einzufügende Wert ist größer als der Inhalt des aktuellen Knotens. Der neue Knoten
         * muss im rechten Teilbaum eingefügt werden.
         */
        nachRechtsVerzweigt = true;
        aktuellerKnoten = aktuellerKnoten.gibRechtenTeilbaum();
      }
    }

    if (vorgaenger == null) {

      /*
       * Die obige Schleife wurde nicht durchlaufen. Der Baum ist leer.
       */
      this.wurzel = knoten;

    } else if (nachRechtsVerzweigt) {

      /*
       * Die letzte Verzweigung erfolgte nach rechts. Der neue Knoten wird rechtes Kind des
       * Vorgängerknotens.
       */
      vorgaenger.setzeRechtenTeilbaum(knoten);

    } else {

      /*
       * Der neue Knoten wird linkes Kind des Vorgängerknotens.
       */
      vorgaenger.setzeLinkenTeilbaum(knoten);
    }
  }

  /**
   * Entfernt aus dem Suchbaum den angegebenen Wert, sofern er im Baum existiert. Gibt es keinen
   * Knoten mit diesem Wert, bleibt der Baum unverändert.
   *
   * @param wert Wert, der aus dem Baum entfernt wird
   */
  public void entferne(String wert) {

    if (this.wurzel != null) {
      this.wurzel = this.wurzel.entferne(wert);
    }
  }
}


```

## BinaererSuchbaumTest
```java

/**
 * Diese Klasse veranschaulicht durch Testaufrufe die Funktionsweise der
 * Klassen BinaererSuchbaum und Baumknoten.
 */
public class BinaererSuchbaumTest {

  /**
   * Liefert Baum mit Zeichenfolgen als Knoteninhalten.
   *
   * @param bauminhalte Daten, die im Baum abgelegt werden
   * @return Suchbaum mit den übergebenen Inhalten
   */
  private static BinaererSuchbaum erzeugeBaum(String... bauminhalte) {

    BinaererSuchbaum baum = new BinaererSuchbaum();

    for (String s : bauminhalte) {
      baum.fuegeHinzuRekursiv(s);
    }

    return baum;
  }

  /**
   * Gibt die Preorder-Folge eines Beispielbaums aus.
   */
  private static void testePreorderDurchlauf() {

    BinaererSuchbaum baum = erzeugeBaum("Fisch", "Birne", "Auto", "Dach", "Pech", "Maus", "Vogel");
//    baum = erzeugeBaum("Auto", "Birne", "Dach", "Fisch", "Maus", "Pech", "Vogel");  // Wörter aufsteigend sortiert
//    baum = erzeugeBaum("Vogel", "Pech", "Maus", "Fisch", "Dach", "Birne", "Auto");  // Wörter absteigend sortiert
    System.out.println(baum.gibPreorderfolge());
  }

  /**
   * Gibt die Inorder-Folge eines Beispielbaums aus.
   */
  private static void testeInorderDurchlauf() {

    BinaererSuchbaum baum = erzeugeBaum("Fisch", "Birne", "Auto", "Dach", "Pech", "Maus", "Vogel");
    System.out.println(baum.gibInorderfolge());
  }

  /**
   * Testet Methode zum rekursiven Hinzufügen von Inhalten in den Baum.
   */
  private static void testeRekursivesHinzufuegen() {

    BinaererSuchbaum baum;

    baum = new BinaererSuchbaum();  // leerer Baum
    System.out.println(baum.gibPreorderfolge());
    System.out.println();

    /*
     * Inhalte sind vorsortiert. Baum degeneriert zur Liste.
     */
    baum = erzeugeBaum("Auto", "Birne", "Dach", "Fisch", "Maus", "Pech", "Vogel");
    System.out.println(baum.gibPreorderfolge());
    System.out.println();

    /*
     * Inhalte sind umgekehrt vorsortiert. Baum degeneriert zur Liste.
     */
    baum = erzeugeBaum("Vogel", "Pech", "Maus", "Fisch", "Dach", "Birne", "Auto");
    System.out.println(baum.gibPreorderfolge());
    System.out.println();

    /*
     * Reihenfolge führt zu ausgeglichenem Baum.
     */
    baum = erzeugeBaum("Fisch", "Birne", "Auto", "Dach", "Pech", "Maus", "Vogel");
    System.out.println(baum.gibPreorderfolge());
    System.out.println();
  }

  /**
   * Testet Methode zum iterativen Hinzufügen von Inhalten in den Baum.
   */
  private static void testeIterativesHinzufuegen() {

    BinaererSuchbaum baum = new BinaererSuchbaum();

    baum.fuegeHinzuIterativ("Fisch");
    baum.fuegeHinzuIterativ("Birne");
    baum.fuegeHinzuIterativ("Auto");
    baum.fuegeHinzuIterativ("Dach");
    baum.fuegeHinzuIterativ("Pech");
    baum.fuegeHinzuIterativ("Vogel");
    baum.fuegeHinzuIterativ("Maus");

    System.out.println(baum.gibPreorderfolge());
    System.out.println();
    System.out.println(baum.gibInorderfolge());
  }

  /**
   * Testet Methoden zum Entfernen von Inhalten aus dem Baum.
   */
  private static void testeEntfernen() {

    BinaererSuchbaum baum;

    baum = new BinaererSuchbaum();
    baum.entferne("Maus");
    System.out.println(baum.gibPreorderfolge());
    System.out.println();

    /*
     * Reihenfolge führt zu ausgeglichenem Baum.
     */
    baum = erzeugeBaum("Fisch, Birne, Auto, Dach, Pech, Maus, Vogel");
    System.out.println(baum.gibPreorderfolge());
    System.out.println();

    baum.entferne("Fisch");
    System.out.println(baum.gibPreorderfolge());
    System.out.println();

    baum.entferne("Auto");
    System.out.println(baum.gibPreorderfolge());
    System.out.println();

    baum.entferne("Vogel");
    System.out.println(baum.gibPreorderfolge());
    System.out.println();

    baum.entferne("Pech");
    System.out.println(baum.gibPreorderfolge());
    System.out.println();
  }

  /**
   * @param args wird nicht verwendet
   */
  public static void main(String[] args) {

    testeInorderDurchlauf();
    testePreorderDurchlauf();
    testeRekursivesHinzufuegen();
    testeEntfernen();
    testeIterativesHinzufuegen();
  }
}

```
