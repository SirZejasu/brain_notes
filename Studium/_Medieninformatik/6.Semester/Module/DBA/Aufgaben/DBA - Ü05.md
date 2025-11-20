# 5.1
## a
```sql
SELECT MAX(frachtkosten) FROM bestellungen 
```
## b
```sql
SELECT bestellungen.frachtkosten, bestellungen.kundencode, firma
FROM bestellungen, kunden
WHERE frachtkosten = (
SELECT MAX (b.frachtkosten) FROM bestellungen AS b
) AND bestellungen.kundencode = kunden.kundencode 
```

```sql
SELECT Firma
FROM Kunden AS K, Bestellungen AS B
WHERE K.Kundencode = B.Kundencode and
Frachtkosten >= all (SELECT Frachtkosten FROM Bestellungen)
```
## c
```sql
SELECT a.artikelnr, artikelname
FROM artikel AS a
WHERE artikelnr NOT IN (
	SELECT b.artikelnr
	FROM bestelldetails as b
)
```

```sql
SELECT a.artikelnr, a.artikelname
FROM artikel as a
WHERE NOT EXISTS (
	SELECT b.artikelnr
	FROM bestelldetails as b
	WHERE a.artikelnr = b.artikelnr
)
```

## d
```sql
(SELECT Firma, Kontaktperson, 'Kunde' AS Typ
FROM Kunden
WHERE Land = 'Deutschland')
UNION
(SELECT Firma, Kontaktperson, 'Lieferant' AS Typ 
FROM Lieferanten
WHERE Land = 'Deutschland')
```

# 5.2
## a
```sql
SELECT COUNT(artikelnr) As Anzahl_An_Artikel_Ueber_30_Euro  
FROM artikel
WHERE einzelpreis > 30
```

## b
```sql
SELECT COUNT (b.bestellnr)
FROM bestelldetails as b, artikel as a
WHERE b.artikelnr IN (
 SELECT artikelnr
 FROM artikel
 WHERE einzelpreis > 30
)
```

## c
