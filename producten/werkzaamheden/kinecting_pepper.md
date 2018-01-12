## Beschrijving toegevoegde functionaliteit Kinect applicatie

Link sourcecode: [Kinect applicatie Github Source](https://github.com/Hans2131/KinectingPepper)

### Naamgeving
In eerste instantie zouden we met een camera werken die geschikt was de Pepper robot. Omdat we in plaats daarvan de Kinect gingen gebruiken tijdens ons onderzoek, heb ik de bijbehorende applicatie de toepasselijke naam KinectingPepper gegeven. De applicatie spreek ik in onderstaande beschrijving dan ook aan als 'de applicatie' of 'KinectingPepper'.

### Kinect testen
Om te kunnen ontwikkelen voor de Kinect heb ik de Microsoft Kinect SDK gedownload en geïnstalleerd. De SDK bevat voorbeeld projecten waarmee je verschillende camera beelden weergeven. Daarmee heb ik de Kinect getest en en me georiënteerd op de werking van de code.

### Ontwikkelproces
Het ontwikkelproces hebben we op de volgende manier uitgevoerd:
- Voor nieuwe functionaliteit een een nieuwe branch aanmaken op basis van een SCRUM taak
- Na toevoegen nieuwe functionaliteit de code laten reviewen door teamgenoot
- Na review en eventuele aanpassingen code committen op de master

### Documentatie
Door tijdsgebrek hebben we besloten niet teveel aan documentatie te doen. Wel heb ik geprobeerd de code zoveel mogelijk 'self-explaining' te maken door middel van goede naamgevingen. Als ik aan het eind van het project nog tijd over heb voeg ik documentatie in de vorm van comments en een class diagram alsnog toe.

### Welke onderdelen heb ik ontwikkeld?
Voor de applicatie heb ik de volgende onderdelen ontwikkeld:
- Weergeven van verschillende camera beelden
- Weergeven van skelet bovenop de beelden
- Opslaan van skeleton data in XML
- Toevoegen van simpele logging/feedback voor gebruiker
- Afspelen van opgeslagen skeleton data
- Effectief opslaan van MP4 files
- Afspelen van opgeslagen MP4 files achter skeleton data
- Oplossen verschillende bugs

#### Weergeven van verschillende camera beelden
Dit was de allereerste versie van de applicatie die met een dropdown menu een camera van de Kinect kon selecteren en het beeld van die camera kon tonen op het scherm. 

#### Weergeven van skelet bovenop de beelden
Met de Kinect SDK heb ik skeleton data uitgelezen die realtime wordt berekend door de Kinect. Deze data zijn gewrichten inclusief een XYZ locatie in 'real world space'. Het mappen van deze coördinaten naar 'screen space' heb ik gedaan met functionaliteit van de Kinect SDK. Uiteindelijk worden de gewrichten inclusief verbindingen realtime getekend op de diepte of kleuren beelden die worden opgenomen door de Kinect.

#### Opslaan van skeleton data in XML
Na het uitlezen en weergeven van Kinect Data, was de volgende stap het opslaan van deze data. Hiervoor heb ik 'object serialization' naar XML gebruikt. De reden dat ik dit gedaan heb is ten eerste dat dit eenvoudig is te implementeren in C#, daarnaast wordt de data op die manier op de puurste manier opgeslagen waardoor de kans klein is dat data verloren gaat of vervormt raakt. Een nadeel van XML is dat dit formaat niet geschikt is voor bijvoorbeeld analyse in python. Om die reden heeft een klasgenoot een csv converter gemaakt die de data omzet naar een tabel formaat.

#### Toevoegen van simpele logging/feedback voor gebruiker

