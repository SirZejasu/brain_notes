 #Thema 
#LDS 
#Medieninformatik   

---
# Quellen
- [[Naives Baye, Klassifikation.pdf]]

# Definition
> [!question] Definition
> Hier kommt die Definition hin.

# Bedingte Warheitstabellen
$P(X|Y)=\frac{P(X\land Y)}{P(Y)}$
(Schnupfen/Krank Beispiel)
$P(Schnupfen|Krank) = \frac{\frac{3}{8}}{\frac{3}{8}}=1$ 
$P(Krank|Schnupfen)=\frac{\frac{3}{8}}{\frac{4}{8}}=\frac{\frac{3}{8}}{\frac{1}{2}}=\frac{3}{4}$

## Likelihoods
> [!question] Lekelihood
> Gegeben sei eine Menge. Wie hoch ist die Wahrscheinlichkeit, ein bestimmtes Element $e$aus einer Menge $h_{1}$ zu ziehen? Es wird mindestens eine Hypothese aufgestellt. Formel: p(e I $h_{x}$) 

### Beispiele
#### Beispiel 1
![[Pasted image 20221213113254.png]]
![[Pasted image 20221213113320.png]]

## A-Priori-Chance
Definition | 
--- | 
Man bezieht sich auf ein Wahrscheinlichkeitswert anhand von allgemeinen Vorwissen bzw. Grundannahmen eines Systems. Es berechnet sich genauso wie Likelihoods. In der Klausur wird es eine genaue Angabe geben, mit dem wir dann berechnet können. |

### Beispiele
#### Beispiel 1
![[Pasted image 20221213113634.png]]


## Der Satz von Bayes
> [!question] Definition
> Mit den Satz von Bayes wollen wir letzendlich herausfinden, wie hoch die Wahrscheinlichkeiten sind von den jeweiligen Fächern zu ziehen.
Der allgemeine Wahrscheinlichkeitswert unserer Hypothese. 
Formeln:
$p(h_{x}|E)  =\frac{p(h_{x})*p(E|h_{x})}{p(E)}=\frac{p(h_{x})*\prod_{e\in E}p(e|h_{x})}{p(E)}$ (Satz von Bayes)
$p(E) = p(h_{1})*\prod_{e\in E}p(e|h_{1})+ \dots +p(h_{n})*\prod_{e\in E}p(e|h_{n})$

### Beispiele
> [!example] Beispiel 1
> Es werden in beiden Fächern die A-Priori-Chance mit den in den Fächern enthaltenen Häufigkeit Multipliziert.
>
> ![[Pasted image 20221213112449.png]]
>  $p(E)$ ergibt sich aus der Addition beider Werte. 
![[Pasted image 20221213115040.png]]
 
# Aus Übung
![[Pasted image 20230113001202.png]]