#Thema 
#LDS 
#Medieninformatik   

---
# Quellen
- S. 3 [[graphprobleme-v103.pdf]]

# Definitionen
Bestandteile von Graphen | Definition
--- | ---
Knoten | Eng.: Vertices, gegeben als Menge V.
Kanten | Eng.: Edges, gegeben als Menge E. Kanten können auch Richtungen sein, dann sind es gerichtete Kanten.
Gewichte | Gewicht einer Kante![[Pasted image 20221219205446.png\|300]]
Multikanten	 | Ein Knoten mit mehreren verbundenen Kanten ![[Pasted image 20221219205613.png\|300]] 
Schleifen | Ein Knoten, das mit sich verbunden ist. ![[Pasted image 20221219205729.png\|300]]
Einfache Graphen | Ein Graphen mit maximal nur einer Kante zwischen zwei Knoten ohne Schleife.
Multigraphen | Ein Graphen, mit mehr als eine Kante zwischen den Knoten (Loops) ![[Pasted image 20221219205800.png\|300]]
Planarität | Planare Graphen können so gezeichnet werden, dass die Kanten sich nicht kreuzen. Graphen, die Teilstrukturen sind, sind nicht planar. Enthält ein Graph die Teilstruktur $K_{5}$ oder $K_{3,3}$, ist es nicht planar. (Schrumpverfahren).
Adjazent und Inzident | Adjazent sind benachbarte Kanten. Im Beispiel sind uv und vw adjazent. Inzident sind Kanten und Knoten, die in eineinander eingehen. Somit ist uv inzident zu u und v. ![[Pasted image 20221219221845.png\|300]]
Trail und Pfad | Ein Trail ist ein Kantenzug (Wanderung), wo keine Kanten wiederholt werden.  Ein Pfad ist ein Trail wo sich keine Knoten wiederholen. 
Geschlossener Pfad und Cycle | Geschlossene Pfade sind Graphen, wo End- und Startknoten gleich sind (Auch Knoten ohne Kanten sind geschlossene Pfade.) z.B v,w,v, u oder w, x, y, w. Ein Cycle ist ein geschlossener Pfad mit mindestens einer Kante. ![[Pasted image 20221219221448.png\|300]]

# Eigenschaften

- <mark style="background: #D2B3FFA6;">Beispiel 1</mark>
	$K_{5}$ steht für einen vollständigen Graphen mit 5 Knoten.
	![[Pasted image 20221219214246.png|300]]

- <mark style="background: #D2B3FFA6;">Beispiel 2</mark>
	$K_{3,3}$ steht für einen vollständigen bipartiten Graphen mit 6 Knoten. 3 Knoten sind jeweils miteinander verbunden.
	![[Pasted image 20221219214300.png|300]]

- <mark style="background: #BBFABBA6;">Teilgraph</mark>
	Ist ein Graph wie $K_{5}$ oder $K_{3,3}$ als Teilstruktur. 
	![[Pasted image 20221219214328.png|300]]
