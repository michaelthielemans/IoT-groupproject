# IoT Groups Project

## Taken verdeling

Vul deze lijst verder aan...
Feel free om extra opties toe te voegen....

|Taak| Verantwoordelijke | Link repo |
|-----|-----|----|
|Teamleader| Michael| / |
|Kamer 1| Michael | [https://github.com/michaelthielemans/iotgroupproject-kamer1] |
|kamer 2| Dieter | |
|kamer 3| Wim | https://github.com/r0913559/ITessentials.git |
|kamer 4| ... | ... |
|kamer 5| Julene | https://github.com/JuleneW/IOT_Project_Room_5 |
|kamer 6| Stijn | ... |
|kamer 7| Kristof | https://github.com/Ultraluminary/IoT_groep |
|Tuinhuis (Raspberry pi Pico) | Michael | |
|centraal dashboard uitlezing licht: data + bepaling gewenste waarde per kamer met telegrambot op gsm-toestel| Stijn | |
|optioneel centrale bediening aansturing door klok (bv automatische rolluit bediening)| | |
|optioneel weerstation (esp)| | |


## Beschrijving functies en componenten per taak
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

#### Kamer2
- Lux meeting
- Led brand bij te lage lux
- Knop 1 = verlagen lux
- Knop 2 = verhogen lux
- Lux meting naar channel "Waardes" (MQTT)
- Gewenste lux waarde naar channel "GewensteWaardes" (MQTT)

#### Kamer3
- licht meeting
- led rood -> meer licht indien niet voldaan aan doel lux waardes
- button 1 & 2 -> verhogen/verlagen doel lux
- step motor -> simulatie openen/dicht gordijnen. Links of rechts afhankelijk van te weinig of teveel lux
- lcd -> tonen huidige lux, doel lux , status led
- subscription based mqtt

#### Kamer6
Input
- licht meting
- drukknop -> verhoog gewenst licht + verlaag gewenst licht
- uitlezing gewenste waarde licht van thingspeak

Output
- controle led bij drukkop
- versturen sensor waarden naar thingspeak

#### Kamer7
Input
- licht meting

Output
- Weergeven waardes meting


#### Centrale aansturing dashboard via gsm: bot op telegram
- lees huidige status licht alle kamers
- lees huidige status specifieke
- stel gewenste lichtwaarde in specifieke kamer
- reset lichtwaarde specifieke kamer
- helpfunctie


