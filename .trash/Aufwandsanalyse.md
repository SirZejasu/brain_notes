---
tags:
  - aufwandsanalyse
  - theoretische_informatik
  - thi
sticker: emoji//1f4bb
banner_y: "48.5"
---
--- 

> [!hint]
    > Nützlich wäre es hier Umformungen mit $\Sigma$ zu üben

>[!question]
># Worum geht es im Kapitel?
> Methoden zur Ermittlung des zeitlichen Aufwands eines Algorithmus in diese in Klassen aufteilen

# Typen von Algorithmen
> [!Definition]
    > ## Iterative Algorithmen
    > Zeitbedarf entspricht die Anzahl der Schleifendurchläufe
    > Note: Nur diese Definition ist relevant für die Klausur.
    
# Klassen

# Algorithmen-Schema

## Schleife
> [!Info] Formel
 > $$
> n-k+s
> $$
> n = Grenzwert / höchster Wert in der Laufvariable
> k = Initialwert / kleinster Wert
> s = ergibt die Schrittweite (Normalerweise 1) 

> [!Example]
> 1. Laufvariable (LV) ermitteln: i
> 2. Werte ermitteln:  $0, 1, 2, \dots, n-1$
> 3. Anzahl der Iterationen ($n-k+s$): $(n-1)-0+1=n$
> 4. Lösung: $f(n)=n$, $O(1)$ (Konstante)
> ![[Pasted image 20250722204255.png]]

## Zwei aufeinanderfolgende Schleifen
> [!Info] Formel
 > $$
> m+n
> $$

> [!Example]
>  1. Ablauf wie im Beispiel von [[#Schleife]] jeweils pro Schleife
>  2. Iteration miteinander addieren: $m+n$
> ![[Pasted image 20250722205026.png]]

| test |

## Zwei geschachtelte Schleifen
> [!Info] Formel
 > $$
> \sum_{i=0}^n (i+1)
> $$
> n = Grenzwert / höchster Wert in der Laufvariable der äußeren Schleife
> i = Initialwert / kleinster Wert der äußeren Schleife
> (Formel neben Sigma) = Ergibt sich aus der Zusammenführung beider Iterationen

> [!Example]
> 1. Ablauf wie im Beispiel von [[#Schleife]] für jeweils die innere und äußere Schleife
> 2. Iteration zusammführen: 
>    
>    
![[Pasted image 20250722205929.png]]