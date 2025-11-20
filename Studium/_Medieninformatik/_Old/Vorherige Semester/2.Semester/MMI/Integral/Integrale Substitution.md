#Formelsammlung 
#Medieninformatik 

---
# Quellen
- s. Vorlesung
- [MathePeter](https://www.youtube.com/watch?v=rKGlE4av4-c&ab_channel=MathePeter)

# Integrale Substitution
> [!question] ~
> Die Substitution wird dazu verwendet, um ein Integral zu vereinfachen.
> Sie sieht folgendermaßen aus:
> ![[Pasted image 20230422213915.png]]
> Sie lässt sich mit der Kettenregel und dem [[Stammfunktion und Hauptsatz der Integralrechnung]] nachvollziehen. (Irgendwie)

# Anwendung und Beispiel

> [!example] Beispiel
> Löse das Integral:  $\int_{0}^{2} x^{2}\cos(x^{3}+1) dx$
> ## Schritt 1 Finde den passenden Term.
>
> <mark style="background:  #ABF7F7A6;">Formel:</mark> $\int_{a}^{b} f(g(x))*g'(x)dx=\int_{g(a)}^{g(b)} f(t)dt$
> Finde einen passenden Term mit x, sodass dessen Ableitung andere Terme in der Funktion auflöst. (Macht mehr Sinn mit der Übung).
> 
> - Setze $t(x)$ auf diesen Term. In diesem Beispiel nehmen wir $x^{3}+1$
> 
> $t(x)=x^{3}+1$
> 
> ## Schritt 2 Leite $t(x)$ ab und Wende eine tolle Formel an.
><mark style="background: #ABF7F7A6;">Formel:</mark> $t'(x)=\frac{dt}{dx}$
>
>  Ableitung: $3x^{2}$
> - Setze $t'(x)$ gleich mit $dt$ durch $dx$.
> 
>  $3x^{2}=\frac{dt}{dx}$
> 
> - Löse nach dx.
> 
> $\frac{1}{3x^{2}}*dt = dx$
> 
> ## Schritt 3 Ersetze. 
> <mark style="background: #ABF7F7A6;">Formel:</mark> $\int_{a}^{b} f(g(x))*g'(x)dx=\int_{g(a)}^{g(b)} f(t)dt$
> Die Ober- und Untergrenze des Integrals werden verschoben.
> 
> $\int_{0^{3}+1}^{2^{3}+1} x^{2}*\cos(t)* \frac{1}{3x^{2}} dt = \frac{1}{3} \int_{1}^{9} \cos(t) dt$
> 
>
> - Die x kürzt sich weg
> - Wenn man die 3 aus dem Bruch nimmt, entsteht $\frac{1}{3}$. 
> - Wenn es sich sich um ein unbegrenztes Integral handelt wird eine unbekannte Konstante hinzugefügt ($. . . +c$).
>   
>   ## Schritt 4 Berechne mit dem [[Stammfunktion und Hauptsatz der Integralrechnung|Hauptsatz]]
>   $\frac{1}{3}[\sin(t)]_{1}^{9}=\frac{1}{3}(\sin(9)-\sin(1))=\sin(9)-\frac{\sin(1)}{3}$
>   


# Tabelle für typische Stammfunktionen
| f(x)                    | F(x)                     |
| ----------------------- | ------------------------ |
| $x^n$ ($\neq -1$)       | $\frac{1}{n+1}*x^{n+1}$  |
| $x^{-1}=\frac{1}{x}$    | ![[lnx.png]]             |
| $e^{x}$                 | $e^{x}$                  |
| $a^{x}$                 | $\frac{1}{\ln(a)}*a^{x}$ |
| $\sin(x)$               | $-\cos(x)$               |
| $\cos(x)$               | $\sin(x)$                |
| $\frac{1}{\cos^{2}(x)}$ | $tan(x)$                   |
| $\frac{1}{1+x^{2}}$     | $arctan(x)$                | 


# Altes Beispiel

> [!example] Beispiel
> Löse das Integral: $\int x*e^{x^{2}} dx$
> 
> ## Schritt 1 Finde den passenden Term.
> $\int f(g(x))*g'(x)dx=\int f(z)dz$
> Finde einen passenden Term mit x, sodass dessen Ableitung andere Terme in der Funktion auflöst. (Macht mehr Sinn mit der Übung).
> 
> - Setze z auf diesen Term. In diesem Beispiel ist es dies die Exponente von $e$.
> 
> $z=x^{2}$
> 
> ## Schritt 2 Wende eine tolle Formel an.
> $dx=\frac{dz}{z'}$
> - Setze $dx$ gleich mit $dz$ durch die Ableitung von $z$
> - In diesem Beispiel: $\frac{dz}{2x}$
> 
> ## Schritt 3 Ersetze $dx$ mit der neuen Berechnung.
> Und ersetze den ausgesuchten Term mit z. 
> $\int x*e^{z} \frac{dz}{2x}$
> - Die x kürzt sich weg
> - Wenn man die 2 aus dem Bruch nimmt, entsteht $\frac{1}{2}$.  Somit entsteht folgende Berechnung: $\frac{1}{2} \int e^{z} dz$
> - Da es sich in diesem Beispiel sich um ein unbegrenztes Integral handelt wird eine unbekannte Konstante hinzugefügt. Somit kommen letzendlich zum folgenden Ergebnis:
>   $\frac{1}{2} \int e^{z} dz + c$



# Vorlesung
![[Substitution1.png|left|330]] ![[Substitution2.png|right|340]]


