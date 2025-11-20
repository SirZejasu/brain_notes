#Themen 
#OPR
#Medieninformatik 

---
# Quellen
- s. Skript
- [Template-Method](https://www.digitalocean.com/community/tutorials/template-method-design-pattern-in-java)

# Definition
> [!question]  .
> In einem Konstruktor einer Klasse wird immer der Konstruktor der direkten Elternklasse aufgerufen. Macht man es selbst nicht, wird es vom Compiler automatisch gemacht.

```java
public class Buch extends Katalogartikel {
	[...]
	public Buch(String titel, String autor,
				int erscheinungsjahr) {

		super(); // automatisch vom Compiler eingefügt
		this.titel = titel;
		this.autor = autor;
		this.erscheinungsjahr = erscheinungsjahr;
	}
}
```

> [!hint] Eine Klasse besitzt keinen Konstruktor
> In dem Fall wird der Konstruktor automatisch mit dem Aufruf der Elternklasse hinzugefügt durch den Compiler.
>

```java
public class Buch extends Katalogartikel {
	[...]
	private String titel;
	private String autor;
	private int erscheinungsjahr;
	[...]
	/* automatisch vom Compiler eingefügt */
	public Buch() {
	super();
	}
}
```

