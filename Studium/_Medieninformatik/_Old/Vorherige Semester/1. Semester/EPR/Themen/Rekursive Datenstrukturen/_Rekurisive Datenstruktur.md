#Themen 
#EPR
#Medieninformatik 

---
# Quellen

# Definition
> [!question] Definition
> Eine Datenstruktur heißt rekursiv, wenn die (direkt oder indirekt) Komponenten derselben Struktur enthält.

## Beispiele
### Listeknoten
```java

/**
 * Ein Listenknoten repräsentiert einen Knoten einer einfach verketteten
 * Liste. Ein Knoten enthält einen Inhalt und einen Nachfolgeknoten.
 */
public class Listenknoten {

  /**
   * Inhalt dieses Knotens.
   */
  private final String inhalt;

  /**
   * Nachfolgender Listenknoten.
   */
  private Listenknoten nachfolger;

  /**
   * Erzeugt einen neuen Listenknoten mit der übergebenen Zeichenkette als Inhalt.
   *
   * @param inhalt Inhalt dieses Listenknotens
   */
  public Listenknoten(String inhalt) {

    this.inhalt = inhalt;
    this.nachfolger = null;
  }

  /**
   * Erzeugt einen neuen Listenknoten mit der übergebenen Zeichenkette als Inhalt und dem
   * übergebenen Knoten als Nachfolger.
   *
   * @param inhalt     Inhalt dieses Listenknotens
   * @param nachfolger Nachfolger dieses Listenknotens
   */
  public Listenknoten(String inhalt, Listenknoten nachfolger) {

    this.inhalt = inhalt;
    this.nachfolger = nachfolger;
  }

  /**
   * Liefert den Inhalt dieses Listenknotens.
   *
   * @return Inhalt dieses Listenknotens
   */
  public String gibInhalt() {

    return this.inhalt;
  }

  /**
   * Liefert den nachfolgenden Listenknoten.
   *
   * @return nachfolgender Listenknoten
   */
  public Listenknoten gibNachfolger() {

    return this.nachfolger;
  }

  /**
   * Weist diesem Listenknoten einen neuen Nachfolger zu.
   *
   * @param knoten Nachfolger dieses Listenknotens
   */
  public void setzeNachfolger(Listenknoten knoten) {

    this.nachfolger = knoten;
  }
}

```
### VerketteListe
```java

/**
 * Ein Objekt dieser Klasse repräsentiert eine einfach verkettete Liste von
 * Zeichenketten.
 */
public class VerketteteListe {

  /**
   * Erster Knoten in der Liste der verketteten Knoten.
   */
  private Listenknoten listenkopf;

  /**
   * Letzter Knoten in der Liste der verketteten Knoten.
   */
  private Listenknoten listenende;

  /**
   * Länge dieser Liste.
   */
  private int listenlaenge;

  /**
   * Erzeugt eine leere Liste.
   */
  public VerketteteListe() {

    this.listenkopf = null;
    this.listenende = null;
    this.listenlaenge = 0;
  }

  /**
   * Fügt eine Zeichenkette vorne in dieser Liste hinzu.
   *
   * @param inhalt Zeichenkette, die vorne hinzugefügt wird
   */
  public void fuegeVorneHinzu(String inhalt) {

    this.listenkopf = new Listenknoten(inhalt, this.listenkopf);

    if (this.listenende == null) {

      /*
       * Die Liste war leer. Neuer Knoten wird auch Listenende.
       */
      this.listenende = this.listenkopf;
    }

    this.listenlaenge = this.listenlaenge + 1;
  }

  /**
   * Fügt eine Zeichenkette hinten in dieser Liste hinzu.
   *
   * @param inhalt Zeichenkette, die hinten hinzugefügt wird
   */
  public void fuegeHintenHinzu(String inhalt) {

    if (this.listenkopf == null) {

      /*
       * Die Liste ist leer. Neuer Knoten wird Listenkopf und Listenende.
       */
      this.listenkopf = new Listenknoten(inhalt);
      this.listenende = this.listenkopf;

    } else {

      /*
       * Die Liste ist nicht leer. Neuer Knoten wird Listenende. Listenkopf bleibt unverändert.
       */
      Listenknoten knoten = new Listenknoten(inhalt);
      this.listenende.setzeNachfolger(knoten);
      this.listenende = knoten;
    }

    this.listenlaenge = this.listenlaenge + 1;
  }

  /**
   * Fügt eine Zeichenkette an der angegebenen Position in diese Liste ein.
   *
   * @param position Position, an der die Zeichenkette eingefügt wird. Wenn position == 0, wird
   *                 vorne eingefügt. Wenn position == 1, wird an zweiter Stelle eingefügt usw.
   * @param inhalt   Zeichenkette, die hinzugefügt wird
   */
  public void fuegeHinzu(int position, String inhalt) {

    if (position == 0) {
      fuegeVorneHinzu(inhalt);
    } else if (position == this.listenlaenge) {
      fuegeHintenHinzu(inhalt);
    } else if ((position > 0) && (position < this.listenlaenge)) {

      Listenknoten knoten = new Listenknoten(inhalt);

      /*
       * Der neue Knoten muss hinter dem Knoten an Position position - 1 eingefügt werden. Deshalb
       * die Liste durchlaufen, bis Variable k den Knoten an dieser Position enthält.
       */
      Listenknoten vorgaenger = this.listenkopf;
      for (int i = 1; i < position; i = i + 1) {
        vorgaenger = vorgaenger.gibNachfolger();
      }

      /*
       * Neuen Knoten als Nachfolger des Knotens an Position position - 1 (Wert der Variablen
       * vorgaenger) einfügen.
       */
      knoten.setzeNachfolger(vorgaenger.gibNachfolger());
      vorgaenger.setzeNachfolger(knoten);

      this.listenlaenge = this.listenlaenge + 1;
    }
  }

  /**
   * Fügt eine Zeichenkette an der angegebenen Position in diese Liste ein.
   *
   * Der Name dieser Methode ist schlecht gewählt. Es interessiert einen Aufrufer nicht, ob beim
   * Hinzufügen die Listenlänge ausgewertet wird oder nicht. Hier wird dieser Name gewählt, um diese
   * Methode von der Methode fuegeHinzu unterscheidbar zu machen. In der Praxis entscheidet man sich
   * für eine Realisierungsart.
   *
   * @param position Position, an der die Zeichenkette eingefügt wird. Wenn position == 0, wird
   *                 vorne eingefügt. Wenn position == 1, wird an zweiter Stelle eingefügt usw. Es
   *                 wird davon ausgegangen, dass die position nicht negativ ist.
   * @param inhalt   Zeichenkette, die hinzugefügt wird
   */
  public void fuegeHinzuOhneListenlaenge(int position, String inhalt) {

    if (position == 0) {

      /*
       * Knoten wird vorne hinzugefügt.
       */
      this.listenkopf = new Listenknoten(inhalt, this.listenkopf);

      if (this.listenende == null) {

        /*
         * Die Liste war leer. Neuer Knoten wird auch Listenende.
         */
        this.listenende = this.listenkopf;
      }

      this.listenlaenge = this.listenlaenge + 1;

    } else {

      /*
       * Knoten soll nicht vorne hinzugefügt werden.
       */

      /*
       * Zähler zur Ermittlung der Einfügeposition.
       */
      int positionszaehler = 1;

      /*
       * Knoten, hinter dem der neue Knoten eingefügt werden soll.
       */
      Listenknoten vorgaenger = this.listenkopf;

      /*
       * Denjenigen Knoten k suchen, hinter dem der neue Knoten eingefügt werden muss.
       */
      while ((positionszaehler < position) && (vorgaenger != null)) {
        positionszaehler = positionszaehler + 1;
        vorgaenger = vorgaenger.gibNachfolger();
      }

      /*
       * Falls vorgaenger == null, so ist die Einfügeposition für diese Liste ungültig.
       */
      if (vorgaenger != null) {

        /*
         * vorgaenger enthält den Knoten, hinter dem der neue Knoten eingefügt werden muss.
         */
        Listenknoten knoten
                = new Listenknoten(inhalt, vorgaenger.gibNachfolger());
        vorgaenger.setzeNachfolger(knoten);
        this.listenlaenge = this.listenlaenge + 1;

        /*
         * Ist der neue Knoten der letzte der Liste, muss das Listenende gesetzt werden.
         */
        if (knoten.gibNachfolger() == null) {
          this.listenende = knoten;
        }
      }
    }
  }

  /**
   * Fügt eine Zeichenkette an der ersten möglichen Stelle in diese Liste ein, sodass sie gleich der
   * darauffolgenden Zeichenkette ist oder lexikografisch vor ihr steht. Fügt man der Liste
   * Zeichenketten nur über diese Methode hinzu, so enthält sie die Zeichenketten in alphabetischer
   * Sortierung.
   *
   * @param inhalt Zeichenkette, die hinzugefügt wird
   */
  public void fuegeSortiertHinzu(String inhalt) {

    /*
     * Hier wird zu Zwecken der Anschauung eine Implementierung gewählt, in der von den Methoden
     * fuegeVorneHinzu und fuegeHintenHinzu kein Gebrauch gemacht wird.
     */

    /*
     * Neuen Knoten für inhalt erzeugen. Es ist noch unklar, wo dieser Knoten eingefügt werden muss.
     */
    Listenknoten knoten = new Listenknoten(inhalt);

    if (this.listenkopf == null) {

      /*
       * Die Liste ist leer. Neuer Knoten wird Listenkopf und Listenende.
       */
      this.listenkopf = knoten;
      this.listenende = this.listenkopf;

    } else {

      /*
       * Die Liste ist nicht leer.
       */

      /*
       * Liste vom Listenkopf an solange durchlaufen, bis der Inhalt eines Knotens (Variable
       * aktuellerKnoten) gleich der einzufügenden Zeichenkette ist oder alphabetisch hinter ihr
       * steht. Der neue Knoten muss dann VOR diesem Knoten eingefügt werden. Deshalb wird in einer
       * zweiten Variablen jeweils der Knoten mitgeführt, der vor dem aktuellen Knoten steht.
       */
      Listenknoten aktuellerKnoten = this.listenkopf;
      Listenknoten vorherigerKnoten = null;

      /*
       * Hinweis: Die Methode compareTo der Klasse String ermöglicht die Untersuchung, in welcher
       * lexikografischen Ordnung zwei Zeichenketten zueinander stehen. Ein String s1 ist
       * lexikografisch kleiner s2, wenn s1.compareTo(s2) < 0.
       */

      /*
       * Solange die Liste durchlaufen, wie noch nicht das Ende erreicht ist und der Inhalt des
       * aktuellen Knotens alphabetisch vor der einzufügenden Zeichenkette steht.
       */
      while ((aktuellerKnoten != null)
              && (aktuellerKnoten.gibInhalt().compareTo(inhalt) < 0)) {

        /*
         * Um einen Knoten weiterrücken.
         */
        vorherigerKnoten = aktuellerKnoten;
        aktuellerKnoten = aktuellerKnoten.gibNachfolger();
      }

      if (vorherigerKnoten == null) {

        /*
         * Die Schleife wurde nicht betreten. Der Knoten muss vorne eingefügt werden.
         */
        knoten.setzeNachfolger(this.listenkopf);
        this.listenkopf = knoten;

      } else {

        /*
         * Knoten wird nicht vorne eingefügt. Listenkopf bleibt unverändert. Knoten wird zwischen
         * vorherigerKnoten und aktuellerKnoten eingefügt.
         */
        vorherigerKnoten.setzeNachfolger(knoten);
        knoten.setzeNachfolger(aktuellerKnoten);

        /*
         * Listenende neu setzen, wenn Knoten als letzter Knoten eingefügt wurde.
         */
        if (aktuellerKnoten == null) {
          this.listenende = knoten;
        }
      }
    }
    this.listenlaenge = this.listenlaenge + 1;
  }

  /**
   * Entfernt die Zeichenkette an der angegebenen Position aus dieser Liste.
   *
   * @param index Index der Zeichenkette, die entfernt werden soll
   */
  public void entferne(int index) {

    if ((index >= 0) && (index < this.listenlaenge)) {

      /*
       * Es soll ein Element aus dem gültigen Indexbereich entfernt werden.
       */
      if (index == 0) {

        /*
         * Die Liste ist nicht leer und es soll der erste Knoten entfernt werden.
         */
        this.listenkopf = this.listenkopf.gibNachfolger();

        /*
         * Enthielt die Liste zuvor nur einen Knoten, so ist anschließend auch das Listenende die
         * null-Referenz.
         */
        if (this.listenkopf == null) {
          this.listenende = null;
        }

        this.listenlaenge = this.listenlaenge - 1;

      } else {

        /*
         * Die Liste ist nicht leer und es wird ein mittlerer oder der letzte Knoten entfernt.
         */

        /*
         * Durch die Liste laufen, sodass anschließend aktuellerKnoten den Knoten enthält, der
         * entfernt werden soll, und vorherigerKnoten seinen Vorgänger.
         */
        Listenknoten aktuellerKnoten = this.listenkopf;
        Listenknoten vorherigerKnoten = null;
        for (int i = 0; i < index; i = i + 1) {
          vorherigerKnoten = aktuellerKnoten;
          aktuellerKnoten = aktuellerKnoten.gibNachfolger();
        }

        /*
         * Der Knoten wird entfernt, indem sein Nachfolger zum Nachfolger des Vorgängers wird.
         */
        vorherigerKnoten.setzeNachfolger(
                aktuellerKnoten.gibNachfolger());

        /*
         * Wurde der letzte Knoten entfernt, muss das Listenende aktualisiert werden.
         */
        if (vorherigerKnoten.gibNachfolger() == null) {
          this.listenende = vorherigerKnoten;
        }

        this.listenlaenge = this.listenlaenge - 1;
      }
    }
  }

  /**
   * Verkettet die übergebene Liste mit dieser Liste. Es wird keine Kopie der übergebenen Liste
   * erstellt.
   *
   * @param liste Liste, die mit dieser Liste verkettet werden soll
   */
  public void verkette(VerketteteListe liste) {

    if (this.listenkopf == null) {

      /*
       * Diese Liste ist leer. Der Kopf der anzuhängenden Liste wird Kopf der verketteten Liste.
       */
      this.listenkopf = liste.listenkopf;

    } else {

      /*
       * Diese Liste ist nicht leer. Der Kopf der anzuhängenden Liste wird an das Ende dieser Liste
       * angefügt.
       */
      this.listenende.setzeNachfolger(liste.listenkopf);
    }

    /*
     * Listenende der anzuhängenden Liste wird zum Listenende dieser Liste, wenn die anzuhängende
     * Liste nicht leer ist.
     */
    if (liste.listenkopf != null) {
      this.listenende = liste.listenende;
    }

    /*
     * Längen der Listen addieren sich.
     */
    this.listenlaenge = this.listenlaenge + liste.listenlaenge;
  }

  /**
   * Liefert die Zeichenkette an der angegebenen Position in der Liste. Ist der Index ungültig, wird
   * null zurückgegeben.
   *
   * @param index Index der Zeichenkette
   * @return Zeichenkette an der angegebenen Position
   */
  public String gibInhalt(int index) {

    String inhalt;

    /*
     * Realisierung, bei der anhand der Listenlänge die Gültigkeit des Index geprüft wird.
     */
    if ((index < 0) || (index >= this.listenlaenge)) {
      // Fehlerfall: muss geeignet behandelt werden
      inhalt = null;
    } else {

      /*
       * Solange die Liste durchlaufen, bis k den angegebenen Listenknoten enthält.
       */
      Listenknoten k = this.listenkopf;
      for (int i = 0; i < index; i++) {
        k = k.gibNachfolger();
      }
      inhalt = k.gibInhalt();
    }
    return inhalt;

    /*
     * Alternative Realisierung, bei der sich während der Iteration ergibt, ob der Index gültig ist.
     */
//    Listenknoten k = index < 0 ? null : this.listenkopf;
//    int i = 0;
//
//    while (k != null && i < index) {
//        k = k.gibNachfolger();
//        i++;
//    }
//
//    return k == null ? null : k.gibInhalt();
  }

  /**
   * Liefert die Länge dieser Liste.
   *
   * @return Länge der Liste
   */
  public int gibLaenge() {

    return this.listenlaenge;
  }

  /**
   * Liefert String-Darstellung der Liste im Format
   * <pre>
   * Listenkopf: k; Listenende: e; Listeninhalt: i
   * </pre> Die String-Darstellung ist so gewählt, dass sie interne Details der Liste zu
   * Anschauungszwecken zeigt. k ist "null", wenn der Listenkopf die null-Referenz ist, sonst der
   * Inhalt des Kopfknotens. e ist "null", wenn das Listenende die null-Referenz ist, sonst der
   * Inhalt des Ende-Knotens. i ist durch Leerzeichen getrennt die Folge der Knoteninhalte.
   *
   * @return String-Darstellung dieser Liste
   */
  public String gibAlsString() {

    String ergebnis = "Listenkopf: "
            + ((this.listenkopf == null)
                    ? "null"
                    : this.listenkopf.gibInhalt())
            + "; ";

    ergebnis = ergebnis + "Listenende: "
            + ((this.listenende == null)
                    ? "null"
                    : this.listenende.gibInhalt())
            + "; ";

    ergebnis = ergebnis + "Listeninhalt:";

    Listenknoten k = this.listenkopf;

    /*
     * Inhalte aller Knoten aneinanderfügen.
     */
    while (k != null) {
      ergebnis = ergebnis + " " + k.gibInhalt();
      k = k.gibNachfolger();
    }

    return ergebnis;
  }
}
```





