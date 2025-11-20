---
tags:
  - dba
  - jdbc
---
	# Allgemein
Um zu erklären, was JDBC ist, brauchen wir Vorwissen:

> [!question] Was ist SQL Embedding in Java?
> Es gibt verschiedene Methoden / Technologien um SQL in Java zu implementieren. Dafür vewendet man **SQLJ** / **OLB** (Beides das gleiche.)
> SQLJ ist die (veraltete) Bezeichnung für das Bestreben, Java und SQL zusammenzuführen (Quelle: [Wikipedia](https://de.wikipedia.org/wiki/SQLJ))
> Mittlerweile heißt es [OLB](https://en.wikipedia.org/wiki/SQL/OLB)


> [!question] Was ist JDBC?
> ![[Pasted image 20250930162958.png]]
    > Das Problem mit SQLJ ist, dass es nur fertig ausformulierte SQL-Ausdrücke anbietet, es ist also **statisches SQL**.
    > 
    > Über **JDBC** ist dynamisches SQL möglich. Es ist die Schnittstelle zwischen der Datenbank und Anwendungslogik von Java.

# Basiskomponenten
![[Pasted image 20250930163715.png]]
![[Pasted image 20250930163820.png]]

## Ablauf von JDBC
![[Pasted image 20250930164057.png]]

### 1. Datenbankverbindung anfordern
```java
try {
	Connectio con = null;
	String url = "jdbc:subprotocol:datasource";
con = DriverManager.getConnection(url, "username", "password");
//...
} catch (SQLException ex) {
//Fehlerbehandlung
//Datenbankverbindung konnte nicht hergestellt werden
...
}finally{
//Ressourcen ggf. schließen!
}

```

> [!NOTE] Aufbau einer URL (Uniform Resource Locator) für Java DB Network
    > ![[Pasted image 20250930165035.png]]

### 2. / 3. SQL-Statement erzeugen und usführen
> [!NOTE]
> ![[Pasted image 20250930165726.png]]
    > - Statement-Objekt als Basis, von wo aus die SQL-Befehle an das DBMS abgeschickt werden
    > - Mehrere execute-Methoden, um mit unterschiedlichen Rückgabewerten umzugehen.

```java
try{
Statement select = con.createStatement();
ResultSet result = select.executeQuery(
"select PersonalNr, Nachname from Personal"
/* SQL-Anweisung als String. Lässt sich dynamisch über String Verkettungsoperationen generieren
und mit Java-Variablen verknüpfen. Prüfung auf Syntax und Semantik erst zur Laufzeit */
);
// Ergebnisverarbeitung
} catch ( SQLException ex) {
// Fehlerbehandlung
..
} finally {
// Ressourcen ggf. schließen!
}
```

### 4. Anfrageergebnisse auswerten
> [!NOTE]
    > ResultSet: Verarbeitung von mengenwertigen Anfrageergebnissen
Cursor-Mechanismus zur Lokalisierung des aktuellen Datensatzes
(Standard: einfacher Vorwärtscursor)
![[Pasted image 20250930170500.png]]

> [!info] Resultset
    >  Ermöglicht den Zugriff auf das ErgebnisTupel, auf das der Cursor zeigt. Der Cursor steht initial vor dem ersten ErgebnisTupel.

| Methodenname                                                                    | Bedeutung                                                                                                                                   |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| next()                                                                          | Setzt den Cursor auf das nächste Ergebnis-Tupel. Gibt false zurück, wenn es kein weiteres Ergebnis-Tupel gab, sonst true.                   |
| getType(spalte)                                                                 | Ermöglicht den Zugriff auf einzelne Spaltenwerte über Spaltenindex (beginnend mit 1) oder Spaltenname. *Type* steht für übliche Datentypen. |
| wasNull()                                                                       | Prüfung, ob der letzte Zugriff auf einen Spaltenwert mit getType ein SQL-NULL war.                                                          |
|                                                                                 | Setzen des Cursors an eine beliebige Stelle<br>                                                                                             |
|                                                                                 | Rückwärtsnavigation des Cursors                                                                                                             |
|                                                                                 | Insert                                                                                                                                      |
|                                                                                 | Update                                                                                                                                      |
|                                                                                 | Delete                                                                                                                                      |
| createStatement(ResultSet.TYPE SCROLL SENSITIVE,<br>ResultSet.CONCUR UPDATABLE) | Zum Erstellen des dem ResultsSet zugrunde liegende Statement-Objekt.<br><br>Der Treiber muss diese optionalen Funktionen unterstützen       |

#### Typkonvertierung
> [!info] Mögliche Probleme
    > - Übergabe von Nullwerten
    > - SQL-NULL wird abhängig vom erwarteten Typ über getType unterschiedlich interpretiert
![[Pasted image 20250930173011.png]]

> [!info] Zulässige Typkonvertierung
>  ![[Pasted image 20250930173518.png]]

> [!example] Anfrageergebnisse auswerten
    > ![[Pasted image 20250930174051.png]]

##### Datums- und Zeitwerte
> [!NOTE] Bereitstellung temporaler Datentypen durch JDBC
    > Problem: Beachte den Hinweis in [[SQL - Allgemein#Datentypen|SQL-Datentypen -> Zeitangaben]]
    > 
    > Es gibt einen Werteverlust bei Timestamp, wenn es von Java in einer DB überführt wird.
    > 
    > ![[Pasted image 20250930183729.png]]
    > 
    > ![[Pasted image 20250930183754.png]]

###### Methoden aus Java

| Name                      | Bedeutung                                                                     |
| ------------------------- | ----------------------------------------------------------------------------- |
| Date()                    | Konstruktor: erzeugt den Zeitpunkt, der dem Jetzt<br>entspricht               |
| Date(long)                | Konstruktor: erzeugt aus einer Millisekunden-Angabe ein<br>Datums-Objekt      |
| long getTime()            | iefert die Anzahl der Millisekunden, die das Datum vom Nulldatum entfernt ist |
| void setTime(long)        | setzt ein Datum                                                               |
| String toString()         | macht aus einem Datum einen String der Form "dow mon dd hh:mm:ss zzz yyyy"    |
| boolean after(Date)       | Vergleich Zweier Zeitpunkte                                                   |
| boolean before(Date)      | Vergleich Zweier Zeitpunkte                                                   |
| boolean equals(Object)    | Vergleich Zweier Zeitpunkte                                                   |
| boolean compareTo(Object) | Vergleich Zweier Zeitpunkte                                                   |
| Object clone()            | kopiert das Datumsobjekt                                                      |
###### Methoden aus SQL
 java.sql.Date
![[Pasted image 20250930184905.png]]
![[Pasted image 20250930184922.png]]

| Name                        | Bedeutung                                                             |
| --------------------------- | --------------------------------------------------------------------- |
| Date(long)                  | Konstruktor: erzeugt aus einer Millisekunden-Angabe ein Datums-Objekt |
| void setTime(long)          | erzeugt ein normalisiertes Datum                                      |
| static Date valueOf(String) | konvertiert einen String im Format "yyyy-mm-dd"                       |
| String toString()           | macht aus einem Datum einen String der Form yyyy-mm-dd                |
java.sql.Time
![[Pasted image 20250930185220.png]]
![[Pasted image 20250930185239.png]]

| Name                        | Bedeutung                                                        |
| --------------------------- | ---------------------------------------------------------------- |
| Time(long)                  | Konstruktor: erzeugt aus einer Millisekunden-Angabe eine Uhrzeit |
| void setTime(long)          | setzt eine Uhrzeit                                               |
| static Date valueOf(String) | Konvertiert einen String im Format "hh:mm:ss" in eine Uhrzeit    |
| String toString()           | Konvertierung in ein String                                      |
java.sql.Timestamp
![[Pasted image 20250930185805.png]]
![[Pasted image 20250930185817.png]]

| Name                                | Bedeutung                                                               |
| ----------------------------------- | ----------------------------------------------------------------------- |
| Timestamp(long)                     | Konstruktor: erzeugt aus einer Millisekundenangabe<br>einen Zeitstempel |
| static Timestamp<br>valueOf(String) | konvertiert String im Format "yyyy-mm-dd hh:mm:ss" in einen Zeitstempel |
| int getNanos()                      | Zugriff auf Nanosekunden                                                |
| void setNanos()                     | setzt die Nanosekunden                                                  |
| boolean equals(Object)              | vergleicht die zeitliche Reihenfolge zweier Zeitstempel                 |
| boolean before(Date)                | vergleicht die zeitliche Reihenfolge zweier Zeitstempel                 |
| boolean after(Date)                 | vergleicht die zeitliche Reihenfolge zweier Zeitstempel                 |

### 5. Ressourcen schließen

| Name          | Bedeutung                                                                                                                                                       |
| ------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| close()       | Ressourcen werden geschlossen.<br><br>Da close() selbst eine SQLException (checked exception) werfen<br>kann, muss sie in einen try-catch-Block gefasst werden. |
| getConnection |                                                                                                                                                                 |
> [!example] Ressource schließen
>
>```java
try {
...
} catch (SQLException ex) {
// Fehlerbehandlung
...
} finally {
// Ressourcen ggf. schließen!
result.close();
select.close();
con.close();
}
>```

> [!example] AutoClosable - Ab Java 7
    >
    >Beispiel vor Java 7
> ```java
>public class DBZugriff {
	>Connection con;
	>String url = "jdbc:derby://localhost:1527/buchhandlung";
>	
	>public DBZugriff() {
	>	try {
	>		con = DriverManager.getConnection(url, "test", "Test");
	>		... // Anwendungs-Code
	>	} catch ( SQLException e) {
	>		System.out.println(" *** SQLException: \n" + e);
	>		e.printStackTrace();
	>	} finally {
	>				​try{
	>					con.close();
	>				} catch (SQLException sqle) {
	>					e.printStackTrace();
	>			}
	>		}
	>	}
	>}
>}
>```
> Beispiel nach Java 7
>```java 
>public class DBZugriff {
	>String url = "jdbc:derby://localhost:1527/buchhandlung";
	>
	>public DBZugriff() {
	>try(Connection con = DriverManager.getConnection(url, "test", "Test")) {
>/* Das try-with-resources statement ist ein try-Block, in dem eine oder mehrere Ressourcen deklariert werden, die nach Abarbeitung des try-catch-Blocks automatisch freigegeben werden. */
... // Anwendungs-Code
	>} catch ( SQLException e) {
	>		System.out.println(" *** SQLException: \n" + e);
		>	e.printStackTrace();
	>}
	>//finally-Block kann entfallen
	>}
>}
>```

> [!info]
    > - Vor dem Schließen müssen die Ressourcen auf Null-Referenzen geprüft werden.

# Statements
> [!question] Was ist ein Statement in JDBC?
    > Es ist eine Basisklasse für alle Anweisungen. Sie ermöglichen die Verarbeitung einfacher SQL-Anweisungen ohne Parameter.     

> [!NOTE] Vorteile von Statement-Formen
    > ![[Pasted image 20250930180113.png]]
    >-  Performance-Gewinn, wenn dasselbe SQL-Statement mehrmals mit verschiedenen Paramtern ausgeführt wird.
    > 
    > Erhöhte Lesbarkeit des Codes, da die umständliche Konkatenation des SQL-Statements aus statischen und dynamischen Anteilen entfällt.


| Statement                           | Bedeutung                                                                                                                                                                                                                                           |
| ----------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| con.createStatement()               | Erstellung von Statements.<br><br>Ablauf eines Statements<br>![[Pasted image 20250930180327.png]]                                                                                                                                                   |
| con.prepareStatement(SQL-Anweisung) | Kapselung einer vorkompilierten Anweisung und Parametrisierbar. Findet Verwendung bei einer Wiederholten Ausführung eine Anweisung, ggf. mit veschiedenen Paramtern<br><br>Ablauf eines PreparedStatements:<br>![[Pasted image 20250930180344.png]] |
# Transaktionsverwaltung in JDBC
Für die Definition siehe [[Transaktionen und Integrität]]
## Schablonen
### Schablone für manuelle Transaktionsverwaltung
```java
try{
	con.setAutoCommit(false); // Manuelle //Transaktion starten
	... //Transaktionslogik
con.commit(); //Transaktion erfolgreich beenden
} catch(Exception e) {
	if( con != null) {
		try{
		con.rollback();
	} catch (Exception e) {
	e.printStackTrace();
	}
}
} finally { //Fehlerbehandlung
	if( con != null) {
	try{
	con.setAutoCommit(true); //Manuelle Transaktion deaktivieren
	} catch (Exception e) {
		e.printStackTrace();
	}
}
}

```

## 
# Fehlerbehandlung
## Methoden - Fehleranalyse

| Name                            | Bedeutung                                                                                                |
| ------------------------------- | -------------------------------------------------------------------------------------------------------- |
| String getMessage()             | Fehlertext; geerbt von Throwable                                                                         |
| String getSQLState()            | normierter Fehlercode nach ANSI X / OPEN                                                                 |
| int getErrorCode()              | Hersteller-spezifischer Fehlercode                                                                       |
| SQLException getNextException() | Verfolgen der Fehlerkette (chaining)<br><br>![[Pasted image 20251001140537.png]]<br><br>Null, wenn Ende. |
| getNextWarning()                | Verfolgung der Warnungskette                                                                             |
| getWarnings()                   | Zugriff auf die erste Warnung                                                                            |
| clearWarnings()                 | Löschen der Warnungen                                                                                    |
## Methoden - Bestimmen des Ausmaßen des Datenverlusts

| Name                   | Bedeutung                                                                                                                                   |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| int getIndex()         | Spaltenindex, wo Trunkierung erfolgte                                                                                                       |
| boolean getParameter() | Indikator, ob Spalte oder Parameter trunkiert wurde.<br><br>true = Parameter, false =  Spalte                                               |
| boolean getRead()      | Indikator, ob die Trunkierung beim Lesen aus der Datenbank oder Schreiben in die Datenbank erfolgte.<br><br>true = Lesen, false = Schreiben |
| int getDateSize()      | Anzahl der zu übertragenden Daten-Bytes                                                                                                     |
| int getTransferSize()  | Anzahl der tatsächlich übertragenen Bytes                                                                                                   |
## Schablonen zur Fehlerbehandlung

## Objekt-Relationale Fehlanpassung
> [!note] Java vs SQL
    > ![[Pasted image 20251001142402.png]]

## Lösungsansätze
