#Themen 
#OPR
#Medieninformatik 

---
# Quellen
s. Skript 

# Maps
> [!question] ~
> Zuordnung von Werten. Es ist vergleichbar mit einem Wörterbuch.  Es werden hier zwei Unterklassen von "Map" genannt:
> HashMap und TreeMap. Beide sind ziemlich gleich doch unterscheiden sie sich in einem wesentlichen Punkt: TreeMap ist hierarchisch, HashMap nicht.

# HashMap
> [!question] ~
> Eine Liste, dessen Elemente (Values) ein Schlüssel (Key) besitzen. Dabei ist jeder Key einzigartig. Wird ein Key mit der derselben Definition hinzugefügt, wird das Element überschrieben.

#  Methoden für HashMaps
> [!hint] Methoden in Hashmaps
> ```java
> V put(K key, V value)
> // Ordnet in der Tabelle dem Schlüssel den angegebenen Wert zu. Falls bereits ein Eintrag zu
> // dem Schlüssel existiert, wird dessen Wert mit dem neuen Wert.
> 
> V get(Object key)
> // Liefert aus der Tabelle den Wert zu dem angegebenen Schlüssel.
>
> boolean isEmpty()
> // Gibt an, ob die Tabelle Einträge enthält. 
> 
> int size()
> // Liefert die Anzahl der Schlüssel der Tabelle.
> 
> void clear()
> // Entfernt alle Einträge einer Zuordnung
> 
> boolean containsKey(Object key)
> // Gibt an, ob Tabelle einen Schlüssel enthält, der gleich (im Sinne von equals) dem angegebenen Objekt ist.
>
> boolean containsValue(Object value)
> // Gibt an, ob Tabelle einen Wert enthält, der gleich (im Sinne von equals) dem angegebenen Objekt ist.                                                                                                                                                                                                                                                           
> 
> V remove(Object key)
> // Entfernt den Eintrag mit dem angegebenen Schlüssel aus der Tabelle   
> 
> Collection<V> values()
>  // Liefert eine Collection aller Values in einer Tabelle. Zum Durchlaufen aller Values benötigt man einen iterator (s.u.), den man mit der Methode iterator() erhält. 
> // Beispiel: Sei z eine Variable des Typs HashMap (oder einer anderen Zuordnungklasse), so liefert z.values().iterator() einen Iterator, um über die Werte der Zuordnung in der Variablen z zu iterieren.
> 
> Set<K> keySet()
> // Liefert eine Menge aller Schlüssel der Tabelle. Zum Durchlaufen aller Schlüssel benötigt man einen Iterator. Beispiel: z.keySet().iterator().
>
> ```


## Beispiele zu den Methoden
> [!example] get
> 
> ```java
> private Entry<K, V>[] table; //Einträge der Tabelle
>
>public V get(Object key){
>
>	int hash = key.hashCode();
>	int index = hash % table.length;
>	for(Entry<K,V> e = table[index]; e != null; e = e.next) {
>		if((e.key.hashCode() == hash) && e.key.equals(key)){
>				return e.value;
>		}
>		
> }
 > 	return null;
> }
>
> ```




> [!example] put
> ```java
> public V put(K key, V value) {
>
> 	int hash = key.hashCode();
> 	int index = hash % table.length;
> 		for (Entry<K, V> e = table[index]; e != null; e = e.next) {
> 			if ((e.key.hashCode() == hash) && e.key.equals(key)) {
> 				V old = e.value;
> 				e.value = value;
> 					return old;
> 			}
>		}
>		tab[index] = new Entry<>(key, value, tab[index]);
>		return null;
> }
> ```

# Speicher des Maps

> [!question] ~
> Jedes <mark style="background: #ABF7F7A6;">value</mark> hat genau einen key. Wird der Key nochmal zugewiesen, wird das neue <mark style="background: #ABF7F7A6;">value</mark> überschrieben.

| key  | value | Bemerkung                           |
| ---- | ----- | ----------------------------------- |
| Haus | house |                                     |
| xy   | abc   |                                     |
| Haus | Maus  | value wird überschrieben            |
| za   | abc   | Anderer Key, gleicher Inhalt wie xy | 

# Iteration in einer Map mit iterator()

```java
boolean hasNext()
// Gibt an, ob der Iterator noch weitere Elemente enthält.

E next()
// Liefert das nächste Element des Iterator, falls dieser noch mindestens ein Element enthält.

```

## Beispiel
> [!example] Beispiel 1
> ```java
> // Annahme: Schlüssel sind vom Typ String
>
> HashMap<String, Object> zuordnung = new HashMap<>();
> ...
> Iterator<String> it = zuordnung.keySet().iterator(); // Liefert Aufzählunh
> 													 // der Schlüsselmenge
> while (it.hasNext()){
> String wort = it.next();
>	System.out.println("Der Wert zum Schlüssel" + wort + " ist " + zuordnung.get(wort));
>
> }
>``` 

# Suchbaum / TreeSet
> [!question] ~
> Ordnungskriterium: Schlüssel der Zuordnung.
> ![[Pasted image 20230427140023.png]]
> ![[Pasted image 20230427140410.png]]

# Weiteres über Hashmap
## Beispiel
```java
public class Eintrag<K, V> {
	private K schluessel;
	private V wert;
	...

}
```

# TreeMap
> [!question] ~
> Hierarchische Ordnung (Baum) von Daten.
> 
> - Schlüssel sind geordnet im Gegensatz zu HashMaps, die nach Hashcodoes geordnet sind.
> - Enthält Methoden, die nur bei geordneten Schlüsseln
> möglich sind, z. B. ceilingKey(K), um kleinsten
> Schlüssel zu erhalten, der größer oder gleich dem
> übergebenen Schlüssel ist

