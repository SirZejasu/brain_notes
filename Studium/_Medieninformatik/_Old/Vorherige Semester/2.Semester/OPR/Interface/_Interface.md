#Themen 
#OPR
#Medieninformatik 

---
# Quellen
- s. Skript

# Definition
> [!question] Schnittstelle / Interface
> Eine Schnittstelle ist eine Klasse bestehend aus abstrakten Methoden und Konstanten. Sie dient also zum definieren von Konstanten und Methoden. Diese "Fähigkeiten" werden dann geerbt.
> Beim Hinzufügen eines Interfaces muss entweder die Klasse abstrakt sein oder die Methoden werden alle in der Klasse übernommen.

# Syntax / Implementierung eines Interfaces

> [!question] Syntax
> Definition eines Interfaces.
> ```java
> public interface Schnittstelle  
> 		extends Schnittstelle1, . . ., Schnittstellen {  
> 
> 	Konstantendefinitionen  
> 
> 	Methodendeklarationen  
> 
> }
> ```

> [!example] Beispiel 
> Interface mit seinen abstrakten Methoden.
> ``` java
>public interface Verkaufbares {
> 	boolean passtZu(String suchbegriff);
> 	String gibText();
> 	float gibPreis();
> }
>```

> [!example] Implementierung eines Interfaces
> Methoden aus der Instanzklasse müssen in die Klasse überschrieben werden.
> ```java
>public class Auto extends Motorfahrzeug 
>		implements Verkaufbares {  
>
> @Override  
>public boolean passtZu(String suchbegriff) {  
> 	...  
> 
> 	}  
> 
> @Override  
> public String gibText() {  
> 	...  
> 
> 	}  
> 
> @Override  
> public float gibPreis() {  
> 	...  
> 
> 	}  
> 
> }
> 
>```

# Vergleich: Abstrakte Klassen $\leftrightarrow$ Interfaces
![[Pasted image 20230511215335.png]]


# Typendeklaration
> [!question] ~
> Das Objekt kann mit der Schnittstelle als Typ deklariert werden, wenn es in der Klasse implementiert ist.
> ![[Pasted image 20230706210839.png]]

