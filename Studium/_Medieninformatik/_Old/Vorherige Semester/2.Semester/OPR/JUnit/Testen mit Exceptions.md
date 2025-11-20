#Themen 
#OPR
#Medieninformatik 

---

```Java
try {

	[Aufruf der zu testenden Methode]
	
	/* Die folgende Anweisung darf nicht erreicht werden.
	* Falls doch, ist der Testfall verletzt. */
	fail("Hinweistext zum Fehler");
} catch (Exceptiontyp e) {
	/* Hier ggfs. Inhalte von e mit assertEquals prüfen. */
	
}
```

```java
@Test  
public void testParse5() throws ParseException {  
  
  ParseException penis = assertThrows(ParseException.class, () -> {  
  
    parser.parse("()").gibWert(liste);  
  
  });  
  
  assertEquals("ungueltiges Token )", penis.getMessage());  
  
}

```




