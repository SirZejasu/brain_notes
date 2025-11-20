#Themen 
#OPR
#Medieninformatik 

---

# Byteorientiert

## Eingabestrom -> InputStream
> [!question] ~
> InputStream ist Oberklasse und Abstraktion aller byteorientierten Eingabeströme.
> Methoden zum Lesen von Bytes:
> ```java
>// liest ein Byte. Ist bei externen Datensenken potenziell ineffizient.
>void read()
> 
> // Zählt die Anzahl der gelesenen Bytes und gibt die länge zurück oder -1, wenn es
> leer ist. 
> void read (byte[])
>```

### BufferedInputStream
> [!question] ~
> Kapselt einen InputStream und liest intern aus diesem blockweise. Methode int read() ist in dieser Klasse auch für externe Datenquellen effizient.

### ByteArrayInputStream
> [!question] ~
> Eignet sich für Tests für Methoden mit InputStream Parameter.




## Ausgabestrom -> OutputStream
> [!question] ~
> OutputStream ist Oberklasse und Abstraktion aller byteorientierten
Ausgabeströme. Es gibt im Prinzip nur zwei Methoden zum Schreiben von Bytes: 
>```java
>// schreibt ein Byte
>void write(int) 
>
>// schreibt mehrere Bytes. Ist bei externen Datensenken potenziell ineffizient.
>void write (byte[])
>```

### BufferedOutputStream
> [!question] ~
> Kapselt einen OutputStream und schreibt blockweise dort hinein. Methode <mark style="background: #ABF7F7A6;">void write(int)</mark> ist in dieser Klasse auch für externe Datensenken effizient.

### ByteArrayOutputStream
> [!question] ~
> Geeignet zum Testen von Methoden mit OutputStream-Parameter.



# Zeichenorientiert

## Eingabestrom -> Reader
> [!question] ~
> Abstrakte Oberklasse aller zeichenorintierten Inputstreams.
> Relevante Methoden:
>```java
>// schreibt ein Byte. Ist bei externen Datensenken potenziell ineffizient.
>void read(int) 
>
>// Zählt die Anzahl der gelesenen Bytes und gibt die länge zurück oder -1, wenn es leer ist. 
>void read (char)
>```

### BufferedReader
> [!question] ~
> Kapselt einen Reader-Objekt und liest intern aus diesem blockweise. Methode<mark style="background: #ABF7F7A6;"> int read()</mark> ist in dieser Klasse auch für externe Datenquellen effizient.
> Weitere Methoden:
> ``` java
> // Liest eine Zeile
> String readLine()
>
> // Stream aller Zeilen
>Stream<String> lines()
>
>```

### StringReader
> [!question] ~
> Eignet sich zum testen von Methoden mit Reader-Parameter.





## Ausgabestrom -> Writer
> [!question] ~
> Writer ist Oberklasse und Abstraktion aller zeichenorientierten
Ausgabeströme. Genau wie in der Byte-orientierten Schreib-Klasse gibt es auch hier prinzipiell zwei relevante Methoden:
>```java
>// schreibt ein Zeichen.
>void write(int) 
>
>// schreibt mehrere Zeichen. Ist bei externen Datensenken potenziell ineffizient.
>void write (char[]) // oder void write(String)
>```


### BufferedWriter
> [!question] ~
> Kapselt Writer-Objekt und schreibt blockweise dort hinein. Methode<mark style="background: #ABF7F7A6;"> int write(int)</mark> ist in dieser Klasse auch für externe Datensenken effizient.

### PrintWriter
> [!question] ~
> Kapselt Writer-Objekt und bietet Komfortmethoden. um elementare Werte und Objekte dort hinein zu schreiben.

### StringWriter
> [!question] ~
> Eignet sich für JUnit test für Methoden mit Writer-Parameter.

# Code-Schema mit Exception


