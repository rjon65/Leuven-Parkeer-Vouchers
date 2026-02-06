# Leuven-Parkeer-Vouchers
Informatie, [discussie](https://github.com/rjon65/Leuven-Parkeer-Vouchers/discussions) en [probleem](https://github.com/rjon65/Leuven-Parkeer-Vouchers/issues) rapportering voor Leuven Parkeer Vouchers app

# Introductie
De app laat je toe om je parkeer vouchers te beheren, parkeersessies in te plannen en vouchers via 4411 te gebruiken of naar een contact door te sturen.
Alle informatie wordt in een real-time database bijgehouden zodat alle gebruikers in dezelfde groep steeds een zicht hebben op de laatste status.
Bij het plannen van een parkeersessie wordt steeds een optimale combinatie (oudste eerst en dan minimaal aantal) van vouchers gebruikt waarbij die met de kortste duurtijd eerst worden gebruikt.
Een lopende parkeersessie kan afgebroken worden waarbij de niet gebruikte vouchers terug worden vrijgegeven.

Bevestigingsberichten van **4411** (indien actief) worden gecheckt waar volgende acties aan zijn gekoppeld:
- Bevestiging start: wordt geannoteerd op de voucher
- Bevestiging einde:
  - Indien 10 minuten voor verwachte eindtijd wordt de parkeersessie herpland
- Bevestiging aan/uitzetten bevestigingsberichten:
  - Status wordt lokaal opgeslaan

Bij gebruik van een foute, reeds gebruikte, of verlopen voucher wordt dit via een gratis SMS van **8920** gemeld en wordt de resterende duurtijd van de parkeersessie herpland. 
Dit zou in principe niet mogen gebeuren, maar je weet nooit.

# Gestart geraken
## Installeren
De app kun je downloaden via de OneDrive link die ik je stuur.
Google zal die eerst screnen (en dat zou geen problemen mogen opleveren) waarna je kunt installeren.
Antivirus programma's kunnen wel wat moeilijk doen

## Aanmelden
Eerst zul je een account moeten aanmaken (email + paswoord) waarna je in een wachtrij terecht komt.
Op dat moment kun je:
- ofwel (door mij) als beheerder van een groep aangesteld worden
- ofwel door een groep beheerder (of ikzelf) tot een groep toegelaten worden

## Instellen
Het is aangeraden om een PIN in stellen om jezelf te beschermen tegen ongewenste operaties (en die ook niet te tonen wanneer niet nodig).

Om correct te werken moet de app bepaalde rechten krijgen:
- Essentieel
  - Zonder deze rechten kun je de app niet gebruiken en het startscherm geeft een menu optie als dit het geval is.
  - Deze rechten moeten vanaf Android 13 buiten de app om toegestaan worden in het App Info scherm waar je via de "3 stippen" rechts bovenaan "Beperkte instellingen toestaan" selecteert en vervolgens rechten toevoegt voor:
    - Wekkers en herinneringen (om SMSen in de toekomst te kunnen sturen)
    - SMS (sturen en lezen van ontvangen SMSen) 
- Comfortabele werking
  - Deze rechten worden gevraagd binnen de app op het moment dat die nodig zijn:
    - Camera (scannen van vouchers en nummerplaat)
    - Berichten (foutboodschappen)


# Groep Beheerder Functies
De OneDrive link kun je doorsturen naar mensen die je van jouw vouchers gebruik wil laten maken (en als medebeheerder aanstellen)

Als groep beheerder kun je het volgende beheren:
- Leden
- Vouchers

## Instellingen
Hier kun voor **test mode** optereren door bvb je eigen te nummer gebruiken ipv 4411 om parkeersessies to starten.
Vouchers die op die manier gebruikt of gereserveerd zijn, kun je weer vrijgeven onder **Beheer** _jouw groep_ **groep**

## Beheer groep

### Beheer vouchers
- Zonder te ontgrendelen krijg je een filterbaar overzicht van de vouchers
- Na het ontgrendelen kun je
  - Vouchers scannen
  - Een voucher manueel invoeren
  - Individuele vouchers bewerken of verwijderen
  - Groepen van vouchers editeren of verwijderen
 
### Scan consistentie parameter
Deze waarde wordt gebruikt door de tekst herkenning om ruis te vermijden en staat bij default op 5.
Voor een eerste poging van het scannen van een voucher lijst is dit een goede waarde.
Maar soms is het lastig om de laatste codes gelezen te krijgen en kun je dan een lagere waarde instellen in combinatie met het gebruik van een langere prefix
