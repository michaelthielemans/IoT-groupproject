# IoT Groups Project

## Taken verdeling

Vul deze lijst verder aan...
Feel free om extra opties to te voegen....

|Taak| Verantwoordelijke | Link repo |
|-----|-----|----|
|Teamleader| Michael| / |
|Kamer 1| Michael | |
|kamer 2| ... | ... |
|kamer 3| ... | ... |
|kamer 4| ... | ... |
|kamer 5| ... | ... |
|kamer 6| ... | ... |
|kamer 7| ... | ... |
|Tuinhuis (Raspberry pi Pico) | Michael | |
|optioneel centraal dashboard uitlezing data + bepaling gewenste waarde per kamer| | |
|optioneel centrale bediening aansturing door klok (bv automatische rolluit bediening)| | |
|optioneel weerstation (esp)| | |


## Beschrijving componenten per taak
#### Kamer1
Input
- Temperatuur meting
- Luchtdruk meting
- afstands meting
- drukknop 1 -> verhoog gewenste temperatuur
- drukkop 2 -> verlaag gewenste temperatuur
- uitlezing gewenste waarde van thingspeak

Output
- Controle led bij drukkop
- led blauw -> aanduiden werking ventilator
- relais 1 -> ventilator
- led rood -> aanduiding werking verwarming
- relais 2 -> verwarming element
- versturen sensor waarden naar thingspeak
