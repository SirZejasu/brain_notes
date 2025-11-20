#Themen 
#OPR
#Medieninformatik 

---
# Quellen

# Definition
> [!question] ~
> Schnittstelle mit nur einer Methode.

> [!example] Beispiel
> ``` java
>@FunctionalInterface
>public interface Filter{
>	boolean leasstDurch(String s)
>}
>```





# Lambda-Ausdruck
> [!question] ~
> Das besondere an funktionalen Schnittstellen ist der einfache Lambda-Ausdruck.
> ``` java
> /** Java-Compiler erkennt die Methode sofort, da es bei der Variable es 
>  * sich um den Typ "Filter", also die Schnittstelle handelt und es nur 
>  *eine Methode beinhaltet. 
>  */
> 
> // Anonyme Klasse wird erstellt.
> Filter filter = (String s ) -> {return s.length() >= 4};
>```


