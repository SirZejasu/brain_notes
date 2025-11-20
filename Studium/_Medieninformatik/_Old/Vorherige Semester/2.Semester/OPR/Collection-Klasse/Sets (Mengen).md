#Themen 
#OPR
#Medieninformatik 

---
# Quellen
s. Skript

# Sets (Mengen)
> [!question] ~
> Schnittstelle in Java.
> 
> - Sorgt dafür, dass eine Menge an Elementen nie gleich sind.
> - Iterieren über die Elemente.
>  - Man kann fragen, ob es ein Element enthält aber nicht spezifisch abrufen (Keine get Methode) 

# Methoden
<mark style="background: #FFB86CA6;">contains</mark>
```java
/**
* Instanzvariable zur Verwaltung
* der Elemente der Menge
*/
private HashMap<E, Object> map;

public boolean contains(Object o) {

	return map.containsKey(o);
}

```

<mark style="background: #FFB86CA6;">add</mark>
```java
/**
* Konstante, die als Wert den Schlüsseln
* zugeordnet wird.
*/
private static final Object PRESENT = new Object();

public boolean add(E o) {

/* put liefert genau dann null, wenn die map noch
* keinen Eintrag für den Schlüssel o enthält. In
* diesem Fall wird die Menge um ein Element erweitert
* und die add-Methode liefert true. Sonst liefert sie
* false.
*/
return map.put(o, PRESENT) == null;

}
```

# Iteration über Menge
> [!question] ~
> Mengen ermöglichen keinen Elementzugriff per Index. Die Iteration über die Elemente einer Menge erfolgt mittels eines Iterators. Einen Iterator zu einer Menge erhält man durch Anwendung der Methode <mark style="background: #ABF7F7A6;">iterator()</mark>. Die Methode befindet sich in der Klasse <mark style="background: #ABF7F7A6;">AbstractCollection</mark>(s. [[_ Klassenhierarchie JDK]]).

# HashSet
> [!question] ~
> Ein Objekt der Klasse HashSet repräsentiert eine Menge (im
mathematischen Sinn) von Objekten. Man kann sich also wirklich vorstellen wir eine "Mathematische Menge". 
Im Gegensatz zum Set kann man HashSet instanziieren.
Wie beim Set werden auch hier nur "einzigartige" Elemente verwaltet.

# TreeSet
Quelle: [TreeSet einfach erklärt](https://www.baeldung.com/java-tree-set)

> [!question] ~
> TreeSet ist im Gegensatz zu TreeSet immer geordnet.


# Comparator and Comparable
Quelle: [Comparator and Comparable](https://www.baeldung.com/java-comparator-comparable)


