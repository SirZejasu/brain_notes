#Medieninformatik 
#LDS 

---
# Lösung
[[LDS-ublatt2-hinweise.pdf]]

# Aufgabe 7

![[Pasted image 20221025105110.png]]

 1. Elementare Aussagen
- "Wein trinken" = W
- "Fleisch essen" = F
- "Schokopudding" = S

2. Zusammengesetzte Aussage formulieren
(1) $\daleth W \to F$ 
(2) $F_{1}W \to \daleth S$
(3) $S \lor \daleth F$

3.
(4) $((\daleth W \to F)\land ((F\land W)\to \daleth S))\land((S \land \daleth W) \to \daleth F )$


4.
![[Pasted image 20221025112011.png]]

5.
$(W \land \daleth F \land \daleth S) \lor (W \land \daleth F \land S) \lor (W \land F \land \daleth S)$

6. <mark style="background: #D2B3FFA6;">Kojunktive Normalform</mark>

<mark style="background: #BBFABBA6;">Ergebnis: "Ich trinke immer Wein und nie Fleisch zusammen mit Schokopudding"</mark>

# Aufgabe 8

![[Pasted image 20221025112421.png]]

1. Elementare Aussagen
- "Ritter" = R
- "Schurken" = S
- 

2. Zusammengetzte Aussagen formulieren
- $S \to FALSE$
- $R \to TRUE$

3.


<mark style="background: #BBFABBA6;">Prof. C lügt. 
Prof L. ist Schurke, Prof. E sollte mein Freund sein.</mark>


# Aufgabe 9

![[Pasted image 20221025114350.png]]

1. Elementare Aussagen
- "Blau" = B
- "Grün" = G
- "Ritter" = R
- "Räuber" = Ra

2. Zusammengesetzte Aussagen
- $TRUE \lor FALSE$

3.

ANTWORT | WAHRHEIT | Zauberer $BLAU \lor GRÜN$ |
--- | --- | ---
NEIN | NEIN | GRÜN
NEIN | JA | GRÜN
JA | NEIN | BLAU
JA | JA | BLAU

<mark style="background: #BBFABBA6;">Lösung:
Es könnten beide der Zauberer sein.</mark>
# Aufgabe 10

![[Pasted image 20221025121841.png]]


Kai <mark style="background: #FF5582A6;">behauptet</mark>, <mark style="background: #FF5582A6;">nicht</mark> die zu die Tat begangen zu haben.

KAI AUSSAGE 1 (KEIN RÄUBER)| KAI AUSSAGE 2 (RÄUBER) | WAHRHEIT (Ritter oder Schurke? | UNSCHULD
--- | --- | --- | ---
JA | NEIN |  JA | JA
JA | JA | NEIN | NEIN

Räuber können nur lügen. Als Räuber hätte Kai bei der ersten Frage mit NEIN beantwortet, wenn er behauptet hätte, nicht der Täter zu sein.
<mark style="background: #BBFABBA6;">Kai ist unschuldig.</mark>

# Aufgabe 11
![[Pasted image 20221025134512.png]]
1. GÜLTIG -> Da alle Diamanten hart sind, sind die "Einige Edelsteine" alle hart.
2. GÜLTIG -> Hunde sind Katzen, also haben sie Flügel.
3. GÜLTIG -> Flegeolets = Flipple-Flutes, somit Monauli auch Flipple-Flutes
4. UNGÜLTIG -> "sterblich" ist nur ein Zustand und assoziiert nicht beide Variablen.

![[Pasted image 20221025134550.png]]
5. GÜLTIG -> Voraussetzung nicht erfüllt (Barometer fällt nicht)
6. GÜLTIG -> Voraussetzung nicht erfüllt (Roman ist nicht bereit auszusagen)
7. UNGÜLTIG -> Es gilt nur für allgemein "einige nicht angepasste Person"
8. GÜLTIG -> Einige Philosophen  sind keine Mathematiker (und somit keine Logiker)

