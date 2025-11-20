---
tags:
  - programmverifikation
  - algorithmus
  - theoretischeinformatik
  - thi
sticker: emoji//1f4bb
banner_y: "48.5"
---
--- 




>[!question]
># Worum geht es im Kapitel?
> Methoden zur Überprüfung von Algorithmen auf ihre Korrektheit 

# Hoare-Tripel
> [!Definition]
    > Die Hoare-Tripel beschreiben den Zustand vor und nach einer Anweisung.
    >```java
    > {Q} S {R}
    >```
> Ist die Aussage Q (Vorbedingung) wahr vor einer Anweisug S, dann gilt nach der Ausführung S die Aussage R (Nachbedingung).
> Hoare-Axiome sind Hoare-Tripel, die offensichtlich wahr sind.
> Hoare-Regeln ermöglichen die Herleitung von wahren Hoare-Tripeln. (sequentielle Zuweisung, s. Übung)

> [!Hint]
    > In der Klausur als auch in der Übung arbeiten wir idR mit der [[Studium/_Medieninformatik/6.Semester/Module/THI/K01/Anhänge/Pasted image 20250717215114.png|linken Implikationsregel]] zum beweisen.

# Regel der sequentiellen Kompsition
> [!definition]
    > Prüfung der Korrektheit bei einer einfachen Anweisung.
    > ![[Pasted image 20250717215633.png]]  
    > ![[Studium/_Medieninformatik/6.Semester/Module/THI/K01/Anhänge/Pasted image 20250717214659.png]]

1. Fang unten mit der sequentiellen Zuweisung an.
2. Wiederhole und arbeite dich hoch.
3. Beweise, dass die letzte Zuweisung gleich Q ist ([[Studium/_Medieninformatik/6.Semester/Module/THI/K01/Anhänge/Pasted image 20250717215114.png|linken Implikationsregel]]). Bedenke die [Rechenregeln](Rechenregeln.md).

## Beispiel
![[Pasted image 20250717215320.png]]

# Regel der bedingten Anweisung
> [!definition]
    > Prüfung der Korrektheit bei einer bedingten Anweisung
    > ![[Pasted image 20250717215703.png]]
    
1. Anfangs- und Endzuweisung im jeweiligen Anweisungsblock mit der [[Studium/_Medieninformatik/6.Semester/Module/THI/K01/Anhänge/Pasted image 20250717215921.png|Regel]] ableiten.
2. Fang unten mit der sequentiellen Zuweisung an.
3.  Beweise mit [[Studium/_Medieninformatik/6.Semester/Module/THI/K01/Anhänge/Pasted image 20250717215114.png|linker Implikationsregel]], dass die Aussagen in beiden Blöcken wahr sind. Bedenke die [Rechenregeln](Rechenregeln.md).

## Beispiel
![[Pasted image 20250717220433.png]]

# Regel der while-Schleife
> [!Definition]
    > Prüfung auf Korrektheit bei while-Schleifen
    > ![[Pasted image 20250717220616.png]]

1. Anfang- und Endzustand ableiten anhand der [[Studium/_Medieninformatik/6.Semester/Module/THI/K01/Anhänge/Pasted image 20250717220734.png|Definition]]
2. Von unten aus die sequentielle Zuweisung anwenden.
3. Beweisen mit  [[Studium/_Medieninformatik/6.Semester/Module/THI/K01/Anhänge/Pasted image 20250717215114.png|linker Implikationsregel]]. Bedenke die [Rechenregeln](Rechenregeln.md).

# Weitere Erklärungen

>[!definition]
> # Algorithmisches Problem
> ![[Pasted image 20250401122728.png]]

---
>[!definition]
># Partielle und Totalle Korrektheit
>Um die Korrektheit eines Algos zu bestimmen, gibt es zwei Wege.
>![[Pasted image 20250401122949.png]]
> 
---
>[!definition]
># Zusicherungen
> ![[Pasted image 20250401123601.png]]
> # Weitere Unterteilung von Zusicherungen
> ![[Pasted image 20250401123716.png]]




---











