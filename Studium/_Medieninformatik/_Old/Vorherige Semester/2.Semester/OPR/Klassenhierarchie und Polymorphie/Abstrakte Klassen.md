#Themen 
#OPR
#Medieninformatik 

---
# Quellen
- s. Skript

# Definition
> [!question] .
> Eine abstrakte Klasse kann nicht instanziiert werden. Außerdem muss eine Klasse abstrakt sein, um eine abstrakte Methode zu erstellen. Beide werden mit dem Modifikator <mark style="background: #BBFABBA6;">abstract</mark> deklariert.
> Es ist allerdings immernoch möglich, dass eine Variable den Typ der Elternklasse hat!
> Kommt in einer Klasse eine abstrakte Methode vor, so muss die Klasse selbst  
ebenfalls abstrakt vereinbart sein.


```java
public abstract class Katalogartikel {

	protected float preis;

	protected Katalogartikel(float preis) {
	this.preis = preis;
	}

	public abstract boolean passtZu(String suchbegriff); // Template-Methode

	public abstract String gibText();
}
```

# Template-Methode
> [!question] .
> Eine Template-Methode ist eine abstrakte Methode und ermöglicht einen 
> Ablauf ( = Template ).
> Nachdem es in der Elternklasse definiert wurde, kann es in der Kinderklasse überschrieben werden.

```java
public class Buch extends Katalogartikel{
	/**
	* Liefert den Suchtext dieses Buchs. Anhand des Suchtexts
	* lässt sich entscheiden, ob das Buch zu einem Suchbegriff
	* passt.
	*/
	@Override
	protected String gibSuchtext() {
	
		return (titel + " " + autor);
	}

}
```
