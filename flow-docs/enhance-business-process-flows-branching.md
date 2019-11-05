---
title: Zakelijke proces stromen verbeteren met vertakkingen met PowerApps | MicrosoftDocs
description: Meer informatie over vertakkingen gebruiken in een bedrijfs proces stroom
ms.custom: ''
ms.date: 06/27/2018
ms.tgt_pltfrm: ''
ms.topic: article
ms.service: flow
author: MSFTMAN
ms.assetid: 62cfac6b-0d78-48de-9364-0287454aa2a0
caps.latest.revision: 9
ms.author: Deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c3a03cefcb3e808bb7900b79b05e6c2b3f8ef7f5
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544790"
---
# <a name="tutorial-enhance-business-process-flows-with-branching"></a>Zelf studie: zakelijke proces stromen verbeteren met vertakkingen
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Bedrijfsproces stromen begeleiden u bij de verschillende stadia van de verkoop-, marketing-of service processen die aan de slag zijn. In eenvoudige gevallen is een lineaire bedrijfs proces stroom een goede optie. In complexere scenario's kunt u echter een bedrijfs proces stroom met vertakkingen verbeteren. Als u beschikt over de machtigingen voor het maken van een bedrijfs proces, kunt u bedrijfsproces stroom met meerdere vertakkingen maken met behulp van de `If-Else` Logic. De vertakkings voorwaarde kan worden gevormd door meerdere logische expressies die gebruikmaken van een combi natie van `AND` of `OR` Opera tors. De vertakkings selectie wordt in realtime automatisch uitgevoerd op basis van regels die tijdens de proces definitie zijn gedefinieerd. U kunt bijvoorbeeld bij het verkopen van auto's een single business proces flow configureren, die na een gemeen schappelijke kwalificatie fase in twee afzonderlijke vertakkingen wordt gesplitst op basis van een regel (de klant prefereert bijvoorbeeld een nieuwe auto of een auto in eigendom) is het budget boven of onder $20.000 , enzovoort. ), één vertakking, voor het verkopen van nieuwe auto's en een andere branch, voor het verkopen van auto's van de eerste eigendom. Zie [overzicht van bedrijfsproces stromen](business-process-flows-overview.md)voor meer informatie over bedrijfs processen.  
  
 Het volgende diagram toont een bedrijfs proces stroom met filialen.  
  
 ![Stroom diagram met de stappen in het auto verkoopproces](media/example-car-sales-flow-chart.png "Stroom diagram met de stappen in het auto verkoopproces")  
  
<a name="Points"></a>   
## <a name="what-you-need-to-know-when-designing-business-process-flows-with-branches"></a>Wat u moet weten bij het ontwerpen van bedrijfs processen met vertakkingen  
 Bekijk de volgende informatie wanneer u de bedrijfs proces stroom ontwerpt met de vertakkingen:  
  
-   Een proces kan Maxi maal vijf unieke entiteiten omvatten.  
  
-   U kunt Maxi maal 30 fasen per proces en Maxi maal 30 stappen per fase gebruiken.  
  
-   Elke vertakking kan niet meer dan 5 niveaus diep zijn.  
  
-   Vertakkings regel moet zijn gebaseerd op de stappen in de fase die direct vooraf worden geplaatst.  
  
-   U kunt meerdere voor waarden in een regel combi neren met behulp van de operator `AND` of de operator `OR`, maar niet beide Opera tors.  
  
-   Wanneer u een proces stroom definieert, kunt u eventueel een entiteits relatie selecteren. Deze relatie moet een 1: N (een-op-veel) entiteits relatie zijn.  
  
-   Meer dan één actief proces kan gelijktijdig op dezelfde gegevens record worden uitgevoerd.  
  
-   U kunt de volg orde van de tegels (stadia, stappen, voor waarden enz.) op de proces stroom wijzigen met behulp van slepen en neerzetten.  
  
-   Bij het samen voegen van filialen moeten alle peer-vertakkingen samen voegen tot één fase. De peer-filialen moeten allemaal samen voegen tot één fase, of elke peer vertakking moet het proces beëindigen. Een peer vertakking kan niet samen voegen met andere vertakkingen en tegelijkertijd het proces beëindigen.  
  
> [!NOTE]
> - Een entiteit die in het proces wordt gebruikt, kan meerdere keren worden gestart (meerdere gesloten entiteit lussen).  
> - Een proces kan terugkeren naar de vorige fase, ongeacht het type entiteit. Als de actieve fase bijvoorbeeld **quote levert** voor een prijsopgave record, kunnen gebruikers van het proces het actieve stadium weer verplaatsen naar de fase Voorst **Ellen** voor een verkoopkansrecord.  
>   
>   Een ander voor beeld: Stel dat er momenteel een proces is in de **huidige** voorbereidings fase in uw proces stroom. **lead kwalificeren** > **identificeren behoeften** > **voor stel** > **huidige voor stel** maken >  **Sluiten**. Als het voor Stel dat aan de klant wordt gepresenteerd, meer Research nodig heeft om de behoeften van de klant te identificeren, kunnen gebruikers eenvoudigweg de fase voor het identificeren van de **behoeften** van uw proces selecteren en **actief instellen**kiezen.  
  
<a name="CarSelling365"></a>   
## <a name="example-car-selling-process-flow-with-two-branches"></a>Voor beeld: proces stroom voor auto verkoop met twee vertakkingen
 
Laten we eens kijken naar het voor beeld van de bedrijfs proces stroom met twee branches, voor het verkopen van nieuwe en pretoetredingssteunde auto's.  
  
 Eerst maken we een nieuw proces met de naam **auto verkoop process**.  
  
1.  [Open Solution Explorer](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) en selecteer in het navigatie deel venster links de optie **processen**.  
  
2.  Selecteer **Nieuw** om een nieuw proces te maken.  
  
3.  Geef de **categorie** op als **bedrijfs proces stroom** en kies voor de primaire **entiteit** **lead**.  
  
4.  Voeg de eerste fase toe aan het proces **kwalificeren** en voeg de stappen voor **aankoop tijd** en **auto voorkeur**toe.  
  
5.  Na **de gebruikelijke fase** wordt het proces in twee afzonderlijke vertakkingen gesplitst met behulp van de tegel **voor waarden** .  
  
    1.  De tegel voor waarde configureren met regels die voldoen aan uw bedrijfs vereisten  
  
    2.  Als u de eerste vertakking voor een fase wilt toevoegen, voegt u een fase tegel toe op het pad Yes van de voor waarde-tegel  
  
    3.  Als u de tweede vertakking wilt toevoegen die wordt uitgevoerd wanneer niet aan de voor waarde wordt voldaan, voegt u een andere fase tegel toe op het pad ' nee ' van de voor waarde-tegel  
  
> [!TIP]
>  U kunt een andere voor waarde toevoegen op het pad ' nee ' van een bestaande voor waarde om complexere vertakkingen te maken.  
  
 ![Afbeelding van de in aanmerking komende fase](media/example-car-sales-qualify-stage.JPG "Afbeelding van de in aanmerking komende fase")  
  
 Als de **auto voorkeur** = **Nieuw**is, wordt het proces bijkantoren naar de **nieuwe verkoop** fase van de auto. dit doet zich anders voor in de verkoop fase van de **eerste** auto, in de tweede vertakking, zoals hieronder wordt weer gegeven.  
  
 ![Afbeelding van het nieuwe auto verkoop stadium](media/example-car-sales-new-stage-1.JPG "Afbeelding van het nieuwe auto verkoop stadium")  
  
 ![Verkoop&#45;fase van de auto in eigendom](media/example-car-sales-pre-owned-stage.JPG "Verkoop fase van de auto in eigendom")  
  
 Na het volt ooien van de stappen in de **nieuwe** verkoop fase of de verkoop fase van de **auto** , keert het proces terug naar de hoofd stroom met de fase **afleveren** van de offerte.  
  
 ![Offerte fase afleveren](media/example-car-sales-deliver-quote-stage.JPG "Offerte fase afleveren")  
  
<a name="PreventInformation"></a>   
## <a name="prevent-information-disclosure"></a>Vrijgeven van informatie voor komen  
 Overweeg een bedrijfs proces stroom met vertakkingen voor het verwerken van een lenings aanvraag bij een bank, zoals hieronder wordt weer gegeven. De aangepaste entiteiten die in de fasen worden gebruikt, worden tussen haakjes weer gegeven.  
  
 ![Stroom diagram met de stappen in een voorbeeld proces om het vrijgeven van informatie te voor komen](media/example-car-sales-flow-chart-process-prevent-information-disclosure.png "Stroom diagram met de stappen in een voorbeeld proces om het vrijgeven van informatie te voor komen")  
  
 In dit scenario heeft de bank lening toegang tot de aanvraag record nodig, maar de lenings medewerker heeft geen inzicht in het onderzoek van de aanvraag. In eerste instantie lijkt het erop dat we dit eenvoudig kunnen doen door de lening een beveiligingsrol toe te wijzen die geen toegang geeft tot de onderzoek-entiteit. Maar we bekijken het voor beeld in meer detail en zien of dit echt waar is.  
  
 Stel dat een klant een lenings aanvraag voor meer dan $60.000 aan de Bank heeft geplaatst. De lenings medewerker beoordeelt de aanvraag in de eerste fase. Als in de vertakkings regel wordt gecontroleerd of het bedrag dat aan de Bank is verschuldigd, groter is dan $50.000, wordt de volgende fase in het proces onderzocht of de aanvraag frauduleus is. Als wordt vastgesteld dat dit inderdaad een geval van fraude is, gaat het proces verder met het uitvoeren van een juridische actie op de aanvrager. De lenings medewerker mag geen inzicht hebben in de twee onderzoekers, aangezien de functionaris geen toegang heeft tot de onderzoek-entiteit.  
  
 Als de lenings medewerker de aanvraag record opent, kan dit echter het hele volledige proces zien. De lening kan niet alleen de fraude onderzoek fase zien, maar ze kunnen ook de uitkomst van het onderzoek identificeren door de juridische actie fase in het proces te kunnen zien. Daarnaast kan de officier een voor beeld van de stappen in de nader onderzoek fases bekijken door de fase te kiezen. Hoewel de lenings medewerker de gegevens of de voltooiings status van de stap niet kan zien, kunnen ze de potentiële acties identificeren die zijn uitgevoerd op basis van de indiener van de aanvraag tijdens het onderzoek en juridische actie fasen.  
  
 In deze proces stroom kan de lenings medewerker het fraude onderzoek en juridische actie fasen zien, wat een onjuiste openbaar making van informatie vormt. We raden u aan om speciale aandacht te best Eden aan de informatie die kan worden afgesloten vanwege vertakkingen. In ons voor beeld splitst u het proces in twee afzonderlijke processen, één voor de aanvraag verwerking en een andere voor het fraude onderzoek om te voor komen dat de informatie openbaar wordt gemaakt. Het proces van de lenings medewerker ziet er als volgt uit:  
  
 ![Stroom diagram met aanvullende stappen in het proces om het vrijgeven van informatie te voor komen](media/example-car-sales-flow-chart-additional-steps-prevent-information-disclosure.png "Stroom diagram met aanvullende stappen in het proces om het vrijgeven van informatie te voor komen")  
  
 Het proces voor het onderzoek is zelf opgenomen en omvat de volgende fasen:  
  
 ![Stroom diagram met de stappen voor een onderzoek proces voor het vrijgeven van informatie](media/example-car-sales-flow-chart-investigation-information-disclosure-case.png "Stroom diagram met de stappen voor een onderzoek proces voor het vrijgeven van informatie")  
  
 U moet een werk stroom opgeven om de beslissing goed keuren/weigeren van het onderzoek record te synchroniseren met de aanvraag record.  
  
### <a name="next-steps"></a>Volgende stappen  
 [Een bedrijfs proces stroom  maken](create-business-process-flow.md)  
 [Aangepaste bedrijfs logica maken met processen](guide-staff-through-common-tasks-processes.md)   
 
