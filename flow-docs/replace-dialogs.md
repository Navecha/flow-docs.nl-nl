---
title: Dialoogvensters vervangen door bedrijfsprocesstromen of canvas-apps | Microsoft Docs
ms.custom: ''
ms.date: 08/02/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
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
ms.openlocfilehash: 498efb98a4c89ca6c2a01e345f5593beae4dbcca
ms.sourcegitcommit: 9ecf4956320d465a3bf618b79a9023b729d33c89
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/06/2019
ms.locfileid: "57463003"
---
# <a name="replace-dialogs-with-business-process-flows-or-canvas-apps"></a>Dialoogvensters vervangen door bedrijfsprocesstromen of canvas-apps

[Dialoogvensters zijn afgeschaft](https://docs.microsoft.com/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated) en moet worden vervangen door bedrijfsprocesstromen of canvas-apps. In dit onderwerp worden de verschillende mogelijkheden van deze opties beschreven.Ook worden situaties behandeld waarbij een bedrijfsprocesstroom of canvas-app die is ingesloten in een modelgestuurd formulier kan worden gebruikt om een bestaand dialoogvenster te vervangen.

## <a name="feature-capability-comparison"></a>Vergelijking van functies

Deze tabel bevat de set met dialoogvensterfuncties en de equivalente functies in bedrijfsprocesstromen en canvas-apps.


|Mogelijkheid in dialoogvenster  | Mogelijkheid in bedrijfsprocesstromen?  | Mogelijkheid in canvas-apps?  |
|---------|---------|---------|
|Pagina     | Ja <br/> (bedrijfsprocesfase)    | Ja <br/> (appscherm)        |
|Alleen prompt   |  Nee    |  Ja <br/> (labels)        |
|Vraag en antwoord     |  Ja <br/> (alleen entiteitskenmerken)    | Ja <br/> (labels en invoervelden)    |
|Invoerargumenten     |  Beperkt <br/> (stappen in bedrijfsprocesfase)    | Ja <br/> (parameters voor querytekenreeksen)     |
|Variabelen   |  Nee     |  Ja       |
|Queryvariabelen    |  Nee     |  Ja     |
|Voorwaardelijke vertakkingslogica    |  Ja     | Ja <br/>  (navigeren naar elk scherm in de app)    |
|Opnieuw gebruiken <br/> (starten als een onderliggend dialoogvenster)   |  Nee     | Ja <br/> (navigeren naar elk scherm in de app en een andere app in een nieuw venster starten)     |
|Werkstromen aan begin/einde uitvoeren    |   Ja      |  Nee <br/> (in plaats daarvan kan een stroom worden gebruikt)  |
|Werkstromen bij invoer uitvoeren    | Ja    | Nee <br/> (in plaats daarvan kan een stroom worden gebruikt)   |
|Werkstromen bij paginaovergang uitvoeren   |  Ja       | Nee <br/> (in plaats daarvan kan een stroom worden gebruikt)    |
|Starten via een URL  |   Nee      |  Ja     |
|Sessie registreren in logboek    |  Ja       |  Nee     |
|SDK-ondersteuning   |  Ja     |  Ja     |

### <a name="additional-capabilities-with-business-process-flows"></a>Aanvullende mogelijkheden met bedrijfsprocesstromen
- Analyse van proces (weergaven, diagrammen en bestede tijd in een fase)
- Aangepaste besturingselementen

### <a name="additional-capabilities-with-canvas-apps"></a>Aanvullende mogelijkheden met canvas-apps
- Analyse van apps (app-gebruik en -prestaties)
- Pagina met meerdere entiteiten samenstellen
- Stromen uitvoeren
- Gegevensconnectoren (standaard en aangepast)
- Starten als zelfstandige app
- Configureerbare indeling

## <a name="choosing-between-a-business-process-flow-or-canvas-app"></a>Kiezen tussen bedrijfsprocesstroom of canvas-app
Als u de vervanging voor dialoogvensters gaat kiezen, is het belangrijk dat u nadenkt over de gebruikerservaring die u wilt leveren. Vergeet niet dat bijna elk dialoogvenster kan worden gemodelleerd met behulp van een canvas-app.

Bedrijfsprocesstromen zijn bij uitstek geschikt om dialoogvensters te vervangen die processen modelleren die richtlijnen bieden voor een overkoepelende werkstroom die samenwerking vereist tussen groepen personen en binnen de context van de Dynamics 365-app. Bijvoorbeeld: prijsopgave en routering. 

U kunt canvas-apps ook gebruiken om dialoogvensters te vervangen die voorgeschreven taken modelleren, zoals een belscript voor leads, of voor het vereenvoudigen van de gebruikerservaring voor andere taken, zoals het bijwerken van een verkoopkans. Voor deze scenario's kan een zelfstandige canvas-app ook een goede keuze zijn. 

## <a name="dialog-replacement-using-business-process-flow-scenario"></a>Scenario voor vervanging van een dialoogvenster met behulp van bedrijfsprocesstroom
Stel dat u een dialoogvenster hebt waarmee voor een reeks pagina's belangrijke informatie wordt aangevraagd bij de gebruiker, een prijsopgave wordt gegenereerd, een e-mail naar revisoren wordt verzonden om de prijsopgave goed of af te keuren, waarna de offerte per e-mail naar de klant wordt verzonden. Dit type proces kan effectiever worden gemodelleerd met behulp van een bedrijfsprocesstroom. 

Voor het vervangen van het dialoogvenster moet u eerst de belangrijkste stappen in het proces bepalen. Denk hierbij bijvoorbeeld aan de fase *Inhoud voorbereiden* waarmee ervoor wordt gezorgd dat alle producten worden vermeld en kortingen zijn toegepast, de fase *Prijsopgave genereren* om de prijsopgave te maken en te beoordelen op nauwkeurigheid en indeling, de fase *Primaire beoordeling* waarin de prijsopgave wordt verzonden ter controle en goedkeuring, de fase *Secundaire beoordeling* waarin de prijsopgave wordt beoordeeld onder bepaalde omstandigheden en ten slotte de fase *Prijsopgave leveren* waarin de prijsopgave naar de klant wordt verzonden.

Daarna bepaalt u de belangrijkste stappen die gebruikers moeten volgen in het proces. Zo kan de fase *Inhoud voorbereiden* kan een eenvoudige waar/niet waar-stap omvatten waarbij de gebruiker de producten op de prijsopgave nogmaals controleert, een verplichte zoekstap om een prijslijst te selecteren en een numerieke stap om een korting in te voeren voordat de gebruiker doorgaat naar de volgende fase. De fase *Prijsopgave maken* kan een [actiestap](create-business-process-flow.md#add-an-on-demand-action-to-a-business-process-flow) bevatten om een prijsopgave te maken op basis van alle informatie die eerder is vastgelegd in de fase *Inhoud voorbereiden* en de bijbehorende Dynamics 365-record. De fasen *Primaire beoordeling* en *Secundaire beoordeling* bevatten mogelijk verschillende waar/niet waar-stappen alsook een vereiste stap voor het vastleggen van de goedkeuringsstatus. Tevens wordt ervoor gezorgd dat het proces alleen naar de volgende fase kan worden verplaatst als er goedkeuring is ontvangen. Configureer [beveiliging op veldniveau](/customer-engagement/admin/field-level-security) voor deze stap om ervoor te zorgen dat alleen bevoegde revisoren goedkeuring kunnen geven voor de prijsopgave.  Daarnaast kunt u een werkstroom toevoegen aan de fasen *Primaire beoordeling* en *Secundaire beoordeling*, zodat er bij invoer een e-mail wordt verzonden naar alle revisoren. 

Configureer ten slotte uw bedrijfsprocesstroomfasen en -stappen in combinatie met de voorwaardelijke logica voor de processtroom. In dit voorbeeld kunt u een [voorwaardelijke vertakking](enhance-business-process-flows-branching.md) toevoegen na de *Primaire beoordeling* zodat als een stap aangeeft dat een tweede beoordelingsniveau nodig is, de volgende fase in het proces de *Secundaire beoordeling* is of anders de fase *Prijsopgave leveren*.

Als u wilt dat deze bedrijfsprocesstroom beschikbaar is voor gebruikers, moet u ervoor zorgen dat de juiste gebruikers de bevoegdheden hebben voor de bedrijfsprocesstroom en moet u deze vervolgens activeren.

Zie voor meer informatie over het maken van een bedrijfsprocesstroom [Zelfstudie: Een bedrijfsprocesstroom maken om processen te standaardiseren](create-business-process-flow.md).

## <a name="dialog-replacement-using-canvas-app-scenario"></a>Scenario voor vervanging van een dialoogvenster met behulp van canvas-app

Stelt u zich eens voor dat u een dialoogvenster hebt dat een belscript volgt dat vertegenwoordigers begeleidt bij cold calls naar leads. Dit proces kan eenvoudig worden vastgelegd met behulp van een canvas-app.

Begin met verbinding maken met de gegevensbronnen die u nodig hebt om gegevens te kunnen lezen en schrijven. In dit voorbeeld wordt een [verbinding met Dynamics 365](/powerapps/maker/canvas-apps/connections/connection-dynamics-crmonline) gebruikt voor lead-, account- en contactgegevens.

Begin met het vaststellen van het aantal benodigde schermen. In dit voorbeeld besluit u vijf schermen te gebruiken. 
-   Scherm 1. Een lead in een lijst selecteren die u gaat bellen.
-   Scherm 2. Kennismaking, beschikbaarheid voor een gesprek controleren en terugbelmoment op een later tijdstip plannen. 
-   Scherm 3. Budget, bevoegdheid, behoefte en tijdlijn (BANT) bepalen. 
-   Scherm 4. Volgende stappen vastleggen en follow-upgesprekken plannen. 
-   Scherm 5. Lead bedanken voor zijn/haar tijd aan het einde van het gesprek.

Vervolgens gat u elke scherm maken. In het eerste scherm [maakt u een galerie](/powerapps/maker/canvas-apps/customize-layout-sharepoint) met leads die moeten worden gebeld. In het tweede scherm gebruikt u labels om het scherm een naam te geven en het belscript op te geven. Gebruik besturingselementen zoals keuzerondjes om vast te leggen of het een goed moment is voor de persoon om te praten. Als dit het geval is, gebruikt u voorwaardelijke logica om een knop in te schakelen om naar het volgende scherm te navigeren. Als het niet het geval is, toont u een script op hetzelfde scherm om te proberen een terugbelmoment te plannen met de klant. Zo kunt u ook uw belscript voor de hierop volgende schermen definiëren.

En als laatste [definieert u navigatie voor meerdere schermen](/powerapps/maker/canvas-apps/functions/function-navigate). In dit voorbeeld kunt u, naast achtereenvolgende navigatie door de schermen, de gebruiker van het tweede scherm naar het laatste scherm laten navigeren (het einde van het script waarbij de lead voor zijn/haar tijd wordt bedankt) als de lead niet geïnteresseerd is in een gesprek.

Als u deze app beschikbaar wilt stellen voor gebruikers, publiceert u de app. Overweeg hoe een dergelijk scenario kan worden getransformeerd met een zelfstandige app die belscripts levert en ondersteuning biedt voor snelle gegevensinvoer.

Stel dat u deze ervaring wilt insluiten in Dynamics 365 for Sales. U doet dit door eerst een iframe in een Dynamics 365 for Sales-formulier te maken. Vervolgens gaat u naar de sectie **Apps** in het menu PowerApps, selecteert u de app die u zojuist hebt gepubliceerd, kopieert u de koppeling op het tabblad **Details** en plakt u deze als de URL voor het iframe. 

We gaan nog een stapje verder. Stel dat u wilt dat deze app rechtstreeks vanuit het leadhoofdformulier beschikbaar is en in de context van de lead wordt geplaatst, zodat de app niet vereist dat de gebruiker een lead op het eerste scherm selecteert. Als u relevante informatie wilt doorgeven aan de app, past u gewoon de URL voor het iframe aan om een querytekenreeks met deze informatie bij te voegen, zoals lead- of account-id's, met behulp van JavaScript dat voor een specifieke gebeurtenis wordt uitgevoerd, bijvoorbeeld het laden van het formulier. Werk vervolgens de app bij om het eerste scherm (voor selectie van lead) te verwijderen en open in plaats daarvan de waarden die via de querytekenreeks met behulp van de [Param-functie](/powerapps/maker/canvas-apps/functions/function-param) zijn doorgegeven aan de app.

## <a name="dialog-replacement-faq"></a>Veelgestelde vragen over vervanging van dialoogvensters

Worden afhankelijkheden van canvas-apps bijgehouden? 
- Afhankelijkheden van canvas-apps worden op dezelfde manier bijgehouden als afhankelijkheden in Dynamics 365 for Customer Engagement.

Kan ik een canvas-app starten als een pop-upvenster met een knop in de opdrachtbalk?
- Ja. Dit doet u door de doel-URL in te stellen op die van de canvas-app. Dit is de waarde die is verkregen uit de sectie **Details** van de app, zoals eerder beschreven.

Kunnen werkstromen worden aangeroepen vanuit een canvas-app?
- Dit wordt niet ondersteund. Hiervoor kunt u beter een stroom gebruiken. Meer informatie: [Inleiding voor knopstromen met gebruikersinvoer](button-flow-with-user-input-tokens.md)

Kan ik dialoogvensters automatisch omzetten in bedrijfsprocesstromen of canvas-apps?
- Er bestaat geen geautomatiseerde manier om dialoogvensters om te zetten in bedrijfsprocesstromen of canvas-apps.


## <a name="see-also"></a>Zie ook
[Zelfstudie: Een bedrijfsprocesstroom maken om processen te standaardiseren](create-business-process-flow.md) </br>
[Wat zijn canvas-apps in PowerApps?](/powerapps/maker/canvas-apps/getting-started)


