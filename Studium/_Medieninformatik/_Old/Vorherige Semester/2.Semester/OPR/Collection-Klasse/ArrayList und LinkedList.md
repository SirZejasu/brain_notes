#Themen 
#OPR
#Medieninformatik 

---
# Quellen

# Arrays undCollections
> [!question] ~
> Die Klassen Arrays und Collections enthalten eine Vielzahl statischer
Methoden, z. B. um Felder oder Listen und Mengen zu sortieren, kopieren und
initialisieren.
>- Eine Liste ist eine endliche Folge von Objekten.
>- Zugriff auf Objekte einer Liste erfolgt meist per nummerischem Index.
>- Listen-Klassen sind u. a.
>	- <mark style="background: #BBFABBA6;">ArrayList</mark> und Stack (basierend auf Feld)
> 	- <mark style="background: #BBFABBA6;">LinkedList</mark> (basiered auf verketteten Knoten)
>- Man verwendet Listen-Klassen, wenn es in einer Anwendung auf die
>Reihenfolge der Objekte ankommt.
>- Kommt es darauf nicht an, sind Mengen oder Zuordnungen häufig
die bessere Wahl.

# ArrayList vs. LinkedList
![[original.png]]

# Iteration
> [!question] ~
> - Die Methode iterator() ist in der abstrakten Klasse
AbstractCollection definiert, von der alle Listen- und
Mengenklassen abgeleitet sind.
> - Sie steht deshalb auch in den Klassen ArrayList, LinkedList und
Stack zur Verfügung.
> - Die Iteration über eine Liste muss deshalb nicht zwingend über den
nummerischen Index erfolgen. Für verkettete Listen (LinkedList)
sollte man dies auf jeden Fall vermeiden.

```java
import java.util.LinkedList;
import java.util.Iterator;
public class Demo {
   public static void main(String[] args) {
      LinkedList<String> l = new LinkedList<String>();
      l.add("John");
      l.add("Sara");
      l.add("Susan");
      l.add("Betty");
      l.add("Nathan");
      System.out.println("The LinkedList elements are: ");
      for (Iterator i = l.iterator(); i.hasNext();) {
         System.out.println(i.next());
      }
   }
}
```
