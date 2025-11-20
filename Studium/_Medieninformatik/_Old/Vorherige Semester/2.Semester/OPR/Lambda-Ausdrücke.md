#Themen 
#OPR
#Medieninformatik 

---
# Definition
> [!question] ~
> Lambda Ausdrücke ermöglichen die Erstellung von sogenannten "Anonymen Klassen" mit eigenen Methoden.
> 

> [!question] Kontext der Parameter
> Enthält der Kontext ausreichend Typinformationen, kann die Typisierung der Parameter entfallen.
> <mark style="background: #D2B3FFA6;">Beispiel</mark>: Wenn sich aus dem Kontext ergibt, dass das Argument der Methode der funktionale Schnittstelle vom Typ String ist, dann ist äqvivalent:
![[Pasted image 20230723164905.png]]


> [!question] Ohne Klammern
> Wird der zurückgegebene Wert durch einen einzelnen Ausdruck berechnet, können die Block-Klammern und kann das return entfallen. Es sind äquivelent:
> ![[Pasted image 20230723165008.png]]


> [!question] Aufruf einer vorhandenen Methode
> Enthält ein Lambda-Ausdruck nichts als den Aufruf einer schon vorhandenen Methode, kann anstelle des Lambda-Ausdruck eine sog. Methoden-Referenz verwendet werden. Im Anwendungsbeispiel handelt es sich natürlich um ein <mark style="background: #BBFABBA6;">Interface</mark>.
> ![[Pasted image 20230723165834.png]]



