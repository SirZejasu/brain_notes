#Coding 
#Practice 

---

# Wofür wird es verwendet
Universelle Sprache von Websites. Dient zur Darstellung als auch zur

## Elemente / Tags
### head
Wird für den Titel des HTML-Dokuments verwendet sowie für Stil und Skripte.
Beispiel:
```HTML
<html>
  <head>
    <title>Seitentitel</title>
  </head>
</html>
```

### header
Repräsentiert eine Gruppe, dass Elemente wie Bilder, Schaltflächen oder Navigationshilfen enthält. Wird für Artikel verwendet.
Beispiel:	
```HTML
<header>
  hier ein Logo
</header>
```
	
### nav
Element, dass einen Link enthält zur Navigation innerhalb des HTML-Dokuments oder anderen Dokumenten. Verwendet z.B in Inhaltsverzeichnisse, Menüs etc.
Beispiel:
```HTML
<nav class="menu">
  <ul>
    <li><a href="#">Startseite</a></li>
    <li><a href="#">Über</a></li>
    <li><a href="#">Kontakt</a></li>
  </ul>
</nav>
```

### section
Dient zur Unterteilung eines Dokuments.
Beispiel:
```HTML
<section>
  <h1>Heading</h1>
  <p>Bunch of awesome content</p>
</section>
```

### iframe
Ein Container-Element, das ein weiteres HTML-Dokument enthalten kann.
Attribute:

src (source)
Enthält Link (URL) zur einer Seite.

width
Definiert Breite des HTML-Dokuments in Prozent oder Pixel.

height
Definiert Höhe des HTML-Dokuments in Prozent oder Pixel.

frameborder
Definiert Breite des Frame-Rahmens.
Beispiel:
```HTML
  <iframe 

        id="video"

        src="https://www.youtube.com/watch?v=V1508wboZXk"

        width="500"

        height="300"

        frameborder="0"

         ></iframe>

```


### frame
Dieses Element enthält interaktive Funktionen um Informationen des Benutzers eintragen zu können.

Beispiel:
```HTML
<!-- Form which will send a GET request to the current URL -->
<form method="get">
  <label>Name:
    <input name="submitted-name" autocomplete="name">
  </label>
  <button>Save</button>
</form>

<!-- Form which will send a POST request to the current URL -->
<form method="post">
  <label>Name:
    <input name="submitted-name" autocomplete="name">
  </label>
  <button>Save</button>
</form>

<!-- Form with fieldset, legend, and label -->
<form method="post">
  <fieldset>
    <legend>Title</legend>
    <label><input type="radio" name="radio"> Select me</label>
  </fieldset>
</form>

```
