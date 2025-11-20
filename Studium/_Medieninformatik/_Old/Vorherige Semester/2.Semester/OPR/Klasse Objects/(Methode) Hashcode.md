#Themen 
#OPR
#Medieninformatik 

---
# Definition
> [!question] .hastCode()
> Jedes Objekt enthält eine ID(Hashcode) als Instanzvariable. Mit dem gleichnamigen Operator ruft man diesen ab. Mit dem Operator .equals() vergleicht man beide IDs.
> ![[Pasted image 20230529125608.png]]
> ![[Pasted image 20230529125745.png]]

# Beispiel
> [!example] Klasse: Buch
> ``` java
>/**  
>* Liefert den Hash-Code dieses Objekts.  
>*  
>* @return Hash-Code dieses Objekts  
>*/  
>
>public int hashCode() {  
>		return titel.hashCode() + autor.hashCode()  
>								+ erscheinungsjahr;  
>}
> ```




