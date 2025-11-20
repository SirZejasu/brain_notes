---
aliases:
  - "Bussysteme: Struktur von Rechner"
---
# Bussysteme
> [!NOTE]
    > Die CPU wird über verschiedene Arten von Busssystemen an Speicher und Ein-/Ausgabegeräte angeschlossen.
    > ![[Pasted image 20250912175913.png]]
    > 
    > Es werden heutzutage verschiedene Bussysteme benutzt. Der Grund dafür sind die Anforderungen Komponenten, an die das Bussystem koppelt. Langsamere Komponenten dürfen schnellere nicht ausbremsen, weswegen es seperate Bussysteme geben muss.
    > ![[Pasted image 20250912180141.png|500]]


# Busleitung
> [!NOTE] Bus
>  Ein Kommunikationsweg zwischen zwei Blöcken des Rechners bezeichnet. Dabei ist impliziert, dass der Bus viele Bits in einem Taktzyklus transportiert (paralleler Datentransport).
>  
Die Daten werden über einen anderen Bus transportiert als die Adressen – Während also Programm und Daten im von-Neumann System nicht getrennt sind, sind es die Datenübertragung und die Adressierung
    > ![[Pasted image 20250912191956.png]]

## Komponenten im Bussystem

| Name                      | Bedeutung                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| ------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Adressbus                 | Übermittelt Adressen zu Daten im Speicher                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Datenbus                  | Übermittelt rohe Daten                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Steuerbus                 | Hierüber werden Instruktionen zur Taktung und Steuerung der Daten (wie lesen und schreiben) vermittelt.                                                                                                                                                                                                                                                                                                                                                                       |
| Chipsätze                 | Ist die Verbindung mehrerer Büsse. Diese liegt außerhalb des Prozessors auf dem Motherboard.<br><br><br>                                                                                                                                                                                                                                                                                                                                                                      |
| Northbridge & Southbridge | Früher gab es eine Northbridge und Southbridge<br>![[Pasted image 20250912194131.png]]                                                                                                                                                                                                                                                                                                                                                                                        |
| Northbridge               | North war für die sehr schnellen Busse nahe an der CPU zuständig, unter anderem<br>- Hauptspeicher (Wie im Neumann-Architektur zu sehen)<br>- Grafikausgaben<br>  - PCIe: ein aktueller Grafikstandard (in der Version PCIe 16fach)<br>  - AGP war davor der Grafikstandard der Wahl<br><br>Heutzutage gibt es mittlerweile diese Anschlüsse direkt am CPU. Der Prozessorchip selbst enthält jetzt also selbst die "schnellen" Busse:<br>![[Pasted image 20250912194726.png]] |
| Southbridge / Chipset     | Alle anderen Chips wurden hier verlagert, z.B. zur Steuerung von<br>- Audio<br>- Tastatur<br>- Maus<br><br>Dieser wird weiterhin verwendet.                                                                                                                                                                                                                                                                                                                                   |
| Parralele Bussysteme      | Daten werden parallel auf alle Busleitungen gelegt.<br><br>Wenn alle Busleitungen stabil sind, können Daten eingetaktet werden. Dazu muss man auf den Letzten warten.<br>Beispiele sind hier <br>- PATA<br>- SCSI für Festplatten intern / extern                                                                                                                                                                                                                             |
| Serielle Bussysteme       | Wird heutzutage bevorzugt.<br><br>Vorteil: Daten können unabhängig von anderen Komponenten übertragen werden, sodass langsame Komponenten die schnelleren abbremsen.<br>Beispiele hierfür sind<br>- SATA für Festplatten<br>- PCIe<br>- USB<br><br>Es wird auch eine Kombination aus seriell und parralel verwendet: Quick Path Interconnect zwischen CPU und Northbridge, wie bei einer Einlasskontrolle im Stadion.                                                         |
| Speichercontroller        | – Der Speichercontroller lag früher in der Northbridge <br><br>– Später ist er in den Prozessor gerück                                                                                                                                                                                                                                                                                                                                                                        |


> [!NOTE] Breite von Busleitung
    > Datenbusse und Adressbusse müssen nicht gleich breit sein und sind es auch häufig nicht. Siehe 68K: 16 bit und 24 bit.
    > Bei kleinen Datenbusbreiten sind die Adressbusse meist größer, was zu einer komplizierten Adressierung führt.
    > Datenbusse bei Universalrechnern haben seit längerem 64 bit.
    > Adressbusse können kleiner sein, denn man braucht keine Adressierbarkeit von  $2^{64}$ unterschiedlichen realen Adressen
    > ![[SC.png]]

## Beispiel eines Bussystems
![[Pasted image 20250912184559.png|550]]  ![[Pasted image 20250912184537.png|700]] 

