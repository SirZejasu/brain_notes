---
tags:
  - dba
  - datenbankentwurf
  - erm
  - relationale_modell
---
# Allgemein
> [!NOTE]
    > Es gibt i.d.R. 3 Stufen der Datenbankarchitektur:
    > ![[Pasted image 20250922173647.png|400]] ![[Pasted image 20250922173704.png|400]]

# Aufgaben rund um ein DBMS

| Name                          | Definition                                                                                                                                                                       |
| ----------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Datendefinitionssprache (DDL) | Datenbankschema muss umgesetzt werden, Tabellen- und Benutzerdefinitionen<br><br>Es beschreibt den SQL-Teil, mit dem das DB-Schema auf der DB erstellt wird (CREATE TABLE, etc.) |
| Anfragesprache (DQL, DML)     | Es sollen Informationen aus der DB gelesen werden und vorhandene Daten geändert werden.                                                                                          |
| Rechteverwaltung (DCL)        | Benutzerrechte sollen definiert werden                                                                                                                                           |
| Tranaktionskontrolle (TCL)    | Transaktionen (eine Menge mehrerer Anfragen) soll kontrolliert an die DB abgesetzt werden.                                                                                       |

## Aufgaben nach Codd

| Name                             | Definition                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   | Visualisierung / Beispiele                                                                                                   |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------- |
| 1. Datenintegration              | Bezeichnung für die einheitliche Datenhaltung der Daten in der Datenbank(en)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | ![[Pasted image 20250922161007.png]]<br><br>[[#ERM-Elemente]] die dies gewährleisten:<br>- Primär- und Fremschlüssel<br><br> |
| 2. Operation und Anfragesprachen | Werden zur Datenverarbeitung benötigt (Speichern, Ändern, Suchen) und müssen realten Daten (> 1000 Tabellen mit >1Mrd. Zeilen) anwendbar sein.<br><br>In dieser Kategorie fallen [[SQL - Allgemein#Typische SQL-Befehle\|SQL-Befehle]]                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                                                                                                                              |
| 3. Datenkatalog                  | Alternativer Name: Data Dictionary<br><br>Es wird von einem Datenbanksystem benutzt um die Definition der Anwendungsdaten, sowie deren Beziehungen untereinander zu beschreiben.<br><br>Enthält Metadaten und Beschreibungen der Daten in der Datenbank und hängt somit stark mit dem [[#Logische Datenmodelle\|logischen Datenmodell]] zusammen.<br><br>Definiert durch eine Data Definition Language (DLL)<br><br>i.d.R. read-only, Änderungen selten und teuer.                                                                                                                                                                                                                                           |                                                                                                                              |
| 4. Benutzersichten               | Alternativer Name: Views<br><br>Mehrere Tabellen werden zu einer Sicht (virtuelle Tabelle) kombiniert<br><br>Daten werden gefiltert.<br><br>Üblicherweise anwendungsspezifisch<br><br>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | ![[Pasted image 20250922163049.png]]                                                                                         |
| 5. Konsistenz                    | Die Datenbank muss frei von Widersprüchen sein (=Konsistenz).<br><br>Inkonsistente Daten können entstehen:<br>- wenn falsche Benutzereingaben gespeichert werden<br>- Daten falsch gespeichert werden<br><br>In beiden Fällen muss die Datenbank Kontrollstrukturen besitzen, die dies verhindern (siehe 7. Transaktionskonzept)                                                                                                                                                                                                                                                                                                                                                                             |                                                                                                                              |
| 6.Zugriffskontrolle              | Unauthorisierte Zugriffe sollen verhindert werden.<br><br>Nutzer mit geeignete Rollen greigen nur auf notwendige Daten zu. <br><br>Die Datenintegrität soll gewährt sein.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                                                                                                                              |
| 7. Transaktionkonzept            | Ein Transaktionkonzept ist verantwortlich für die Korrektheit und Integrität der Daten in der Datenbank.<br><br>Als transaktion bezeichnet man eine Menge an Datenbankoperation.<br><br>Alle Transaktionen müssen eine gewissen Qualität besitzen. Einige Eigenschaften, die diese Qualität beschreiben, werden wir später mit dem sogenannten ACID-Prinzip kennenlernen.<br><br>ACID Steht für<br>**Atomoricity** - Transaktionen werden "ganz oder gar nicht" ausgeführt<br><br>**Consistency** - Transaktionen führen nur zu zulässigen Zuständen<br><br>**Isolation** - Transaktionen werden isoliert für einen Nutzer ausgeführt.<br><br>**Durability** - Das Ergebniss der Transaktion ist persistent. |                                                                                                                              |
| 8. Synchronisation               | Wenn mehrere Nutzer gleichzeitig auf eine Datenbank zugreifen, müssen Transaktionen, die sich gegenseitig beeinflussen, synchronisiert werden.<br><br>Dafür müssen Schreibkonflikte vermieden werden und Inkonsistenzen ausgeschlossen werden.                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                                                                                                                              |
| 9. Datensicherung                | Die Daten in der Datenbank müssen gegen Verlust gesichert werden. Hier kann eine Reihe von Fehlern auftreten, die beachtet werden müssen: von lokalen Systemfehlern bis größere Katastrophen (disaster recovery)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                                                                                                                              |


# ERM - Entity Relationship Modell
> [!question] Was ist der ERM?
> ![[Pasted image 20250923173908.png]]
>  Ein mögliches konzeptuelles Datenbankschema
>  Informationen über Objekten aus der realen Welt werden in sogenannten Entitäten ([[#Entities]]) gespeichert.
>  
>  Es werden Beziehungen ([[#Relationships]]) benutzt um Beziehungen zwischen Objekten zu modellieren.
>  
>  Entitäten sowie Beziehungen können Attribute([[#Attributes]]) besitzen, die deren Eigenschaften beschreiben.

> [!example]
    > ![[Pasted image 20250923174012.png]]
## Aufgaben des ERM

| High-Level Beschreibung der Daten in der Datenbank.                                                                        |
| -------------------------------------------------------------------------------------------------------------------------- |
| Formale Notation, aber unabhängig vom verwendeten DBMS.                                                                    |
| Anfoderungen des Kunden erfüllen und so einfach wie möglich das Modell in ein konkretes Datenbankschema übersetzen lassen. |
| So weit es geht automatisierend in ein systemabhängiges DB-Schema übersetzt werden kann. (Technisches Niveau ähnlich UML)  |

## ERM-Elemente

| Name                  | Definition                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | Beispiel                                                                     |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| Entity                | Eine Entität ist ein Objekt in der realen Welt.<br><br>Eine Menge gleichartiger Objekte wird zu einer Entitätenmenge zusammengefasst.<br><br>Ein Entitätentyp / eine Entität wird durch ein Rechteck dargestellt                                                                                                                                                                                                                                                                                                                                                                                                                                      | ![[Pasted image 20250923174234.png]]                                         |
| Attributes            | Eine Entität kann durch ein oder mehrer Attribute beschrieben werden. Ein Attribut wird durch eine Ellipse im ERM dargestellt.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | ![[Pasted image 20250923174440.png\|300]]                                    |
| Domain                | Zu jedem Attribut gehört eine Domäne, die die erlaubten Werte des Attributs beschreibt<br><br>Beispiel: Titel mit Domäne String(30)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                                                                              |
| **Beziehungen**       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                                                                              |
| Relationships         | Eine Beziehung assoziiert zwei (oder mehr) Entitäten miteinander.<br><br> Eine Menge gleichartiger Beziehungen wird zu einer Menge zusammengefasst.<br><br>Ein solcher Beziehungstyp wird durch eine Raute im ERM dargestellt.<br><br>Beziehungen können auch Attribute besitzen.<br><br>![[Pasted image 20250923174926.png\|300]]<br>                                                                                                                                                                                                                                                                                                                | ![[Pasted image 20250923174748.png]]<br>![[Pasted image 20250923174834.png]] |
| Rekursive Beziehungen | **Rekursive Beziehung**: Beziehungen zwischen Entitäten des gleichen Entitätstyps<br><br>![[Pasted image 20250923175717.png]]<br><br>![[Pasted image 20250923175704.png]]                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                                                                              |
| n:m<br>               | = Min-Max Intervall<br><br>![[Pasted image 20250923181828.png]]<br>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   | ![[Pasted image 20250923181436.png]]                                         |
| **Schlüssel**         | Schlüssel ermöglichen folgendes:<br><br>Das Einfügen oder Ändern von Datensätzen ist nur möglich wenn alle<br>Primär- und Fremdschlüssel gewahrt bleiben.<br><br>Löschungen werden nur durchgeführt wenn dadurch keine<br>Fremdschlüsselbeziehungen verletzt werden.                                                                                                                                                                                                                                                                                                                                                                                  |                                                                              |
| Primärschlüssel       | ![[Pasted image 20250923180447.png]]<br><br>Entitäten können durch ihre Attribute eindeutig identifiziert werden.<br><br>Eine minimale Menge solcher Attribute wird Schlüssel genannt, andernalls handels es sich nur um einen Superschlüssel.<br><br>In ERM wird der Schlüssel durch Unterstreichen gekennzeichnet.<br><br>Es kann mehrere Optionen (Schlüsselkandidaten) geben, aber nur ein Hauptschlüssel oder Primärschlüssel (Primary Key).<br><br>Für Entitäten ohne "natürlichen" Schlüssel, kann ein künstlicher Schlüssel (z.Bsp. ein ObjektID) eingeführt werden.<br><br>Ein Primärschlüssel kann die Menge von zwei Fremdschlüsseln sein. | ![[Pasted image 20250923180726.png]]                                         |
| Fremdschlüssel        | Ein Fremdschlüssel (oder Foreign Key) verweist eindeutig auf einen Schlüsselkandidaten einer weiteren Tabelle mit der gleichen Definition.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | ![[Pasted image 20250923183817.png]]                                         |

## Weitere Beziehungen
### Schwache Entitäten
> [!NOTE] Definition
    > Schwache Entitäten (engl. weak entities) existieren nur in Verbindung mit einer starken Entität (strong entity)
    > 
    > ![[Pasted image 20251003134507.png]]
    > 
    > - Schwache Entitäten besitzen keinen eigenen eindeutigen Schlüssel.
    > - Stattdessen wird der Schlüssel um ein oder mehrere Attribute der abhängigen Entität ergänzt.
> - Hier bilden (Film-ID, Zuschauer) den vollständigen Schlüssel der Entität Rezension.

### IST-Beziehung
> [!NOTE] Definition
    > Die Ist-Beziehung besitzt keine eigene feste Notation im ER-Modell.
    > ![[Pasted image 20251003134746.png]]![[Pasted image 20251003134758.png]]
    > − Es gilt: Alle Filme und Serien
besitzen einen Datensatz in der
Entität Medium.
− Dies kann durch sogenannte
Fremdschlüssel modelliert
werden (dazu gleich mehr).
− Auÿerdem erlauben wir keine
Mehrfachvererbung (nur
Bäume)
# Logische Datenmodelle
> [!question] Was sind logische Datenmodelle?
    > Ein logisches Datenmodell wird benutzt um den Inhalt der Datenintegration für verschiedene Anwendungen zu beschreiben und zu kommunizieren.

| Modellname                | Definition                                                                                                                                                                                                                                            | Beispiel                                                                                                                            |
| ------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| Hierarchisches Modell     | "Objekte" aus der realen Welt ist durch eine Baumstruktur abgebildet.<br><br>Nachteil: nur 1:n-Beziehung, komplexe Verknüpfungen zwischen Objekten nicht möglich.                                                                                     | ![[Pasted image 20250922155623.png\|400]]                                                                                           |
| Netzwerkmodell            | Keine Strenge Hierarchie erforderlich.<br><br>Ungefähr zeitgleich mit Relationalen Modell<br><br>Vorteil: Auch komplexe Verbindungen und n:m Beziehungen erlaubt                                                                                      | ![[Pasted image 20250922155843.png]]                                                                                                |
| Relationales Modell       | Objekte und Beziehunen werden in Tabellen modelliert.<br><br>Die Informationen in den Tabellen können mit Operationen ausgewertet werden.<br><br>Der am häufigsten verwendete Standard ist SQL.                                                       | ![[Pasted image 20250922160041.png]]                                                                                                |
| XML-Modell                | Objekte und Beziehungen werden in Baumstrukturen modelliert.<br><br>Die Baumstruktur kann durch Schemata beschrieben werden.<br><br>Eigene Anfragesprachen werten die enhtaltenen Daten aus, z.B. über die Auswertung von Pfaden in der Baumstruktur. | ![[Pasted image 20250922160206.png]]<br><br>Baumstruktur<br>![[Pasted image 20250922160224.png]]                                    |
| Objektorientiertes Modell | Daten und Funktionen werden in einem Objekt gespeichert.<br><br>Selten in der Praxis genutzt.<br><br>Nachteil:<br>- Komplexität bei der Dateverarbeitung <br>- Komplexe Schnittstellen<br>                                                            | Beispiele: Java ([OOP](https://de.wikipedia.org/wiki/Objektorientierte_Programmierung))<br><br>![[Pasted image 20250922160621.png]] |
|                           |                                                                                                                                                                                                                                                       |                                                                                                                                     |

# Phasenmodell
> [!NOTE]
    > Beschreibt eine Abfolge von Entwurfsdokumenten. Jede Phase soll die existierenden Informatonen erhalten bzw. konsistent zu den anderen Phasen sein.

| Schritt                        | Definition                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1. Anforderungsanalyse         | Anforderungen der Endandwender (Client-Level, [OSI Layer 8](https://de.wikipedia.org/wiki/OSI-Modell)).<br><br>Trennung Datenanalyse und Funktionen (Software-Engineering)<br><br>Ergebnis: Informelle Beschreibung des Fachproblems                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| 2. Konzeptioneller Entwurf     | Formale Beschreibung des Datenmodells (hier: [[#ERM - Entity Relationship Modell]])<br><br>Modellierung und Analyse der verschiedenen Kundensichten.<br><br>Ergebnis: Ein integriertes Datenmodell (Datenschema).<br><br>Die verschiedenen Sichten der Endanwender werden zusammengebracht und in ein Gesamtschema überführt.<br>![[Pasted image 20250923164353.png]]<br><br>Es kann zu Integrationskonflikten kommen.<br>- Namenskonflikte: Dozenz, Professor, Lehrender<br><br>- Typkonflikte: STRING, VARCHAR, INTEGER<br><br>- Wertbereichskonflikte: Maximale und Minimale Werte<br><br>- Bedingungskonflikte: Studenten Identifikation über Matirikelnummer oder Matrikelnummer und die Hochschule<br><br>- Strukturkonflikte: Listen oder Mengen |
| 3. Verteilungsentwurf          | Falls die DB später auf mehreren Knoten (Verteiltes System) realisiert werden soll.<br><br>Analyse und Planung wie das Schema in verschiedene Partition aufgeteilt wird.<br><br>Nicht in diesem Kurs.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| 4. Logischer Entwurf           | (Automatische) Transformation in die passende technische Beschreibung (Datenbankschema)<br><br>Beispielsweise relational Modell (Tabellendesign), XML, Schlüssel-Werte-Modelle etc.<br><br>Optimierung nach techischen Kriterien (u.a. Normalformen, Redundanzvermeidung, etc.)                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 5. Datendefinition             | Der noch systemunabhängige Entwurf wird in eine konkrete Deklaration überführt.<br><br>Mit Hilfe von Datendefinitionsprache (DDL), zum Bsp. in SQL<br><br>Auf Integritätsbedingungen (wie Schlüssel, Fremdschlüssel, etc.)<br><br>Auch Integritätsbedingungen (wie Schlüssel, Fremdschlüssel, etc.) und Benutzersichten werden angelegt.                                                                                                                                                                                                                                                                                                                                                                                                                |
| 6. Physischer Entwurf          | Entwurd auf der Datenbank<br><br>Optimierung übernimmt meistens das [[#Aufgaben rund um ein DBMS\|DBMS]] automatisiert (Bsp. geeginete Indexe)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| 7. Implementierung und Wartung | Realisierung auf der Datenbank<br><br>Kontinuierliche Anpassung an neue Anforderungen und Updates<br><br>Auch Anpassungen an neue Plattformen, DBMS, etc.<br><br>Kostenaufwändigste und längste Phase.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
# Relationen und Tabellen
## Schema
> [!NOTE]
    > Der Schemateil der Relation bzw. der Tabelle besteht aus der Beschreibung ihrer Struktur: $sch(Film)=(Film-ID, Titel, Genre)$
    > Jedes [[#ERM-Elemente|Attribut besitzt außerdem eine Domäne]]: dom(Film-ID) = INTEGER
    > 
    > In der DB gehören außerdem die Schlüsselbedingungen zum Schema.
    > 

## Werte / Instanz
> [!NOTE]
    > Als Werte oder Instanz val(Film) der Relation bezeichnen wir die aktuelle Tupelmenge, die in der Tabelle enthalten ist.
    > 
    > Die Reihenfolge der Tupel / Zeichen ist nicht definiert 
    > ${1,2,3}\equiv{3,2,1}$
    > 
    > Eine Relation kann nicht das gleiche Tupel mehrfach enthalten (Menge vs. Multimenge) ~~{1, 1, 2, 3}~~
    > Dadurch wird auch garantiert, dass es immer mindestens den Schlüssel gibt, der aus allen Attributen besteht.
    > Die Attribute der Tupel können nur aus atomaren Werten bestehen.
    > ![[Pasted image 20250923183445.png]]
    > das heißt, eine Spalte kann keine weiteren Tabellen enthalten.

# Optimierung
> [!NOTE]
    > Zusammenlegen von Relationen
    > ![[Pasted image 20250923184738.png]]
    > ![[Pasted image 20250923184846.png]]
# Normalformen
> [!NOTE] Änderungsanomalien
    > Rendundante Informationen können zu hohen (Zeit-)kosten führen. Es ist daher wichtig, dass wir bestimmte Kriterien beachten, um eine Datenbank effizient zu verwalten.
    > 1. Datenqualität über Normalformen vergleichbar machen.
    > 2. Eigenschaften definieren mit denen verglichen werden kann (siehe z. Bsp. Informationskapazität)
    > 3. Algorithmisch ein gegebenes Schema verbessern. (Nicht hier in der Vorlesung.)    

## Funktionale Abhängigkeiten
> [!note] Definition
    > ![[Pasted image 20251001145153.png]]

> [!example]
    > ![[Pasted image 20251001145340.png]]

### Dekompositionsregel
![[Pasted image 20251001145945.png]]
> [!NOTE] Definition
    >  ![[Pasted image 20251001145856.png]]

> [!example] Beispiel
    > ![[Pasted image 20251001150026.png]]
### Vereinigungsregel
![[Pasted image 20251001145945.png]]
> [!note] Definition
    > ![[Pasted image 20251001145834.png]]

> [!example] Beispiel
    > ![[Pasted image 20251001150107.png]]

## Armstrong Axiome
> [!NOTE] Definition 
    > ![[Pasted image 20251001150313.png]]

> [!example] Beispiel
    > ![[Pasted image 20251001150343.png]]

## Normalformen - Typen
> [!NOTE]
    > ![[Pasted image 20251001155217.png]]
    > Normalformen werden verwendet, um Redundanzen zu vermeiden. Allerdings kommt es auch vor, dass auf Schritte der Normalisierung zugunsten von Performanz verzichtet wird.
### 1.Normalform (1NF)
> [!NOTE] Definition
    > Ein Datenbankschema befindet sich in 1. Normalform (1NF), wenn alle Attributenwerte im Schema atomar sind.

> [!example] Beispiel
    > ![[Pasted image 20251001150935.png]]

### 2. Normalform (2NF)
> [!NOTE] Definition
    > Ein Datenbankschema befindet sich in 2. Normalform (2NF), wenn es in 1NF ist und es keine funktionalen Abhängigkeiten von einem Teil des Schlüsels gibt.

> [!example] Beispiel
    > ![[Pasted image 20251001151126.png]]
### 3. Normalform (3NF)
> [!NOTE] Definition
    > Ein Datenbankschema befindet sich in 3.Normalform (3NF), wenn es in 2NF ist und es keine transitiven Abhängigkeiten (in nicht Schlüsselattributen) gibt.

> [!example] Beispiel
    > ![[Pasted image 20251001151525.png]]
    > ![[Pasted image 20251001151618.png]]
### Boyce-Codd-Normalform (BCNF)
> [!NOTE] Definition
    > Ein Datenbankschema befindet sich in Boyce-Codd Normalform (BCNF), wenn es in 3NF ist und es auch keine transitiven Abhängigkeiten innerhalb der Schlüsselkandidaten gibt.

> [!example] Beispiel
    > ![[Pasted image 20251001152005.png]]

## Minimalität
> [!NOTE] Definition
    > Ein Datenbankschema ist minimal bzgl. einer Normalform, wenn es alle Eigenschaften der [[#Normalformen - Typen|Normalformen]] erfüllt und so wenige Relationen wie möglich verwendet.
    > 
    > Also: Können wir dasselbe Schema mit 3 Relationen ausdrücken, so ist das besser als das Schema mit 5 Relationen auszudrücken.

