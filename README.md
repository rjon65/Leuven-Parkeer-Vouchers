# Leuven-Parkeer-Vouchers
Informatie, [discussie](https://github.com/rjon65/Leuven-Parkeer-Vouchers/discussions) en [probleem rapportering](https://github.com/rjon65/Leuven-Parkeer-Vouchers/issues) voor Leuven Parkeer Vouchers app

# Introductie
De app laat je toe om je parkeer vouchers in te lezen, parkeersessies in te plannen en vouchers via de 4411 SMS service te gebruiken of naar een contact door te sturen.
Alle informatie wordt in een real-time database bijgehouden zodat gebruikers in groep steeds een zicht hebben op de laatste status.
Groepen zijn van elkaar afgeschermd en data is geencrypteerd door een door de groep beheerder ingestald paswoord (dus ook niet voor mij zichtbaar).
Bij het plannen van een parkeersessie wordt steeds een optimale combinatie (oudste eerst en dan minimaal aantal) van vouchers gebruikt waarbij die met de kortste duurtijd eerst worden gebruikt.
Een lopende parkeersessie kan afgebroken worden waarbij de niet gebruikte vouchers terug worden vrijgegeven.

Bevestigingsberichten van **4411** (indien actief) worden gecheckt waar volgende acties aan zijn gekoppeld:
- Bevestiging start: wordt geannoteerd op de voucher
- Bevestiging einde:
  - Indien 10 minuten voor verwachte eindtijd wordt de parkeersessie herpland
  - _Zou dit een configureerbare instelling moeten zijn voor de groep beheerder?_
- Bevestiging aan/uitzetten bevestigingsberichten:
  - Status wordt lokaal opgeslaan

Bij gebruik van een foute, reeds gebruikte, of verlopen voucher wordt dit via een gratis SMS van **8920** gemeld en wordt de resterende duurtijd van de parkeersessie herpland. 
Dit zou in principe niet mogen gebeuren, maar je weet nooit.

# 4411 SMS service
Omdat de 4411 app geen toegankelijke API heeft, wordt de SMS service gebruikt. De kostprijs is 0.15 per SMS.
  - Als je bevestigingsberichten hebt geactiveerd kost je dit 0.45 💶 per geactiveerde voucher
  - Zonder bevestigingsberichten kost een voucher activering je 0.15 💶
      - Eventuele foutberichten ontvang je wel nog via een gratis SMS
  - Via de app kost een een voucher activering 0.35 💶

# Gestart geraken
## Installeren
De app kun je downloaden via de OneDrive link die ik je stuur.
Bij het installeren wordt de app eerst gescreend (en dat zou geen problemen mogen opleveren) waarna de eigenlijke installatie kan gebeuren.
Antivirus programma's kunnen wel wat moeilijk doen.

## Aanmelden
Eerst zul je een account moeten aanmaken (email + paswoord) waarna je in een wachtrij terecht komt.
Op dat moment kun je:
- ofwel (door mij) als beheerder van een groep aangesteld worden
- ofwel door een groep beheerder tot een groep toegelaten worden, die je dan ook nog het groep paswoord moet aanleveren

## Instellingen
### PIN
Het is aangeraden om een PIN in stellen zodat edit/delete operaties standaard niet getoond worden.

Om correct te werken moet de app bepaalde rechten krijgen:
- Essentieel
  - Zonder deze rechten kun je de app niet gebruiken en het startscherm geeft een menu optie als dit het geval is.
  - Deze rechten moeten vanaf Android 13 buiten de app om toegestaan worden in het App Info scherm waar je via de "3 stippen" rechts bovenaan "Beperkte instellingen toestaan" selecteert en vervolgens rechten toevoegt voor:
    - Wekkers en herinneringen (om SMSen in de toekomst te kunnen sturen)
    - Sms (sturen en lezen van ontvangen SMSen) 
- Comfortabele werking
  - Deze rechten worden gevraagd binnen de app op het moment dat die nodig zijn:
    - Berichten (foutboodschappen)
    - Camera (scannen van vouchers en nummerplaat)

### Groep paswoord
Dit paswoord moet je groep beheerder je aanleveren. Zonder paswoord heb je geen toegang tot de data.

# Groep Beheerder Functies
Stuur de OneDrive link naar de app + het groep paswoord naar mensen die je van jouw vouchers gebruik wil laten maken.

Als groep beheerder kun je het volgende beheren:
- Leden
- Vouchers

## Instellingen
Hier kun je voor de **test mode** opteren door bvb je eigen te nummer gebruiken ipv 4411 om parkeersessies to starten.
Zo verlies je geen vouchers en heb je geen kosten eigen aan 4411 gebruik.
Vouchers die op die manier gebruikt of gereserveerd zijn, kun je weer vrijgeven onder **Beheer** _jouw groep_ **groep**

## Beheer groep

### Encryptie
Data wordt geencrypteerd opgeslagen in de realtime database. Als groep beheerder moet je daarom eerst een paswoord (van 128 karakters) genereren.
Sla dit paswoord op op een veilige plaats want als die verloren gaat uit je settings heb je geen toegang meer tot de data.
Dit paswoord moet ook je doorsturen naar groepsleden om hen toegang te verlenen.

### Backup
Hiermee kun je je groep data (vouchers, nummerplaten, en contacten) opslaan in een CVS file op je Google Drive en ook terug importeren of in Excel inlezen.

### Beheer vouchers
- Zonder te ontgrendelen krijg je een filterbaar overzicht van de vouchers
- Na het ontgrendelen kun je vouchers:
  - Van PDF file(s) inlezen.
    - Mocht je niet (meer) over de elektronische versie beschikken dan zijn er de volgende alternatieven:
      - Vouchers scannen
      - Vouchers manueel invoeren
  - Bewerken of verwijderen
 
#### Voucher scan parameters
Omdat het scannen nogal variabel is qua resultaat, zijn er een aantal parameters waar je kunt mee spelen om tot een beter resultaat te komen
##### Scan consistentie
Deze waarde wordt gebruikt door de tekst herkenning om ruis (vals positieven) te vermijden en staat bij default op 5.
Voor een eerste poging van het scannen van een voucher lijst is dit een goede waarde.
Maar soms is het lastig om de laatste codes gelezen te krijgen en kun je dan een lagere waarde instellen in combinatie met het gebruik van een langere prefix

##### Prefix
Bij mijn observatties starten vouchers van eenzelfde type en zelfde geldigheidsdatum met de 8 zelfde karakters (dit aantal wordt weergegeven op het voucher scherm).
Om de kans op valse positieven verder te vermijden kun je meer karakters specifieren dan de default **LEU**.
Als je een lijst al gedeeltelijk hebt gescand wordt de default automatisch verlengd met wat geld voor de al bestaande lijst.

##### Ingebouwd
Er wordt gechekt of een nieuwe voucher minimaal 2 karakters verschilt van de reeds ingelezen vouchers.

