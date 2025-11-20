#Themen 
#OPR
#Medieninformatik 

---

# Definition
> [!question] .equals()
> .equals vergleicht den Inhalt/Zustands eines Objekts mit einem anderen Objekt, indem es dessen [[(Methode) Hashcode]] vergleicht. Somit ist jedes Objekt mit sich selbst equal.
> 
>  <mark style="background: #D2B3FFA6;">Was sind sind sinnvolle Eigenschaften einer Gleichheitsbeziehung zwischen Objekten?</mark>
>  - <mark style="background: #BBFABBA6;">Reflexivität:</mark> Jedes Objekt ist mit sich selber gleich.
>  - <mark style="background: #BBFABBA6;">Symmetrie:</mark> Wenn ein Objekt A mit einem Objekt B gleich ist, dann ist auch B mit A gleich.
>  - <mark style="background: #BBFABBA6;">Transitivität:</mark> Wenn ein Objekt A mit einem Objekt B gleich ist, und dieses mit einem Objekt C, dann sind auch A und C gleich.
>  - <mark style="background: #BBFABBA6;">Konsistenz:</mark> Wenn ein Objekt A mit einem Objekt B gleich ist und man A und B unverändert lässt, dann sind A und B immer noch gleich.
>  - <mark style="background: #BBFABBA6;">NotNullReference:</mark> Ein Objekt kann nicht gleich mit null sein, da dies gar kein Objekt ist.

> [!hint] Syntax
> ``` java
>public boolean equals(Object obj) {
>
>return (this == obj);
>}
>```


# Beispielcodes
> [!example] Klasse Buch
> ``` java
>/**  
>* Gibt an, ob dieses Buch gleich dem angegebenen Objekt ist.  
>* @param obj Objekt, das mit diesem Buch verglichen wird  
>* @return <code>true</code> genau dann, wenn das angegebene  
>* Objekt ein Buch ist und mit diesem Buch in Titel,  
>* Autor und Erscheinungsjahr übereinstimmt.  
>*/
>  
>public boolean equals(Object obj) {  
>	boolean istGleich = false;  
>		if (obj instanceof Buch) {  
>			Buch b = (Buch) obj;  
>			istGleich = titel.equals(b.titel) && autor.equals(b.autor)  
>			&& erscheinungsjahr == b.erscheinungsjahr;  
>		}  
>	return istGleich;  
>}
> ```





