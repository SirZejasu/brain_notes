#Medieninformatik 
#LDS 
#Thema   

---
# Quelle
- Seite 88 [[LDS Skript.pdf]]
- [[LDS-V-Mitschrieb-Aussagenlogik.pdf|Mitschrieb]]
- https://www.matheretter.de/wiki/aquivalenz
- https://iltis.cs.tu-dortmund.de/nlogspace/#

# Syntax und Semantik

> [!question] Definition
> Das Ziel der Syntax und Symantik ist es, logische Aussagen und Modelle in möglichst simple aber stark-aussagende Ausdrücke umzuformen. Ein Syntax ist eine Zeichenkette einer Aussage. Eine Semantik definiert die Bedeutung einer Aussage in mathematischer Form.


![[1. Syntax und Symantik 2022-11-14 22.21.06.excalidraw]]

Symbole | Bedeutung | Logische "Umgangssprache" und Klassenkalkül | Anmerkung
--- | --- | --- | ---
$\daleth$ | Nicht bzw. Negation | Ersetzt "-", Minus ((a-b) wird zu ($a \land \daleth b$)) und $\overline{a}$ (Wird zu $\daleth a$)  
$\lor$ | Oder bzw. Disjunktion |  $\cup$ | Bindet stärker als $\to$
$\land$ | Und bzw. Konjunktion |  $\cap$ | Bindet stärker als $\to$
$\to$ | Implikation | $a \subseteq c$, "aus... folgt...", "wenn... dann..." | ($a \to b$) = $(\daleth a \lor b)$
$\leftrightarrow$ | Biimplikation |"=", "gleich", "Äquivalent", "genau dann, wenn..." | ($a \leftrightarrow b$) = ($(\daleth a \lor b) \land (\daleth b \lor a)$)
1 | TRUE | | Tautologie
0 | FALSE| Ersetzt $\emptyset$ | Unerfüllbar
gültig | Wenn eine Formel ausschließlich true ist. | Tautologie
Unerfüllbar | Wenn eine Formel ausschließlich false ist. |
erfüllbar | Mindestens einmal true
ungültig | Mindestens einmal false

## Vorlesung
![[Pasted image 20230113200922.png]]

# Abkürzungen
## Tafel
![[Pasted image 20221113173920.png]]
![[Pasted image 20221107085525.png]]
![[Pasted image 20221114204358.png]]

# Implikation und Biimplikation
----
Die Implikation und Biimplikation sind recht simpel. Ihre Funktion können auf der Tafel gelesen werden. Die Implikation kann besser verstanden werden, wenn sie wie im ersten Bild gezeigt umgeformt wird.

---
![[Pasted image 20221107115607.png]]
![[Pasted image 20221107120223.png]]

## Implikation
![[Pasted image 20221114190128.png]]
![[Pasted image 20221114190158.png]]

## Äquivalenz / Biimplikation
![[Pasted image 20221114190227.png]]
![[Pasted image 20221114185958.png]]
![[Pasted image 20221114190035.png]]

# Fachwörter
Tautologie: Es enthält nur Wahrheitswerte. (Es ist gültig)
![[Pasted image 20221114115652.png]]

## Aus Übungen
### Baumstruktur, Negotationsnormalform
![[Aussagenlogik 2022-11-08 22.42.39.excalidraw]]

# Vorlesung
![[Pasted image 20221114185003.png]]
