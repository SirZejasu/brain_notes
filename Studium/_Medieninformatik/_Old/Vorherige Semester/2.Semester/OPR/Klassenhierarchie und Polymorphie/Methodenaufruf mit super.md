#Themen 
#OPR
#Medieninformatik 

---
# Quellen

# Schlüsselwort: super
> [!question] .
> Mithilfe des Schlüsselworts <mark style="background: #BBFABBA6;">super</mark> ist es einer Kinderklasse möglich, auf die geerbte Methode der Elternklasse (superclass) zuzugreifen.
> Es ist dann nützlich, wenn die Klasse die Methode überschrieben hat und nun auf die vererbte Methode zugreifen will.

> [!hint] Syntax
> ```java 
> super.[Methodenname](Parameter)
> ```

```java
/* Die Methode gibWert() der Klasse B soll den Wert, den die Methode der
Klasse A liefern würde, multipliziert mit dem Wert der Instanzvariablen b
liefern. */

public int gibWert() {

return b * super.gibWert();
}
```



