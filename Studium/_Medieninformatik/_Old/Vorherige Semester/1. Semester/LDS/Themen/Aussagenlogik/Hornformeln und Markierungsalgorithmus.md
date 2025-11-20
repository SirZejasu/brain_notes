#Thema 
#LDS 
#Medieninformatik   

---
# Quellen
- [[logik-labyrinth-v1.pdf|Markierungsalgorithmus-Skript]]
- [[LDS-V-Mitschrieb-Aussagenlogik.pdf]] s. 15 (Markierungsalgorithmus)
- Siehe s. 116, [[LDS Skript.pdf]]
- [[Konjunktive Normalform (KNF)]]
- [YouTube](https://www.youtube.com/watch?v=TqCl3GJ5pMw&ab_channel=NLogSpace)

# Definition
> [!question] Die Horn-Norm
> Eine Formel ist "Horn", wenn die Formel in der [[Konjunktive Normalform (KNF)\|speziellen KNF]] oder normalen [[Konjunktive Normalform (KNF)|KNF]] ist und in jeder [[1. Syntax und Symantik 2022-11-14 22.21.06.excalidraw\|Klausel]] maximal ein positives Literal ist.

## Beispiel
$F = (A \lor \daleth B) \land (\daleth C \lor \daleth A \lor D) \land (\daleth A \lor \daleth B) \land D \land \daleth E$

# Erfüllbarkeitstest
## Markierungsalgorithmus / Implikationsform
> [!question] Markierungsalgorithmus / Implikationsform
> Ist die Formel Horn und KNF, kann sie für den Erfüllbarkeitstest in die Implikationsform gebracht werden. 

### Beispiele
> [!example] Implikationsform
> siehe [[_Allgemein - Aussagenlogik#Implikation\|Syntax und Symantik > Implikation]]). Außerdem gilt:
> - Negatierte Literale werden positiv, wenn es Tautologien sind. 
> - Das ist der Fall, wenn sie in Klauseln sind. 
> - Der Operator nach dem positiv gemachte Literal wird umgekehrt.
> - Jedes alleinstehende Literal wird umgewandelt in $1 \to A$(Wenn positiv) oder $A \to 0$ wenn negativ.
> - ![[Pasted image 20230107234947.png]]



> [!example] Beispiel Markierungalgorithmus
> $F = (B \to A) \land(C \land A\to D) \land(A\land B\to 0)\land(1 \to D)\land(E \to 0)$
>
> ### <u>Vorgehen</u>
> 
> #### <u> Schritt 1 Markieren von Atomaren Formeln </u>
> Markiere jede Literal in F mit der Form $(1 \to A)$. Jedes markierte Literal oder
> Klausel muss dann im jeden Fall TRUE sein, damit die Formel erfüllbar wird.
> ![[Hornformeln 2022-12-18 19.44.54.excalidraw]]
>
Markiere dann dasselbe Literal in allen anderen Klauseln.
![[Hornformeln 2022-12-18 19.58.48.excalidraw]]
>
>#### <u>Schritt 2</u>
Wenn der linke Teil einer Klausel in Implikationsform markiert ist, sollte der Rechte Teil auch markiert werden. In diesem Beispiel ist das nicht der Fall. Hier ein anderes Beispiel, wo B bei der ersten Klausel markiert wird, weil A markiert wurde:
![[Pasted image 20230107235507.png]]
>
Der Prozess wiederholt sich ab Schritt 2.
>
Wenn keine neue Markierung stattfindet, werden alle andere Literale zum Testen auf Falsch gesetzt. Dann wird überprüft, ob es ein Wiederspruch gibt.
![[Hornformeln 2022-12-18 20.04.19.excalidraw]]
In diesem Beispiel gibt es kein Widerspruch. Die Formel ist erfüllbar.
>
Sobald eine Klausel die Form ($A \to 0$) aufweist und die linke Seite markiert ist, ist die Klausel und somit auch die Formel unerfüllbar.
>
>
> #### <u>Schritt 3</u>
Gib erfüllbar aus und stoppe. Gib Außerdem das Modell aus.

> [!example] Beispiel 2
> ![[Pasted image 20230116094749.png]]

## Data Driven

## Goal driven

# Vorlesung

![[Pasted image 20221114220806.png]]
![[Pasted image 20221114222818.png]]
