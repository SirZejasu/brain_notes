#Formelsammlung 
#Medieninformatik 

---
# Quelle
- [Youtube](https://www.youtube.com/watch?v=hQfUEl3k-jU&ab_channel=Matheretter)

# Ableitung (Grafisches Ableiten)
> [!question] Ableitung
> Die Ableitung ermöglicht es uns, die Steigung an jeden Punkt des Graphen zu lesen. Eine Ableitung ist möglich, wenn die Funktion differenzierbar ist.
Formel für Ableitungsfunktion:


## Tabelle für besondere Ableitungen
Denk an die Kettenregel!

| Funktion()            | Ableitung                            |
| --------------------- | ------------------------------------ |
| ln(x) / ln($x^{2}-1$) | $\frac{1}{x}$ / $\frac{2x}{x^{2}-1}$ |
| sin(x)                | cos(x)                               |
| cos(x)                | -sin(x)                              |
| tan(x)                | $\frac{1}{(cos(x))^2}$               |
| $\sqrt{x}$            | $\frac{1}{2\sqrt{ x }}$              |

![[Unbenannt-3.jpg]]
# Konstante
> [!question] Definition
> Ein Term ohne eine Ziffer. Bei der Ableitung bleibt sie weg bzw. wird zu 0

> [!example] Beispiele
> ![[Pasted image 20230224185122.png]]

# Potenzregel
> [!question] Potenzregel
> f(x) = $x^{n}$
f'(x) = $n*x^{n-1}$

> [!example] Beispiele
> ![[Pasted image 20230224185335.png]]

# Faktorregel
> [!question] Definition
> Der Faktor, der mit dem x multipliziert wird, bleibt beim Ableiten bestehen.
 
> [!example] Beispiele
> ![[Pasted image 20230224185724.png]]

# Summenregel
> [!question] Definition
> Die Funktion ist mit Plus oder Minus gebunden. Hier wird einfach jeder Teil mit den bereits bekannten Regeln abgeleitet.
 
> [!example] Beispiele
> ![[Pasted image 20230224190024.png]]


# Produktregel
> [!question] Definition
> Wird verwendet für Multiplikationsterme mit Variablen (also mit x).
> 
> $u'*v+u*v'$
 
> [!example] Beispiele
> ![[Ableitung 2023-02-24 19.00.50.excalidraw]]
> ![[Ableitung 2023-02-24 21.36.15.excalidraw]]


# Bruch (Quotientenregel)
> [!question] Definition
> Wird verwendet, wenn im Bruch sowohl im Nenner als auch Zähler ein x gibt.
> 
> $\frac{u'*v-u*v'}{v^{2}}$

> [!example] Beispiele
> ![[Ableitung 2023-02-24 19.15.35.excalidraw]]
> ![[Pasted image 20230212204942.png]]
> 
> 

## Ohne Quotientenregel
> [!question] Definition
> Für Brüche ohne X auf beiden Seiten.

> [!example] Beispiele
> Für x nur im Zähler
> ![[Pasted image 20230225171947.png]]
> 
> Für x nur im Nenner
> ![[Pasted image 20230225172517.png]]



# Kettenregel

> [!question] Kettenregel
> Die Kettenregel wird dazu verwendet, um eine verschachtelte Funktion innerhalb einer Klammer abzuleiten.
Dabei wird die innere Ableitung (u') mit der äußeren Ableitung (v') multipliziert.
Formel: 
$f(x)=b*(ax+m)^{n}$
$u=ax+m$
$v = u^n$
$f'(x)=v' * u'$

![[Pasted image 20230224192938.png]]

> [!example] Beispiele
> 
> ![[Ableitung 2023-02-24 19.31.39.excalidraw]]
> ![[Ableitung 2023-02-24 19.39.50.excalidraw]]

> [!hint] Hinweis
> Bei der Ableitung der e-Funktion handelt es sich um eine Besonderheit, wo e gleich bleibt (s. untere Tabelle.)
> Ist die Potenz allerdings verändert, sollte die [[Ableitung#Kettenregel|Kettenregel]] angewendet werden.

> [!example] Beispiele
> Auch hier bleibt die e-Funktion gleich mit dem Unterschied, dass hier $e^{3x}$ die äußere Ableitung ist und mit der inneren Ableitung Multipliziert wird ($f(x)=3x \to f'(x)=3$)
> ![[Pasted image 20230224212423.png]]





# Vorlesung
![[GMI Vorlesungsskript Teil 41024_9.jpg]]

> [!hint] Hinweis
> Die Ableitung von $f(x)=e^x$ bleibt gleich, da $1*e^x$. 


```functionplot
---
title: Ableitung von f(x)=x^2
xLabel: 
yLabel: 
bounds: [-10,10,-10,10]
disableZoom: true
grid: false
---
f(x)=x^2
f'(x)=2x
```

