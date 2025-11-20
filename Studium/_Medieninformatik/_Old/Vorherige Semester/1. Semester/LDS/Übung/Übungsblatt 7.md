
#Übung 
#LDS 
#Medieninformatik  

---
# Aufgabenblatt
[[LDS-ublatt7.pdf]]

# Lösung
[[LDS-decision-tree-hinweise.pdf]]

Height? $\to$ Attractive?
Small $\to$ 2 NO, 1 YES 
Tall $\to$ 3 NO, 2 YES

Hair $\to$ Attractive?
Blonde $\to$ 3 YES, 2 NO
Dark $\to$ 3 NO, 0 YES
Red $\to$ 0 NO, 1 YES

Eyes $\to$ Attractive?
Brown $\to$ 3 NO, 0 YES
Blue $\to$ 3 YES, 2 NO

![[Übungblatt 7 2022-12-23 17.32.27.excalidraw]]

# Aufgabe 30
<mark style="background: #ABF7F7A6;">Wieviele mögliche Kombinationen bereits gesehener Attributwerte gibt es? (mit anderen Worten: wie groß ist das Kreuzprodukt Height × Hair × Eyes, wenn sie davon ausgehen, dass sie bereits alle ymöglichen Werte der einzelnen Attribute gesehen haben – sonst könnten sie die Größe ja auch gar nicht angeben!)</mark>
Spalte | Anzahl der **unabhängigen** Attribute in Spalte | Attribute
--- | --- | ---
Height | 2 | Small, Tall
Hair | 3 | Blonde, Dark, Red
Eyes | 2 | Brown, Blue
$Kombination = 2*3*2 = 12$

<mark style="background: #ABF7F7A6;">Welchen Wert für die abhängige Variable gibt ihr Baum für die Kombination (Height:Tall, Hair:Red, Eyes:Blue) an?</mark>
ATTRACTIVE

<mark style="background: #ABF7F7A6;">Welchen Wert sagt er für (Height:Small, Hair:Dark, Eyes:Brown) voraus?</mark>
NOT ATTRACTIVE


<mark style="background: #ABF7F7A6;">Welchen Wert sagt er für (Height:Tall, Hair:Red, Eyes:Brown) voraus?</mark>
ATTRACTIVE

<mark style="background: #ABF7F7A6;">Zur Übung: Geben Sie einen zweiten Baum an und prüfen Sie dessen Antworten auf Punkt 2,3 und 4.</mark>
![[Übungblatt 7 2022-12-23 18.40.34.excalidraw]]

<mark style="background: #ABF7F7A6;">Welchen Wert für die abhängige Variable gibt ihr Baum für die Kombination (Height:Tall, Hair:Red, Eyes:Blue) an?</mark>
ATTRACTIVE

<mark style="background: #ABF7F7A6;">Welchen Wert sagt er für (Height:Small, Hair:Dark, Eyes:Brown) voraus?</mark>
NOT ATTRACTIVE

<mark style="background: #ABF7F7A6;">Welchen Wert sagt er für (Height:Tall, Hair:Red, Eyes:Brown) voraus?</mark>
NOT ATTRACTIVE
