---
tags:
  - aufwandsanalyse
  - theoretische_informatik
  - thi
sticker: ""
banner_y: "48.5"
---
--- 
    
> [!hint]
    > Nützlich wäre es hier Umformungen mit $\Sigma$ zu üben

---

>[!question]
># Worum geht es im Kapitel?
> Methoden zur Ermittlung des zeitlichen Aufwands eines Algorithmus in diese in Klassen aufteilen

# Typen von Algorithmen
> [!Definition]
    > ## Iterative Algorithmen
    > Zeitbedarf entspricht die Anzahl der Schleifendurchläufe
    > Note: Nur diese Definition ist relevant für die Klausur.
    

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
![[Beispiel Aufwandsanalyse geschachtelte Schleifen]]
> 3. Lösung: $\sum_{i=1}^n (n-i+1) = \frac{1}{2}n^2+\frac{1}{2}n$
![[Pasted image 20250722205929.png]]

# O - Notation

> [!Definition]
> Mit der O-Notation beschreiben wir den Zeitbedarf eines Algorithmus im schlechtesten Fall. 
> - Algorithmen, die im Sinne der O-Notation besser sind, sind in der Regel
auch in der Praxis besser.
> - Das macht die Untersuchung der größenordnungsmäßigen Zeitkomplexität auch für
Praktiker interessant.
    > ![[Pasted image 20250722225345.png]]
    > ![[Pasted image 20250722225704.png]]

> [!info] Rechengesetze
    > ![[Pasted image 20250722225526.png]]

> [!hint] Klausurrelevanz
    > - Funktion erkennen und diese Klassen zuweisen können.
    > - Beweisen, dass es in dieser Klasse enthalten ist. 
>    
> > [!example] Beispiel 1
> > Zu finden ist die Konstante c. Hier erkennt man sofort, dass c mindestens 1 sein muss. Somit wurde bewiesen, dass die obere Aussage gilt, solange c mindestens 1 ist.
> > ![[Pasted image 20250722230644.png]]
>
 > > [!example] Beispiel 2
 > > 1. Betrachte die Definition von max{}
 > > 2. Aus der Definition lässt sich herleiten, dass f(n) kleiner ist max{f,g} (Wenn g größer) und umgekerht.
 > > 3. Damit können herleiten und f(n) mit g(n) addieren
 >>
 > ![[Pasted image 20250722231923.png]]
 > 
 > > [!example] Beispiel 3
 > > ![[Pasted image 20250724171141.png]]
 > 
 > > [!example] Beispiel 4
 > > ![[Pasted image 20250724171403.png]]