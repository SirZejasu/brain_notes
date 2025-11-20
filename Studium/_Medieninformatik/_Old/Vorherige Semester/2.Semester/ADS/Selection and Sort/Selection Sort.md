#Thema 
#ADS
#Medieninformatik   

---

# Quellen
- s. Notizen 3_Selection_and_Sort

# Selection Sort

> [!question] ~
> Kleinste Ziffer herausnehmen und in eine neue Liste hinzufügen.
> Der Aufwand berechnet sich folgendermaßen: $\left( \frac{n*(n*1)}{2} \right)$

## Algorithmus
> [!hint] Algorithmus
> ![[Algorithmus.png]]
> ![[Algorithmus2.png]]
>  <mark style="background: #FFB86CA6;">Zu Orientierung habe ich die Schritte im Algorithmus markiert!</mark>
> - (1) Wir fangen beim ersten Index an.
> 
> - (2) Im Grunde überprüft der Algorithmus, ob der Wert in<mark style="background: #BBFABBA6;">a[i]</mark> kleiner ist als der Rest der Reihe. 
> 
> - (3) Daraufhin wird der Index der Ziffer mit dem Index des kleineren Werts ausgetauscht. 
> 
> - In Runde 2 sieht man, dass 7 mit 3 ausgetauscht wurde. Dabei wird in der zweiten Vorschleife der kleinste Vergleichbare Wert gesucht. 
>   Als erstes wird der Wert 4 dem <mark style="background: #BBFABBA6;">minPos</mark> zugewiesen, da $4 < 7$ true ist. Die Suche wird fortgesetzt und es wird ein kleinerer Wert gefunden, $3 < 4$ ist true, somit wird <mark style="background: #BBFABBA6;">minPos</mark> auf 3 gesetzt. Die for-schleife bricht ab, da der höchste Index bereits erreicht wurde.
>   
>  - (4) Nach der For-Schleife wird dann der Wert in <mark style="background: #BBFABBA6;">a[i]</mark> mit der kleineren Zahl getauscht.
>    Wird kein kleinerer Wert gefunden, wird der Algorithmus den Wert "mit sich selbst tauschen". (s. Runde 0 und 1)


## Beispiele

> [!example] Beispiel
> Folge:  
>
| 0   | 1   | 2   | 3   | 4   | 5   | 6   |
| --- | --- | --- | --- | --- | --- | --- |
| 1   | 2   | 7   | 4   | 9   | 6   | 3   |
>
> Runde im Algorithmus:
> ![[Pasted image 20230420112204.png|450]] ![[Pasted image 20230420113043.png|130]] 
>

# Aufwand
![[Pasted image 20230420153633.png]]







 






