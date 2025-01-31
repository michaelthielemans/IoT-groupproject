# IoT Groups Project

## Taak verdeling

|Taak| Verantwoordelijke | Link repo | status |
|-----|-----|----|----|
|Teamleader| Michael| / | / |
|Kamer 1| Michael | [https://github.com/michaelthielemans/iotgroupproject-kamer1] | - |
|kamer 2| Dieter | https://github.com/dieterverbeek/IoT2024-2025.git | - |
|kamer 3| Wim | https://github.com/r0913559/ITessentials.git | - |
|kamer 4| Ahmad | ... | - |
|kamer 5| Julene | https://github.com/JuleneW/IOT_Project_Room_5 | - |
|kamer 6| Stijn | https://github.com/SDBeu/pi_scripts | done |
|kamer 7| Kristof | https://github.com/Ultraluminary/IoT_groep | - |
|kamer 8| Niels | https://github.com/NielsJanssen90/IoT-Kamer-Niels | - |
|Tuinhuis (Raspberry pi Pico) | Michael | | - |
|Kinderkamer (Raspberry pi Pico) | Niels | Weklampje verbonden met NTP server + temperatuurmeting met weergave op LCD | - |
|centraal dashboard uitlezing licht: data + bepaling gewenste waarde per kamer met telegrambot op gsm-toestel| Stijn | | done |
|optioneel centrale bediening aansturing door klok (bv automatische rolluit bediening)| | | - |
|optioneel weerstation (esp)| | | - |

## Algemene beschrijving project

Ons project richt zich op het ontwerpen en implementeren van een home-automationsysteem. De opstelling omvat een woning met acht kamers, een kinderkamer en een tuinhuis. Elke ruimte is uitgerust met een microprocessor (orangepi) of microcontroller (raspberry pi pico) die verantwoordelijk is voor de aansturing van actieve componenten en de uitlezing van sensoren in die specifieke kamer.

Alle gemeten waarden in de verschillende kamers worden automatisch geüpload naar een cloud-dashboard. Voor dit project maken we gebruik van het ThingSpeak-platform, waarbij elke kamer een eigen kanaal heeft. Het protocol om gegevens te verzenden en ontvangen hiervoor is MQTT.

Naast de gemeten sensorgegevens wordt er ook een gewenste waarde per kamer naar ThingSpeak geüpload. Deze gewenste waarde kan op verschillende manieren worden ingesteld: via drukknoppen in de kamer zelf of via een Telegram-bot voor externe bediening.

De microcontroller in elke kamer ontvangt de gewenste waarde via een subscription van het corresponderende kanaal op ThingSpeak. Vervolgens stuurt de microcontroller de actieve componenten, zoals LED-lampen of verwarmingsweerstanden, aan om de ingestelde waarde te bereiken.

De specifieke functies per kamer worden hieronder in detail beschreven. De uitwerking hiervan is terug te vinden in de verschillende github repositories.( zie tabel)

## Beschrijving functies en componenten per kamer
#### Kamer1
Input:
- Temperatuur meting
- Luchtdruk meting
- afstands meting
- drukknop 1 -> verhoog gewenste temperatuur
- drukkop 2 -> verlaag gewenste temperatuur
- bewegingsmelder

Output:
- Controle led bij drukkop
- Controle led bij verzenden van data
- led indicator bij beweging
- led blauw -> aanduiden werking ventilator
- relais 1 -> ventilator
- relais 2 -> verwarming element
- versturen van gemeten waarden naar thingspeak

#### Kamer2
Input:
- Luxmeting door BH1750-sensor.
- Knop 1: Verlagen van de gewenste luxwaarde.
- Knop 2: Verhogen van de gewenste luxwaarde.
  
Output:
- LED brandt bij te lage luxwaarde (onder de ingestelde drempel).
- Luxmetingen worden gepubliceerd naar het MQTT-kanaal "Waardes".
- Gewenste luxwaarden worden gepubliceerd naar het MQTT-kanaal "GewensteWaardes".

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
- Drukknoppen voor led feller of minder te laten branden (5 stappen) 0 - 100
- Drukknop led aan/uit
- Bij opstart gaat hij laatste waarde op thingspeak halen.

Output
- Weergeven waardes meting
- Gewenste waardes naar Thingspeak (qua licht van led)


#### Centrale aansturing dashboard via gsm: bot op telegram
- lees huidige status licht alle kamers
- lees huidige status specifieke
- stel gewenste lichtwaarde in specifieke kamer
- reset lichtwaarde specifieke kamer
- helpfunctie


