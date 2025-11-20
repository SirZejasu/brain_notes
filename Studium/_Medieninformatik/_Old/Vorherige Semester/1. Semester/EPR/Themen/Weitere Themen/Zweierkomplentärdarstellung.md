#Medieninformatik 
#EPR 
#Themen 

---

# Code Beispiel aus Praktikum
## Farbe
```js
package farbe;

/**
 *
 *
 */
public class Farbe {

  /**
   * Invertiert die Farbe.
   *
   * @param r für rot in Prozent.
   * @param g für gruen in Prozent.
   * @param b für blau in Prozent.
   * @return gibt die invertierte Farbe aus in rrrgggbbb.
   */
  public static int invertiere(int r, int g, int b) {

    // Inventierung von r
    r = (r != 0)
        ? ((r * (-1)) & 0xFF) - 1
        : 255;

    // Inventierung von g
    g = (g != 0)
        ? ((g * (-1)) & 0xFF) - 1
        : 255;

    // Inventierung von b
    b = (b != 0)
        ? ((b * (-1)) & 0xFF) - 1
        : 255;

    // Umwandlung in die Darstellung rrrgggbbb
    int rgbWert = r * 1_000_000 + g * 1_000 + b;

    return rgbWert;

  }

  /**
   * Naechste Farbe ausgeben.
   *
   * @param r für rot in Prozent.
   * @param g für gruen in Prozent.
   * @param b für blau in Prozent.
   * @return gibt die nachst-hoehere Farbe aus in rrrgggbbb.
   */
  public static int gibNaechsteFarbe(int r, int g, int b) {

    // Es wird wieder von links nach rechts gelesen. Wenn g nicht 255 ist, ändert sich der Wert
    // nicht. Andernfalls wird der Wert von r erhöht.
    r = (g != 255)
        ? r
        : (r != 255)
            ? r + 1
            : 0;
    //Wenn b nicht 255 ist, ändert sich der Wert nicht. Andernfalls wird der Wert von g erhöht.
    g = (b != 255)
        ? g
        : (g != 255)
            ? g + 1
            : 0;
    //b wird erhöht. Ist bereits b = 255, so wird es auf 0 gesetzt.
    b = (b != 255)
        ? b + 1
        : 0;

    // Umwandlung in die Darstellung rrrgggbbb
    int rgbWert = r * 1_000_000 + g * 1_000 + b;

    return rgbWert;
  }

  /**
   * Main methode zum ausführen der statischen Methoden.
   *
   * @param args wird nicht verwendet.
   */
  public static void main(String[] args) {

    // Invertierung.
    System.out.println(invertiere(0, 0, 0));
    System.out.println(invertiere(10, 128, 255));

    // Nächste Farbe berechnen.
    System.out.println(gibNaechsteFarbe(10, 11, 12));
    System.out.println(gibNaechsteFarbe(10, 128, 255));
    System.out.println(gibNaechsteFarbe(0, 255, 255));
    System.out.println(gibNaechsteFarbe(255, 255, 255));
  }

}

```
