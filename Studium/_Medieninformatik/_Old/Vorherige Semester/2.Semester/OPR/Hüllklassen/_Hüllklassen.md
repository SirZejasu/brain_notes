#Themen 
#OPR
#Medieninformatik 

---
# Quellen

# Definition
> [!question] ~
> Objekte von "Hüllklassen" umhüllen elementare Werte, wie <mark style="background: #BBFABBA6;">int</mark> und <mark style="background: #BBFABBA6;">double</mark>. Wird unter anderem für ArrayListen verwendet.

> [!hint] Hüllklassen der elementaren Werte.
> ![[Pasted image 20230617143805.png]]


# Methoden der Hüllklassen
> [!example] Methoden
> ```java
> 
>[Integer] intValue() 
>// Liefert den Int Wert aus der Klasse.
>
>[Integer] parseInt(String s)
>// Liest Zeichen im String und erzeugt daraus ein int Wert.
>
> [Double] parseDouble(String s)
> // Liest Zeichen im String und erzeugt daraus ein double Wert.
> 
> [Boolean] parseBoolean(String s)
> // Liest Zeichen im String und erzeugt daraus ein boolean  Wert.
>
> [Boolean] booleanValue()
> // Liefert den Int Wert aus der Klasse.
>
>```
> 
> 
> ## Beispiele
> ```java
>  // Erstellen des Objekts.
> Integer i = new Integer(10);
> Boolean b = new Boolean(true);
> 
> /* ungültige Ausdrücke, da i und b keinen elementaren
> Typ besitzen. (Seit JDK 1.5 ist es doch möglich.)
>*/
> i + 20
> b && true ? ... : ...
> 
> // Methode zum "auspacken" der Werte aus der Hüllklasse.
> boolean booleanValue() // in Klasse Boolean
> int intValue() // in Klasse Integer
> double doubleValue() // in Klasse Double
>
> /* Gültiger Ausdruck */
> i.intValue() + 20
> b.booleanValue() && true ? .
> 
> // Parsen
> int i = Integer.parseInt("4711");
> double d = Double.parseDouble("-1.25E-13");
> boolean b = Boolean.parseBoolean("true");
>```






