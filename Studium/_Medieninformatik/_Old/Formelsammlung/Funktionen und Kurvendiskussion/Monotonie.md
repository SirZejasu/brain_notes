#Formelsammlung 
#Medieninformatik 

---
# Quellen
- [YouTube - Matheretter](https://www.youtube.com/watch?v=nqYb7y3N3wQ&ab_channel=Matheretter)
- [Studyflix](https://studyflix.de/mathematik/monotonieverhalten-4227)
- [Mathematrick -  Monotonie berechnen für Funktion](https://www.youtube.com/watch?v=R0zBCociKiI&ab_channel=MathemaTrick)
# Definition
https://www.youtube.com/watch?v=qyj5PQ34Ffw&ab_channel=Matheretter
> [!question] Monotonie
> Die Monotonie definiert den Verlauf des Graphen
>![[Pasted image 20230214154857.png]]

# Bestimmen der Monotonie einer Folge
> [!question] Monotonie von Folgen
> Wenn die Aussage war ist, gilt folgender Satz ($a_{n+1}$ steht für jeden nachfolgenden Wert:
> 
> Funktion | Monotonie
> --- | ---
> $a_{n+1}< a_{n}$ | streng monoton fallend.
>  $a_{n+1} \geq a_{n}$ | monoton wachsend.
>  $a_{n+1} > a_{n}$ | streng monoton wachsend.
>  $a_{n+1} \leq a_{n}$ | monoton fallend.  

> [!example] Monotonie beweisen.
> Hier kommt die Definition hin.

# Monotonie von Funktion
> [!question] Definition
> Die Untersuchung der Monotonie sagt aus, wann der Graph in welchem Bereich fällt und steigt.
>  $f'(x)\geq 0$ = monoton steigend
> $f'(x) \leq 0$ = monoton fallend

> [!example] Vorgehensweise
> ## Schritt 1 Definitionsmenge bestimmen
> Siehe [[Definitionsmenge bestimmen]]
> 
> ## Schritt 2 Ableitungen bilden
> Bestimmen der ersten beiden [[Ableitung]]. Schreib daneben den Definitionsbereich.
> ![[Pasted image 20230226145121.png|500]]
> 
> ## Schritt 3 Extremstellen bestimmen
> Nullstelle der ersten Ableitung.
> ![[Pasted image 20230226145558.png|500]]
> 
> Nullstellenwerte in der zweiten Ableitung eingeben.
> ![[Pasted image 20230226145835.png|500]]
> 
> ## Schritt 4 Monotonieintervalle angeben
> ![[Pasted image 20230226150253.png|500]]
> 
>  ## Wie Keskin es machen würde
> ![[Pasted image 20230226193247.png]]
> 

# Wendepunkt bestimmen
> [!question] Definition
> Der Punkt in einem Graph, wo sich der Verlauf ändert.
>

> [!example] Vorgehensweise
> ## Schritt 1 Ableitungen
> Bestimme die 2. und 3. Ableitung
> ![[Pasted image 20230226143027.png|500]]
> 
> ## Schritt 2 Nullstellen bestimmen
> Bestimme die Nullstellen der 2.Ableitung. Damit bestimmt man den X-Wert des *potenziellen* Wendepunkts.
> ![[Pasted image 20230226143213.png|500]]
> 
> ## Schritt 3 Ist es ein Wendepunkt?
> Mit der 3.Ableitung bestimmen, ob es ein Wendepunkt ist. Die X-Werte aus Schritt 2 eingeben  (Wenn in der Ableitung ein X ist). Wenn das Ergebnis eine Null ist, gibt es kein Wendepunkt.
> ![[Pasted image 20230226143237.png|500]]
> 
> ## Schritt 4 Wo ist der Wendepunkt?
> Gib die X-Werte von Schritt zwei in die ursprüngliche Funktion ein, um den Y-Wert herauszufinden.
> ![[Pasted image 20230226143341.png|500]]
> # Beispiel aus Lerngruppe
> ![[Pasted image 20230305003129.png]]

# Krümmungsverhalten
> [!question] Definition
> Es gibt an, ob ein Graph rechts oder links gekrümmt ist.
> 
> $f''(x) < 0$ = Rechtskure (konkarv)
> $f''(x) >0$ = Linkskurve (konvex)
> 

> [!example] Vorgehensweise
> ## Schritt 1 Ableitung bilden
> 2. [[Ableitung]] bilden.
>   ![[Pasted image 20230226170146.png|500]]
>    
> ## Schritt 2 Ändert sich das Krümmungsverhalten?
> Bei einem Wendepunkt kann sich das Krümmungsverhalten ändern. Deshalb wird nach der Nullstelle in der zweiten Ableitung gesucht.
> In dem Beispiel gibt es kein Wendepunkt.
> ![[Pasted image 20230226170211.png|500]]
> 
>  ## Schritt 3 Bestimmen der Krümmung
>  Wir setzen 0 für x in der zweiten Ableitung ein (Nein, es ist nicht die Nullstelle.)
>  ![[Pasted image 20230226170602.png|500]]
>  
> ## Wie Keskin es will
> ![[Pasted image 20230226204214.png]]
> 
> ## Vorlesung
![[Pasted image 20230215151413.png]]

# Vorlesung
![[Pasted image 20230213183328.png]]