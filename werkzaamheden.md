## Werkzaamheden voor Pepper project

### Opstarten van project
Tijdens het opstarten van het project hebben we eerst vooronderzoek gedaan, in deze fase hebben we zoveel mogelijk vooronderzoek gedaan en de gevonden informatie in een document gezet. Ik daarbij vooral bijgedragen aan onderzoek naar technische mogelijkheden.
- [Link document met informatie (pdf)](producten/werkzaamheden/Aanpak_vooronderzoek.pdf){:target="_blank"}

Daarnaast hebben we een plan van aanpak opgesteld, hier heb ik ook aan meegeholpen.
- [Link naar plan van aanpak (pdf)](producten/werkzaamheden/Plan_van_aanpak.pdf){:target="_blank"}

### Werken met RealSense ZR300
De eerste twee weken van het project heb ik gewerkt met de RealSense ZR300 dieptecamera. Omdat we uiteindelijke tot de conclusie kwamen dat we de camera niet konden gebruiken zijn hier geen producten uit voorgekomen. Wat heb ik tijdens deze weken gedaan:
- ZR300 op Window werkend gekregen, we dachten eerst dat we  alleen op Linux konden werken met de ZR300
- Zoveel mogelijk informatie, documentatie en code over de ZR300 verzamelen
- De OpenCV librarie werkend proberen te krijgen met de ZR300, hierbij geen succes gehad

![Screenshot ZR300](producten/werkzaamheden/Printscreen_zr300.png "Werkend op windows")

### Keuze voor Kinect
Tijdens het werken met de ZR300 kwamen we er als projectgroep achter dat de ZR300 niet goed ondersteunt werd met software die functionaliteit biedt die wij nodig hadden. Ik ben daarom op zoek gegaan naar alternatieven en kwam daarmee uit op de Kinect. De argumenten en informatie voor het gebruik van de Kinect heb ik verwerkt in een document.

[Kinect vs RealSense (pdf)](producten/werkzaamheden/Kinect_vs_RealSense.pdf){:target="_blank"}

### Applicatie voor Kinect (EDIT THIS WHEN ADDING DOCUMENTATION) (ADD SCREENSHOTS OF APPLICATION)
Dit is het product waar ik tijdens het project verantwoordelijk voor ben geweest, en waar ik de meeste tijd in heb gestoken. Onderstaande link verwijst naar een pagina waar ik per deel functionaliteit kort beschrijf wat ik aan de applicatie heb toegevoegd.

[Belangrijk! Beschrijving toegevoegde functionaliteit Kinect applicatie](producten/werkzaamheden/kinecting_pepper.md){:target="_blank"}

### Opnemen Kinect Data
Omdat ik het grootste deel van de opname applicatie gemaakt heb wist ik hier tijdens het project ook het meeste van af. Dit maakte mij tijdens de opnamesessies de aangewezen persoon om mensen op te nemen. Overigens was de applicatie wel zo gemaakt dat ook andere zonder al te veel kennis gebruik konden maken van de applicatie. Ik was verantwoordelijk voor opnames (bediening van applicatie) tijdens de volgende opnamesessies, bij elkaar was ik betrokken bij ongeveer 70% van de opnames:
- Verschillende testen voor de projectgroep zelf
- Opnamesessie in het Atrium
- Opnamesessies van scholieren die zelfstandig naar het lokaal kwam als reactie op bericht blackboard

#### Organiseren data op server
Eén van de problemen waar ik tijdens het project tegen aan liep was het feit dat de data die we verzamelden niet echt georganiseerd op de server gezet werden. Om die reden heb ik de dat op de server per opname sessie in een folder gezet.
![Screenshot data georganiseerd](producten/werkzaamheden/Capture_data_organised.png)

Daarnaast heb ik een handleiding gemaakt voor het toevoegen van nieuwe data op de server.

[Link handleiding data (pdf)](producten/werkzaamheden/Handleiding_uploaden_data.pdf){:target="_blank"}

#### Cleaning van data met python
De data van een opname bevatten veel overbodige frames, dit komt doordat op het moment dat de opname met de applicatie gestart wordt de oefening niet direct begint. Mijn code verwijdert deze overbodige frames op basis van data uit een excel file. Dit betekent dat projectgenoten alleen de start en eind frames van een oefening in een excellijst hoefden te zetten en mijn script hoefden te runnen. Later is mijn code door andere klasgenoten licht aangepast zodat het met meerdere excel sheets overweg kon.

[Link naar notebook](https://github.com/Hans2131/Portfolio14137879/blob/master/producten/werkzaamheden/Cleaning%2Bdata%2Bfunctions%2Bv2.ipynb){:target="_blank"}

#### Pepper treintje
De functionaliteit van het Pepper Treintje is vooral bedacht door teamgenoten omdat ik vooral bezig was met de applicatie KinectingPepper. Later tijdens het project was mijn hulp echter nodig omdat we het treintje niet op tijd af zouden krijgen. Het teamgenoot die verantwoordelijk was voor toen huidige codebase had alles gemaakt in een normale python environment. Dit was echter niet handig omdat ik daardoor niet makkelijk mee kon helpen, ik heb daarom eerst alles overgezet naar Notebooks en alles toegevoegd aan een Github repository. 

[Link naar Github repository met code treintje](https://github.com/KinectingPepper/spark_train){:target="_blank"}

Mijn bijdrages zijn voor geweest:
- Splitsen van grote methode met functionaliteit in kleine meer behapbare methodes
- Programmeren data flow door treintje, elke stuk functionaliteit levert data voor een volgend stukje functionaliteit
- Oplossen van wat bugs
 
 Op het moment van schrijven is de code nog niet efficient en hoewel het treintje werkt werken de stukken functionaliteit onderling nog niet echt goed. (EDIT THIS AFTER NEW PRORESS ON TRAIN)

Uiteindelijk heb ik aan de volgende twee files gewerkt:
- [Link Notebook 'Code Train'](https://github.com/KinectingPepper/spark_train/blob/master/Code%20Train.ipynb){:target="_blank"}
- [Link Notebook 'Run Train'](https://github.com/KinectingPepper/spark_train/blob/master/Run%20Train.ipynb){:target="_blank"}

#### Gesprekken opdrachtgever
Ik ben op verschillende momenten meegeweest voor een gesprek met een opdrachtgever of andere stakeholder
- Drie keer op bezoek geweest bij manueel therapeut UMC Leiden
- Eén keer op bezoek geweest bij sport fysio Zuiderpark

#### Presentaties 
- [Link presentatie 1 (pdf)](producten/werkzaamheden/presentaties/Extern_P2.pdf){:target="_blank"}
- [Link presentatie 2 (pdf)](producten/werkzaamheden/presentaties/Externe_presentatie_6_Okt.pdf){:target="_blank"}
- [Link presentatie 3 (pdf)](producten/werkzaamheden/presentaties/Extern_22_December_DEMO.pdf){:target="_blank"}
- [Link presentatie 4 (pdf)](producten/werkzaamheden/presentaties/Intern_P10.pdf){:target="_blank"}
