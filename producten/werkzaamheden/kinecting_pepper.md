## Beschrijving toegevoegde functionaliteit Kinect applicatie

De applicatie is gebouwd met C#, deze link verwijst naar de github repo waar alle source code staat. Het project kan worden geopend worden met Visual Studio 2017.

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
- Verbeteren opslaan CSV converter
- Overige werkzaamheden zoals bugs oplossen

Bij de beschrijving van de functionaliteit heb ik de link naar elke commit gezet. Let op, dit geeft niet 100% een beeld van het ontwikkelproces omdat we met branches gewerkt hebben.

#### Weergeven van verschillende camera beelden 
[Link naar commit](https://github.com/Hans2131/KinectingPepper/commit/f3f9319b950546b7e1e77b053c85ea98bf3b0ee0){:target="_blank"}

Dit was de allereerste versie van de applicatie die met een dropdown menu een camera van de Kinect kon selecteren en het beeld van die camera kon tonen op het scherm. 

#### Weergeven van skelet bovenop de beelden
[Link naar commit 1](https://github.com/Hans2131/KinectingPepper/commit/d877be48e42caaaf4da88a495da431fb26e1eba7){:target="_blank"} 
[Link naar commit 2](https://github.com/Hans2131/KinectingPepper/commit/e8532c4aaf8a4953823de18d95bded609aaefdb7){:target="_blank"}
Met de Kinect SDK heb ik skeleton data uitgelezen die realtime wordt berekend door de Kinect. Deze data zijn gewrichten inclusief een XYZ locatie in 'real world space'. Het mappen van deze coördinaten naar 'screen space' heb ik gedaan met functionaliteit van de Kinect SDK. Uiteindelijk worden de gewrichten inclusief verbindingen realtime getekend op de diepte of kleuren beelden die worden opgenomen door de Kinect.

#### Opslaan van skeleton data in XML 
[Link naar commit](https://github.com/Hans2131/KinectingPepper/commit/e1e495c31fee9789dd847aa6c96fc41f8c96b65e){:target="_blank"}
Na het uitlezen en weergeven van Kinect Data, was de volgende stap het opslaan van deze data. Hiervoor heb ik 'object serialization' naar XML gebruikt. De reden dat ik dit gedaan heb is ten eerste dat dit eenvoudig is te implementeren in C#, daarnaast wordt de data op die manier op de puurste manier opgeslagen waardoor de kans klein is dat data verloren gaat of vervormt raakt. Een nadeel van XML is dat dit formaat niet geschikt is voor bijvoorbeeld analyse in python. Om die reden heeft een klasgenoot een csv converter gemaakt die de data omzet naar een tabel formaat.

#### Toevoegen van simpele logging/feedback voor gebruiker 
[Link naar commit](https://github.com/Hans2131/KinectingPepper/commit/79c6081c43e47e82d249e4f789d19b3b190f4926){:target="_blank"}
Tijdens het testen van de opname functionaliteit kwam ik erachter dat ik weinig feedback kreeg over de huidige status van de applicatie. Op het moment dat ik het opnemen stopte, wist ik bijvoorbeeld niet of de juiste files werden opgeslagen. Om die reden heb ik een simpel logsysteem toegevoegd die op het huidige scherm een log weergeeft van de belangrijkste acties gedaan door de applicatie.

#### Afspelen van opgeslagen skeleton/video data 
[Link naar commit 1](https://github.com/Hans2131/KinectingPepper/commit/14c2d45adc2d4e13d61e2b30609eec9b40580cd9){:target="_blank"}
[Link naar commit 2](https://github.com/Hans2131/KinectingPepper/commit/0d2d2a06541cabdfd15b91388ea1b1a68d7d4127){:target="_blank"}
Een van de functionaliteiten die we als project groep nodig hadden was het bekijken van de opgeslagen data. Eén van mijn projectgenoten heeft hier de UI (een tweede scherm met knoppen zonder functionaliteit) voor gemaakt. In eerste instantie heb ik alleen een systeem gemaakt die de verschillende skeleton frames gebaseerd op tijd achter elkaar afspeelt. Laat heb ik hier extra functionaliteit aan toegevoegd zoals het afspelen van mp4 video beelden achter het skeleton, het handmatig verslepen van een slider om door de frames te kunnen bewegen en het bekijken van elke frame apart door er 1 voor 1 doorheen te stappen.

#### Effectief opslaan van MP4 files 
[Link naar commit](https://github.com/Hans2131/KinectingPepper/commit/0d2d2a06541cabdfd15b91388ea1b1a68d7d4127){:target="_blank"}
Een van mijn projectgenoten had functionaliteit geschreven in C++ die de beelden op kon slaan als mp4 formaat op de harde schijf. Omdat hij deze functionaliteit echter zelf geschreven had was dit totaal niet efficiënt. Er zaten fouten in het formaat en ook werd het opnemen van data sterk vertraagd. Ik ben dus op zoek gegaan naar bestaande functionaliteit voor het opslaan van bitmaps als een video formaat. Uiteindelijk heb ik hier Accord.NET voor gevonden, dit is een Machine Learning Framework die onder andere functionaliteit bevat voor het opslaan van videobeelden. 

Een van de problemen die ik echter ondervond, was dat het opslaan van beelden op de harde schijf een relatief traag proces is die veel invloed had op het aantal beelden die de applicatie per seconde kon verwerken. Om dit op te lossen heb ik multi threading gebruikt, dit houdt in dat er binnen de applicatie parallel een extra proces draait die zich alleen bezig houdt met het opslaan van videoframes. De werking gaat in het kort als volgende:
- Bij het starten van een opname wordt een nieuw proces gecreeërd met een bitmap queue en een loop die bitmaps uit de queue haalt en opslaat op de harde schijf
- Er komt een Kinect frame binnen die alle data bevat
- Kinect video frame data wordt omgezet naar een bitmap
- Bitmap wordt naar het andere proces gestuurd en daar in een queue gezet
- Nieuwe frames komen binnen terwijl het andere proces de oude frames parallel blijft opslaan

#### Verbeteren CSV converter 
[Link naar commit](https://github.com/Hans2131/KinectingPepper/commit/e7828eaaabcac984fe3d9cb215caaeeed6471372){:target="_blank"}
Omdat ik binnen de groep de meeste ervaring had in C# heb ik een klein deel van de functionaliteit voor het opslaan van CSV bestanden herschreven. Dit ging vooral over het openen van een te kiezen folder, en alle xml bestanden in deze folder converteren. Daardoor was de converter net iets beter bruikbaar.

#### Overige werkzaamheden zoals bugs oplossen
Naast het toevoegen van bovenstaande belangrijkste functionaliteit heb ik de volgende dingen gedaan
- Opzetten van vergaderingen tussen ontwikkelaars om wat beslissingen te nemen
- Oplossen van bugs
- Reviewen van wat code van projectgenoten
- Kleine, niet noemenswaardige functionaliteiten toegevoegd

