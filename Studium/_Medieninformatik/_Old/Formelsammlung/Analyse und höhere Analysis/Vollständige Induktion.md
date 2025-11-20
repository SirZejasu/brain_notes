#Medieninformatik 
#Formelsammlung 

---
Quelle: [[GMI Vorlesungsskript 13.10.2022.pdf]]

 <mark style="background: #FF5582A6;">!UNVOLLSTÄNDIG!</mark>

# Beweistechnik "Vollständige Induktion"

---
Die natürlichen Zahlen können durch die im Dokument der Vorlesung genannten Axiome charakterisiert werden.
Axiome in der Mathematik sind Grundannahmen, die vorher schon überlegt wurden und grundsätzlich immer gültig sind, weswegen sie nie bewiesen werden müssen.
Die Axiome der natürlichen Zahlen helfen bei der vollständigen Induktion.

---

> [!hint] Hinweis zur Summen- und Produktformel
> $\sum_{k=1}^n k = \frac{n(n+1)}{2}$
> $\sum_{k=1}^n x = n*x$
> $\prod_{k=1}^n k = n!$
> $$\prod_{k=1}^n x = x^n$


Aussage: 
Für alle n>= 1 gilt: $\sum_{i=1}^{n}{i}=\frac{n(n+1)}{2}$

## Induktionsanfang
> [!question] Induktionsanfang
> Die unterste Grenze von n. Hier wird bewiesen, ob die Aussage für das erste Element in N gilt. 

### Beispiel
> [!example] Beispiel 1
> 
$n=1$ (Wir setzen die kleinste natürliche Zahl im Intervall der Behauptung in die Aussage ein ein)
>
$\sum_{i=1}^{1}{i}=1$ 
>
$\frac{1(1+1)}{2}=\frac{2}{2}=1$
>
Somit ist $\sum_{i=1}^{n}i=\frac{n(n+1)}{2}$



## Induktionsvoraussetzung
> [!question] Induktionsvoraussetzung
> Nach dem Induktionsanfang wird die Aussage als Beweis nochmals notiert.
> "Für ein beliebiges aber festen ... gilt ..."

### Beispiele
> [!example] Beispiel 1
> Für ein beliebiges aber festen $n \in \mathbb{N}$ gilt
$\sum_{i=1}^{n}{i}=\frac{n(n+1)}{2}$

## Induktionsschritt
> [!question] Indukstionsschritt
>  In diesem Schritt wird bewiesen, dass die Aussage auch für andere Werte stimmt. Wenn die Aussage von n (A(n)) gilt, gilt auch n+1 (A(n+1)).
Wenn die Aussage für den Nachfolger bewiesen wurde, ist auch die Aussage bewiesen.

### Beispiele
> [!example] Beispiel 1
> 
$n\to n+1$
$\sum_{i=1}^{n+1}{i}=\frac{(n+1)((n+1)(n+1))}{2}$
>
$\sum_{i=1}^{n+1}i=\sum_{i=1}^{n}{i}+(n+1)$
>
Wir wissen: $\sum_{k=1}^{n}{k} =\frac{n(n+1)}{2}$. Dies wurde durch die Induktionsvoraussetzung bewiesen (und gilt auch allgemein).
>
$\leftrightarrow \frac{n*(n+1)}{2}+(n+1)$
$\leftrightarrow\frac{n(n+1)}{2}+\frac{2(n+1)}{2}$
$\leftrightarrow \frac{n(n+1+2(n+1))}{2}$
$\leftrightarrow \frac{(n+1)(n+2)}{2}$

# Vorlesung
![[Pasted image 20221105211038.png]]
![[Pasted image 20221105211059.png]]
![[Pasted image 20221105211126.png]]
![[Pasted image 20221105211201.png]]

## Notizen
$(n+1)! = (n+1)*n!$
![[Pasted image 20221029221334.png]]
