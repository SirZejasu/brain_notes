---
tags:
  - dba
  - transaktionsverwaltung
---

# Transaktionsverwaltung

> [!question] Was ist eine Transaktion?
    > Als Transaktion definieren wir eine Folge von einer oder mehr
logisch zusammenhängenden Anfragen an die Datenbank.
![[Pasted image 20250930190423.png]]
> Das Problem: Daten können falsch manipuliert werden, wenn mehrere Nutzer auf diese Daten zugreifen. Beispiel: Bank-Konto
> ![[Pasted image 20251001164856.png]]

> [!example] Beispiel
    > ![[Pasted image 20251001164939.png]]

# ACID - Transaktionseigenschaften
> [!NOTE]
    > ![[Pasted image 20251001160818.png]]

# Mehrbenutzerbetrieb
## Inkonsistentes Lesen (Nonrepeatable Read)
> [!question] Was ist Inkonsistentes Lesen?
    > ![[Pasted image 20251001162609.png]]

## Abhängigkeiten von nicht freigegebenen Daten (Dirty Read)
> [!question] Was ist Dirty Read?
    > ![[Pasted image 20251001162842.png]]
    > Beide Probleme könnten mit Hilfe von explizieten Sperren für DB-Objekte verhindert werden.

## Phantom-Problem
> [!NOTE] Was ist das Phantom-Problem?
    > ![[Pasted image 20251001164215.png]]

## Verlorgengegangenes Ändern (Lost Update)
> [!question] Was ist ein Lost Update?
    > ![[Pasted image 20251001164401.png]]

# Lösungsansätze
## Scheduler
> [!NOTE] Definition
> ![[Pasted image 20251001165202.png]]
    > Im Mehrbenutzerbetrieb entschiedet der Scheduler im DBS die Ausführungsreihenfolge der einzelnen Operationen
    > ![[Pasted image 20251001164749.png]]

## Serialisierbarkeit
> [!question] Was ist eine serielle Ausführung?
    > ![[Pasted image 20251001165335.png]]
    > In einer seriellen Ausführung können keine Anomalien auftreten
    > Dies erlaubt allerdings keinen verschränkten Mehrbenutzerbetrieb und ist somit nicht praxisnah.
    > Vielmehr wollen wir im Folgenden nur Ausführungspläne erlauben, die äquivalent zu einer seriellen Ausführung sind.
    > ![[Pasted image 20251001165634.png]]

### Sperrprotokoll
> [!NOTE]  Definition
    > ![[Pasted image 20251001170540.png]]
    > 
    > Ein Sperrprotokoll ist eine andere Möglichkeit, die im Allgemeinen Serialisierbarkeit zu garantieren.

#### Sperrverfahren
> [!NOTE] Sperrverfahren Eigenschaften
    > - Transaktionen müssen geeignete Sperren zum Lesen und Schreiben von Objekten setzen.
    > - Wenn eine Transaktion T eine Sperre nicht setzen kann, wird diese Transaktion (vom [[#Scheduler]]) blockiert und wartet.
    > - Wird die gewünschte Sperre frei und kann von T gesetzt werden, kann T weiterlaufen.
##### Sperren
> [!example]
> Das bloße Sperren von Daten löst noch nicht ein Transaktionsproblem, [[#Verlorgengegangenes Ändern (Lost Update)]].
> 
    > ![[Pasted image 20251001171404.png]]

> [!warning] Sperren ist teuer!
    > Umso strikter die Konsistenzbedingungen der DB sind, desto weniger Transaktionen können (pro sek.) ausgeführt werden
##### Two Phase Locking (2PL)
> [!NOTE] Definition
    > Im Two Phase Locking (2PL) darf eine Transaktion keine neuen Sperren anfordern sobald sie einmal eine Sperre freigegeben hat.
    > ![[Pasted image 20251001171252.png]]

> [!example]
    > ![[Pasted image 20251001171828.png]]

##### Deadlocks
> [!question] Was ist ein Deadlock?
    > Ein Deadlock kommt zustande, wenn beide Prozesse sich in einer Situation befinden, wo sie unendlich lange warten müssen.

> [!example]
    > ![[Pasted image 20251001172121.png]]

> [!success] Lösung
    > DB können Deadlocks effizient entdecken (Kreise im waits-for Graph)
    > Deadlocks werden normalerweise gelöst indem ein Prozess gestoppt wird (young / old victims oder timeouts)
    > 

# Isolationsstufen

| Isolationsstufe  | [[#Abhängigkeiten von nicht freigegebenen Daten (Dirty Read)\|Dirty Read]] | [[#Inkonsistentes Lesen (Nonrepeatable Read)\|Nonr. Read]] | [[#Verlorgengegangenes Ändern (Lost Update)\|Lost Update]] | [[#Phantom-Problem]] |
| ---------------- | -------------------------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- | -------------------- |
| read uncommitted | x                                                                          | x                                                          | x                                                          | x                    |
| read committed   |                                                                            | x                                                          | x                                                          | x                    |
| repeatable read  |                                                                            |                                                            |                                                            | x                    |
| serializable     |                                                                            |                                                            |                                                            |                      |


| Stufe            | Bedeutung                                                                                                                                                                                                              | Beispiel                             |
| ---------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------ |
| read uncommitted | = dirty read oder browse<br><br>Die schwächste Stufe, in der nur Sperren für schreibende Zugriffe gesetzt werden (nur write locks)<br>                                                                                 |                                      |
| read committed   | = cursor stability<br><br>Die zweitschwächste Stufe, in der write locks nach [[#Two Phase Locking (2PL)]]  gesetzt werden und read locks nur solange gesetzt werden wie der Cursor auf der entsprechenden Zeile steht. | ![[Pasted image 20251001173304.png]] |
| repeatable read  | = read stability<br><br>Es werden read locks und write locks strikt nach [[#Two Phase Locking (2PL)]] gesetzt.                                                                                                         |                                      |
| serializable     | Zusätzliche Sperren um das [[#Phantom-Problem]] zu verhindern.                                                                                                                                                         |                                      |
# Integritätssicherung
> [!NOTE]
    > Ein möglicher Lösungsansatz, um die Integrität der Daten zu sichern ist das Definieren von Integritätsbedingungen.
siehe [[Datenbank - Allgemein#Aufgaben rund um ein DBMS|DDL]]

## Integritätsbedingungen

| Name                     | Bedeutung                                                                                                                               |
| ------------------------ | --------------------------------------------------------------------------------------------------------------------------------------- |
| Typintegrität            | Beim Erstellen von Tabellen legen wir mit Hilfe von Datentypen die Domäne von Attributen fest.<br><br>NULL-Werte können verboten werden |
| Schlüsselintegrität      | Attribute können Schlüsseln gemacht werden.                                                                                             |
| Referentielle Integrität | Es können Fremdschlüssel deklariert werden.                                                                                             |
## SQL-Integritätsbedingungen

| Name      | Bedeutung                                                                                                                                                                                                           | Beispiel                             |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------ |
| UNIQUE    | Mit UNIQUE darf jeder Wert in der refenziertes Spalte nur einmal auftauchen                                                                                                                                         | ![[Pasted image 20251001175519.png]] |
| CHECK     | Check definiert lokale Bedingungen für ein Attribut.<br><br>Im Beispiel wird es in Kombination mit CONSTRAINT verwendet. Dieser definiert Bedingungen für mehrere Attribute.                                        | ![[Pasted image 20251001175638.png]] |
| ON DELETE | ON DELETE löst Reaktion auf Eriegnins aus.<br><br>Im Beispiel: CASCADE Löscht die Zeile entsprechend.<br><br>SET NULL, SET DEFAULT, NO ACTION: Reaktion entsprechend<br><br>                                        | ![[Pasted image 20251001175825.png]] |
| ON UPDATE | Bei einem ON UPDATE in Kombination mit NO ACTION wird die Fremdschlüsselbedingung nicht neu geprüft.                                                                                                                | ![[Pasted image 20251001180008.png]] |
| ASSERTION | Mit ASSERTION können auch tabellenübergreifende Bedingungen erstellt werden.<br><br>In Kombination mit CHECK ist eine beliebige Boolesche-Bedingung erlaubt.<br><br>Assertions werden von JavaDB nicht unterstützt. |                                      |
