# Hauptthema: Erkennen und Präventionsmethoden gegen die Verbreitung von Fehlinformationen

## Quellen
- https://w-hs.digibib.net/search/katalog/list?start=1&count=20&defaults=on&q-al=Falschinformation+%7C+Misinformation&q-ti=&q-au=&q-yr=&q-ky=Computer+Science+%7C+Data+%7C+Data+Science+%7C+Algorithm+&q-co=&q-pb=&q-ib=&q-is=&q-cn=

## Erscheinungsform: Konzeptionell
- Forschungsfrage beantworten ohne empirische Untersuchung
- Was ist der Stand der Forschung?
	- Wie können diese Information zur Beantwortung der Forschungsfrage helfen?
- Das Fazit basiert auf Recherche und die eigene kritische Beurteilung

## Erscheinungsform: Modellierend mit Erkenntniszielen (Analysemodelle)
- Erkennen eines realen Problems
- Originale / Realprobleme abstrahieren zu Modelle / Realmodelle
- Mögliche Lösungen zum Problem vorstellen
## Erscheinungsform: Methodisch
- Entwickeln eines Algorithmus oder Heuristiken
- Prototypentwicklung von Anwendungen / Plugins
- Am Ende eine Lösung vorstellen
## Die verschiedenen Informationsquellen
- Bücherei
- Internetquellen
	- Google
		- Zeitungsartikel
		- Websites
	- ChatGPT
		- Woher kommen die Daten?
			- Datenbank
			- Datenrechennetzwerke
		- Wie werden die Daten behandelt?
			- Wahrscheinlichkeiten durch Datenclustern
	- Social Media

## IT und Ethik/Verantwortung
- Verantwortung als Entwickler der Algorithmen
- Verantwortung als UI Designer
## Manipulation von Informationen (Faktoren)
- Leser ist Voreingenommen
	- Informationsquelle enthält Informationen, die der Leser ohnehin bestätigt
	- Vorallem kritisch für Internetbubbles

## Gründe für Falschinformationen (Problemfindung)
- Krisen
	- Situation ist neu und muss von Forschern/Experten zunächst erforscht werden
	- Es gibt für einen bestimmten Zeitraum keine validen Informationen zum Thema -> "Raum" wird durch Falschinformationen eingenommen. Falschinformationen geben Antworten.
- Lokale Faktoren
	- Nicht genug ausgebaute Informations- und Kommunikationstechnologien -> s. Buch 
	- information asymmetries (?)

## Fragen
- Ist die Verbreitung von Falschinformation geographisch abhängig? (Faktoren)
	- Durch Regierungsform -> Russland, Diktatur, königlich
	- Mangel an Informations- und Kommunikationstechnologien
	- Wie kann man trotz geograhischer Merkmale Falschinformation erkennen und verständlich erklären lassen?
- Ist es kulturell abhängig?
- Abhängig vom Sozialstatus? (Arm, reich, Bildung)

## Lösungsansätze
- Ausbauen von Informations- und Kommunikationstechnologien in Entwicklungsländern
- Entwickeln von Algorithmen 

## Realbeispiele
- Ground News
- [Context Function in X](https://help.x.com/en/using-x/community-notes)

## Spezifizierung des Themas

### Entwickeln eines Prototypen zum erkennen von potenziellen Falschinformationen


- Als Anwendung
	- Beachtung des UI/UX Designs
- Als Algorithmus in Foren und Sozialmedien 
- Valide Datenquellen als Vergleich
- Bereits umgesetzte Beispiele
	- Ground News
		- Ziel: Eliminieren von Politischen "Blind Spots"
		- Zusammenfassung von Informationen  verschiedener (politisch angesehener) ausgewählten Zeitungsartikeln aus dem Internet
	- X und Context ding
### Gestaltung digitaler Informationsumgebungen zur Förderung kritischer Informationsaufnahme: Wie können digitale Interfaces gestaltet werden, um Nutzer:innen zu unterstützen, Informationen kritisch zu bewerten und kognitive Verzerrungen zu reduzieren?
#### Mögliche Quellen
- https://tufind.hds.hebis.de/Record/HEB531183777
- User Centered Design -> [[Navigating Misinformation.pdf]]
#### Anmerkung
- Klingt wie "Modellierendes Arbeiten"

#### Konkretisierung des Problems
- Wie schnell können Falschinformationen sich verbreiten
	- Unter welchen Umständen?
		- In welcher Umgebung?
#### Hypothese

#### Frage: Aus was besteht die Infromationsumgebung
- UI-Design
	- Automatische Fakechecks, automatische Generierte Hinweise durch Schlüsselwörter im Text oder Post
	- Beispiel: X, früher Twitter, enthält eine Funktion womit die Community einen Post Kontext geben können.
-  Browser-Funktion (z.B. Durch Plugins)
	- Fake-News Check
-  Algorithmen
	- Automatische Erkennung und Hinweisen von potentiellen Falschinformationen.
- Administration
- Data Governance 
### Automatisierte Erkennung manipulativer Inhalte und deren Einfluss auf Nutzerwahrnehmung: Wie wirkt sich der Einsatz automatisierter Systeme zur Erkennung von Falschinformationen (Fake News Detection) auf das Vertrauen und Verhalten der Nutzer/-innen aus? Hier könnte ein entsprechendes System (prototypisches) entwickelt werden.
#### Quellen
- Erkennen von Falschinformationen -> [[Dive into Misinformation Detection.pdf]]
- AI Lösungansätze zum erkennen von Falschinformationen -> [[Misinformation and Disinformation.pdf]] 

#### Anmerkung
- Klingt wie "Methodisches Arbeiten"
#### Mustererkennung
- Welche Musterprobleme könnte man hier entwickeln? Welche Inhalte sind typisch kritisch?
	- Suche anhand von Schlüsselwörtern
	- Themen, die im momentanen Trend häufig zu Missverständnissen kommen
		- Emotionale Themen -> Häufig politische Themen

### Soziale Dynamiken in digitalen Diskussionsplattformen: Wie beeinflusst die technische Gestaltung sozialer Medienplattformen (z.B. Like-/Share-Systeme, Kommentarstrukturen) das Diskussionsverhalten und die Meinungsbildung?

#### Fragen
- Beeinflusst die Menge der Likes oder Kommentare, ob der Post für den User als glaubwürdig erscheint?
- Beeinflusst der Inhalt der Kommentare die Glaubwürdigkeit des Posts?
- Beeinflussen die User-Profile die Glaubwürdigkeit einer Aussage?
### Intelligente Data Governance (Data Quality Management): Überprüfung 

### Dashboarding und Datenanalyse basierend auf Streamlit und Flask (beides Python)