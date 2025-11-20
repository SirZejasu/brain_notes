#Medieninformatik 
#LDS 
#Thema   

---
# Quellen
- [[Extended Euclid - Mitschrieb.png]]

# Euclidean Algorithm
> [!question] Euclidean Algorithm
> Der #Euclid #Algorithmus dient dazu, den größten gemeinsamen Teiler zweier positiven  Werte zu berechnen. gcd steht für "Greatest Common Divisor". Ist das Ergebnis 1, handelt es sich bei beiden Zahlen um Primzahlen.
Merksatz:
Wenn $a=bq+r$ dann $gcd(a,b)=gcd(b,r)$
ODER
Wenn $b=aq+r$ dann $gcd(a,b)=gcd(a,r)$
Es wird immer der größere Wert geteilt.

## Beispiele
### Beispiel 1
$gcd(2322,654)$

$2322=654*3+360$ <- 654 (also b) passt nur 3-mal in 2322, der Rest ist 360.

$gcd(2322,654) \to gcd(654,360)$
	$654=360*1+294$

$gcd(654,360) \to gcd(360,294)$
	$360 = 294*1+66$

$gcd(360,294) \to gcd(294,66)$
	$294=66*4+30$

$gcd(294,66) \to gcd(66,30)$
	$66=30*2+6$

$gcd(66,30) \to gcd(30,6)$
	$30 = 6*5 + 0$ <- Rest ist null.- Somit ist 6 der größte Teiler der beiden Zahlen.

# Extended Euclidean Algorithm
> [!question] EEA
>  Erweiterung des Euclidean Algorithmus. Auch hier wird der Rest berechnet.

## Vorgehen
> [!hint] Hinweis
> In den Aufgaben von Conen werden nur Primzahlen verwendet.

![[Extended Euclid (EEA) 2022-12-27 20.08.34.excalidraw|700]]

## Beispiele
> [!example] Beispiel 1
> ### Schritt 1
Sei p = 17 und q = 7 gegeben. 
>
$n = 17*7=119$
$TF(n)=TF(91)=(p-1)*(q-1)=16*6=96$
$e = 77$ <-- Der Wert ist vorgegeben
>
> ### Schritt 2
> 
> ![[Extended Euclid (EEA) 2022-12-27 21.14.02.excalidraw]]
>Zum Kontrollieren der Werte:
>$x*a+d*b=t$

## e Wert selbst bestimmen
> [!question] e-Wert
> Der e-Wert ist kein einziger Wert, sondern kann aus einem Bereich sein, aus dem man irgendeine Zahl nimmt. 
> Voraussetzung:
> - Es ist eine Primzahl
> - Es ist kein vielfaches von (p-1) oder (q-1) (Nicht durch diese Zahlen teilbar)
> - (p-1) oder (q-1) sind kein Vielfaches von der ausgewählten Zahl.

# Vorlesung
![[18. RSA 2023-01-03 09.13.03.excalidraw]]