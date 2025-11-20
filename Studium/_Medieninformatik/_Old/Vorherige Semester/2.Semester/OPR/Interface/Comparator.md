#Themen 
#OPR
#Medieninformatik 

---
# Quellen

# Definition
> [!question] ~
> Ermöglich das Sortieren von Elementen von beliebigen Kriterien. Es fügt die Methode <mark style="background: #BBFABBA6;"> int compare(T,T)</mark> hinzu..
> Dabei wird das Sortierkriterium als Parameter übergeben vom Typ <mark style="background: #D2B3FFA6;">Comparator</mark>.
> ```java
>public static void sort(List<T>, Comparator<? super T>)
>```

> [!example] ~
>Variable wird erzeugt, die dann als "Sortierkriterium" benutzt wird als anonyme, innere Klasse.
>``` java
>Comparator<Buch> vergleicher = new Comparator<Buch>() {  
  >
>  @Override  
  > public int compare(Buch buch1, Buch buch2) {  
  >
   > int vergleichswert  
    >    = buch1.gibAutor().compareTo(buch2.gibAutor());  
   > 
> 	 if (vergleichswert == 0) {  
    > 		 vergleichswert = (int) Math.signum(buch1.gibPreis()  
    > 	     - buch2.gibPreis());  
   > 		}  
   > 	
   > 	return vergleichswert;  
 > 	}  
> };
>```
.




