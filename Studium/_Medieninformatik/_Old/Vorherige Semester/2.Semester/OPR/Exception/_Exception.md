#Themen 
#OPR
#Medieninformatik 

---
# Quellen

# Definition
> [!question] ~
> Eine Exception unterbricht einen Algorithmus und gibt einen Wert früher aus.
> Es gibt zwei Möglichkeiten bei einer Exception:
> - Methode versagt.
> - Methode sucht Alternative <mark style="background: #D2B3FFA6;">(Exception Handling)</mark>.
> 
>  Gründe für das versagen einer Methode:
> 
> - Mangel an Speicherplatz
> - Unzulässiger Index beim Zugriff auf Array, Liste oder Zeichenkette
> - Versuch, Methode für null-Referenz aufzurufen
> - Versuch der Typkonvertierung zwischen unverträglichen Typen
> - Problem bei Dateizugriff, z. B. ungültiger Dateiname
> - Verletzung einer Zusicherung (assert)

> [!hint] Beispielklasse
> ``` java
>  Klasse deklarieren.
> public class DemoException extends Exception {  
 > 
  >/**  
   > * Zahleninformation zu dieser Ausnahme.   */  
   > * private final int zahl;  
  > /**  
   > * Erzeugt ein Objekt dieser Klasse für die angegebenen Daten.   *   * @param meldung Meldungstext zu dieser Ausnahme  
   > * @param zahl    Zahl zu dieser Ausnahme  
   > */  
   > public DemoException(String meldung, int zahl) {  
 >  
   >  /*  
 >     * Die Klasse Exception besitzt einen Konstruktor, dem ein erläuternder Text zu der Ausnahme     * übergeben werden kann.     */    super(meldung);  
  > 
>     this.zahl = zahl;  
  > }  
  >
  > /**  
  >  * Liefert die Zahl dieser Ausnahme.   *   * @return Zahl dieser Ausnahme  
   > */  public int gibZahl() {  
  > 
>    return zahl;  
 >  }  
> }
> ```


# Try und Catch (Exception handling)
> [!question] ~
> <mark style="background: #BBFABBA6;">Try:</mark> Kommt es zur einer Exception, wird dieser im "Try-Block" in einer Anweisung weiterverarbeitet.
><mark style="background: #BBFABBA6;">Catch:</mark> Kommt es innerhalb dieses Blockes zur einer Ausnahme, werden sie im "Catch-Block" weiterbearbeitet werden.

> [!hint] Aufbau von Try und Catch
> ``` java
> try {
> /* Dies ist der normale Code, in dem Ausnahmen
> auftreten können.
> */
> ...
> } catch (Exceptiontyp1 e1) {
> /* catch-Block, um Ausnahmen der Klasse
> * Exceptiontyp1 zu fangen und zu behandeln
> */
> ...
> }
> 
>catch (Exceptiontyp2 e2) {
> /* catch-Block, um Ausnahmen der Klasse
> * Exceptiontyp2 zu fangen und zu behandeln
> */
> ...
> }
> ... // weitere catch-Blöcke
> } finally {
> /* Dieser Block wird immer ausgeführt, unabhängig davon,
> * ob bei Ausführung des try-Blocks eine Ausnahme auftrat
> * oder nicht. Er wird auch ausgeführt, wenn eine Ausnahme
>* zuvor gefangen und behandelt wurde.
> * Der finally-Block ist optional, wenn die try-Anweisung
> * mindestens einen catch-Block enthält.
> */
> ...
> } 
>  
>```

> [!question] Final Block
> Der try-Block wird vollständig ausgeführt.
> 
> a) Die try-Anweisung enthält einen finally-Block.
>     -> Der finally-Block wird nach Ausführung des try-Blocks ausgeführt.
> 	-> Die Ausführung der Methode wird hinter der try-Anweisung fortgesetzt.
>
> b) Die try-Anweisung enthält keinen finally-Block.
> -> Nach Ausführung des try-Blocks wird die Ausführung der Methode hinter der try-Anweisung fortgesetzt.

> [!example] Beispiel-Methode 1
> ```java
>private static void erkenneZahlen() throws IOException {  
>  
>String zeile = EinAusgabe.liesVonTastatur("Eingabe (exit zum  Beenden): ");  
>  while (!"exit".equalsIgnoreCase(zeile)) {  
>  try {  
>  
>    /*  
>     * dargestellten Wert ermitteln
>     */      
> 	int zahl = Integer.parseInt(zeile);  
>
> 	 System.out.println(zahl + " ist ein int-Wert.");  
>  
> 	  } catch (NumberFormatException e) {  
>     
>	 /*  
>       * keine gültige int-Darstellung      
> 	  */ 
> 	   System.out.println(zeile + " ist kein int-Wert.");  
> 		
> 	}  
>    zeile = EinAusgabe.liesVonTastatur("Eingabe: ");  
>   }  
> }
> ```

> [!example] Beispiel-Methode 2
> ``` java
>
> /**  
> * Gibt den übergebenen Wert auf dem Bildschirm aus, wenn dieser gerade ist. * * >@param n eine Zahl  
> * @throws DemoException wird geworfen, wenn n ungerade ist  
 > */
 > 
 > private static void m2(int n) throws DemoException {  
  >
  >if (n % 2 == 1) {  
    >	throw new DemoException("Parameter ist ungerade.", n);  
  >		} else {  
   > 			System.out.println(n);  
  >		}  
>	}  
  >
>/**  
 >* Gibt den übergebenen Wert auf dem Bildschirm aus, wenn dieser gerade ist. * *  @param zahl eine Zahl  
 >*/
 >private static void m1(int zahl) {  
  >
  >try {  
   > 	m2(zahl);  
 > 
   > /*  
   >  Wenn diese Ausgabeanweisung ausgeführt wird, weiß man, dass der Aufruf von m2 nicht versagt hat.
   > */    
   > 	  
   > System.out.println("m2 hat nicht versagt. Die Zahl war gerade.");  
  >
  >	} catch (DemoException e) {  
  >
    >/*  
     >* An dieser Stelle weiß man, dass der Aufruf von m2 im try-Block versagt hat.     >*/    
     >
     >System.out.println("m2 hat versagt. Die Zahl war ungerade.");  
  >
   > /*  
     >* Für jede Ausnahme steht die Methode getMessage() zur Verfügung. Diese Methode ist in der     * Klasse Throwable definiert.     */    
     > 
     > System.out.println(e.getMessage());  
  >
    > /*  
     > * Zugriff auf spezielle Information zu dieser Ausnahme.
     > */   
     > 
>  System.out.println("Ursache des Versagens: " + e.gibZahl());  
>  
> } finally {  
> 	
> 	System.out.println("Es wurde geprüft, ob die Zahl " + zahl + " gerade ist.");  
> 		}  
> 	}
>
>```







