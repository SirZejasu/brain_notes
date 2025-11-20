#Medieninformatik 
#LDS 
#Thema   

---
# Quellen
- [[LDS-V-Mitschrieb-Aussagenlogik 1.pdf|Mitschrieb 1]] S.12
- [[LDS-Mitschrieb-Logik-WS2122.pdf|Mitschrieb 2]] 
- [YouTube](https://www.youtube.com/watch?v=4sHZd1OrXG8&t=234s&ab_channel=NLogSpace)

# Definition
> [!question] KNF
> Eine Konjunktion von Literalen. 

# Umformen einer Formel in KNF
Schritt | Definition
--- | --- 
$0.Schritt$ | Pfeile durch Gesetze entfernen.
$1.Schritt$ | Distributivgesetze einsetzen, siehe dazu die [[_Allgemein - Aussagenlogik\|Gesetze]] an. 
$2.Schritt$ | Darauf achten, das innerhalb einer Klausel mindestens ein positives [[_Allgemein - Aussagenlogik#Syntax und Semantik\|Literal]] gibt. 

### Beispiel
> [!example] Beispiel 1
> ![[Pasted image 20230107182653.png]]
> ![[Pasted image 20230107182726.png]]



# Spezielle KNF
> [!question] Spezielle KNF
> Bei einer Speziellen KNF werden die Klauseln (Also Teile der Formeln) in geschweiften Buchstaben kurzegefasst.

> [!example] Beispiel
> In diesem Beispiel wird der längere Ausdruck in einzelne Buchstaben zusammengefasst aus den Teilen der Aussage. Daraus formt sich die spezielle KNF.
> ![[Pasted image 20221227160502.png]]

# Harmloser und nicht-harmloser KNF
Name | Definition
--- | ---
Harmlose Ausdrücke | <mark style="background: #BBFABBA6;">Harmlose Ausdrücke</mark> entsprechen der [Horn-Norm](Hornformeln%20und%20Markierungsalgorithmus.md), also besitzen maximal einen positiven Literal.
Nicht-Harmlose Ausdrücke | <mark style="background: #BBFABBA6;">Nicht-Harmlose Ausdrücke</mark> . Nicht-Harmlose Ausdrücke entsprechen nicht der Horn-Norm und müssen einzeln überprüft werden. |


## Beispiele

> [!example] Harmloser Ausdruck.
> Dieser Ausdruck ist harmlos und kann sofort in der Warheitstabelle eingesetzt werden.

> [!example] Nicht-Harmloser Ausdruck
> Nicht-Harmloser Ausdruck hat mehr als ein positives Literal. Wenn das der Fall ist, müssen die Teile der Formeln einzeln betrachtet werden.
> ![[Pasted image 20221227160858.png]]
>
Diese untersucht man nach und nach. Logischerweise muss man nicht alle Teile betrachten, wenn einer davon eine Tautologie ist (-1 gültig) und die gesamte Formel eine Disjunktion ist. Somit wäre dann der gesamte Ausdruck gültig.

# (Alternativer Weg aus Recherche) Eine Aussage in KNF Umformen.
Funktioniert wie DNF, nur umgekehrt.

Es wird auf die Wahrheitstabelle geachtet und geprüft, unter welchen Bedingungen die Aussage falsch ist.
![[Pasted image 20221113185206.png]]

Hier können wir sehen, welche Umstände die Aussage als false stehen lässt.
Somit kommen wir zur folgender Erkenntnis.
![[Pasted image 20221113185334.png]]

Diese Formeln werden dann mit der Konjunktion ( $\land$ ) verbunden.  
![[Pasted image 20221113185559.png]]