#Thema 
#LDS 
#Medieninformatik   

---
# Quellen
- S. 41 [[graphprobleme-v103.pdf]]
- [[LDS Graphen.pdf]]

# Definition
> [!question] Eulersche Graphen
>Ein eulerscher Graphen ist ein geschlossener Pfad und Trail.
Ein eulerscher Graphen enthält nur Knoten mit einem geraden Grad! Somit lässt es sich leicht überprüfen, ob der Graph eulersch ist.
> - <mark style="background: #BBFABBA6;">semi-eulersch</mark>
Ein nicht-geschlossener Trail. Semi-eulersch Graphen enthalten immer genau zwei Knoten mit ungeraden Grad.
> - <mark style="background: #BBFABBA6;">Eulertour</mark>
Angefangen beim Grad mit einer ungeraden werden dabei alle Kanten genau einmal durchlaufen und die Kosten der Kanten berechnet.
> - <mark style="background: #BBFABBA6;">Gesamtweg</mark>
Berechnet den Pfad vom ungeraden Grad und zurück.	
Also im Grunde genommen: Eulertour + Rückweg = Gesamtweg.

# Algorithmus von Fleury
> [!question] Definition
> Der Algorithmus fährt diese Eulertour ab und soll alle Brücken entfernen, so weit es geht.
> 
> <mark style="background: #BBFABBA6;">disconnecting set</mark>
Würde man eine Menge von bestimmten Kanten im Graphen entfernen, wäre der Graphen unzusammenhängend. Diese Menge nennt man "disconnecting set."
>
> <mark style="background: #BBFABBA6;">cutset</mark>
Der cutset enthält den minimalen disconnecting set. Es gibt also weitere Kanten, die ohne dessen eigene Existenz den Graphen zusammenhängend lässt.

## Ablauf
