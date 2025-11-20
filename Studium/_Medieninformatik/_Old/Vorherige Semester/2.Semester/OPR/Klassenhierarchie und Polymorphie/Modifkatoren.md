#Themen 
#OPR
#Medieninformatik 

---
# Quellen
s. Skript

# Modifikator-Tabelle
> [!hint] Modifikator-Tabelle
> Die Tabelle zeigt Modifikatoren in Java an und wo sie eingesetzt werden können.

|              | Interface | Klasse | Konstruktor | Methode | Methodenparameter | Feld | Statement |
| ------------ | --------- | ------ | ----------- | ------- | ----------------- | ---- | --------- |
| public       | x         | x      | x           |         |                   | x    |           |
| protected    |           |        | x           | x       |                   | x    |           |
| private      |           |        | x           | x       |                   | x    |           |
| static       |           |        |             | x       |                   | x    | x         |
| final        |           | x      |             | x       | x                 | x    |           |
| abstract     | x         | x      |             | x       |                   |      |           |
| native       |           |        |             | x       |                   |      |           |
| transient    |           |        |             |         |                   | x    |           |
| volatile     |           |        |             |         |                   | x    |           |
| synchronized |           |        |             | x       |                   |      | x         |
| strictfp     | x         |        | x           | x        |                   |      |           |

# Zugriff-Tabelle
> [!hint] Zugriff-Tabelle
> Zeigt an, was die Modifikatoren einschränken

| Modifier                       | Class | Package | Subclass | World |
| ------------------------------ | ----- | ------- | -------- | ----- |
| public                         | x     | x       | x        | x     |
| protected                     | x     | x       | x        | N     |
| no modifier(Standard Modifier) | x     | x       | N        | N     |
| private                        | x     | N       | N        | N     | 	

