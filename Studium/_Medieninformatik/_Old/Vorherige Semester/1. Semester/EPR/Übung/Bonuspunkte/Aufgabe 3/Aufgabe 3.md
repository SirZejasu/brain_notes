#Bonuspunkte  
#EPR
#Medieninformatik  

---
# Tabelle
f("ZUZUG", "ZUG")

i | j | b
--- | --- | ---
0 | / | false
0 | 0 | false
0 | 1 | false
0 | 2 | false
1 | 2 | false
1 | 0 | false
2 | 0 | false
2 | 0 | false
2 | 1 | false
2 | 2 | false
2 | 3 | false
3 | 3 | true
    
<mark style="background: #BBFABBA6;">Ausgabe:</mark> true

f("BAUM", "BAR")

i | j | b
--- | --- | ---
0 | / | false
0 | 0 | false
0 | 1 | false
0 | 2 | false
1 | 2 | false
1 | 0 | false
2 | 0 | false




<mark style="background: #BBFABBA6;">Ausgabe:</mark> false

# Sourcecode
```java
public static boolean f(String s, String t) {  
  
    boolean b = false;  
    int i = 0;  
  
    // <---  
    while (i <= s.length() - t.length() && !b) {  
      int j = 0;  
      // <---  
      while (j < t.length() && s.charAt(i + j) == t.charAt(j)) {  
        j++;  
        // <---  
      }  
      b = j == t.length(); 
      i++;  
      // <---  
    }  
    return b;  
  }
```
