---
aliases: []
---
# Aufgabe 1.3
## a

``` sql
SELECT land FROM kunden WHERE land != 'USA' AND land != 'Kanada' ORDER BY land
```

```sql
SELECT land FROM kunden WHERE land NOT IN ('Kanada', 'USA') ORDER BY land
```

## b
```sql
SELECT kontaktperson, position FROM kunden WHERE position IN ('Inhaberin', 'Inhaber') 
```

## C
```sql
SELECT * FROM kunden WHERE land IN ('Deutschland', 'Frankreich')
```

## d
```sql
SELECT artikelnr, kategorienr FROM artikel WHERE artikel.kategorienr != 2
```

## e
```sql
SELECT bestellungen.bestellnr, kunden.firma, bestellungen.frachtkosten FROM kunden, bestellungen 
WHERE firma != 'Ernst Handel' AND frachtkosten > 100
```

# Aufgabe 1.4
## a
```sql
UPDATE artikel 
SET lieferantennr = 7
WHERE artikelnr = 1
```
ODER
```sql
UPDATE artikel 
SET lieferantennr = 1
WHERE artikelnr = 1
```

## b
```sql
UPDATE artikel 
SET einzelpreis = einzelpreis * 1.1
WHERE artikelname = 'Chai'
```

## c
```sql
UPDATE artikel
SET einzelpreis = einzelpreis * 1.5
WHERE kategorienr IN (
	SELECT kategorienr FROM kategorien WHERE kategoriename = 'Gewürze'
)
```
ODER 

```sql
UPDATE artikel
SET einzelpreis = einzelpreis * 1.5
WHERE kategorienr = 2
```

| Alt                                  | Neu                                  |
| ------------------------------------ | ------------------------------------ |
| ![[Pasted image 20251002153204.png]] | ![[Pasted image 20251002153445.png]] |

## d
```sql
UPDATE artikel
SET mindestbestand = mindestbestand * 0.5
WHERE einzelpreis > 15
```

| Alt                                  | Neu                                  |
| ------------------------------------ | ------------------------------------ |
| ![[Pasted image 20251002154506.png]] | ![[Pasted image 20251002154613.png]] |
## e
```sql
INSERT INTO artikel (artikelnr, artikelname, lieferantennr, kategorienr, liefereinheit, einzelpreis)
VALUES (0, 'Polohemd', 1, 1, 0, 20)
```

## f
```sql
INSERT INTO lieferanten (lieferantenNr, firma)
VALUES (30, 'Duck');

UPDATE artikel 
SET lieferantennr = (
SELECT lieferantennr FROM Lieferanten WHERE firma = 'Duck')
WHERE artikelname = 'Polohemd';

/* Nochmal zum checken, ob es funktiorniert hat */
SELECT firma FROM artikel, lieferanten WHERE
artikel.lieferantennr = lieferanten.lieferantennr AND artikel.artikelname = 'Polohemd'
```

## g
```sql
DELETE FROM artikel
WHERE artikelname = 'Polohemd';

DELETE FROM lieferanten
WHERE firma = 'Duck';
```

## h
```sql
DELETE FROM bestelldetails
WHERE bestellnr IN (
SELECT bestellnr FROM bestellungen WHERE kundencode = (
SELECT kundencode FROM kunden WHERE firma = 'Ernst Handel'
) 
);

DELETE FROM bestellungen WHERE kundencode = (
SELECT kundencode FROM kunden WHERE firma = 'Ernst Handel'
);

```

| Vorher                               | Nachher                              |
| ------------------------------------ | ------------------------------------ |
| ![[Pasted image 20251002165302.png]] | ![[Pasted image 20251002165319.png]] |
