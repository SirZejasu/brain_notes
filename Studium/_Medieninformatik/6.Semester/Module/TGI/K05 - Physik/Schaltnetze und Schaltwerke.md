
# Arten von Netzen

| Name                        | Bedeutung                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         | Beispiel                                                                                                                                                                                                                                                                    |
| --------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Kombinatorisch / Schaltnetz | Ein Schaltnetz ist eine Kombination mehrerer kombinatorischer Bausteine (z.B. Oder-Gatter, Und-Gatter, Addier-Gatter, oder Schiebe-Gatter)<br><br>Kombinatorische Bausteine können Daten verarbeiten. <br><br>Ein bestimmtes Eingangssignal ergibt bei diesen Bausteinen immer das gleiche Ausgabesignal. In einigen Prozessoren bestehen [[CPU-Aufbau und Geschichte#Haupteinheiten\|ALUs]] (= Arithmetic Logic Unit) nur aus kombinatorischen Bausteinen.                                                                                                                                                                                                                                                                                                       | ![[Pasted image 20250921193645.png]]<br><br>![[Pasted image 20250917161810.png]]<br><br>Zur besseren Referenz, das hier ist ist ein Multiplexer:<br>![[Pasted image 20250917161908.png]]                                                                                    |
| Sequentiell / Schaltwerk    | Im Gegensatz zu kombinatorischen Bausteinen, können sequentielle Bausteine Zustände speichern. <br><br>Zudem ist das Ausgangssignal zusätzlich abhängig vom gespeicherten Zustand.<br><br>Diese Bausteinen, oder eine Kombination dieser Bausteine bezeichnet man auch als **Schaltwerk**. <br><br>Da die Schaltnetze keine Zustände speichern können, ist der Zustand eines ganzen Prozessors nur über die Zustände seiner sequentiellen Bausteine definiert. <br><br>Ein **Schaltwerk** muss mindestens zwei Eingänge und einen Ausgang haben: Es muss eine Eingangsleitung vorhanden sein, die den gespeicherten Zustand bestimmt und eine Eingangsleitung für den Prozessortakt, über die bestimmt wird, wann der anliegende Datenwert gespeichert wird. <br> | Beispiele für **Schaltwerke** sind Flip-Flops.<br><br>Abstrakte Form eines Schaltwerks, um einen Wert zu speichern.<br>![[Pasted image 20250917162535.png]]<br><br>![[Pasted image 20250917164609.png\|400]]<br><br>Flip Flop:<br>![[Pasted image 20250917165915.png\|400]] |

# Takverfahren
> [!NOTE]
    > 
Um valide Signale am Ausgang von Logikgattern und somit bei Schaltnetzen zu ermöglichen, ist ein Taktverfahren nötig. Das Problem entstammt den bekannten Problem, dass Signale aus unterschiedlich langen "Wegen" zum Ziel kommen. Siehe Beispiel-Bild:
![[Pasted image 20250914170842.png]]
Solche Situationen, in denen temporär die Signalwerte in Gattern aufgrund der teilweise unterschiedlichen Signallaufzeiten verfälscht sind, bezeichnet man in Informatik und Elektrotechnik auch als race condition.

> [!FAQ] Flankengesteuertes Taktverfahren
    > Wir gehen von einem flankengesteuerten Taktverfahren aus, d. h. sämtliche in einem Logikbaustein gespeicherten Werte werden nur während einer Taktflanke aktualisiert.
>
> Damit durch das flankengesteuerte Taktverfahren alle race conditions ausgeschlossen werden können, müssen die Eingänge in alle **Schaltnetze** aus **Schaltwerken** stammen und alle Ausgänge eines **Schaltnetzes** müssen in ein **Schaltwerk** münden.
> 
> An den jeweiligen Eingängen liegen immer die Werte an, die in einem vorhergehenden Taktzyklus geschrieben wurden.
> 
> Es ist folgendes möglich:
> 1. Auslesen eines Registerwertes (Bereitstellen der stabilen Eingangssignale)
> 2. Senden diese Registerwertes durch ein Schaltnetz.
> 3. Zurückschreiben der Ausgabe des Schaltnetzes in das Register (Abspeichern des richtigen Ergebnisses, bevor es überschrieben wird.)
>    
>    Beispiel: siehe Struktur von [[CPU-Aufbau und Geschichte#IAS|IAS]]
>    Das [[CPU-Aufbau und Geschichte#Registernamen des IAS|MBR]] liefert hier die stabilen Eingangssignale, die Artihmetische-Logischen Schaltkreise bilden das Schaltnetz und das richtige Ergebnis wird im [[CPU-Aufbau und Geschichte#Registernamen des IAS|AC]] gespeichert.
>    

## Hz-Frquenzen Tabelle

| Maße                  | in Hz            |
| --------------------- | ---------------- |
| 1 kHz (Kilohertz)<br> | 1000 Hz          |
| 1 MHz (Megahertz)     | 1.000.000 Hz     |
| 1 GHz (Gigahertz)     | 1.000.000.000 Hz |

## Zeit Maßen Tabelle

| Sekunden | Nanosekunden  |
| -------- | ------------- |
| 1        | 1 000 000 000 |
