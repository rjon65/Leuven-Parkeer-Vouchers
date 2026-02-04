# Leuven-Parkeer-Vouchers
Informatie, discussie en probleem rapportering voor Leuven Parkeer Vouchers app

# Introductie
De app laat je toe om je parkeer vouchers te beheren, parkeersessie in te plannen en vouchers via 4411 te gebruiken of naar een contact door te sturen.
Alle informatie wordt in een real-time database bijgehouden zodat alle gebruikers in dezelfde groep steeds een zicht hebben op de laatste status.
Bij het plannen van een parkeersessie wordt steeds een optimale combinatie (minimaal aantal) van vouchers gebruikt waarbij die met de kortste duurtijd eerst worden gebruikt.
Een lopende parkeersessie kan ook afgebroken worden waarbij de niet gebruikte vouchers terug worden vrijgegeven.

Bevestigingsberichten van 4411 (indien actief) worden gecheckt waar volgende acties worden aan gekoppeld:
- Bevesting start: wordt geannoteerd op de voucher
- Bevesting einde:
  - Indien 10 minuten voor verwachte eindtijd wordt de parkeersessie herpland
- Foute voucher code (dit komt via een gratis SMS op **8920** binnen):
  - Parkeersessie wordt herpland

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

# Groep Beheerder
De OneDrive link kun je doorsturen naar mensen die je van jouw vouchers gebruik wil laten maken (of zelfs medebeheerder)

Als groep beheerder kun je het volgende beheren:
- Leden
- Vouchers

## Test mode
In test mode kun je bvb je eigen nummer gebruiken ipv 4411 om parkeersessies to starten.
Vouchers die op die manier als gebruikt zijn, kun je dan wel weer vrijgeven

## Voucher beheer
Dit kan in twee schermen
- Vouchers
   - Overzicht van vouchers
   - Na unlocken 
     - Vouchers scannen
     - Een voucher manueel invoeren
     - Individuele vouchers bewerken of verwijderen
  
- Instellingen
  - Bulk veranderingen van vouchers
  - Instellen van een prefix lengte bij het inscannen (voor vouchers van hetzelfde type zijn de eerste 7 of 8 karakters hetzelfde). Dit op een hogere waarde dan 3 (LEU) zetten vermindert het risico op foute scans.
