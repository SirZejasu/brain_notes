
#Medieninformatik 

---
# Quellen
- Studyflix
- [Grenzwert mit Ln](https://www.youtube.com/watch?v=pfXzUNE76Sc&t=256s&ab_channel=MathemaTrick)

# Divergieren und Konvergieren
> [!question] 
> Ob eine Folge Konvergiert oder Divergiert hängt vom Wert des Grenzwerts ab.
> Nährt sich die Folge einen bestimmten Grenzwert, ist sie konvergent. Wenn kein Grenzwert existiert, ist sie divergent.
> 


# Grenzwerte bestimmen von Funktionen
> [!question] Grenzwert
> Der Grenzwert ist der Wert an der sich eine Folge beliebig oft nährt.
> $\lim_{ x \to \infty^+ }$ bedeutet, dass man den x Wert gegen unendlich laufen lässt. Also gibt man unendlich viele Werte für x ein. Das Ergebnis ist ein Grenzwert, an dem diese Werte angrenzen (divergieren).
![[Pasted image 20230214161052.png]]
> ![[Pasted image 20230214161620.png]]

> [!hint] Regeln
> Ein Grenzwert ist entweder 
> - eine Relle Zahl ($\mathbb{R}$)
> - $+ \infty$
> - $- \infty$
> - nicht existent


```functionplot
---
title: d
xLabel: 
yLabel: 
bounds: [-10,10,-10,10]
disableZoom: false
grid: true
---
f(x) = 2/x
```

## Beispiel-Graph
```functionplot
---
title: Grenzwert 0 der Funktion 1/x
xLabel: 
yLabel: 
bounds: [-10,10,-10,10]
disableZoom: true
grid: false
---
f(x) = 1/x
```

> [!example] Vorgehensweise
> Schritt 1
> Man betrachtet den Ausdruck. Man sucht nach der höchsten Potenz.
> ![[Pasted image 20230212164653.png]]
> 
> Schritt 2
> Klammer die höchste Potenz aus und ggf. kürze diese.
> ![[Pasted image 20230212165110.png]]
> 
> Schritt 3
> Im Idealfall können wir jetzt die einzelnen Brüche im Ausdruck betrachten und sehen sofort, wie die Folge verläuft. 
> ![[Pasted image 20230212165219.png]]
> 
> Schritt 4
> Da es in diesem Beispiel nach 0 verläuft, kann man diese Wert mit 0 ersetzen
> ![[Pasted image 20230212165337.png]]
> 
> Schritt 5
> Normales kürzen
> ![[Pasted image 20230212165352.png]]
> 
> Hier nochmal die komplette Rechnung
> ![[Pasted image 20230212165404.png]]

> [!hint] Hinweis für besondere Vorgehensweisen.
> - [[L'Hospital]]

> [!hint] Hinweis zum kürzeren Rechenweg.
> Theoretisch ist es möglich, den Wert schneller herauszufinden. Aber da es eine Klausur ist, ist Effizienz nicht gefragt.
> Wenn man nur die höchste Potenz betrachtet, können alle niedrigere weggelassen werden.
> ![[Pasted image 20230212164948.png]] 
> Daraufhin wird normal gekürzt, wie man es aus der Schule kennt.
> ![[Pasted image 20230212164852.png]]

> [!hint] Berechnen von Wurzeln
> ![[Pasted image 20230314160824.png]]



## Polstelle

### Beidseitiger Grenzwert


```functionplot
---
title: d
xLabel: 
yLabel: 
bounds: [-10,10,-10,10]
disableZoom: true
grid: true

---
f(x)= (x^7+x^4-4x^3-4)/((x^2+4)(x^3+1))
```



# Grenzwerte bestimmen von Folgen

# Schmierzeug
