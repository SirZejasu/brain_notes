#Medieninformatik 
#LDS 
#Thema   

---
# Quellen
- [[_Medieninformatik/Vorherige Semester/1. Semester/LDS/Themen/Aussagenlogik/Anhänge/LDS-V-Mitschrieb-Klassenkalkül.pdf|Klassenkalkül-Mitschrieb]]
- s. Seite 130 [[LDS Skript.pdf]]

# Definition
> [!question] Klassenkalkül
> Formalisierung einer (Wort-)Aussage durch logische Operatoren. Für die Liste von logischen Operatoren und dessen Definitionen siehe [[_Allgemein - Aussagenlogik]].

> [!example] Beispiel
> Ein Beispiel eines Klassenkalkülausdrucks aus dem Lernsystem. Hier wird "Wenn... dann.." mit $\to$ ersetzt und "oder" mit "$\lor$"
> ![[Pasted image 20221227151320.png]]
 
# Mengenalgebra
> [!Info] Trivia
> Die Klauseln in den sogenannten Prämissen sind Mengen. Die Logische Schlussfolgerung nennt man "Konklusion".

## Beispiele
> [!example] Beispiel 1 Harmloser Ausdruck
> ![[Pasted image 20221214121942.png]]
> 
>#### Venn-Diagramm
![[Klassenkalkül 2022-12-14 12.20.52.excalidraw]]
K = "Katzen"
H = "Hunde"
F = "Geflügelte Objekte"
>
>Somit gilt folgendes: Wenn $K \subseteq F$ und $H \subseteq K$, dann $H \subseteq F$ oder auch ausgedrückt, wenn $\forall k \in K$ auch $k \in F$, dann ist $H \in F$. Soll also heißen, wenn alle "Katzen" in "Katzen" auch in der Menge "Flügel" sind, dann sind somit "Hunde", die auch "Katzen" sind, geflügelt.
>
>Klassenkalkül: $((K \subseteq F) \land (H \subseteq K)) \to (H \subseteq F)$
>Aussagenlogik: $((K \to F) \land (H \to K)) \to (H \to F$)


> [!example] Beispiel 2: Nicht-Harmloser Ausdruck
> (AvB)

## Übersetzungstabelle
Klassenkalkül | Aussagenlogik
--- | ---
$A = B$| $A \leftrightarrow B$
$A \subseteq B$ | $A \to B$
$\cup$ | $\lor$
$\cap$ | $\land$

> [!example] Beispiel
> Vollständige Vorgehensweise.
> 1. Ausdruck in Klassenkalkül umzuwandeln
> 2. Einfaches KNF
> 3. Harmlos
> 4. Aussagenlogik
> 5. Warheitstabelle, (-1) gültig?
> ![[Klassenkalkül.pdf]]
# Vorlesung
### Beispiel 1
![[Pasted image 20221206094806.png]]

### Beispiel 2
![[Pasted image 20221206094901.png]]

### Beispiel 3
![[Pasted image 20221206094929.png]]
