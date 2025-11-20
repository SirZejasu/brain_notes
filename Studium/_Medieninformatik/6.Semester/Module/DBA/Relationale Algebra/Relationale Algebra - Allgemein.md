---
tags:
  - dba
  - datenbanken_
  - relationale_algebra
---
# Allgemein
> [!question] Was ist relationale Algebra?
    > Eine Algebra wird über einer Menge von Operanden und einer Operationsmenge definiert.
    > 
    > Die Operationen sind dabei abgeschlossen über die gegebenen Menge, das heißt die Anwendung eines Operators auf einem Element der Menge resultiert wieder in einem Element der Menge.
    > ![[Pasted image 20251003151034.png]]

> [!NOTE] Wsa ist relationale Algebra?
    > Relationale Algebra wird verwendet um SQL-Anfragen mathematisch zu formulieren
    > Es ist die Grundlage für Verifikation und Anfrageoptimierung
    > 

> [!example] Relationale Algebra
    > ![[Pasted image 20250922151333.png]]


# Mengen - Algebra
> [!NOTE] 
    > ![[Pasted image 20250923182305.png]]
    > ![[Pasted image 20250923182417.png]]

> [!example]
    > ![[Pasted image 20250923182452.png]]
    > 
    > ![[Pasted image 20250923182514.png]]

# Algebra Operationen
![[Pasted image 20250923203143.png]]

## Liste der Mengenoperation
Die Beispiele beziehen sich auf die Tabelle.
![[Pasted image 20250923202117.png]]

| Namen                                                    | Definition                                                                                                                                                                                                                                                                                                                                | Beispiel                                                                                                                     |
| -------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| ![[Pasted image 20251003152322.png]]Selektion            | ![[Pasted image 20250923201659.png]]<br><br>![[Pasted image 20250923201730.png]]                                                                                                                                                                                                                                                          | ![[Pasted image 20250923201712.png]]                                                                                         |
| ![[Pasted image 20251003152354.png]]Projektion           | ![[Pasted image 20250923201747.png]]<br><br>![[Pasted image 20250923201813.png]]                                                                                                                                                                                                                                                          | ![[Pasted image 20250923201758.png\|300]]                                                                                    |
| ![[Pasted image 20251003152401.png]]Umbenennung          | ![[Pasted image 20250923203043.png]]![[Pasted image 20250923203043.png]]                                                                                                                                                                                                                                                                  | ![[Pasted image 20250923203053.png]]                                                                                         |
| ![[Pasted image 20251003152408.png]]kartesisches Produkt | ![[Pasted image 20250923201948.png]]<br><br>$R_1$ und $R_2$ müssen dabei keine gemeinsamen Attribute haben.<br><br>Über die Eigenschaften des kartesische Produkts   assoziativ:<br>![[Pasted image 20250923203336.png]]<br><br>nicht kommutativ:<br>![[Pasted image 20250923203448.png]]<br><br>![[Pasted image 20250923203536.png]]<br> | ![[Pasted image 20250923203400.png]]<br><br>![[Pasted image 20250923203500.png]]<br><br>![[Pasted image 20250923203606.png]] |
## Schnittmengen
Die Beispiele beziehen sich auf diese Tupel.
 ![[Pasted image 20250923195939.png]]

| Name                                                | Definition                                                                                                                                              | Beispiel                             |
| --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------ |
| ![[Pasted image 20251003152418.png]]Vereinigung     | ![[Pasted image 20250923195853.png]]<br><br>                                                                                                            | ![[Pasted image 20250923195956.png]] |
| Schnitt                                             | ![[Pasted image 20250923195904.png]]<br><br>Die Schnittmenge ist ableitbar aus der Vereinigung und Mengendifferenz und kann deshalb benutzt werden.<br> | ![[Pasted image 20250923200009.png]] |
| ![[Pasted image 20251003152427.png]]Mengendifferenz | ![[Pasted image 20250923195915.png]]<br><br>                                                                                                            | ![[Pasted image 20250923200020.png]] |


![[Pasted image 20250923205036.png]]
### Liste der Join-Operationen
Die Beispiele beziehen sich auf diese Tabelle.
Kreuzprodukt:
![[Pasted image 20251003194353.png]]

| Name                           | Bedeutung                                                                                                                   | SQL-Beispiel                                                                          |
| ------------------------------ | --------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| Join                           | ![[Pasted image 20250923204127.png]]<br><br>                                                                                | ![[Pasted image 20250923204135.png]]<br><br>![[Pasted image 20250923204147.png]]      |
| Equi Join                      | ![[Pasted image 20250923204456.png]]<br><br>Basically Join mit einer bestimmten Bedingung                                   | ![[Pasted image 20251003164129.png]]<br>![[Pasted image 20251003164142.png]]          |
| Natural Join                   | ![[Pasted image 20250923204647.png]]<br><br>Ein Natural Join wird oft genutzt um eine Fremdschlüsselbezeichnung aufzulösen. | ![[Pasted image 20251003164012.png]]<br><br>![[Pasted image 20251003164504.png\|400]] |
| Theta Join                     | ![[Pasted image 20250923204238.png]]<br><br>Join mit einer bestimmten Bedingung                                             | ![[Pasted image 20250923204506.png]]                                                  |
| Semi Join<br>(LEFT OUTER JOIN) | ![[Pasted image 20250923204925.png]]<br><br>                                                                                | ![[Pasted image 20251004094839.png]]<br>![[Pasted image 20251004094913.png]]          |


# Gemeinsame Eigenschaften der relationalen Algebra

| Eigenschaft | Defintion                                                                                                                                                                                                                                                                                                                                | Beispiel                             |
| ----------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------ |
| Monotonie   | ![[Pasted image 20250923203752.png]]<br><br>Das heißt, mit mehr Daten in der DB, werden die Ergebnisse<br>dergleichen Anfrage nur größer.<br><br>Es folgt daraus auch, dass ein neu eingefügter Wert eine korrekte<br>Anfrageantwort nicht invalidiert.<br><br>Inklusive der Mengendifferenz verhält sich die Algebra nicht mehr monoton | ![[Pasted image 20250923203802.png]] |
