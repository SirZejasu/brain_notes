#Praktika 
#EPR
#Medieninformatik 

---
# Methoden

## Verkettung
Korrigierte Version, unterscheidet sich vom Baum
```java
  public static long verkette(long zahl1, long zahl2) {

    // Fallunterscheidung
    return (zahl2 < 10 || zahl1 == 0)
        ? zahl1 * 10 + zahl2
        : verkette(zahl1, (zahl2 / 10)) * 10 + zahl2 % 10;

  }
```


### Baum




### Verkettung

## GibAnzahl
### Baum
![[Zahlenspielerei 2022-11-17 17.34.07.excalidraw]]

### Verkettung

## Filter
### Baum

### Verkettung