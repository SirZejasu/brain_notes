#Medieninformatik 
#Formelsammlung 

---
# Was sind Funktionen (Bzw. Abbildungen)?

----
Eine eindeutige Zuordnung des Definitions- und Wertbereichs heißt Funktionen. Eine Funktionsgleichung nimmt einen x-Wert aus dem Definitionsbereich und weist diesem einen Element aus dem Wertebereich zu.
Es ist nicht anderes als eine Gleichung, die in der Graphentabelle eingezeichnet wird.

---


# Lineare Gleichung
```functionplot
---
title: Lineare Funktion
xLabel: x
yLabel: y
bounds: [-10,10,-10,10]
disableZoom: true
grid: false
---
f(x)=1*x+0
```
$$
f(x)=mx+n
$$
- m gibt die Steigung der Geraden an.
- b gibt y-Achsenabschnitt an.
- $D_{f}$ Definitonsbereich.
- $W_{f}$ Wertebereich.

mit dem Steigungsdreieck kann die Steigung m bestimmt werden.

$$
m= \frac{\triangle y}{\triangle x}=\frac{y_{2}-y_{1}}{x_{2}-x_{1}}
$$

Dafür benötigt man zwei Punkte vom Graphen.

$A(x_{1} \textbackslash y_{1}), B(x_{1}\textbackslash y_{2})$

+m = steigend
-m = fallend

## Beispiel 1

Eine Gerade verläuft durch die Punkte P(2/3) und Q(1/1).

Ermittle die Funktionsgleichung

$f(x)$

## Beispiel 2
$f(x)=2x$

$f(1)=2*1=3$

$f(2)=2*2=4$

$f(0)=2*0=0$

```functionplot
---
title: f(x)= ax + m
xLabel: X
yLabel: Y
bounds: [-10,10,-10,10]
disableZoom: true
grid: false
---
f(x) = 6x + 0
g(x) = 2x + 4
```

# Quadratische Funktion

```functionplot
---
title: Quadratische Funktion
xLabel: 
yLabel: 
bounds: [-10,10,-10,10]
disableZoom: true
grid: false
---
f(x)=x^2
```

## Quadratische Ergänzung
### Scheitelpunktform

### Normalform
(s. Matheretter)

# Kubische Funktion
```functionplot
---
title: Kubische Funktion
xLabel: x
yLabel: x
bounds: [-10,10,-10,10]
disableZoom: true
grid: false
---
f(x)=x^3
```
$$
f(x)=x^{3}
$$


# Definitionsbereich
----
Der Definitionsbereich definiert den Bereich auf dem Zahlenstrahl der X-Achse, die wir in einer Funktion (f(x)) einsetzen können. 

---

## Berechnen eines Definitionsbereichs
### Beispiel
Siehe: [[5.Vorlesung (03.11.2022)]] (Irgendwo unten)
$f(x):=x-\sqrt{ x^{2}+3x }$
$x^{2}+3x\geq 0$
$\leftrightarrow x(x+3)\geq 0|$Einer der Produkte ist = 0
$\leftrightarrow (x\geq 0 \land x+3\geq 0) \lor (\leftrightarrow x\leq 0 \land x+3 \leq 0)$
$\leftrightarrow (x\geq 0) \lor (x\leq -3)$
$x \in (-\infty,-3 ]\cup[0,\infty \to \mathbb{R})$
$f: (-\infty, -3] \cup [0, \infty)\to \mathbb{R}$


# Wertebereich
----
Der Wertebereich denkt den Bereich, die von der Funktion f(x) abgedeckt werden auf der Y-Achse.

---



# Achsensymmetrie und Punktsymmetrie (Gerade und ungerade Funktionen)

## Achsensymmetrie
----
Man spricht von einer Achsensymmetrie, wenn der Verlauf auf der negativen und positiven Seite der Y-Achse (Deshalb Achsensymmetrie) gleich sind.

---



```functionplot
---
title: Achsensymmetrie
xLabel: 
yLabel: 
bounds: [-10,10,-10,10]
disableZoom: true
grid: false
---
f(x)=x^2
g(x)=x^2 - x^8 + x^4 + 3
```
$f(x)=f(-x)$

## Punktsymmetrie
----
Man spricht von einer Punktsymmetrie, wenn der Verlauf der negativen und positiven Seite der X-Achse gleich ist.

---
```functionplot
---
title: Punktsymmetrie
xLabel: 
yLabel: 
bounds: [-10,10,-10,10]
disableZoom: true
grid: false
---
f(x)=x^3
g(x)=x^3 - x^7 + x^5
```
$-f(x)=f(-x)$

## Tipp
Hat die Funktion nur gerade Potenzen, ist sie gerade und umgekehrt.

# Beispiele

## Beispiel 1
$f(x) = 4x^6+3x^2+5x^0$ |x umwandeln in (-)
$f(-x) = 4(-x)^6 + 3(-x)^2 + 5(-x)$
$=4x^{6}+3x+5$
$=f(x)$

## Beispiel 2
$f(x)=5^{7}+4x^{3}+x$

$f(-x)=5(-x)^{7}+4(-x)^{3}+(-x)$
$=-(5x^{7}-4x^{3}-x)$
$=-(5x^{7}+4x^{3}+x)$
$=-f(x)$

## Beispiel 3
$f(x)=\frac{8x^{5}+2x^{3}}{x^{2}+1}$

<mark style="background: #ABF7F7A6;">Probieren</mark> $-f(x)=f(-x)$
$f(x)=\frac{8(-x)^{5}-2x^{3}}{x^{2+1}}$
$=\frac{-8x^{5}-2x^{3}}{x^{2}+1}$
$=-\frac{(8x^{5}-2x^{3})}{x^{2}+1}$
$=f(x)$

## Beispiel 4
$f(x)=\sin(x)$          $-f(x)=f(-x)$

$f(-x)=\sin(-x)$
$=-\sin(x)$
$=-f(x)$

Ergebnis: ungerade

## Beispiel 5
$f(x)=e^{x}$

$f(-x)=e^{-x}$
$-f(x)=-e^{x}$

Ergebnis: Weder gerade noch ungerade

![[Pasted image 20221027110447.png]]



# Ganzrationale Funktion und Gebrochene Funktion
## Ganzrational Funktion


## Gebrochene Funktion


# Abbildungen
## Abbildung
----
Eine Abbildung ist eine Funktion zweier Mengen, A und B. 
Bei f von A nach B werden alle Elemente aus A ($a \in A$) genau ein Element aus B ($b \in B$) zugeordnet.
Schreibweise: ($f:A\to B,a|\to f(a)$).

---
### Definition aus Vorlesung
![[Pasted image 20221103223147.png]]

### Beispiel aus Vorlesung
![[Pasted image 20221103223206.png]]

## Bild, Urbild
----


---

### Beispiel
```functionplot
---
title: Urbild
xLabel: X
yLabel: Y
bounds: [-10,10,-10,10]
disableZoom: true
grid: false
---
f(x)=x^2-1
```

### Definition aus Vorlesung
![[Pasted image 20221103230202.png]]

## Umkehrfunktion
Quelle: https://studyflix.de/mathematik/umkehrfunktion-1885


# Stetigkeit  

## Rechtsseitiger und linksseitiger Grenzwert


## Stetigkeit mit Folgen

### Zwischenwertsatz

# Grenzwerte



## In endlichen Mengen


## Beweisen
# Komposition von Abbildungen

# Umkehrabbildung

