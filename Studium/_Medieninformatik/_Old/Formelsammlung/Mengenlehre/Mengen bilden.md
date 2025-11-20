#Formelsammlung 
#Medieninformatik 

---
# Quellen
- [Rechner zur Mengenbildung](https://rechneronline.de/mengenlehre/)

# Schnittmenge
Definition |
--- | 
Elemente aus A die auch in B enthalten sind bilden eine neue Schnittmenge. |

$A\cap B$ $\to$ Elemente aus A sind auch in Menge B.

![[Schnittmenge.png|300x300]]

# Teilmenge
Definition |
--- | 
Alle Mengen von A sind in B enthalten |

$A\subset B \to$ A ist Teilmenge von B. 

![[Teilmenge.png|300x300]]


# Vereinigungsmenge
Definition |
--- | 
Elemente aus A und B vereinigen |

$A\cup B\to$ Elemente aus A und B vereinigen

![[Vereinigungsmenge.png|300x300]]

# Differenzmenge
Definition | Formel
--- | ---
Alle in A enthaltene Mengen, die **auch** in B enthalten sind, werden ausgenommen.| $A \textbackslash B$ (oder in LDS $(A-B)$) := {xIx $\in A\not \in B$} 




# Definitionsmenge (Bruchgleichung)
Definition |
--- | 
Die Definitionsmenge sagt aus, wieviele (x) bei der Gleichung eingsetzt werden dürfen. |

$D=IR \textbackslash${$1,3$}

## Beispiele

### Beispiel 1
$\frac{3}{2x+1}=\frac{2}{2-x}$

```
x-Wert vom Nenner berechnen mit 0.
```

$2x+1=0 |-1$
$\leftrightarrow 2x= -1 |:2$
$\leftrightarrow x=\left( -\frac{1}{2} \right)$

$2-x=0|-2$
$\leftrightarrow-x=(-2)|:(-1)$
$\leftrightarrow x=2$

<mark style="background: #BBFABBA6;">Ergebnis</mark>: $D= \mathbb{R}\textbackslash${$-\frac{1}{2},2$}

$2-x=0|-2$
$\leftrightarrow -x=-2 |:(-1)$
$\leftrightarrow x=2$

### Beispiel 2

$\frac{1}{x}-\frac{x}{x^{2}-6x+9}=-\frac{5}{x^{2}-3x}$

$x=0$

$x^{2}-6x+9=0|$bin. Form
$\leftrightarrow (x-3)^{2}=0|\sqrt{ }$
$x-3=0|+3$

Ergebnis: $x=3$

ODER

$x^{2}-6x+9=0$|Pq-Formel
$x_{1|2}=-\frac{6}{2}\pm\sqrt{\left( \frac{6}{2} \right)^{2}-9}$
$=3\pm\sqrt{ (3)^{2}-9 }$
$=3\pm 0$
x = 3

$x^{2}-3x$|Ausklammern
$\leftrightarrow x(x-3)=0$|Aufteilen

x=0            x-3 = 0 |+3 $\to$ x = 3

$D=\mathbb{R\textbackslash}${0,3}

# Komplementärbildung
> [!question] Definition
> B enthält Menge A nicht. Elemente von A in B werden in B entfernt.

$A^{c}:=B \textbackslash A=${$x \in B|x \in B \land x \not \in A$}

![[Komplementärbildung|300x300]]


# Kreuzprodukt für "Mengen"

A x B ={$(a,b):a \in A,b \in B$}

# Familie von Mengen

$\cup_{i\in I} A;=$ {$x:x \in A;$ für ein $i \in I$}
$\cap_{i \in I}A;=${$x: x \in A;$ für alle $i \in I$}

## Beispiele

### Beispiel 1

$I=\{1,2,3\}$       $M_{1}=\{1\};M_{2}=\{5,7\};M_{3}=\{1,5\}$

![[Familie von Mengen.png]]

### Beispiel 2
$I=\mathbb{N}$   $N_{n}=\{n\}$

$\cup_{n \in I}N_{n}=\cup_{n=1}^{\infty}\{n\}=\{1\}\cup \{2\}\cup \{3\}\dots=\mathbb{N}$

$\cap_{n \in I} N_{n}=\cap_{n \in I}^{\infty}\{n\}=\{1\}\cap \{2\}\cap \{3\}\dots=\{\}$
