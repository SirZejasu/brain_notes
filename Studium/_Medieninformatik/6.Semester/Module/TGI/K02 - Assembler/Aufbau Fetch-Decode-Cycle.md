---
tags:
  - aufbau-fetch-decode-cycle
  - technische_informatik
  - tgi
sticker: ""
banner_y: "48.5"
---


# Befehlszyklus
![[Pasted image 20250801180608.png]]

## Befehlszyklus im Detail
![[Pasted image 20250801175520.png]]

## Ablauf eines Befehlzyklus mit Erklärung

| Schritt                                  | Erklärunng                                                                                                                                                                                          |
| ---------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1. Instruction Address Calculation (iac) | Berechne die Adresse der nächsten auszuführenden Instruktion. Beim MC68000 muss dafür die Länge der letzten Instruktion bzw. das Sprungziel der letzten Instruktion mit in Betracht gezogen werden. |
| 2. Fetch Instruction (fi)                | Die nächste auszuführende Instruktion wird in ein prozessorinternes Register geladen.                                                                                                               |
| 3. Decode Instruction (di)               | Der Instruktionstyp (also der Opcode) wird bestimmt und die zum Opcode gehörenden Operanden analysiert.                                                                                             |
| 4. Calculate Operand Address (coa)       | Die effektive Adresse eines Operanden wird berechnet. Hierbei kann es evtl. notwendig sein, arithmetische Operationen auszuführen.                                                                  |
| 5. Fetch Operand (fo)                    | Ein Operand der sich im Hauptspeicher befindet wird in den Prozessor zur weiteren Verarbeitung geladen. Hinweis: Bei zwei Operanden im Speicher wird der Zyklus 4,5 wiederholt!                     |
| 6. Execute Instruction (ei)              | Jetzt, da die Operanden dem Prozessor zur Verfügung stehen, kann die eigentlich Instruktion ausgeführt werden.                                                                                      |
| 7. Write Operand (wo)                    | Bei der Befehlsausführung des letzten Schrittes können Ergebnisse entstehen, die im Hauptspeicher abgelegt werden sollen; die entsprechende Schreib-Operation wird in diesem Schritt ausgeführt.    |
