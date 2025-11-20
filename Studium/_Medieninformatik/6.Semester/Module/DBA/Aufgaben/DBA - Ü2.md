# 2.1
## a
- Visualisierung von Beziehungen zwischen Entitäten
- Entitäten haben Attribute

## b
Enität und Entitättyp
Präsentiert ein Objekt aus der realen Welt.
Ein Entitätentyp ist eine Gruppe von Objekten mit ähnlichen Eigenschaften. Sie werden als Rechtecke dargestellt.

Beziehung bezeichnen simple Assoziation zwischen Entitäten. Es wird als Raute dargestellt.

Attribute sind Eigenschaften von Beziehungen und Entitäten. Sie werden rund dargestellt.

Domäne beschreibt die erlaubten Werte eines Attributs, z.B. Integer.

## c
Primärschlüssel:
Eindeutige Identifikation zu einem Objekt.

Fremdschlüssel:
Ein Objekt kann ein Attribut enthalten, das gleichzeitig ein Objekt ist. Der Fremdschlüssel verweist auf dieses Objekt.

## d
Der Primärschlüssel ist eindeutig ableitbar durch unterstrichene Attribute. 
Der Primärschlüssel der einen Tabelle ist der Fremdschlüssel einer anderen Tabelle, wenn die in einer Beziehung stehen.

Beispiel: 
Professor hat Kürzel.
Professor hat einen Wiss. Mitarbeiter zugeordnet. Einer von beiden Tabellen enthält den Primärschlüssel des anderen als Fremdschlüssel. Es können auch beide jeweils ein Fremdschlüssel haben.

# 2.3
## b
```
CREATE TABLE "Professor" (
kuerzel INTEGER NOT NULL, titel VARCHAR(30), vorname VARCHAR(30) zugeordnet INTEGER
PRIMARY KEY (kuerzel),
FOREIGN KEY (zugeordnet) REFERENCES Wissenschaftlicher_Mitarbeiter(kuerzel)
)

CREATE TABLE ...
```