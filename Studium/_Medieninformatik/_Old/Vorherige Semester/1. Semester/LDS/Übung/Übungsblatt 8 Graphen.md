#Übung 
#LDS 
#Medieninformatik  

---
# Aufgabenblatt
- [[LDS-ublatt8.pdf]]

# Lösung
- [[Übungsblatt 8 LDS .pdf|Lösung von Julia]]
- 

# Aufgabe 32
- <mark style="background: #ABF7F7A6;">Zeichnen Sie den vollständigen Graphen K4 und den vollständigen bipartiten Graphen K2,4.</mark>
	 ![[Übungsblatt 8 Graphen 2022-12-20 20.21.17.excalidraw|300]]

- Der Graph $K_{2,4}$ ist planar, denn es lässt sich nicht auf $K_{3,3}$ kürzen, allerdings finde ich keinen Weg.
![[Übungsblatt 8 Graphen 2022-12-20 20.50.25.excalidraw|300]]

- <mark style="background: #ABF7F7A6;">Ist der Graph K2,4 eulersch? Wenn ja: zeichnen Sie den Graphen und nummerieren Sie die Kante fortlaufend, beginnend mit 1, so, dass die Reihenfolge des Kantenbesuchs einer Eulertour erkennbar wird.</mark>
	 ![[Übungsblatt 8 Graphen 2022-12-20 21.15.44.excalidraw|300]]
- <mark style="background: #ABF7F7A6;">Ist der Petersen-Graph aus der Vorlesung planar?</mark>
	 Der Peterson Graph enthält einen $K_{5}$ als Teil-Graph, also nein.
	 
- <mark style="background: #ABF7F7A6;">Ist der Petersen-Graph aus der Vorlesung eulersch? Wenn ja, geben sie wie oben eine Eulertour an.</mark>
	Es ist nicht eulersch, da es mindestens einen Knoten mit einem ungeraden Grad enthält.
	![[Übungsblatt 8 Graphen 2022-12-20 21.21.57.excalidraw]]
- <mark style="background: #ABF7F7A6;">Ist der Petersen-Graph aus der Vorlesung bipartit? Wenn ja, geben Sie eine entsprechend Färbung an (z.B. durch ausgefüllte, nicht ausgefüllte Knoten).</mark>
	Nein, da es mindestens einen Cycle gibt mit ungerader Anzahl an Kanten.

- <mark style="background: #ABF7F7A6;">Zeichnen Sie den folgenden Graphen: Es gibt die Knoten A,B,C,D,E und die Kanten (mit Gewicht) AB/2, AC/8, AD/4, AE/6, BC/7, BD/3, BE/6, CD/9, CE/8, DE/5.</mark>
	![[Übungsblatt 8 Graphen 2022-12-20 21.30.12.excalidraw]]

- <mark style="background: #ABF7F7A6;"> Finden sie im zuletzt gezeichneten Graphen eine minimale Rundtour (also einen Hamilton-Kreis minimalen Gewichts), mit anderen Worten: lösen sie das Travelling Salesman Problem. Geben Sie hierzu die Rundtour als Knotenfolge an, beginnen Sie mit A. Geben Sie auch die Gewichtssumme an.</mark>
	![[_Medieninformatik/Vorherige Semester/1. Semester/LDS/Übung/Anhänge/index-1.jpg]]
	A -> B -> D -> E -> C -> A Summe 26

- <mark style="background: #ABF7F7A6;">Zeichnen Sie OHNE KREUZENDE KANTEN den Graphen mit den Knoten A,B,C,D,E,F und den Kanten und Gewichten AB/3, BC/5, CD/5, DE/9, EF/6, FA/4, FB/8, FC/14, EC/10.</mark>
- ![[Übungsblatt 8 Graphen 2022-12-21 00.18.13.excalidraw]]
- <mark style="background: #ABF7F7A6;">Lösen sie das Chinese Postman-Problem in diesem Graphen optimal (Hinweis: suchen sie zuerst nach einer Eulerschen Tour in diesem semi-eulerschen Graphen und dann nach einem kürzesten Weg zur Verbindung der beiden Endpunkte des Eulerschen Weges). Geben Sie die Lösung an (s. TSP-Problem oben).</mark>
![[Übungsblatt 8 Graphen 2022-12-21 15.33.12.excalidraw]]
Eulersch Tour: B - C - D - E - C  - F - B - A - F - E $\to 64$
Rückweg: E - F - A - B $\to 13$
Gesamtwert: 64 + 13 = <mark style="background: #BBFABBA6;">77</mark>

- <mark style="background: #ABF7F7A6;">Zeichnen Sie (wieder ohne kreuzende Kanten!) den Graphen mit den Knoten A,B,C,D,E und den Kanten AB/4, BC/5, AC/1, BD/1, DC/4, DE/1, AE/1, AD/3.</mark>
	![[Übungsblatt 8 Graphen 2022-12-22 20.29.50.excalidraw]]


- <mark style="background: #ABF7F7A6;">Finden Sie eine optimale Lösung des Chinese Postman-Problems in diesem Graphen. Geben Sie die Lösung an (s. oben).</mark>
	C - D - E - A - D - B - C - A - B $\to$ <mark style="background: #BBFABBA6;">20</mark>
	Kürzester Rückweg
		B - D - E - A - C $\to$ 4
		20 + 4 = <mark style="background: #BBFABBA6;">24</mark>

- <mark style="background: #ABF7F7A6;">Finden Sie den Hamiltonischen Cycle mit dem größten(!) Gewicht in diesem Graphen. Geben Sie die Lösung an (s. oben: Knotenfolge, beginnend in A, Gesamtgewicht).</mark>
	A - B - C - D - A $\to$ 16
	A - D - B - C - D - A $\to$ 16
	A - D - C - B - A $\to$  16
	A - C - B - D - A $\to$ 10
		Größter Pfad: A - B - C - D - A $\to$ 16
		
	