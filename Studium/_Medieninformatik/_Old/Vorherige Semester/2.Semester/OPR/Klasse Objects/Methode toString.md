#Themen 
#OPR
#Medieninformatik 

---
# Definition
> [!question] .toString()
> Vererbte Methode aus Klasse Object. Wird normalerweise überschrieben und an der eigenen Klasse angepasst mit einer seperaten Methode.
> Findet Verwendung zur textuellen Darstellung des Objekts. Es ist sinnvoll, diesen in den Klassen zu überschreiben.
> ![[Pasted image 20230529130825.png]]

# Beispiel
> [!example] Klasse: Buch
> 
> ``` java
> /**  
> * Liefert standardmäßige textuelle Darstellung dieses  
>* Buchs.  
>*  
>* @return textuelle Darstellung dieses Buchs  
>*/  
>@Override
> public String toString() {  
>	return titel + ", " + autor;  
>}
> ```


