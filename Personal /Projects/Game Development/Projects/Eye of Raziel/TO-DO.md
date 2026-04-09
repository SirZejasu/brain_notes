# Misc
- [ ] Notizbuch mit Hinweisen
	- [ ] Im Weltraum horizontal und vertikal scrollen
	- [ ] Zauber erstellen und kombinieren
		- [ ] Wenn man Zauber kombiniert bzw. hintereinander anwendet, lassen sich Gegenstände/Zutaten erstellen.
		- [ ] Feuer + Wasser + Erde + Luft = Stein der Weisen
			- [ ] Stein der Weisen ist eine Zutat für weitere Alchemierezepte
	- [ ] Konstellationen kombinieren, um neue Zauber zu bekommen.
		- [ ] Wasser + Erde = Leben
		- [ ] Feuer + Wasser = Nebel
		- [ ] Feuer + Luft = Magische Macht

# Game-Mechancics
- [ ] Randomly generated Nightsky
	- [x] Variable: List of [[Celestial Bodies]] 
		- [ ] Attributes: Celestial Body (Star, Moon, Planet), Type (Star: Young, Mature, Ancient; Planet: Gas, Rock, Water, Atmosphere), Coordinates XY, ListOfPartners 
- [ ] For Init execute method (generate stars)
	- [x] Ratio for Types (Blue, red, green for e.x.)
	- [ ] Randomly set the Coord of CB with "social distancing"
- [ ] Connect Celestial Bodies
	- [ ] When Star chosen, initiate pair mode -> TargetCB not Nil
	- [ ] Load ListOfPartner of currently targeted CB
	- [ ] Update cache Value to store current connections
	- [ ] For Each new connection, check if amount of right CB types have been meet (Compare with Spellbook Variable). 
	- [ ] Finish editing
		- [ ] Give it a name
		- [ ] Save: Update ListOfCB ListOfPartners
# Visuals
## Map
- [ ] Weltraum erweitern
- [ ] Make an actual Tower
	- [ ] Scroll Effect when going up
- [ ] Decorate the Tower
- [ ] Interaction Field
- [ ] Notizbuch
	- [ ] Enthält bereits zu Anfang Informationen über "Natursymbole" und Assoziationen mit 
- [ ] Starmap
	- [ ] Functions to make notes
 - [ ] Hauptmenü (?)
## Animations
- [ ] Zoom-Effect out/in the Tower
- [ ] Alpha Canal Animations for Currently Editing Constellation
- [ ] Nach den ersten Zaubern erscheinen Augem um den Turm