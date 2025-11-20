#Thema 
#ADS
#Medieninformatik   

---
# Quellen
- [Floyd-Warshall-Algorithmus mit Java Beispiel](https://www.happycoders.eu/de/algorithmen/floyd-warshall-algorithmus-java/)
- [YouTube](https://www.youtube.com/watch?v=4OQeCuLYj-4)

# Definition
> [!question] ~
> Floyd-Warshall ist ein klassischer Algorithmus der Gruppe Dynamische Programme.
Sie wird dazu verwendet um den kürzesten Pfad in einem Graphen mit negativem Gewicht ausfindig zu machen.

# Vorgehen
> [!example] ELearn Conen
> Siehe als Referenz den Pseudocode als vages aber gutes Beispiel an.
> 
> Zu Beginn sind zwei leere Matrizen und ein Graph in Form von Verbindung und dessen Gewichten gegeben. Stell dir vor, die Matrizen haben neben ihren Feld eine Reihen-/ und Spaltennummerierung enstsprechend ihrer Koordination.
> ![[Pasted image 20230607210735.png]]
> ## Schritt 0 Initialisierung der ersten Matrizen.
> Felder in der Matrix "shortest" mit 0 füllen. 
> ![[Pasted image 20230607203814.png]]
> 
> Danach werden die Felder mit den Gewichten der Pfade gefüllt. Leere Felder mit Nicht-existierende Pfaden
> werden mit "inf / $\infty$" gefüllt.
> ![[Pasted image 20230607204329.png]]
> 
> Die andere Matrix "pred" wird in einer Reihe mit der Ziffer der Reihennummer der benachbarten Matrix aktualisiert. Befindet sich in der Reihe ein "inf" also unendlich, wird dementsprechend das gegenüberliegende Feld mit "-" aktualisiert. 
> Diese Matrix wird später relevant, wenn es bei der anderen zur Veränderungen kommt.
> ![[Pasted image 20230607204639.png]]
> 
> So sieht es dann aus:
> ![[Pasted image 20230607210452.png]]
> 
> ## Schritt 1 Update der Matrizen
> Stell dir vor, es gibt eine sogenannte "Scan-Tabelle" innerhalb der **vorherigen** "Shortest-Matrix".
> Dabei steht in diesem Fall die 0 in der "Mitte". Die Zahl in der Mitte bestimmt, ob die Zahlen in der Reihe oder Spalte verändert werden. Da es eine natürliche Zahl ist (x >= 0) bleiben die Werte unverändert. Im späteeren Verlauf wird gezeigt was passiert, wenn die Zahl negativ ist.
> ![[Pasted image 20230607205023.png]]
> 
> Da die Zahlen unverändert bleiben, können diese einfach übernommen werden.
> ![[Pasted image 20230607205356.png]]
> 
> Jetzt werden die Restlichen Felder mit der Summe der Spalte und der Reihe gefüllt, wenn diese eine Verbesserung sind, also kleiner als die aktuelle Zahl im Feld.
> Beispiel: [1][2] + [2][1] = -5 -> -5 + 0 = -5. Somit wird [2][2] = -5 initalisiert, da -5 > 0 wahr ist. Und das macht man so weiter.
> Befindet sich in der **Addierung** ein infinity, bleibt der Wert ebenfalls unverändert. 
> 
> In der "pred" Matrix müssen die Veränderungen wahrgenommen werden, in dem die Felder mit den Werten der "vorherigen" Matrix aus der Zeilennummer im letzten Parameter (also in dem Fall 1) aktualisiert werden. Blau sind die veränderten Werte, Pink sind die Werte, die initalisiert werden müssen (unten) mit den entsprechenden Werten (oben).
> ![[Pasted image 20230607211247.png]]
> 
> ## Schritt 2 "Scanfeld" wandert, alles andere wiederholt sich.
> Das "Scanfeld" wandert die Diagonale nach jeder Schleife weiter nach unten. 
>![[Pasted image 20230607213739.png]]
>
>Dieses Mal ist die Mittige Zahl negativ, weswegen ALLE Zahlen initalisiert werden müssen. Dabei werden sie mit der Mitte-Zahl Addiert. Dabei ist es in dem Fall egal, ob die Werte sich bessern. Sie werden im jeden Fall aktualisiert.
> Beispiel: [1][2] + [2][2] = -10. 
> ![[Pasted image 20230607212119.png]]
> 
> Es folgt das gleiche Prinzip wie vorher. Spalte + Reihe (Also der "alten" Werte), aktualisiere nur, wenn es besser ist.
> ![[Pasted image 20230607214012.png]]
> 
> # Schritt 4 Wiederhole.
> Wenn die Prinzipien der vorherigen Schritte verstanden wurde, muss nur noch wiederholt werden.
> ![[Pasted image 20230607214906.png]]
> ![[Pasted image 20230607214554.png]]
>
> Nochmal. Mitte Zahl ist negativ, somit werden Spalte und Reihe aktualisiert.
> ![[Pasted image 20230607214945.png]]
> ![[Pasted image 20230607215321.png]]

# Algorithmus als Code
> [!example] Pseudocode (From YouTube)
> ```java
>  // Numbers of fields in the matrix.
> let V = [number of vertices in graph]
>
>// Array of minimum distanced initialized to infinity (shortest).
> let dist = V x V
>
> // Initializing the diagonal of the first Matrix to 0.
> for each (vertex v)
> 	dist [v][v] <- 0
> 
> /*
> Initializing the first Matrix with the weights of the graph-edges.
> All empty fields, so path-connections that don't exist, will be initialized as infinity.
> */
> for each (edge (u,v))
> 	dist [u][v] <- weight(u,v)
> 	
> // From now on, the fields will initialized and updated with cheaper paths.
> for (k from 1 to V)
> 	for (i from 1 to V)
> 		for (j from 1 to V)
> 			if (dist[i][j] > dist [i][k] + dist [k][j])
> 			end if
>```


