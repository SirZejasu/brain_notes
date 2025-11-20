# Klassifikation
Wir wollen Texte klassifizieren! Wir haben eine Menge von Daten zur Verfügung, deren Klasse wir kennen (so, wie in unserem Entscheidungsbaumbeispiel). Wir wollen lernen, einen "neuen" Datensatz, dessen Klasse wir noch nicht kennen, zu klassifzieren.

Ein typisches Anwendungsbeispiel ist die Unterscheidung zwischen HAM ("guten Nachrichten") und SPAM ("schlechten Nachrichten") in Emails, WhatsApp/Threema, Twitter, ...

Ein einfaches Vorgehen lernen wir jetzt kennen, es nennt sich **naives Bayes'sches Modell**.

## Das Handtaschen-Modell der Texterzeugung
Ihr Freund hat eine (Herren-)Handtasche mit zwei Fächern. In dem einen Fach sammelt er Wörter für **Liebesbriefe**, in dem anderen für **Trennungsschreiben**. Jedes Wort steht auf einem eigenen kleinen Zettel, nennen wir diese Zettel _Wortzettel_. Er sammelt nur _wichtige_ Wörter (z.B. nicht _und_, _die_, _der_, _das_, etc.).

Briefe schreibt er Ihnen, in dem er nach und nach einige _Wortzettel_ aus genau einem der Fächer nimmt, jedes gezogene Wort auf einen neuen kleinen Zettel überträgt, diesen neuen Zettel in einen kleinen Beutel steckt und den gezogenen Zettel wieder zurück ins Fach steckt, aus dem er kam. Am Ende bekommen Sie den Beutel mit den neuen Wortzetteln, das ist der Brief!

Auf diese Art hat Ihnen bisher 5 Liebesbriefe geschrieben und 2 Trennungsschreiben (es ist eine On-Off-Beziehung...).

## Oh, ein neuer Brief!
Heute morgen haben Sie wieder einmal die Zahnpastatube nicht von hinten nach vorn ausgedrückt! Beim Frühstück liegt ein kleiner Stoffbeutel auf ihrem Platz...[oh](http://freiesschauspiel.de/wp-content/uploads/2016/09/BriefEinerUnbekannten-1-1024x768.jpg "Link zu Bild mit Bettina Kaminski in 'Brief einer Unbekannten'"), ein Brief!

Wird ihr Freund noch einmal Gnade walten lassen und Ihnen erneut sein Liebe gestehen oder ist das (schon wieder...) ein Schlussstrich? Zum Glück kennen Sie den Inhalt der Tasche (sind sie eventuell ein wenig neugierig? ;)

## Die Tasche
Im Fach **Trennungsschreiben** befinden sich folgende Wortzettel:

$\{ich,liebe,dich,nicht,mehr,nie,mehr,nie,mehr\}$

Im Fach **Liebesbrief** befinden sich folgende Wortzettel

$\{ich,liebe,liebe,liebe,liebe,dich,nicht,nicht,mehr,nie\}$

PS: Ihr Freund ist Logiker, die letzten Liebesbriefe gab es jeweils nach einem Trennungsschreiben...

_Hinweis_: Die Mengenklammern deuten an, dass die Reihenfolge keine Rolle spielt. Es sind aber keine Mengen, sondern Multimengen oder _Bags_, Elemente können dort also mehrfach auftreten.

## Der Brief
Sie schütten den Beutel aus:

$\{nicht,ich,mehr,liebe,dich\}$

Oops, der Zettelhaufen auf dem Tisch sieht nicht gut aus. Aber als angehende Informatikerin wollen sie es, **gegeben die Fakten**, die sie kennen, genau wissen:

(a) Wie wahrscheinlich ist die **Hypothese** h1: der Brief ist aus dem Fach **Trennungschreiben**

(b) Wie wahrscheinlich ist die **Hypothese** h2: der Brief ist aus dem Fach **Liebesbrief**

## Die Rechung (1)
Wenn sie einen Zettel aus einem Fach ziehen, gibt es für jedes Wort des Wortschatzes (=alle Wörter, die auf einem Wortzettel vorkommen, eine echte "Menge") ihres Freundes eine bestimmte Wahrscheinlichkeit, einen Zettel mit diesem Wort zu ziehen.

Hier nochmal unsere Fachinhalte:

Trennungsschreiben:Liebesbrief:{ich,liebe,dich,nicht,mehr,nie,mehr,nie,mehr}{ich,liebe,liebe,liebe,liebe,dich,nicht,nicht,mehr,nie}

Wie hoch ist die Wahrscheinlichkeit, einen Wortzettel mit dem Wort _mehr_ aus dem Fach **Trennungsschreiben** zu ziehen, wenn sie zufällig einen Zettel auswählen (also es für jeden Zettel die gleiche Wahrscheinlichkeit gibt, gezogen zu werden)?

## Die Rechnung (2)
Formal ist das die Frage nach $p(mehr∣h1)$, also nach der Wahrscheinlichkeit für das Ziehen der Wortes mehr **gegeben** die Annahme, wir zögen aus dem Fach **Trennungsschreiben**.

Wir schätzen die Wahrscheinlichkeit, in dem wir sie gleichsetzen mit der relativen Häufigkeit der Wortzettel mit dem Wort mehr im Fach **Trennungsschreiben**.

Die relative Häufigkeit ist die absolute Häufigkeit der Wortzettel mit dem Wort mehr, also 3, geteilt durch die Anzahl an Wortzetteln in dem Fach insgesamt, also 9, d.h.

$p(mehr∣h1)=3/9=1/3$

Das können wir für alle Wörter errechnen, die im Brief vorkamen - und zwar für beide Hypothesen!

Tun sie das für alle Wörter in $\{nicht,ich,mehr,liebe,dich\}$!

## Die Rechnung (3)
h1 | h2
--- | ---
p(nicht∣h1)=1/9 |p(nicht∣h2)=2/10
p(ich∣h1)=1/9 |p(ich∣h2)=1/10
p(mehr∣h1)=3/9 | p(mehr∣h2)=1/10
p(liebe∣h1)=1/9 | p(liebe∣h2)=4/10
p(dich∣h1)=1/9 | p(dich∣h2)=1/10

Wir haben bisher 7 Briefe bekommen. Davon waren 5 **Liebesbriefe** und 2 **Trennungsschreiben**, die A-priori-Chancen (also wenn wir sonst nichts wissen und mal den Zahnpastatubenzwischenfall ignorieren), Briefe aus dem jeweiligen Fach zu erhalten, schätzen wir

$p(h1)=2/7$ und $p(h2)=5/7$.

## Der Satz von Bayes
Was wollen wir insgesamt wissen? Nun ja, wie wahrscheinlich jeweils unsere Hypothesen sind (die ausdrücken, woher der Brief kommt), gegeben die "Evidence" E, also unseren Brief!

$p(h1∣E)$ und $p(h2∣E)$.

Im Grunde ist das auch noch abhängig von unseren "Trainingsdaten", also der Handtasche. Das nehmen wir aber nicht als Symbol auf, sondern berücksichtigen es automatisch in unserem Modell durch die bereits bestimmten Wahrscheinlichkeiten. Wir können das ausrechnen!

$p(hx∣E)=\frac{p(hx)∗p(E∣h_{x})}{p(E)}=\frac{p(hx)∗∏e∈ E * p(e∣hx)}{p(E)}$ für $x∈\{1,2\}$

Hier unterstellen wir beim zweiten Gleichheitszeichen, dass sich die Wahrscheinlichkeit für unsere "Evidence", also den Brief gegeben ein Fach, bestimmen lässt, in dem wir die Wahrscheinlichkeiten für die einzelnen Wortzettel miteinander multiplizieren. Hierbei läuft e

über alle Wortzettel in E

(nicht Wörter! Obwohl das in unserem Beispiel zusammenfällt, jedes im Brief vorkommende Wort steht nur auf genau einem Zettel).

## Naives Bayes'sches Modell[](https://moodle.w-hs.de/pluginfile.php/551994/mod_resource/content/2/handtaschen_modell_der_texterzeugung.html#Naives-Bayes'sches-Modell)

Das macht in unserem _Handtaschenmodell des Briefeschreibens_ sogar Sinn!

Diese Annahme ist eine sogenannte **Unabhängigkeitsannahme** (die Wahl eines Wortzettels ist unabhängig von den anderen gewählten einzelnen Wortzetteln und auch unabhängig von jeder anderen Teilmenge der bereits gewählten oder nicht gewählten Wortzettel).

Diese Annahme ist _naiv_...deshalb der Name des Wahrscheinlichkeitsmodells: **naives Bayes'sches Modell**.

## Rechnung (4)[](https://moodle.w-hs.de/pluginfile.php/551994/mod_resource/content/2/handtaschen_modell_der_texterzeugung.html#Rechnung-(4))

p(h1∣E)=2/7∗1/9∗1/9∗3/9∗1/9∗1/9p(E)=0.00001451578p(E)

p(h2∣E)=5/7∗2/10∗1/10∗1/10∗4/10∗1/10p(E)=0.00005714285p(E)

Jetzt haben wir schon die wahrscheinlichste Hypothese gefunden (die Maximum-a-posteriori- oder MAP-Hypothese)!

Aber wir kennen die Wahrscheinlichkeiten noch nicht...das ist aber leicht, denn

p(E)=0.00001451578+0.00005714285=0.00007165863, also

p(h1∣E)=0.000014515780.00007165863∼0.2026undp(h2∣E)=0.000057142850.00007165863∼0.7974

Hier steht das Symbol ∼

für "ungefähr" oder "annähernd".

## Sie dürfen...[](https://moodle.w-hs.de/pluginfile.php/551994/mod_resource/content/2/handtaschen_modell_der_texterzeugung.html#Sie-dürfen...)

...also wohl in der gemeinsamen Wohnung bleiben, denn die (bei weitem) wahrscheinlichere Hypothese ist, dass ihr Freund mit dem etwas unbeholfenen "Brief" erneut seine Liebe offenbaren wollte und er Ihnen das falsche Ausdrücken der Zahnpastatube wieder mal verziehen hat...

...aber seien sie vorsichtig, beim nächsten Brief fehlt vielleicht das Wort liebe

!

**Übungsaufgabe**: Situation wie oben, gleiche Hypothesen, aber zwei veränderte Briefe:

(b) E1={nicht,ich,mehr,dich}

(a) E2={nie,ich,mehr,liebe,dich}

Bestimmen sie jeweils die Wahrscheinlichkeiten für beide Hypothesen gegeben E1 bzw. E2

.

Ganz ähnlich kann eine **Bonusaufgabe** in der Klausur aussehen, also: Inhalt von zwei Fächern gegeben (zur Bestimmung der sogenannten Likelihoods), eine Angabe zum Prior (welche Hypothese ist "vorab" wie wahrscheinlich), und ein Brief E

(die Evidence).

Das kann man übrigens sehr leicht zu drei oder mehr Fächern (=vorherzusagenden Klassen) verallgemeinern!