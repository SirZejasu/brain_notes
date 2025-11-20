---
tags:
  - reko
  - technische_informatik
  - tgi
sticker: ""
banner_y: "48.5"
---
# Geschichte des PCs
> [!NOTE]
    > Der erste frei programmierbare und funktionstüchtige Rechner wird Conrad Zuse zugeschrieben.
    >  
    >  Es hieß Z3 und verwendete Relais als Schaltelemente.
    >  
    >  Es wurden Relais als "Schaltelemente" verwendet.
    >  
    >  Die erste Generation verwendete Vakuum Röhren als "Schaltelemente"
    >  
    >  Die zweite und bis heute nachfolgenden Generation verwenden [[Transistoren und Speicher|Transistoren]] 

## Mooresches Gesetz
> [!NOTE] Mooresches Gesetz
    > Alle 12 - 24 Monate verdoppelt sich die Anzahl an Transistoren auf der Chipfläche.
    > ![[Pasted image 20250921213953.png]]

## CPU
> [!NOTE]
    > Ein Mehrkernprozessor verwendet mehrere Kerne, um schneller zu rechnen und um Hitze zu vermeiden. Das ist besser als nur die Taktfrequenz zu erhöhen.
    > 2 Kerne rechnen doppelt so viel als 1.
    > ![[Pasted image 20250921214521.png]]
# IAS / Von-Neumann-Architektur
> [!NOTE] Allgemein
    > IAS verwendet die Von-Neumann-Architektur.
    > Die Architektur besagt, dass bei einem universal
programmierbaren Rechner Programmdaten (also die Programmierbefehle)
im gleichen Speicher liegen wie die Daten, die bearbeitet werden. Und zwar
prinzipiell durchaus wahlfrei und durcheinander. Auch wenn man sie per
Convention doch in getrennte Bereiche des Speichers legt.
    > 
    > Es war ein nicht kommerzieller Forschungsrechner entwickelt von Princeton.
## Haupteinheiten der IAS
> [!Definition] Von-Neumann-Architektur
> ![[Pasted image 20250729173625.png]]
> 
> ![[Von-Neumann-Architektur-Anhang#Haupteinheiten der IAS]]
>
>![![Studium/_Medieninformatik/6.Semester/Module/TGI/K01/Anhänge/#*Table]]
## Struktur von Wörtern bei IAS
> [!NOTE] Wörterstruktur des IAS: Rechte und Linke Instruktion
>  Programmdaten / Instruktion bestehen meistens aus 2 Wörtern 40 Bits. Die Rechte und die Linke Instruktion. Diese Zusammsetzung erhöht die Rechengeschwindigkeit, da man nun nur einmal die Daten lesen muss statt zweimal. Ein Abruf der Daten aus dem [[#Haupteinheiten|Hauptspeicher]] ist länger als aus den [[#Register in der CPU|Registern]].
> ![[Pasted image 20250731184049.png]]
> > 


## IAS
> [!NOTE] Register von IAS
    > Register (oder Buffer) sind relativ kleine Speicher von Prozessoreinheiten. Sie nehmen ein Wort auf und ermöglichen einen schnelleren Zugriff als der Hauptspeicher. Heutzutage hat ein CPU eine größere Anzahl an Register und sind schneller als ältere.
> ![[Pasted image 20250731183342.png]]
> 
## Register des IAS und Motorolla 68k

| Name                                           | Bedeutung in IAS                                                                                                                                                                                                                                       | Besonderheit in Motorolla 68k                                                                                                                                                                                                                                                          | Beispiele / Modelle                                                                                                                                                                                                                 |
| ---------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Memory buffer register (MBR)                   | Das Memory buffer register (MBR) enthält ein Wort, das in den Speicher geladen oder an eine Ein/Ausgabe-Einheit gesendet werden soll. Es ist der zentrale Verteilpunkt zwischen Hauptspeicher und CPU. Manchmal auch Verteilpunkt für die I/O Einheit. |                                                                                                                                                                                                                                                                                        |                                                                                                                                                                                                                                     |
| Memory adress register (MAR) / Adressregister  | Das Memory address register (MAR) enthält die Adresse, an die das Wort im MBR geschrieben werden soll. Deren Verwendungen beeinflussen die Control-Block Flags nicht!<br><br>                                                                          | Der 68000 hat nur 24 Adressleitungen auf den Adressbus herausgeführt (HW-Aufwand reduzieren!). Deshalb sind nur $2^{24}$, also 16.777.216 Adressen unterscheidbar. Da jede Adresse ein bestimmtes Byte im Speicher adressiert, sind also maximal 16 MByte große Speicher adressierbar. |                                                                                                                                                                                                                                     |
| Instruction register (IR)                      | Das Instruction Register (IR) enthält einen 8-Bit-Opcode, der als nächstes ausgeführt werden soll. Dessen Inhalt steuert direkt die Schaltkreise, die die Instruktion umsetzen.                                                                        |                                                                                                                                                                                                                                                                                        |                                                                                                                                                                                                                                     |
| Instruction Buffer Register (IBR)              | Das Instruction Buffer Register (IBR) speichert die rechte Seite einer Instruktion temporär.                                                                                                                                                           |                                                                                                                                                                                                                                                                                        |                                                                                                                                                                                                                                     |
| Accumulator (AC) *und* Multiplier Quotien (MQ) | Der Accumulator (AC) und der Multiplier Quotient (MQ) enthalten temporäre Operanden und Ergebnisse von ALU-Operationen.                                                                                                                                |                                                                                                                                                                                                                                                                                        |                                                                                                                                                                                                                                     |
| PC                                             | Der Program Counter (PC) enthält die Adresse des nächsten Instruktionen-Paars, das aus dem Speicher geholt werden soll.                                                                                                                                | = **P**rogram **C**ounter<br><br>Wie beim IAS enthält es die Adresse der nächsten Instruktion.                                                                                                                                                                                         | ![[Pasted image 20250921135918.png]]                                                                                                                                                                                                |
| CCR                                            | -                                                                                                                                                                                                                                                      | = Condition Code Register<br><br>I.d.R. werden die Bits automatisch durch Maschinenbefehle beeinflusst, die die Datenregister ändern.<br><br>Bit 8 - 15 sind im Benutzermodus gesperrt.<br><br>Informationen über die Flags siehe  [[#Flags und ihre Bedeutung]]<br>                   | ![[Pasted image 20250921135928.png\|200]]<br><br>![[Pasted image 20250921140453.png]]<br><br>Hinweis: "Mit erwähnten Flags" sind hier der Negativ-Flag N und Zero-Flag Z gemeint, wie in [[#Flags und ihre Bedeutung]] beschrieben. |
## Ablauf einer Instruktion im MBR
> [!FAQ] Ablauf Instruktion
> Ist das Wort bestehend aus zwei Instruktionen, so wird es in der CU weitervearbeitet. 
> 1. Dabei wird der Opcode gelöscht und im IR geladen.
> 2. Der Adressteil wird in das MAR geladen. Somit zeigt die Adresse im MAR zur nächsten Speicheradresse im Hauptspeicher.
> 3. Die Zweite Instruktion wird zwischengespeichert im IBR. 
>
 In modernen CPUs speichert man mehrere Instruktionen.

## Ablauf von Daten im MBR
> [!FAQ] Ablauf Daten
    > Daten im MBR werden im ALU bearbeitet. Ein MBR kann nur ein Operand speichern. Bestehen die Daten aus zwei Operanden, passiert folgende Dinge: 
    > 1. Der Inhalt von MBR wird im AC geladen.
    > 2. Im MBR wird der nächste Operand geladen.
    > 3. Über die logischen Schaltkreise werden jetzt die gwünschte Operation durchgeführt.
    > 4. Das Erebnis steht im AC. Von hier wird es entweder in M gespeichert oder ausgegeben über I/O

## Programmdaten / Instruktion

| Name    | Bedeutung in IAS                                                                                                                                                                                                            | Besonderheit in Motorlla 68k                                                                                   |
| ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| OpCode  | = **Op**eration **Code**<br><br>Gibt an, welche möglichen Operation im nächsten Schritt ausgeführt werden soll.<br><br>8bit, also $2^{8}$ Mögliche [[Befehle in Assembler#Liste der Assembler-Befehle\|Assembler-Befehle]]. | Siehe [[#Struktur von Wörtern bei Motorola 68k]]<br><br>16 Bit lang, also $2^{16}$ mögliche Assembler-Befehle. |
| Adresse | 12 Bit Teil des Codes. Enthält entweder Adresse oder Daten.<br><br>Als Adresse wird ein [[Befehle in Assembler#Datenlänge\|Wort]] (2 Byte) im Hauptspeicher referenziert.                                                   |                                                                                                                |
# Ablauf eines Fetch-Decode-Cycle des IAS
> [!NOTE] Ablauf eines IAS
> Es ergibt sich eine wichtige grundlegende Erkenntnis:
• Die CPU verarbeitet das Programm in mehreren Zyklen.
• Erster Zyklus: Fetch (Instruktion holen)
• Zweiter Zyklus: Decode (Instruktion dekodieren, was ist zu tun?)
• Dritter Zyklus: Execute (Die gewünschte Aktion durchführen)
• Es ergibt sich der sogenannte grundsätzliche
Fetch-Decode-Execute-Cycle
• Danach kann die nächste Instruktion geholt und bearbeitet werden, deshalb als
Zyklus (Cycle) bezeichnet
    > ![[Pasted image 20250731190409.png|700]]
    > ![[Pasted image 20250917192514.png|700]]

## Detaiierte Darstellung
> [!NOTE] Beispiel einer Ausführung eines Programms
    > ![[Pasted image 20250924223918.png]]
    > 

| Name                                  | Bedeutung                                                                                                                                                                                                                                                                                                   |
| ------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Fetch Instruction (fi)                | Wenn ein Rechner ein Programm ausführt, wird eine Instruktion aus dem Hauptspeicher geladen (Instruction Fetch)<br><br>Die geladene Instruktion wird zunächst in einem prozessorientierten Register gespeichert, dem [[CPU-Aufbau und Geschichte#Registernamen und ihre Bedeutung\| Instruction Register]]. |
| Fetch Operand (fo)                    | Ein Operand der sich im Hauptspeicher befindet wird in den Prozessor zur weiteren Verarbeitung geladen.                                                                                                                                                                                                     |
| Instruction Address Calculation (iac) | Berechne die Adresse der nächsten auszuführen- den Instruktion. Beim MC68000 muss dafür die Länge der letzten Instruktion bzw. das Sprungziel der letzten Instruktion mit in Betracht gezogen werden.                                                                                                       |
| Calculate Operand Address (coa)       | Die effektive Adresse eines Operanden wird berechnet. Hierbei kann es evtl. notwendig sein, arithmetische Operationen auszuführen.                                                                                                                                                                          |
| Execution Instruction (ei)            | Der Prozessor führt die Instruktion aus.                                                                                                                                                                                                                                                                    |
| Decode Instruction (di)               | Der Instruktionstyp (also der Opcode) wird bestimmt und die zum Opcode gehörenden Operanden analysiert.                                                                                                                                                                                                     |
| Write operant (wo)                    | Bei der Befehlsausführung des letzten Schrittes können Ergebnis- se entstehen, die im Hauptspeicher abgelegt werden sollen; die entsprechende Schreib- Operation wird in diesem Schritt ausgeführt.                                                                                                         |
> [!example] Klausurrelevant
    > ![[Pasted image 20250924223551.png]]
    > ![[Pasted image 20250924134857.png]]
## Trivia
> [!Tldr] Wartezeit und Takt
    > Aufgrund von physikalischen und technischen Begrenzungen ist die Schaltung von Transistoren begrenzt. Es braucht seine Zeit, bis Daten gelesen und geladen werden. Es muss also erst gewartet werden, bevor eine nächste Operation durchgeführt werden kann. Dafür hat man eine Wartezeit eingeführt: 
    > Ein Takt von 1GHz bedeutet, dass nach jedem Schritt eine Nanosekunde gewartet wird, bevor es weiter macht. Somit stellt man sicher, dass die Daten sicher gelesen und geladen werden.
    > 
    > Die CPU taktet zwischen Registern schneller als zum M oder IO.

# Weiteres Klausurrelevant
## Motorolla 68000
### Register
Der Motorolla hat ähnliche Register wie der IAS, mit einigen Besonderheiten.

Die Register sind in folgende Gruppen aufgeteilt:

| Adressregister         | 32 Bits            |
| ---------------------- | ------------------ |
| **Datenregister**      | 32 Bits            |
| **Spezielle Register** | (UnterschiedlichA) |

> [!NOTE] Programmmodell Motorolla 6800
 > ![[Pasted image 20250918220216.png]]



##### Flags und ihre Bedeutung
> [!Definition]
> Operation, wie arithmetische- und Vergleichoperationen auf Datenregister, können auf dem CCR bestimmte Bits (= **Flags**) beeinflussen.
> 
> 
Sie zeigen bestimmte Eigenschaften der Ergebnisse der Ergebnisse der letzten arithmetischen Operation. Sie werden also von der ALU gesetzt.
>
Sie finden häufig Verwendung bei bedingten [[Befehle in Assembler#Sprungbefehle|Sprungbefehlen]].

| Flags           | Bedeutung                                                                                                                                                                                                 |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Negativ-Flag N  | wird 1, wenn das Ergebnis der letzten Operation negativ war. Das heißt bei einer Zahlendarstellung im 2er-Komplement wird geprüft, ob das höchstwertige Bit eine 1 enthält.                               |
| Zero-Flag Z     | wird 1 gesetzt, wenn das Ergebnis der letzten Operation<br>gleich Null war oder wenn bei einem Vergleich beide Operanden gleich groß waren.                                                               |
| Überlauf-Flag V | wird 1, wenn eine Bereichsüberschreitung stattgefunden hat.<br>Dieses Flag wird<br>z. B. gesetzt, wenn bei einer Wortbreite von n Bit das Ergebnis größer als $2^{n-1}$ oder kleiner als $−2^{n−1}$  ist. |
| Carry-Flag C    | wird auf 1 , wenn ein Übertrag beim höchsten Bit entsteht oder wenn bei einer Subtraktion vom nächst höheren Bit geborgt werden muss.<br><br>Auch Übertrags-Flag genannt                                  |

### Programmodell Motorolla 68k 
### Struktur von Wörtern bei Motorola 68k

> [!NOTE] Allgemeine Struktur eines Maschinecodes im Assembler
> Anders als beim [[CPU-Aufbau und Geschichte#Struktur von Wörtern bei IAS|IAS]] haben die Wörter keine feste länge.
> Sie sind mindestens ein Wort (2 Bytes) lang und höchstens 5 Worte (10 Bytes) lang.
> 
> Die untere Abbildung zeigt grob die Struktur eines Maschinencodes
![[Pasted image 20250919143728.png]] 
> 
> Die Bezeichnung ist gleich wie bei [[CPU-Aufbau und Geschichte#Programmdaten / Instruktion|IAS-Wörtern]] 
### Datenlänge
> [!callout]
    > Das "x" in der Syntax steht für die Datenlänge, die kopiert werden soll.

| Namen    | Bits | Bytes | Hexadezimalziffern | Wörter             |
| -------- | ---- | ----- | ------------------ | ------------------ |
| Byte     | 8    | 1     | 2                  | $\frac{1}{2}$ Wort |
| Word     | 16   | 2     | 4                  | 1 Wort             |
| Langwort | 32   | 4     | 8                  | 2 Wörter           |

# Vorzeichenbehaftete Binärzahlen
> [!NOTE] Zweierkomplement
> Der führende Bit ist der Bit ganz links.
> 
    > Positive Zahlen haben eine führende 0
    > 
    > Negative Zahlen haben eine führende 1.
![[Pasted image 20250921141450.png]]

## Hilfreiche Formel
> [!NOTE]
    > Von mir abgeleitete Formel aus dem Graphen oben.

| Anwendung                              | Formel + Angehensweise                                                                                                                                                                                                                                                                                 | Beispiel                                                                                                          |
| -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------- |
| Die negative Zahl herausfinden<br><br> | 1. Variable **a** = Zahl als positiv.<br><br>2. Variable **b** = Die höchstmögliche **Anzahl der Zustände** durch Anzahl der Bits -> $2^n$, z.B. $2⁸ = 256$<br><br>3. **Ergebnis** = $b - a$<br><br>4. **Ergebnis** als Binärzahl eingeben. Wenn vorzeichenbehaftet, entspricht es der negativen Zahl. | 8 Bit großer Speicher.<br><br>1. a = 26<br><br>2. b = $2⁸$ = 256<br><br>3. 256 - 26 = 230<br><br>4. 1110 0110<br> |
## Alternative Angehensweise
![[Pasted image 20250921143126.png]]
## Beispiele

| Binär     | Dezimalziffer | Dezimalziffer Vorzeichenbehaftet |
| --------- | ------------- | -------------------------------- |
| 0001 1010 | 26            | 26                               |
| 1110 0110 | 230           | -26                              |

