
#Themen 
#OPR
#Medieninformatik 

---
# Quellen

# Definition
> [!question] ~
> Sagt aus, welche Art von Methode ausgeführt wird.


# Import
> [!question] ~
> Die Annotationen müssen importiert werden.
> ![[Pasted image 20230518211616.png]]
> ![[Pasted image 20230617142711.png]]

## After
> [!question] After
> Methode wird nach der Testausführung durchgeführt. Ermöglicht Abbau von Daten.

> [!example] Beispiel
> ![[Pasted image 20230519001356.png|400]]



## Before
> [!question] Before
> Methode wird vor jedem Testfall ausgeführt. Ermöglicht das Aufbauen der Daten.

> [!example] Beispiel
> ![[Pasted image 20230519001128.png|400]]



## Ignore
## Test
> [!question] 
> Notwendige Annotation für die automatische Testdurchführungen. Damit geben dem Compiler an, dass es sich um eine Testmethode handelt.

> [!example] ~
>![[Pasted image 20230519001053.png|400]]



## Die Klasse Assert
> [!question] ~
> Enthält statische Methoden, die für die automatische Testdurchführung notwendig ist. 

# Aufbau
> [!question] ~
> Es sieht aus wie eine normale Klasse. Die Klasse wird am Ende mit "Test" benannt.
> ![[Pasted image 20230518233351.png]]




 # Ablauf einer Testklasse
> [!example] Beispiel
> ## Schritt 1 Testdaten aufbauen (Optional)
>
> ## Schritt 2 Testmethode wurde ausgeführt.
>
> ## Schritt 3 Testdaten abbauen (Optional)

> [!Hint] 
> Die Daten, also Instanzvariablen innerhalb einer Testklasse, bleiben für alle Testausführungen / Methoden gleich. Sie werden nicht durch vorherige Tests manipuliert. 


# Ist-Soll Vergleich
![[Pasted image 20230519001649.png]]

> [!hint] ~
> <mark style="background: #BBFABBA6;">assertEquals</mark> stammt aus der Klasse <mark style="background: #D2B3FFA6;">Assert</mark>. Es ersetzt den "Augentest".

