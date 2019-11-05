---
title: Dialoog vensters vervangen door bedrijfs proces stromen of canvas-apps | MicrosoftDocs
ms.custom: ''
ms.date: 08/02/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- flow
ms.assetid: 046480e6-f2ff-4c56-9e03-f642c982ff7d
caps.latest.revision: 12
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: a7e8bac3c33fa5bb8cfb0501b981af65115036ea
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548820"
---
# <a name="replace-dialogs-with-business-process-flows-or-canvas-apps"></a>Dialoog vensters vervangen door bedrijfs proces stromen of canvas-apps
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

[Dialoog vensters zijn afgeschaft](https://docs.microsoft.com/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated)en moeten worden vervangen door bedrijfs proces stromen of canvas-apps. In dit onderwerp worden verschillende mogelijkheden van deze opties beschreven, evenals situaties waarbij een bedrijfs proces stroom-of canvas-app die is inge sloten in een model formulier kan worden gebruikt om een bestaand dialoog venster te vervangen.

## <a name="feature-capability-comparison"></a>Vergelijking functie functies

Deze tabel bevat een lijst met de mogelijkheden van het dialoog venster en de equivalente mogelijkheden van bedrijfs processen en op canvas-apps.


|Dialoog mogelijkheid  | Mogelijkheden van bedrijfs proces stromen  | Mogelijkheden in canvas-apps?  |
|---------|---------|---------|
|Faxvoorblad     | Klikt <br/> (fase van het bedrijfs proces)    | Klikt <br/> (app-scherm)        |
|Alleen prompt   |  Geen    |  Klikt <br/> Labels        |
|Vraag en antwoord     |  Klikt <br/> (alleen entiteits kenmerken)    | Klikt <br/> (labels en invoer velden)    |
|Invoer argumenten     |  Aantal <br/> (stappen in de fase van het bedrijfs proces)    | Klikt <br/> (query reeks parameters)     |
|Variabelen   |  Geen     |  Klikt       |
|Query variabelen    |  Geen     |  Klikt     |
|Voorwaardelijke vertakkings logica    |  Klikt     | Klikt <br/>  (Navigeer naar elk scherm in de app)    |
|Gebruikt <br/> (starten als onderliggend dialoog venster)   |  Geen     | Klikt <br/> (Ga naar een scherm in de app, start een andere app in een nieuw venster)     |
|Werk stromen uitvoeren bij begin/einde    |   Klikt      |  Geen <br/> (gebruik in plaats daarvan een stroom)  |
|Werk stromen uitvoeren op invoer    | Klikt    | Geen <br/> (gebruik in plaats daarvan een stroom)   |
|Werk stromen uitvoeren op pagina overgang   |  Klikt       | Geen <br/> (gebruik in plaats daarvan een stroom)    |
|Beginnen met het gebruik van een URL  |   Geen      |  Klikt     |
|Sessie logboek registratie    |  Klikt       |  Geen     |
|SDK-ondersteuning   |  Klikt     |  Klikt     |

### <a name="additional-capabilities-with-business-process-flows"></a>Aanvullende mogelijkheden met bedrijfs proces stromen
- Proces analyse (weer gaven, grafieken en tijd die aan een fase zijn besteed)
- Aangepaste besturings elementen

### <a name="additional-capabilities-with-canvas-apps"></a>Aanvullende mogelijkheden met canvas-apps
- App-analyse (app-gebruik & prestaties)
- Pagina samenstelling met meerdere entiteiten
- Stromen uitvoeren
- Gegevens connectors (standaard en aangepast)
- Starten als zelfstandige app
- Configureer bare indeling

## <a name="choosing-between-a-business-process-flow-or-canvas-app"></a>Kiezen tussen een bedrijfs proces stroom of een canvas-app
Wanneer u de vervanging van het dialoog venster kiest, is het belang rijk dat u rekening moet doen met de gebruikers ervaring die u wilt leveren. Houd er ook rekening mee dat bijna elk dialoog venster kan worden gemodelleerd met behulp van een canvas-app.

Bedrijfs proces stromen zijn het meest geschikt voor het vervangen van dialoog vensters waarin processen worden geboden over een overkoepelend-workstream waarvoor samen werking tussen groepen personen en Dynamics 365-app-context is vereist. Bijvoorbeeld: offerte beoordeling en route ring. 

Canvas-apps kunnen ook worden gebruikt om dialoog vensters te vervangen die een model maken van voorscriptieve taken, zoals een aanroep script voor potentiële klanten of de gebruikers ervaring voor andere taken te vereenvoudigen, zoals het bijwerken van een verkoop kans. Houd er rekening mee dat deze scenario's zelfs kunnen profiteren van een zelfstandige canvas-app. 

## <a name="dialog-replacement-using-business-process-flow-scenario"></a>Vervanging van dialoog vensters met scenario voor bedrijfs processen stroom
Stel dat u een dialoog venster hebt dat, op een reeks pagina's, belang rijke gegevens van de gebruiker opvraagt, een offerte genereert, een e-mail verzendt naar revisoren om de offerte te accepteren of afwijzen, voordat deze naar de klant wordt verzonden. Dit type proces wordt effectiever gemodelleerd met behulp van een bedrijfs proces stroom. 

Om het dialoog venster te vervangen, moet u eerst de belangrijkste fasen in het proces identificeren. Dit kan een *voorbereidings inhouds* fase omvatten om ervoor te zorgen dat alle producten worden weer gegeven en kortingen worden toegepast, een *offerte fase genereren* om de offerte te maken en deze te controleren op nauw keurigheid van de indeling, een *primaire beoordelings* fase voor het verzenden van de offerte voor beoordeling en goed keuring, een *tweede beoordelings* fase voor het controleren van de offerte onder bepaalde omstandigheden en tot slot, een *aflever* fase om de offerte naar de klant te verzenden.

Bepaal vervolgens de belangrijkste stappen die gebruikers in het proces moeten volgen. De voor *bereide inhouds* fase kan bijvoorbeeld een eenvoudige waar-of onwaar-stap bevatten voor de gebruiker om te controleren of de producten moeten worden genoteerd, een verplichte Zoek stap om een prijs lijst te selecteren en een numerieke stap om een korting in te voeren voordat u doorgaat naar de volgende fase. De fase *offerte genereren* kan een [actie stap](create-business-process-flow.md#add-an-on-demand-action-to-a-business-process-flow) bevatten voor het maken van een offerte op basis van alle gegevens die eerder zijn vastgelegd in de inhouds fase voor het *voorbereiden* en de gerelateerde Dynamics 365-record. De *primaire beoordeling* en *secundaire controle* fasen kunnen verschillende waar of onwaare stappen hebben om de offerte beoordeling te begeleiden, samen met een vereiste stap voor het vastleggen van de goedkeurings status en ervoor te zorgen dat het proces alleen kan worden verplaatst naar de volgende fase zodra goed keuring is Ontvangen. Configureer [beveiliging op veld niveau](/customer-engagement/admin/field-level-security) voor deze stap om ervoor te zorgen dat alleen geautoriseerde revisoren goed keuring kunnen bieden op de offerte.  Daarnaast kan een werk stroom aan de *primaire beoordeling* en *secundaire controle* fasen worden toegevoegd, zoals bij invoer, een e-mail melding wordt verzonden naar alle revisoren. 

Configureer tot slot uw bedrijfsproces stroom fasen en stappen, samen met de voorwaardelijke logica, om de proces stroom te begeleiden. Voor dit voor beeld kunt u een [voorwaardelijke vertakking](enhance-business-process-flows-branching.md) toevoegen die volgt op de *primaire beoordelings* fase, zodat, als een stap aangeeft dat er een tweede beoordelings niveau nodig is, de volgende fase in het proces de *secundaire revisie* fase is, anders, *het Aflever* fase van de offerte.

Als u deze bedrijfsproces stroom beschikbaar wilt maken voor gebruikers, zorg er dan voor dat de juiste gebruikers bevoegdheden hebben voor de stroom van het bedrijfs proces en vervolgens te activeren.

Zie [zelf studie: een bedrijfsproces stroom maken om processen te standaardiseren](create-business-process-flow.md)voor meer informatie over het maken van een bedrijfs proces stroom.

## <a name="dialog-replacement-using-canvas-app-scenario"></a>Vervanging van dialoog vensters met het canvas-app-scenario

Stel dat u een dialoog venster hebt dat een aanroepend script volgt dat verkoop medewerkers begeleidt via koude aanroepen van leads. Dit proces kan eenvoudig worden vastgelegd met behulp van een canvas-app.

Begin met het maken van verbinding met de gegevens bronnen die u nodig hebt om gegevens te lezen en te schrijven. In dit voor beeld wordt een [verbinding met Dynamics 365](/powerapps/maker/canvas-apps/connections/connection-dynamics-crmonline) gebruikt voor lead-, account-en contact gegevens.

Begin met het identificeren van het aantal schermen dat nodig is. Voor dit voor beeld kunt u besluiten om vijf schermen te hebben. 
-   Scherm 1. Een lead selecteren in een lijst om aan te roepen.
-   Scherm 2. Voor introducties, het controleren van de beschik baarheid voor een gesprek en het plannen van een terugbellen op een later tijdstip. 
-   Scherm 3. Voor het bepalen van BANT (budget, instantie, behoefte en tijd lijn). 
-   Scherm 4. Volgende stappen vastleggen en opvolgings aanroepen plannen. 
-   Scherm 5. Hartelijk dank dat u aan het einde van de oproep de potentiële klant hebt.

Vervolgens bouwt u elk scherm. Bouw in het eerste scherm [een galerie](/powerapps/maker/canvas-apps/customize-layout-sharepoint) met leads die moeten worden aangeroepen. In de tweede gebruikt u labels voor de titel van het scherm en geeft u het aanroepende script op, terwijl u besturings elementen als keuze rondjes gebruikt om vast te leggen of het een goede tijd is voor de communicatie van de persoon. Als dat het geval is, gebruikt u voorwaardelijke logica om een knop in te scha kelen naar het volgende scherm. als dat niet zo is, onthult u een script op hetzelfde scherm om te proberen een oproep terug te plannen met de klant. Op dezelfde manier kunt u het aanroepen van scripts op volgende schermen definiëren.

Definieer ten slotte [Navigatie op verschillende schermen](/powerapps/maker/canvas-apps/functions/function-navigate). In dit voor beeld is het mogelijk dat u, naast het volgen van de schermen, de gebruiker wilt navigeren van het tweede scherm naar het laatste scherm (het einde van het script dat de lead voor hun tijd verdankt) als de lead niet geïnteresseerd is in een gesprek.

Als u deze app beschikbaar wilt maken voor gebruikers, publiceert u de app. Denk na over de manier waarop een scenario kan worden omgezet via de beschik baarheid van een zelfstandige app die aanroepende scripts biedt en snelle gegevens invoer ondersteunt.

Stel dat u deze ervaring wilt insluiten in Dynamics 365-omzet. Als u dit wilt doen, begint u met het maken van een iframe op een Dynamics 365-verkoop formulier. Ga vervolgens naar het gedeelte **apps** in het PowerApps-menu, selecteer de app die u zojuist hebt gepubliceerd, kopieer de webkoppeling onder het tabblad **Details** en plak deze als de URL voor de IFRAME. 

Als u deze stap verder uitvoert, wilt u dat deze app beschikbaar is in het hoofd formulier Lead en zich in de context van de lead bevindt, zodat de gebruiker in het eerste scherm geen lead hoeft te selecteren. Als u relevante informatie wilt door geven aan de app, wijzigt u eenvoudigweg de iframe-URL om een query reeks toe te voegen die deze informatie bevat, zoals lead-of account-Id's, met behulp van Java script dat wordt uitgevoerd op een bepaalde gebeurtenis, zoals bij het laden van formulieren. Werk vervolgens de app bij om het eerste scherm (voor het selecteren van leads) te verwijderen en in plaats daarvan toegang te krijgen tot de waarden die worden door gegeven aan de app via de query reeks met behulp van de [functie param](/powerapps/maker/canvas-apps/functions/function-param).

## <a name="dialog-replacement-faq"></a>Veelgestelde vragen over dialoogvenster vervanging

Zijn afhankelijkheden op canvas-apps te volgen? 
- Afhankelijkheden van canvas-apps worden op dezelfde manier bijgehouden als afhankelijkheden in Dynamics 365-apps.

Kan ik een canvas-app starten als een pop-upvenster van een knop op de opdracht balk?
- Klikt. U doet dit door eenvoudigweg de doel-URL in te stellen op die van uw canvas-app, die u hebt verkregen in de sectie **Details** van de app, zoals eerder beschreven.

Kunnen werk stromen worden aangeroepen vanuit een canvas-app?
- Dit wordt niet ondersteund. Het is raadzaam om in plaats daarvan een stroom te gebruiken. Meer informatie: [introductie van knop stromen met gebruikers invoer](button-flow-with-user-input-tokens.md)

Kan ik automatisch dialoog vensters converteren naar stromen voor bedrijfs processen of op canvas-apps?
- Er is geen geautomatiseerde manier om dialoog vensters te converteren naar bedrijfs proces stromen of canvas-apps.


## <a name="see-also"></a>Zie ook
[Zelf studie: een bedrijfs proces stroom maken om processen te standaardiseren](create-business-process-flow.md) </br>
[Wat zijn canvas-apps in PowerApps?](/powerapps/maker/canvas-apps/getting-started)


