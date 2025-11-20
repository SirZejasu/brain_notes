#Themen 
#OPR
#Medieninformatik 

---
# Quellen

![[_Medieninformatik/Vorherige Semester/2.Semester/OPR/Streams/Anhänge/13_Ein-Ausgabe.pdf]]
# Definition
> [!question] ~
> Ein Stream ist eine Folge von Elementen, auf die sequentielle und
parallele Operationen angewendet werden können.
Es ermöglicht
> - Eine Interne Iteration
> - Greift auf bereits vorhandene Daten oder erzeugt welche.

> [!example] Beispiel (Erzeugung von Stream, Operationen auf Stream)
> ```java
> 
>Stream.of("08/15", "4711", "501", "S04", "1250", "333", "475")
> 	.filter(wort -> wort.matches("[0-9]+"))
> 	.map(wort -> Integer.parseInt(wort))
> 	.filter(zahl -> zahl >= 500)
> 	.sorted()
> 	.forEach(System.out::println);
> 	
> 	// ODER	
> String[] woerter = new String[]{
> 			"08/15", "4711", "501", "S04", "1250", "333", "475"}
>Arrays.stream(woerter)
> 	.filter(wort -> wort.matches("[0-9]+"))
> 	.map(wort -> Integer.parseInt(wort))
> 	.filter(zahl -> zahl >= 500)
> 	.sorted()
> 	.forEach(System.out::println);
> 	
> ```

# Stream-Klassen
| Klasse       | Typ der Element |
| ------------ | --------------- |
/ | Stream<T>    | T               |
| DoubleStream | double          |
| IntStream    | Int             |
| LongStream   | long                |

> [!example] Stream erzeugen
> - in Schnittstelle Stream<T> statische Methode
> ``` Stream<T> of(T... values) ```
> 
> - in Schnittstelle Collection<E> Instanzmethode 
> ``` Stream<E> stream() ```
> 
> - in Klasse Arrays statische Methode
> ``` Stream<T> stream(T[] array) ```
> 
> - in Klasse BufferedReader Instanzmethode
> ``` Stream<String> lines() ```
> 
> - in Schnittstelle Stream statische Methode
> ``` Stream<T> iterate(T seed, UnaryOperator<T> f) ```
> Analog für IntStream/IntUnaryOperator,
> LongStream/LongUnaryOperator ...
> 
> - in Schnittstelle Stream statische Methode
> ```Stream<T> generate(Supplier<T>)```
> Analog für IntStream/IntSupplier, LongStream/LongSupplier,
> ...
> 
> - in Schnittstelle IntStream statische Methode
> ``` IntStream range(int startInclusive, int endExclusive) ```
> Analog für LongStream, jedoch nicht für DoubleStream.
>
> - in Schnittstelle IntStream statische Methode 
> ``` IntStream rangeClosed(int startInclusive, int endInclusive)) ```
> Analog für LongStream.


# Befehle
> [!example] ~
> ``` java
> //Liefert das erste Element eines Streams, oder ein leeres Optional, wenn der Stream leer ist . Ergebnistyp ist Optional<T> (oder OptionalInt, ...). Ein Optional kapselt einen Wert bzw. Objekt, oder repräsentiert die Abwesenheit eines Werts bzw. Objekts
> findFirst()
>
> // Liefert ein beliebiges Element. Ergebnistyp ist Optional<T> (oder OptionalInt, ...) 
> findAny()
>  
> // Gibt an, ob eine Bedingung auf alle Elemente eines Streams zutrifft.
> // Bei allen Match Methoden:  Die Bedingung wird durch ein Objekt der Schnittstelle Predicate<T> (oder IntPredicate, ...) repräsentiert (Entwurfsmuster Strategie).
> boolean allMatch(...) 
>
> // Gibt an, ob es ein Element gibt, auf das die Bedingung zutrifft
> boolean anyMatch(...) 
> 
> // gibt an, ob eine Bedingung auf keines der Elemente eines Streams zutriff
> boolean noneMatch(...) 
> 
> // liefert einen Stream aller Elemente eines Streams, für die eine Bedingung zutrifft. Die Bedingung wird durch den Parameter von filter vom Typ Predicate angegeben.
> filter()
> 
> // Stream zu List<Object>
> toList()
> 
> // Abbilden der Werte im Stream, also so ähnlich, als würde man einen Wert neu deklarieren (int a = 1 + 2).
> map(...)
> 
>```







