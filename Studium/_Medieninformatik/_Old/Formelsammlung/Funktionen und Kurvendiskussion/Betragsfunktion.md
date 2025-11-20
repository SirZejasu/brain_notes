#Medieninformatik 
#Formelsammlung 

---

Quelle: [[GMI Vorlesungsskript 13.10.2022.pdf]]
# Betragsfunktion
> [!question] Betragfunktion
> Bei der Betragsfunktion in der Menge R (x in R) handelt es sich bei dem x-Wert im Betrag, der entweder eine negative oder positive Zahl ist.

## Beispiele
> [!example] Beispiel 1
> $$
f(x)=|x| \begin{cases}
x -für \to x\geq 0 \\
-x -für\to x<0
\end{cases}
$$

 ![[_Medieninformatik/1. Semester/GMI/Formelsammlung/_Anhänge/Betragsfunktion]]

> [!hint] Anmerkung
> Mit den Fällen wird überprüft, ob der Betrag positiv oder negativ ist.
Wenn im 1.Fall x>=0, ist sie gültig. Daraufhin wird der Betrag aufgelöst.
Wenn im 2.Fall x<0, ist sie gültig. Daraufhin wird der Betrag in Klammern mit einem "-"Symbol aufgelöst.

> [!example] Beispiel 2
># Aussage
|x| = 5
>
>## 1.Fall (positiv)
$x \geq 0$
>
>### Auflösen
$x = 5$ ($x\geq 0$)
Prüfen: $5\geq 0$ ?
Wenn ja, ist der Wert gültig.
>
> ### Lösungsmenge von 1.Fall
$\mathbb{L}_{1}=5$
>
>##2. Fall (negativ)
$x<0$
>
> ### Auflösen
$-x = 5|:(-1)$
$x=-5$ ($x<0$)
>
Prüfen: $-5<0$ ?
Wert gültig.
$x=-5$
>
> ### Lösungsmenge von 1.Fall
$\mathbb{L}_{2}=-5$
>
>## Lösungsmenge
$\mathbb{L}= \mathbb{L}_{2} \cup \mathbb{L}_{1} = \{-5,5\}$




### Beispiel 2
#### Aussage
|x|=-5

#### 1. Fall (positiv)
$x\geq 0$

##### Auflösen
$x=-5$

Prüfung: $-5 \geq 0$. Ungültig.

##### Lösungsmenge 1.Fall
$\mathbb{L}_{1}=\{\}$

#### 2.Fall (negativ)
$x\leq 0$

##### Auflösen
$-x=-5|:(-1)$
$x=5$
Prüfen: 5 ist nicht kleiner als 0. Ungültig

##### Lösungsmenge 2.Fall
$\mathbb{L}_{2}=\{\}$

#### Lösungsmenge
$\mathbb{L}=\mathbb{L}_{1}\cup \mathbb{L}_{2}=\{\}$

```
Für die Betragsfunktion ist der x-Wert relevant. Hat man die Werte beider Fälle, werden sie vereinigt. Bei einem Betrag wie |x+3| folgt vorher eine Äquivalenzumformung, sodass nur noch der x-Wert bleibt. 
```

### Weitere Beispiele aus der Vorlesung
#### Äquivalenzumformung
![[Pasted image 20221103130930.png]]

#### Betrag im Betrag
![[Pasted image 20221103131047.png]]
![[Pasted image 20221103131130.png]]
![[Pasted image 20221103131155.png]]

#### Mit Ungleichungen
![[Pasted image 20221103131443.png]]
![[Pasted image 20221103131504.png]]
![[Pasted image 20221103131521.png]]
![[Pasted image 20221103131537.png]]
