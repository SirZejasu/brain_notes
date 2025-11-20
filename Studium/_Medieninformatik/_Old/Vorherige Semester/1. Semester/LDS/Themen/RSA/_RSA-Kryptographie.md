#Thema 
#LDS 
#Medieninformatik   

---
# Quellen
- [[LDS-RSA-2.1.pdf]]

# Definition
## RSA
> [!question] RSA
> Die RSA-Kryptographie wird dazu verwendet um Nachrichten verschlüsseln zu können. Ein ähnliches Thema hatte ich in der [[Verschlüsselungsverfahren|Ausbildung]].

> [!info] Formel für RSA-Verschlüsselung 
> ### Verschlüsselung
>  $m^{e}$ $mod$ $n$ = $m^{2er-Potenz}$ e wird aufgeteilt in 2er Potenzen.
>
>### Entschlüsselung
>$c^{d}$ $mod$ $n=c^{2er-Potenz}$
>  Für Rest siehe Beispiel.

### Beispiele
> [!example] Beispiel 1
> Vorgegebene Werte:
> 	 Verschlüsselung: $m=41$, $e=17$, $n=55$
> 	 Entschlüsselung: $d=46$, $n=55$, $c = ?$
> 	 
> ### Schritt 1 Werte eingeben
> $41^{17}mod 55=41^{16+1}$
> 
> ### Schritt 2 Verschlüsseln Vorschritte
> $41^{2}$ $mod$ $55=41^{2}$ $mod$ $55=31$
> $41^{4}$ $mod$ $55=31^{2}$ $mod$ $55=26$
> $41^{8}$ $mod$ $55=26^{2}$ $mod$ $55=36$
> 
> ### Schritt 3 Variable c (Die eigentliche Verschlüsselung) herausfinden
> $c=41^{16+1}mod$ $55 = (36*41)$ $mod$ $55=46$ 
>
> ### Schritt 4 Werte für Entschlüsselung (mit neuen n)
> $46^{33}$ $mod$ $55=46^{32+1}$ $mod$ $55$
> 
> ### Schritt 5 Entschlüsselung Vorschritte
> $46^{1}$ $mod$ $55=46$
> $46^{2}$ $mod$ $55=46^{2}$ $mod$ $55=26$
> $46^{4}$ $mod$ $55=26^{2}$ $mod$ $55=16$
> $46^{8}$ $mod$ $55=16^{2}$ $mod$ $55=36$
> $46^{16}$ $mod$ $55=36^{2}$ $mod$ $55=31$
> $46^{32}$ $mod$ $55=31^{2}$ $mod$ $55=26$
> 
> ### Schritt 6 Eigentliche Entschlüsselung
> $m=46^{(32+1)}$ $mod$ $55=(26*46)$ $mod$ $55=41$

# Vorlesung
![[LDS_Vorlesung_RSA_EEA.pdf]]