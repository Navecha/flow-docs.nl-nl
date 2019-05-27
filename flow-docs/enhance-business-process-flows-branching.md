---
title: Bedrijfsprocesstromen verbeteren met vertakkingen met PowerApps | Microsoft Docs
description: Leer hoe u vertakkingen gebruikt in een bedrijfsprocesstroom
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: Mattp123
ms.assetid: 62cfac6b-0d78-48de-9364-0287454aa2a0
caps.latest.revision: 9
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f8911c828b216d8f65210b4c54603fd8838e848b
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2019
ms.locfileid: "65054109"
---
# <a name="tutorial-enhance-business-process-flows-with-branching"></a>Zelfstudie: Bedrijfsprocesstromen verbeteren met vertakkingen

Bedrijfsprocesstromen begeleiden u door verschillende fasen van verkoop-, marketing- of serviceprocessen om tot afronding van het proces te komen. In eenvoudige scenario's is een lineaire bedrijfsprocesstroom een goede optie. In complexere scenario's kunt u een bedrijfsprocesstroom echter verbeteren met behulp van vertakkingen. Als u beschikt over de machtiging voor het maken van bedrijfsprocesstromen, kunt u bedrijfsprocesstromen met meerdere vertakkingen maken met behulp van de `If-Else`-logica. De vertakkingsvoorwaarde kan bestaan uit meerdere logische expressies waarin een combinatie van de operatoren `AND` en `OR` wordt gebruikt. De selectie van de vertakking gebeurt automatisch, in realtime, op basis van regels die zijn gedefinieerd tijdens de procesdefinitie. In een scenario voor het verkopen van auto's kunt u bijvoorbeeld een bedrijfsprocesstroom configureren die na een algemene kwalificatiefase wordt gesplitst in twee afzonderlijke vertakkingen, op basis van een voorwaarde die antwoord geeft op de vraag of de klant liever een nieuwe auto of een tweedehands auto heeft, of het budget hoger of lager is dan € 20.000 , enzovoort. Er is dan één vertakking voor het verkopen van nieuwe auto's en een andere vertakking voor het verkopen van tweedehands auto's. Zie [Overzicht van bedrijfsprocesstromen](business-process-flows-overview.md) voor meer informatie over bedrijfsprocesstromen.  
  
 In het volgende diagram ziet u een bedrijfsprocesstroom met vertakkingen.  
  
 ![Stroomdiagram met de stappen in het verkoopproces voor auto's](media/example-car-sales-flow-chart.png "Stroomdiagram met de stappen in het verkoopproces voor auto's")  
  
<a name="Points"></a>   
## <a name="what-you-need-to-know-when-designing-business-process-flows-with-branches"></a>Wat u moet weten bij het ontwerpen van bedrijfsprocesstromen met vertakkingen  
 Houd rekening met de volgende informatie bij het ontwerpen van bedrijfsprocesstroom met vertakkingen:  
  
-   Een proces kan maximaal 5 unieke entiteiten omvatten.  
  
-   U kunt maximaal 30 fasen per proces en 30 stappen per fase gebruiken.  
  
-   Elke vertakking mag niet meer dan 5 niveaus hebben.  
  
-   De vertakkingsregel moet worden gebaseerd op de stappen in de fase die er direct aan voorafgaan.  
  
-   U kunt meerdere voorwaarden in een regel combineren met behulp van de operator `AND` of `OR`, maar niet met allebei de operatoren tegelijk.  
  
-   Wanneer u een processtroom definieert, kunt u eventueel een entiteitsrelatie selecteren. Deze relatie moet een een-op-veel-relatie (1:N) zijn.  
  
-   Er kan gelijktijdig meer dan één actief proces worden uitgevoerd op dezelfde record.  
  
-   U kunt tegels (fasen, stappen, voorwaarden, enzovoort) ordenen in de processtroom met behulp van slepen en neerzetten.  
  
-   Bij het samenvoegen van branches moeten alle peer-vertakkingen worden samengevoegd in één fase. De peer-vertakkingen moeten allemaal worden samengevoegd in één fase of elke peer-vertakking moet het proces beëindigen. Een peer-vertakking kan niet worden samengevoegd met andere vertakkingen en op hetzelfde moment het proces beëindigen.  
  
> [!NOTE]
> - Een entiteit die wordt gebruikt in het proces kan verschillende keren worden bezocht (meerdere gesloten entiteitslussen).  
> - Een proces kan teruggaan naar de vorige fase, ongeacht het type entiteit. Als de actieve fase bijvoorbeeld **Deliver Quote** is voor een offerterecord, kunnen procesgebruikers de actieve fase wijzigen in de eerdere fase **Propose** voor een verkoopkansrecord.  
>   
>   Stel dat een proces is momenteel in een ander voorbeeld: de **voorstel presenteren** fase in de processtroom: **Potentiële** > **behoeften aan identificeren** > **voorstel maken** > **voorstel**  >  **Sluiten**. Als het voorstel dat is gepresenteerd aan de klant meer onderzoek vereist om de behoeften van de klant in kaart te brengen, kunnen gebruikers de fase **Identify Needs** van het proces selecteren en **Instellen op actief** kiezen.  
  
<a name="CarSelling365"></a>   
## <a name="dynamics-365-customer-engagement-example-car-selling-process-flow-with-two-branches"></a>Voorbeeld van Dynamics 365 Customer Engagement: Auto processtroom met twee vertakkingen verkopen
 
Laten we eens kijken naar het voorbeeld van een bedrijfsprocesstroom met twee vertakkingen, voor het verkopen van nieuwe en tweedehands auto's.  
  
 Eerst maken we een nieuw proces met de naam **Car Sales Process**.  
  
1.  [Open Solution Explorer](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) en selecteer vervolgens in het linkernavigatiedeelvenster **Processen**.  
  
2.  Selecteer **Nieuw** om een nieuw proces te maken.  
  
3.  Selecteer **Bedrijfsprocesstroom** bij **Categorie** en **Lead** voor **Entiteit**.  
  
4.  Voeg de eerste fase toe aan het proces met de naam **Qualify** en voeg de stappen **Purchase Time frame** en **Car Preference** toe.  
  
5.  Na de gemeenschappelijke fase **Qualify** wordt het proces opgesplitst in twee afzonderlijke vertakkingen, met behulp van de tegel **Voorwaarde**.  
  
    1.  Configureer de tegel Voorwaarde met regels die voldoen aan uw bedrijfsvereisten.  
  
    2.  U kunt de eerste vertakking voor een fase toevoegen door een tegel Fase toe te voegen aan het pad 'Yes' van de tegel Voorwaarde.  
  
    3.  Om de tweede vertakking toe te voegen, die wordt uitgevoerd wanneer niet aan de voorwaarde wordt voldaan, voegt u een tegel Fase toe aan het pad 'No' van de tegel Voorwaarde  
  
> [!TIP]
>  U kunt nog een voorwaarde toevoegen aan het pad 'No' van een bestaande tegel Voorwaarde om een complexere vertakking te maken.  
  
 ![Afbeelding van de fase Qualify](media/example-car-sales-qualify-stage.JPG "Afbeelding van de fase Qualify")  
  
 Als **Car preference** = **New**, gaat het proces verder naar de fase **New Car Sales**. Bij een andere waarde gaat het proces verder met de fase **Pre-Owned Car Sales**, in de tweede vertakking, zoals hieronder wordt aangegeven.  
  
 ![Afbeelding van de fase New Car Sale](media/example-car-sales-new-stage-1.JPG "Afbeelding van de fase New Car Sale")  
  
 ![Fase Pre&#45;owned car sales](media/example-car-sales-pre-owned-stage.JPG "Fase Pre-owned car sales")  
  
 Nadat alle stappen in de fase **New Car Sales** of **Pre-Owned Car Sales** zijn voltooid, keert het proces terug naar de hoofdstroom, met de fase **Deliver Quote**.  
  
 ![Fase Deliver Quote](media/example-car-sales-deliver-quote-stage.JPG "Fase Deliver Quote")  
  
<a name="PreventInformation"></a>   
## <a name="prevent-information-disclosure"></a>Openbaarmaking van informatie voorkomen  
 We nemen een ander voorbeeld. U gebruikt een bedrijfsprocesstroom met vertakkingen voor het verwerken van een aanvraag voor een lening bij een bank, zoals hieronder wordt weergegeven. De aangepaste entiteiten die in de verschillende fasen worden gebruikt, staan tussen haakjes.  
  
 ![Stroomdiagram van de stappen in een voorbeeldproces om openbaarmaking van informatie te voorkomen](media/example-car-sales-flow-chart-process-prevent-information-disclosure.png "Stroomdiagram van de stappen in een voorbeeldproces om openbaarmaking van informatie te voorkomen")  
  
 In dit scenario, de bank lening officer moet toegang hebben tot de aanvraag-record, maar de lening officer al dan niet mogen inzicht hebben in het onderzoek van de aanvraag. Op het eerste gezicht lijkt het dat we dit eenvoudig kunnen realiseren door de medewerker een beveiligingsrol te geven die geen toegang heeft tot de entiteit Investigation. Maar laten we het voorbeeld eens wat beter bestuderen en kijken of dat inderdaad zo is.  
  
 Stel dat een klant een aanvraag heeft ingediend bij de bank voor een lening van meer dan € 60.000. De medewerker beoordeelt de aanvraag in de eerste fase. Als wordt voldaan aan de vertakkingsregel die controleert of het gewenste bedrag hoger is dan € 50.000, is de volgende fase van het proces het onderzoeken of de aanvraag frauduleus is. Als wordt vastgesteld dat dit inderdaad een geval van fraude is, wordt het proces verplaatst naar de fase voor het opstarten van juridische stappen tegen de aanvrager. De lening officer mag geen zichtbaarheid in de twee resulterend fasen bevatten als u de functionaris heeft geen toegang tot de entiteit onderzoek.  
  
 Echter, als de lening officer wordt geopend de record van de aanvraag, alle zou kunnen om te zien van het gehele end-to-end-proces. Niet alleen de lening officer zich om te zien van de fase van fraude onderzoek, maar ze waarschijnlijk ook het resultaat van het onderzoek identificeren door te kunnen zien van de fase juridische actie in het proces zijn. Ook is de officer mogelijk om een voorbeeld van de stappen in de fasen van de door het kiezen van de fase. Terwijl u de functionaris lening is niet mogelijk om te zien van de gegevens of de status van de stap voltooid, is het waarschijnlijk dat ze kunnen de mogelijke acties die zijn uitgevoerd tegen de indiener van de aanvraag tijdens het onderzoek en -fasen van de juridische actie identificeren.  
  
 In deze processtroom kan de medewerker de fasen Fraud Investigation en Legal Action raadplegen, wat neerkomt op een onjuiste openbaarmaking van informatie. Het is dan ook belangrijk dat u zeer goed kijkt welke informatie kan worden vrijgegeven in een bedrijfsprocesstroom met vertakkingen. In ons voorbeeld kan dit probleem worden opgelost door het proces op te splitsen in twee afzonderlijke processen, één voor de verwerking van de aanvraag en een andere voor het fraudeonderzoek. Op deze manier wordt onjuiste openbaarmaking van informatie voorkomen. Dit is dan het proces voor de medewerker die de aanvraag beoordeelt:  
  
 ![Stroomdiagram met aanvullende stappen in het proces om openbaarmaking van informatie te voorkomen](media/example-car-sales-flow-chart-additional-steps-prevent-information-disclosure.png "Stroomdiagram met aanvullende stappen in het proces om openbaarmaking van informatie te voorkomen")  
  
 Het proces voor het onderzoek is op zichzelf staand en omvat de volgende fasen:  
  
 ![Stroomdiagram met stappen voor een onderzoeksproces voor gevallen van openbaarmaking van informatie](media/example-car-sales-flow-chart-investigation-information-disclosure-case.png "Stroomdiagram met stappen voor een onderzoeksproces voor gevallen van openbaarmaking van informatie")  
  
 U moet een werkstroom opzetten om de beslissing voor goedkeuren/weigeren (Approve/Deny) uit de onderzoeksrecord te synchroniseren met de aanvraagrecord.  
  
### <a name="next-steps"></a>Volgende stappen  
 [Een bedrijfsprocesstroom maken](create-business-process-flow.md)   
 [Aangepaste bedrijfslogica maken met processen](guide-staff-through-common-tasks-processes.md)   
 
