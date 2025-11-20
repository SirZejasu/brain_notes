---
tags:
  - technische_informatik
  - tgi
  - Programmieren_in_Assembler
sticker: ""
banner_y: "48.5"
---
# Allgemein
## Was sind Maschinenbefehle?
> [!NOTE] Maschinenbefehle
    > Maschinenbefehle werden vom Prozessor abgerufen, um bestimmte Prozesse auszuführen. Unter [[Befehle in Assembler#Liste der Assembler-Befehle|Liste der Assembler-Befehle]] sind einige Befehle zu sehen, die der Prozessor ausführen kann.
    > 
    > Maschinenbefehle sind im Programmspeicher alle hintereinander angeordnet und ein Maschinenprogramm wird vom Prozessor normalerweise linear abgearbeitet; der Befehlszähler wird immer entsprechend der jeweiligen Befehlslänge erhöht.
    > 
    > Syntax-Beispiel:
    > `MOVE.x <ea1>,<ea2>`

## Liste der Assembler-Befehle

| Assembler-Befehl                                                    | Bedeutung                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | Beispiel                                            |
| ------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------- |
| ORG                                                                 | ORG ist kein Maschinenbefehl, sondern eine Anweisung bestimmt für den Assembler.<br><br>Die physikalischen Adressen der Befehle, Konstanten und Variablen im Arbeitsspeicher können bei den meisten Assemblern mit der ORG-Anweisung festgelegt werden. Dazu muss der Anwender die Adressen des verfügbaren Speichers kennen.<br><br>Mit ORG festgelegt, kann der Programmcode nicht mehr verschieben werden.                                                                                                                                                                                                             | ![[Pasted image 20250920150944.png\|400]]           |
| MOVE.x                                                              | Überträgt ein Wert von einer Quelle ins Ziel.<br><br>Erklärung im Beispiel:<br>1. Der MOVE-Befehl in Zeile 1 überträgt ein Wort, das in der Speicherzelle mit der Adresse $2000<br>steht, in die untersten 16 Bit des Registers D0. <br><br>2. Das Wort wird auf der Speicherstelle<br>$2002 zum unteren Wort in D0 addiert.<br><br>3. Das untere Wort von D0 wird in das Speicherwort mit der Adresse $2004 übertragen.<br><br>x steht für [[#Datenlänge\|Byte, Wort, Lang]]<br><br>Größe: OpCode ist 16Bit + Größe des Operanden (B, W oder L)                                                                          | ![[Pasted image 20250920151438.png]]                |
| MOVEA.X                                                             | Falls der Zieloperand ein Adressregister ist, muss der Befehl MOVEA verwendet werden.<br><br>x steht für [[#Datenlänge\|Byte, Wort, Lang]]                                                                                                                                                                                                                                                                                                                                                                                                                                                                                | ![[Pasted image 20250920181930.png]]                |
| DC                                                                  | Definiert Konstanten. Es gelten die Regeln der [[Adressierung#Die Adressierungsarten\|Unmittelbaren Adressierung]]<br><br>Größe: Größe des Operanden (B, W oder L)                                                                                                                                                                                                                                                                                                                                                                                                                                                        | ![[Pasted image 20250920150819.png]]<br><br>        |
| ADD.x                                                               | Addiert Quelle mit Ziel.<br><br>x steht für [[#Datenlänge\|Byte, Wort, Lang]]                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | ![[Pasted image 20250920152214.png]]                |
| CLR.x                                                               | Setzt Register auf 0<br><br>x steht für [[#Datenlänge\|Byte, Wort, Lang]]                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | ![[Pasted image 20250924151804.png]]                |
| Jump                                                                | Absoluten Sprungbefehl. Ein unbedingter Sprung zu der als Operand angegebene Adresse.<br><br>D32 steht für eine 32Bit lange Zahl, d16 für 16Bit. Sie werden vom Prozzessor als absolute Adresse interpreitert. d16 spart Speicherplatz.                                                                                                                                                                                                                                                                                                                                                                                   | `JMP d32` oder<br>`JMP d16`                         |
| Branch                                                              | Relativen Sprungbefehl. Ein unbedingter Sprung zu einer Adresse, die relativ zur Position des aktuellen Programmzählers ist. [[Adressierung#Programmzähler relativ\|vgl. Adressierungsart "PC relativ"]]<br><br>d16 oder d8 wird verwendet. Beides sind vorzeichenbehaftete Zahlen, die vom Prozessor als Adressdistanz zum aktuellen Inhalt des Programm Counters interpretiert wird. Negative Zahl geht rückwärts, eine positive Zahl vorwärts.<br>                                                                                                                                                                     | `BRA d16`<br>oder<br>`BRA d8`                       |
| JSR                                                                 | = **J**ump to **S**ub**R**outine<br><br>Sprung zu Unterprogramm (absolut). Der Unterschied zu JMP und BRA ist, dass bei Unterprogrammaufrufen zusätzlich die Adresse im Programmcode, die der JSR oder BSR Instruktion jeweils folgt, für einen späteren Rücksprung in das "aufrufende" Programm gespeichert.                                                                                                                                                                                                                                                                                                             | `JSR d32`<br>oder<br>`JSR d16`                      |
| BSR                                                                 | = **B**ranch to **S**ub**R**outine<br><br>Sprung zu Unterporgamm (relativ). <br>s. obere Zeile.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | BSR d16<br>oder<br>BSR d8                           |
| RTE                                                                 | = **R**e**t**urn from **E**xception<br><br>Lädt die Rücksprungadresse vom Stack in den Programmzähler.<br><br>Befehl wird am Ende eines [[Synchronisation und Interrupthandling#Synchronisationsarten\|ISRs]] ausgeführt                                                                                                                                                                                                                                                                                                                                                                                                  |                                                     |
| RTS                                                                 | = **R**e**t**urn from **S**ubroutine<br><br>Der RTS-Befehl holt die Rücksprungadresse vom Stack (pop-Operation) und lädt sie in den Befehlszähler zurück. <br><br>Der Befehlt wird am Ende eines Unterprogrammaufrufs verwendet.                                                                                                                                                                                                                                                                                                                                                                                          |                                                     |
| NOP                                                                 | = **N**o **O**peration<br><br>Hier passiert nichts außer die Erhöhung von PC (= Programm Counter)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |                                                     |
| CMP                                                                 | = **C**o**mp**are<br><br>Vergleichs- und Testbefehle führen eine Testsubtraktion des Operanden mit<br>einem Vergleichswert durch, ohne einen der Operanden zu verändern. Durch die Testsubtraktion werden aber die Flags der CCR-Registers<br>beeinflusst.<br><br>Der Befehl kann Byte, Wort und Langwort-Operanden vergleichen. <br><br>Eine Subtraktion ist nützlich um zu wissen, ob das Ergebnis negativ oder positiv ist.<br><br>Beim Beispiel ist das Ergebnis positiv, wenn Dn größer ist als Quelle.                                                                                                              | `CMP <Quelle>,Dn`<br><br>Ergebnis = **Dn - Quelle** |
| CMPI                                                                | Wie CMP, nur wird es zum Vergleich eines Konstanten verwendet.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | CMPI                                                |
| **[[Befehle in Assembler#Schleifen\|Schleifen]]-Relevante Befehle** | ---                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | ---                                                 |
| MOVEQ.x                                                             | Die Konstante ist ein Teil des Opcode-Wortes. Jede MOVEQ- Befehlszeile benötigt so nur **2 Byte**, was der Mindestlänge eines Maschinencodes einer 68000-Befehlszeile entspricht.<br><br>Die Ausführungszeit ist schneller, als die Ausführungszeit des entsprechenden MOVE-Befehls. Alleine schon deshalb, weil der Prozessor weniger Speicherzugriffe durchführen muss, um den Maschinencode zu laden.<br><br>Verwendet wird der MOVEQ-Befehl in Verbindung mit der unmittelbaren Adressierung oft, um einen Schleifenzähler in ein Datenregister zu speichern.<br><br>x steht für [[#Datenlänge\|Byte, Wort, Lang]]    | `MOVEQ #$3F, D3`                                    |
| ADDQ.x                                                              | Mit dem ADDQ-Befehl kann eine Konstante, deren Wert zwischen 1 und 8 liegt, zu einem Byte-, Wort- oder Langwortoperanden addiert werden. <br><br>Findet Verwendung vorallem bei [[Befehle in Assembler#Schleifen\|Schleifen]] und wird dem ADD-Befehl vorgezogen, weil es schneller und kompakter ist.<br><br>x steht für [[#Datenlänge\|Byte, Wort, Lang]]                                                                                                                                                                                                                                                               | `ADDQ #<data,<ea>`                                  |
| SUBQ                                                                | Der SUBQ-Befehl dient dazu von einem Operanden (vom Typ Byte, Wort oder Langwort) eine Konstante zwischen 1 und 8 zu subtrahieren. Ebenso wie<br>der ADDQ-Befehl dem ADD-Befehl ist auch der SUBQ Befehl dem SUB-Befehl vorzuziehen.<br><br>Findet Verwendung vorallem bei [[Befehle in Assembler#Schleifen\|Schleifen]].                                                                                                                                                                                                                                                                                                 | `SUBQ #<data>,<ea>`                                 |
| DBRA                                                                | = **D**ecrement and **Bra**nch<br><br>DBRA arbeitet mit Befehlszähler-relativer Adressierung. Die Adresse des Sprungziels wird also berechnet aus dem Stand des Befehlszählers (genauer: PC + 2) und dem vorzeichenbehafteten Wortabstand.<br><br>Der Befehl DBRA dient zum Aufbau von Zählschleifen der Schrittweite −1. Schleifenvariable ist immer das untere (d. h. niederwertige) Wort eines Datenregisters. Bei jedem Aufruf eines DBRA-Befehls werden die folgenden beiden Aktionen ausgeführt:<br><br>1. Vermindere zuerst den Zähler (im Datenregister) um eins.<br>2. Falls Zähler ungleich −1 springe zu Ziel. | `DBRA Dn,Ziel`                                      |
| [[Befehle in Assembler#Bedingte Befehle\|Bedingte Befehle]]         | ---                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | ---                                                 |
| Bcc                                                                 | Ein bedingter Sprungbefehl.<br><br>cc steht für die Bedingung<br><br>Für weitere Informationen den Abschnitt [[#Bedingte Befehle]] lesen.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |                                                     |
| Scc                                                                 | Ein bedingter Setzbefehl<br><br>cc steht für die Bedingung                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |                                                     |
| DBcc                                                                | Hier steht cc für eine Abbruchbedingung. Die DBcc-Instruktion bricht ab, falls entweder der Zähler = −1 ist, oder falls die durch cc spezifizierte Abbruchbedingung auftritt.                                                                                                                                                                                                                                                                                                                                                                                                                                             | `DBcc Dn, Ziel`                                     |
| [[Befehle in Assembler#Stacks\|Stacks]]                             | ---                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | ---                                                 |
| PEA                                                                 | Verwendet effektiv den Stack.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                                                     |

## Sprungbefehle
> [!NOTE] Sprungbefehle
    > Soll ein Maschinenprogramm nicht beim nächsten Befehl, sondern an einer anderen Stelle fortgesetzt werden, so muss der Programmzähler mit einer anderen Adresse geladen werden. Dies bewerkstelligen Sprungbefehle und als weitere Möglichkeit Unterprogrammaufrufe.
> 
> Die Sprungziele werden in der Assemblerprogrammierung meist als symbolische Adressen (sprich: Labels) angegeben; bei der Assemblierung werden dann die Labels durch entsprechende Zahlenwerte ersetzt
## Bedingte Sprungbefehle


> [!NOTE] Was sind bedingte Befehle?
    > Bei der Ausführung eines bedingten Befehls wird das CCR-Register (Flag-Register) im Steuerwerk geprüft. Der bedingte Befehl wird nur dann ausgeführt, wenn die spezifizierte Bedingung, die sich in einem oder mehreren Flags des CCR-Registers widerspiegelt, erfüllt ist. 
> 
> Ist die Bedingung nicht erfüllt, wird stattdessen der nächste Befehl ausgeführt (Lineare Programmausführung)
> Die Sprungadressierung der bedingten Befehle sind relativ. Das Zweierkomplement ist zu beachten, siehe hierzu [[Adressierung#Die Adressierungsarten|Adressierung]]. 
> 
> Der Assembler berechnet beim Übersetzungsvorgang den Abstand (=Adressdistanz, vorzeichenbehaftete 8-Bit bis 16-Bit Zahl)des aktuell bearbeiteten Befehls zum Sprungziel und trägt diesen Abstand um zwei vermindert als relative Sprungadresse in den Maschinenbefehl ein.
### Arten von Bedingungen

| Gruppe                                       |
| -------------------------------------------- |
| 1. Abfrage einzelner Flags                   |
| 2. Vergleich vorzeichenbehaftetet Dualzahlen |
| 3. Vergleich vorzeichenloser Dualzahlen      |
### Bedingungen und ihre Sprungbefehle
![[Pasted image 20250814152420.png]]

### Beispiel
> [!example]
>  Einseitige bedingte Anweisung. DIe Realisierung basiert daher auf einer bedingten Sprunganweisung.
 ![[Pasted image 20250814154508.png]]
>
> Zweiseitige bedingte Anweisung. Die Realisierung basiert auf einer bedingten und einer unbedingten Sprunganweisung. Letztere ist erforderlich, um den Programmblock beim Label "Bpruef1" nicht auch noch zu durchlaufen.
 ![[Pasted image 20250814155643.png]]
 
> [!FAQ]  Welche Aktionen werden bei Unterprogrammaufrufen durchgeführt?
    > 
 >
 >1. Inhalt / Adresse / Rücksprungadresse des Befehlszählers wird als Langwort auf den Stack gespeichert (Push-Operation)
>2. Der Befehlszähler mit der Adresse des auszuführenden Unterprogramms wird geladen. Es werden d32, d16 oder d8 ausgewertet.
>3. Unterprogramm wird ausgeführt
>4. Die Ausführung des Unterprogramms endet immer mit dem Rücksprungbefehl RTS.
>5. Das Programm, das das Unterprogramm aufgerufen hat, wird nun fortgesetzt.

> [!example] Unterprogrammaufruf
    > ![[Pasted image 20250810182929.png]]

> [!Hint] Persönlicher Hinweis
    > Das Beispiel erinnert mich an einen Kapitel in TGI mit den LOOP-Programmen. Es war Kapitel 4

# Assembler-Struktur
> [!NOTE]
    > Es ist ratsam zu versuchen, übersichtliche Programme in strukturierter Weise zu erstellen,
indem man Assembleranweisungen nach bestimmten strukturierten Mustern zusammenfügt und „denkt“.
>
Dabei helfen die Methoden **Pseudocode-Notation** oder **Flussdiagramm** als
Zwischenstufe für die Erstellung komplexer Assembler-Programme. Jede
Methode hat ihre Vor- und Nachteile:

## Vor- und Nachteile Pseudocode und Flussdiagramm

| Methode             | Nachteile                                                          | Vorteile                                             |
| ------------------- | ------------------------------------------------------------------ | ---------------------------------------------------- |
| Pseudocode-Notation | - Wird zu unübersichtlich bei sehr viel Text und Verschachtelungen | - Kompakter als Flussdiagramm<br>- Direkter Plan für |
| Flussdiagramm       | - Weniger explizit bei "Code-Logik"                                | - Explizite Darstellung des Kontrollflusses          |
## Vergleich: Pseudocode und Flussdiagramm

| Pseudocode                           | Flussdiagramm                        |
| ------------------------------------ | ------------------------------------ |
| ![[Pasted image 20250810191433.png]] | ![[Pasted image 20250810191450.png]] |
| ![[Pasted image 20250810191510.png]] | ![[Pasted image 20250810191538.png]] |
## Vergleichs- und Testbefehle
> [!NOTE]
    > Zur Umsetzung dieser strukturierten Anweisungen werden Vergleichs- und
Testbefehle und bedingte Sprünge benötigt. Vergleichs- und Testbefehle führen eine Testsubtraktion des Operanden mit einem Vergleichswert durch, ohne einen der Operanden zu verändern.

# Schleifen

| Name         | Bedeutung                                                                                                                                                                                                                        | Beispiel (Pseudocode)                                                              |
| ------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| While        | Die Prüfung der Terminierungsbedingung findet hier am Schleifenanfang statt. Block A wird nicht ausgeführt, wenn die Terminierungsbedingung nicht erfüllt ist. Schleifen dieses Typs werden auch „abweisende Schleifen“ genannt. | 1: while Bedingung do<br>2: Block A<br>3: end while                                |
| Repeat-Until | Die Terminierungsbedingung wird am Ende der Schleife kontrolliert. Schleifen dieses Typs werden immer mindestens einmal durchlaufen (nicht abweisend)                                                                            | 1: repeat<br>2: Block A<br>3: until Bedingung                                      |
| For-Schleife | Mit jedem Schleifendurchlauf wird der Schleifenzähler um die Schrittweite verändert.<br>Die Schleife wird so oft durchlaufen, bis der Stand des Schleifenzählers den Endwert<br>erreicht hat                                     | 1: for i = Anfangswert to Endwert step Schrittweite do<br>2: Block A<br>3: end for |
## Beispiel

| Pseudocode                                                                | Assembler                                                                                                                                |
| ------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| 1. for i = 99 to 0 step −1 do<br><br>2. Schleifenkörper<br><br>3. end for | 1. MOVE.W #99,D0 ; 99 = Anzahl Schleifendurchläufe - 1<br><br>2. loop: ... ; Schleifenkörper<br><br>3. DBRA D0,loop ; Schleifenkontrolle |

# Stack
> [!NOTE] Was ist ein Stack und wie ist es aufgebaut?
    > Ein Stack (häufig auch Stapel, Stapelspeicher oder Kellerspeicher genannt) bezeichnet eine Datenstruktur, wo Elemente nur von oben aufgelegt (Push-Operation) und entfernt (pop-Operation)werden können. 

| Push-Operation                       | Pop-Operation                        |
| ------------------------------------ | ------------------------------------ |
| ![[Pasted image 20250817213839.png]] | ![[Pasted image 20250817213850.png]] |

## Wo hat es seine Anwendung?
> [!NOTE]
    > Findet Verwendung vor allem bei der Speicherung bei Sprunganweisungen, z.B. Rücksprungadressen.
    > 
    > Nehmen wir als Beispiel die folgende Situation: Unterprogramm A ruft Unterprogramm B auf und Unterprogramm B ruft Unterprogramm C auf und C wiederum ruft Unterprogramm D auf. Bei jedem Unterprogrammaufruf muss die Rücksprungadresse gespeichert werden: Zuerst muss die Rücksprungadresse zurück nach A gespeichert werden, dann die nach B und dann erst die nach C. Nach Abarbeitung von Unterprogramm D wird zuerst die Rücksprungadresse nach C benötigt (also die zuletzt gespeicherte Information), dann erst die nach B und zuletzt erst die zuerst gespeicherte Adresse zurück nach A.

### Mit Stack Werte speichern
> [!NOTE]
    > Für rekursive Aufrufe ist ein Stack nützlich, um Werte zu speichern. Unter anderem:
    > 	- Registerwerte
    > 	- Parameter
    > - 
    >   Dabei läuft es meistens folgendermaßen ab:
    >   1. Programm läuft bis zu einem Subroutinen-Aufruf, Register wird im Stack gepeichert. 
    >   2. Das Programm läuft woanders weiter.
    >   3. Das Programm macht weiter, wo es aufgehört hat und lädt die Werte aus dem Stack.

### Parameterübergabe - Wie und worüber werden Werte übergeben?
#### Mögliche Orte:

| Werte in Datenregistern                                                                                                                                                                                                                                                                                                          | Werte über den Stack                                                                                                                                                                                                                                                                                                                      |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| In Maschinenprogrammen bevorzugt man oft eine Parameterübergabe in Registern. Das ist die zeiteffizienteste Möglichkeit der Parameterübergabe;<br>Zugriffe auf prozessorinterne Register sind um Größenordnungen schneller als Zugriffe auf den (i. A.) prozessorexternen Hauptspeicher, der unter Anderem<br>den Stack enthält. | Der Stack gibt keine Einschränkun an die Anzahl der Parameter vor, die zu übergeben sind.<br><br>Der Stack wird meistens zu Speicherung des Prozessorstatus und der lokalen Variablen eines Unterprogramms benutzt. Man kann den Stack als zur Verieinheitlichung für Daten- Status- und Parameterzugriff-relevante Mechanismen anwenden. |

##### Arten von Parametern

| Name              | Bedeutung                                                                                                                                                                                                                                                                                                              |
| ----------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Call-by-value     | Der Wert der Variable wird in den Datenbereich des Unterprogramms kopiert. Das Unterprogramm arbeitet mit der Kopie des Wertes und der eigentliche Wert bleibt unverändert.<br><br>Den Programmteil, der das Unterprogramm aufruft, nennt man Oberprogramm; Synonyme sind „Hauptprogramm“ oder „aufrufendes Programm“. |
| Call-by-reference | Die Adresse (Referenz) des Wertes wird gespeichert.<br><br>Unter- und Oberprogramm arbeiten mit dem selben Wert.                                                                                                                                                                                                       |


## Umsetzung im Assembler
> [!NOTE]
	> A7 wird speziell als Stackpointer reserviert. Die Adressierungsart Register-indirekt mit Postinkrement und Prädekrement ist ideal für den Aufbau eines Stack. Siehe (A7)+ und –(A7).
	> 
	> Der Stack wird automatisch genutzt bei Unterprogrammaufrufen. Der Programmierer muss sich hier nicht darum kümmern.


