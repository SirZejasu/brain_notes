#Themen 
#Netzwerktechnik 
#IHKPrüfung2022 

---
## Verschlüsselung von Nachrichten

Das Verschlüsseln von Daten soll Unbefugte daran hindern, die Daten zu lesen oder zu manipulieren. Mithilfe eines digitalen Schlüsseln, die normalerweise der befugte Leser besitzt, kann die Nachricht wieder entschlüsselt werden.


### Verschlüsselungsverfahren

### Asymmetrische Verschlüsselung
Sender und Empfänger besitzen jeweils einen öffentlichen und privaten Schlüssel. Der öffentliche wird dazu verwendet, um die Nachricht zu verschlüsseln und kann von jedem verwendet werden. Die Nachricht kann dann nur noch mit dem richtigen private Key des Empfängers entschlüsselt werden.
Die Nachricht des Senders wird mit dem öffentlichen Schlüssel des Empfängers verschlüsselt. Bei einem abhörbaren Kanal ist diese Übertragung sicherer, da selbst beim Auffangen die Nachricht nicht entschlüsselt werden kann, aber dafür langsam bei der Erzeugung.
![[Pasted image 20220420202341 2.png]]



### Symmetrische Verschlüsselung
![[Pasted image 20220420201736 1.png]]

Sender und Empfänger besitzen den selben digitalen Schlüssel zum Entschlüsseln der Daten. Empfägner, die den selben privaten Schlüssel besitzen, können die Daten ebenfalls lesen. Die Übertragung findet schnell statt.


### Hybride Verschlüsselung
Gleicht Nachteile beider Verfahren aus und nimmt beide Vorteile. 
Das asymmtrische Verfahren nutzt man, um einmal den gemeinsamen, privaten sicher Schlüssel auszutauschen. 
Das symmetrische Verfahren wird dann für alle weiteren Übertragung verwendet.
![[Pasted image 20220420202820 1.png]]


Der Empfänger prüft mit dem PSK (Pre-Shared-Key), ob der Wert mit dem des Senders übereinstimmt. Ist das der Fall, wird das Datenpaket weiter verarbeitet.

### Hash-Funktion
Mit der Hash-Funktion wird ein Hash (Prüfsumme) mit fester Länge durch beliebig lange Datensätze generiert.
