#Themen 
#OPR
#Medieninformatik 

---

# Throwable
> [!question] 
> Ausnahmen sind Instanzen aus der Klasse Throwable. Dieser enthält Unterklassen, die unter diesem benannt werden.
> ```java
> // Exception aus Throwable oder Unterklasse rufen (oder auswerfen)
> throw [Throwable]
> 
> // Beispiel
> throw new DemoException("Parameter ist ungerade.", n);
> 
>```
>
> 
> 
> Die Klasse gibt folgende Informationen aus:
> 
> <mark style="background: #BBFABBA6;">Stack Trace</mark>
>  Enthält Methoden, die bis zum Auslösen der Ausnahme
> aufgerufen und noch nicht beendet wurden.
> 
> ```java
> // Zugriff auf Stack Trace z. B. durch
 > void printStackTrace() 
 > // oder
> StackTraceElement[] getStackTrace()
> ```
> 
> <mark style="background: #BBFABBA6;">Detaillierte Meldung</mark>
> Textuelle Information über aufgetretene
> Ausnahme.
> 
> ``` java
>// Zugriff auf Meldung
> String getMessage().
> ```


# Unterklassen von Throwable

## RuntimeException
> [!question] ~
> Bei Ausnahmen dieser Klasse handelt es sich um Programmierfehler, z.B -> 
> ```java
>  new StringTokenizer(null). 
>  ```

## Error
> [!question] ~
> Objekte dieser Klasse präsentieren Ausnahmen, die normalerweise nicht behandelt werden können.
> Zu den Ausnahmen dieser sind Klasse gehören z.B.
> 	-> <mark style="background: #BBFABBA6;">OutOfMemoryError</mark> (Speicherüberlauf)
> 	-> <mark style="background: #BBFABBA6;">StackOverflowError</mark> (Stacküberlauf)

## Exception
> [!question] ~
> Ausnahmen dieser Klasse "dürfen" auftreten und sind sogar förderlich. Die treten auf, vorausgesetzt, es gibt kein [[#RuntimeException]].


### Unchecked- und Checked Exceptions
> [!question] ~
> Unchecked Exception sind Fehler ohne weitere Behandlung Checked Exceptions schon.

