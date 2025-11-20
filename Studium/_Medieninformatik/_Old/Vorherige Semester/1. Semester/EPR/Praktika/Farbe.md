#Medieninformatik 
#EPR 
#Praktika 

---

# Code
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
   * @return gibt die invertierte Farbe aus.
   */
  public static int invertiere(int r, int g, int b) {

    return r + g + b;

  }

  /**
   * Naechste Farbe ausgeben.
   *
   * @param r für rot in Prozent.
   * @param g für gruen in Prozent.
   * @param b für blau in Prozent.
   * @return gibt die nachst-hoehere Farbe aus.
   */
  public static int gibNaechsteFarbe(int r, int g, int b) {

    return r + g + b;

  }
  
  
  public static void main(String[] args) {
    
    System.out.println((invertiere(10, 128, 255)));
  }

}

```

# Marc Code
```js
  public static int gibNaechsteFarbe(int farbe) {
    // Der rot Wert.
    int red = farbe > 255255 ? farbe / 1000000 : 0;
    // Der grün Wert.
    int green = farbe > 255 ? (farbe - red * 1000000) / 1000 : 0;
    // Der blau Wert.
    int blue = farbe - red * 1000000 - green * 1000;

    int uebertrag;
    // Der erhöhte blau Wert.
    blue = blue + 1;
    uebertrag = blue / 256;
    blue = blue % 256;
    // Der erhöhte blau Wert.
    green = green + uebertrag;
    uebertrag = green / 256;
    green = green % 256;
    // Der erhöhte blau Wert.
    red = red + uebertrag;
    uebertrag = red / 256;
    red = red % 256;




    return red * 1000000 + green * 1000 + blue;
  }
```
