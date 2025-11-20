#Thema 
#ADS
#Medieninformatik   

---
# Quellen
s. Skript

# Definition
> [!question] ~
> Bei der Sortierung werden Datensätze in einer bereits sortierten Reihe von Datensätzen hinzugefügt.


# Algorithmus
> [!hint] Algorithmus
> ![[InsertSort.png]]
> 
> 
> Die Schleife beginnt mit dem Index 1.
> 
> - (1) Als erstes wird eine Int-Variable "element" generiert. Element wird der Wert vom <mark style="background: #BBFABBA6;">a[index] </mark>zugewiesen.
>	Daraufhin wird eine Int-Variable "j" generiert, dieser bekommt den Wert <mark style="background: #BBFABBA6;">Index - 1</mark>. Also den Index-Wert vor dem Momentanen Index.
>
> - (2) Die While-Schleife überprüft, ob der j Wert größer ist als null. Diese Überprüfung ist wichtig, wenn der Array leer ist.
> 	Zusätzlich wird überprüft, ob das ausgewählte Element größer ist als das vorherige. 
>- (3) Wenn True, wird der Index-Höhere Wert in der Liste ausgewählt und mit dem vorherigen Wert ersetzt.
>	<mark style="background: #BBFABBA6;">j</mark> wird um eins verringert. Wenn esDas ist nachher relevant, um das gelöschte Element wieder einzufügen.
>
> - (4) Das kleinere Element wird in der Liste dort hinzugefügt, wo der größere Wert war. Die Werte sind jetzt vertauscht.
>   Ist die Prüfung bei der While-Schleife false gewesen, so ersetzt sich der Wert mich sich selbst. Die Liste bleibt an dieser Stelle unverändert.



# Beispiele
> [!example] Beispiel
> Folge:
> 
| 0   | 1   | 2   | 3   | 4   |
| --- | --- | --- | --- | --- |
| 1   | 2   | 4   | 6   | 3   |
> 
> Ablauf des Algorithmus
>
> ![[Pasted image 20230507180620.png]]
> 
# Aufwand
> [!question] ~
> Best-Case(Easy): Folge bereits sortiert.
> Worst-Case: Absteigende Folge.
> Average-Case: $0(n^2)$

