#Übung 
#LDS 
#Medieninformatik  

---
# Aufgabenblatt
[[LDS-ublatt6.pdf|Übungsblatt]]

# Lösung
- [[LDS-Blatt6-Lösungshinweise-Klassenkalkül.pdf]]

# Aufgabe 28
In spezielle KNF bringen. Formel ist harmlos, da es horn ist.
1.
$\equiv (a \land \daleth b) \lor c \leftrightarrow (a\lor c) \land \daleth(a\land b)\land \daleth c)$

![[Warheitstabelle]]

2.
$\equiv (a \lor (b \land c)) \land ((b \lor c) \land\daleth a) \leftrightarrow ((b \land c) \land \daleth a)$
![[Übungsblatt 6 2022-12-25 20.50.53.excalidraw]]

3.
$(a \land b \leftrightarrow b \lor c) \to (c \to a) \land (b \to a)$
![[Übungsblatt 6 2022-12-26 13.40.57.excalidraw]]

4.
$(a \land \daleth b \land c \leftrightarrow 0) \lor (a\land \daleth b)\to c$
![[Übungsblatt 6 2022-12-26 14.20.39.excalidraw]]

5.
$(b\to a) \to ((a \land \daleth b) \land c \leftrightarrow 0) \lor ((a \land \daleth b)\to c )\lor (c \to (a\land \daleth b))$
![[Übungsblatt 6 2022-12-26 14.44.41.excalidraw]]
