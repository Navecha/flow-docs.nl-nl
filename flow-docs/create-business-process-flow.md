---
title: Een bedrijfs proces stroom maken in PowerApps | MicrosoftDocs
description: Meer informatie over het maken van een bedrijfs proces stroom
ms.custom: ''
ms.date: 08/17/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: efe86ab3-430f-485a-b924-6ed82cfbb449
caps.latest.revision: 39
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3bd154935e06031b031432e10fa977f23e1a2c54
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546513"
---
# <a name="tutorial-create-a-business-process-flow-to-standardize-processes"></a>Zelf studie: een bedrijfs proces stroom maken om processen te standaardiseren
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Deze zelf studie laat zien hoe u een bedrijfsproces stroom maakt met PowerApps. Zie [overzicht van bedrijfsproces stromen](business-process-flows-overview.md)voor meer informatie over waarom u bedrijfs proces stromen gebruikt. Zie [een Mobile task flow maken](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-mobile-task-flow)voor meer informatie over het maken van een stroom voor een mobiele taak.  
  
 Wanneer een gebruiker een bedrijfs proces stroom start, worden de fasen en stappen van het proces weer gegeven in de proces balk boven aan een formulier:  
  
 ![Bedrijfs proces met fasen](media/business-process-stages.png "Bedrijfs proces met fasen")  
  
 > [!TIP]
 >  Nadat u een definitie van een bedrijfs proces stroom hebt gemaakt, kunt u de controle geven over wie het exemplaar van de bedrijfsproces stroom kan maken, lezen, bijwerken of verwijderen. Voor service-gerelateerde processen kunt u bijvoorbeeld volledige toegang bieden aan de klant service medewerkers om het exemplaar voor de bedrijfsproces stroom te wijzigen, maar alleen-lezen toegang tot het exemplaar voor vertegenwoordigers te bieden zodat ze na verkoop activiteiten kunnen bewaken voor hun hun. Selecteer **beveiligings rollen inschakelen** op de actie balk om beveiliging in te stellen voor een bedrijfsproces stroom definitie die u maakt.  
  
<a name="BKMK_Createbusinessprocessflows"></a>

## <a name="prerequisites"></a>Vereisten

U hebt [flow plan 2](https://preview.flow.microsoft.com/pricing/) nodig om bedrijfsproces stromen te kunnen maken. Sommige Dynamics 365-licentie plannen omvatten flow-abonnement 2.

## <a name="create-a-business-process-flow"></a>Een bedrijfs proces stroom maken  
  
1. Open [Solution Explorer](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer).
  
2. Selecteer in het navigatie deel venster aan de linkerkant de optie **processen**. 
  
3.  Selecteer **Nieuw**op de werk balk **acties** .  
  
4.  In het dialoog venster **proces maken** vult u de vereiste velden in:  
  
    -   Voer een proces naam in. De naam van het proces hoeft niet uniek te zijn, maar het moet zinvol zijn voor mensen die een proces moeten kiezen. U kunt dit later wijzigen.  
  
    -   Selecteer **bedrijfs proces stroom**in de lijst **categorie** .  
  
         U kunt de categorie niet wijzigen nadat u het proces hebt gemaakt.  
  
    -   Selecteer in de lijst **entiteit** de entiteit waarop u het proces wilt baseren.  
  
         De entiteit die u selecteert, is van invloed op de velden die beschikbaar zijn voor stappen die kunnen worden toegevoegd aan de eerste fase van de proces stroom. Als u de gewenste entiteit niet kunt vinden, controleert u of de entiteit bedrijfs proces stromen (velden wordt gemaakt) in de entiteits definitie heeft ingesteld. U kunt deze niet meer wijzigen nadat u het proces hebt opgeslagen.  
  
5. Selecteer **OK**.  
  
     Het nieuwe proces wordt gemaakt en de ontwerp functie voor bedrijfs processen wordt geopend met één fase die al voor u is gemaakt.  
  
 ![Venster bedrijfs proces stroom met de hoofd elementen](media/business-process-flow-window-showing-main-elements.png "Venster bedrijfs proces stroom met de hoofd elementen")  
  
6. **Fasen toevoegen.** Als uw gebruikers in het proces naar een andere bedrijfs fase worden uitgevoerd:  
  
    1.  Sleep een onderdeel **fase** van het tabblad **onderdelen** en zet het neer in een plus teken in de ontwerp functie.  
  
        ![Een bedrijfs proces fase verslepen](media/drag-business-process-stage.png "Een bedrijfs proces fase verslepen")  
  
    2.  Als u de eigenschappen voor een fase wilt instellen, selecteert u het werk gebied en stelt u de eigenschappen in op het tabblad **Eigenschappen** aan de rechter kant van het scherm:  
  
        -   Voer een weergave naam in.  
  
        -   Selecteer desgewenst een categorie voor het stadium.  De categorie (zoals **kwalificeren** of **ontwikkelen**) wordt weer gegeven als een dubbele punt haak in de werk balk.  
  
            ![Dubbele punt haak van de bedrijfs proces balk](media/business-process-bar-chevron.png "Dubbele punt haak van de bedrijfs proces balk")  
  
        -   Wanneer u klaar bent met het wijzigen van eigenschappen, selecteert u de knop **Toep assen** .  
  
7. **Voeg stappen toe aan een fase.** Als u de stappen in een fase wilt zien, selecteert u **Details** in de rechter benedenhoek van het werk gebied. Meer stappen toevoegen:  
  
    1.  Sleep de **stap** component naar het werk gebied van het tabblad **onderdelen** .  
  
        ![Een stap toevoegen aan een fase in een bedrijfs proces](media/add-step-stage-business-process.png "Een stap toevoegen aan een fase in een bedrijfs proces")  
  
    2.  Selecteer de stap en stel eigenschappen in op het tabblad **Eigenschappen** :  
  
        1.  Voer een weergave naam in voor de stap.  
  
        2.  Als u wilt dat gebruikers gegevens invoeren om een stap te volt ooien, selecteert u het betreffende veld in de vervolg keuzelijst.  
  
        3.  Selecteer **vereist** als mensen het veld moeten invullen om de stap te volt ooien voordat de volgende fase van het proces wordt verplaatst.  
  
        4.  Selecteer **Toep assen** wanneer u klaar bent.  
  
8. **Voeg een vertakking (voor waarde) toe aan het proces.** Een vertakkings voorwaarde toevoegen:  
  
    1.  Sleep het onderdeel **voor waarde** van het tabblad **onderdelen** naar een plus teken tussen twee fasen.  
  
        ![Een voor waarde toevoegen aan een bedrijfs proces stroom](media/add-condition-business-process-flow.png "Een voor waarde toevoegen aan een bedrijfs proces stroom")  
  
    2.  Selecteer de voor waarde en stel vervolgens eigenschappen in op het tabblad **Eigenschappen** . Voor meer informatie over vertakkings eigenschappen raadpleegt u [bedrijfs proces stromen verbeteren met vertakkingen](enhance-business-process-flows-branching.md). Wanneer u klaar bent met het instellen van de eigenschappen voor de voor waarde, selecteert u **Toep assen**.  
  
9. **Een werk stroom toevoegen.** Een werk stroom aanroepen:  
  
    1.  Sleep een **werk stroom** onderdeel van het tabblad **onderdelen** naar een fase of naar het **globale werk stroom** item in de ontwerp functie.   Aan de ene toepassing die u toevoegt, is afhankelijk van het volgende:  
  
       - **Sleep het naar een fase** wanneer u de werk stroom wilt activeren of afsluiten van het stadium. Het werk stroom onderdeel moet zijn gebaseerd op dezelfde primaire entiteit als de fase.  
  
       - **Sleep het naar het globale werk stroom item** wanneer u de werk stroom wilt activeren wanneer het proces wordt geactiveerd of wanneer het proces wordt gearchiveerd (wanneer de status wordt gewijzigd in **voltooid** of **afgebroken**). Het werk stroom onderdeel moet worden gebaseerd op dezelfde primaire entiteit als het proces.  
  
    2.  Selecteer de werk stroom en stel eigenschappen in op het tabblad **Eigenschappen** :  
  
       1.  Voer een weergave naam in.  
  
       2.  Selecteren wanneer de werk stroom moet worden geactiveerd.  
  
       3.  Zoek naar een bestaande actieve werk stroom op aanvraag die overeenkomt met de entiteit van de fase of maak een nieuwe werk stroom door **Nieuw**te selecteren.  
  
       4.  Selecteer **Toep assen** wanneer u klaar bent.  
  
       Zie [werk stroom processen](../common-data-service/workflow-processes.md)voor meer informatie over werk stromen.  
  
10. Selecteer **valideren** op de actie balk om de bedrijfs proces stroom te valideren.  
  
11. Als u het proces wilt opslaan als een concept terwijl u aan de slag gaat, selecteert u **Opslaan** in de actie balk.  
  
    > [!IMPORTANT]
    >  Zolang een proces een concept is, kunnen mensen het niet gebruiken.  
  
12. Selecteer **activeren** op de actie balk om het proces te activeren en het beschikbaar te maken voor uw team.  

13. Selecteer **beveiligings rollen bewerken** op de opdracht balk van de ontwerp functie om de controle te geven over wie het exemplaar van de bedrijfs proces stroom kan maken, lezen, bijwerken of verwijderen. Voor service-gerelateerde processen kunt u bijvoorbeeld volledige toegang bieden aan de klant service medewerkers om het exemplaar voor de bedrijfsproces stroom te wijzigen, maar alleen-lezen toegang tot het exemplaar voor vertegenwoordigers te bieden zodat ze na verkoop activiteiten kunnen bewaken voor hun hun.

  Selecteer in het scherm **beveiligings rollen** de naam van een rol om de pagina informatie over beveiligings rollen te openen. Selecteer het tabblad stromen van bedrijfs proces en wijs vervolgens de juiste bevoegdheden toe aan de bedrijfs proces stroom voor een beveiligingsrol.

  > [!NOTE]
  > De beveiligings rollen systeem beheerder en Systeemaanpasser hebben standaard toegang tot nieuwe bedrijfs proces stromen.

   ![Machtigingen toewijzen aan een bedrijfs proces stroom](media/bpf-assign-privileges.png)

  Geef bevoegdheden op door de juiste keuze rondjes te selecteren en klik op opslaan. Zie voor meer informatie over bevoegdheden [bedrijfsproces stroom privileges](business-process-flows-overview.md#BKMK_MultipleBPF).

  Vergeet niet om de beveiligingsrol vervolgens toe te wijzen aan de juiste gebruikers in uw organisatie.

> [!TIP] 
>  Hier volgen enkele tips waarmee u op de hoogte blijft van uw taak stroom in het ontwerp venster:  
>   
> - Als u een moment opname van alles in het venster bedrijfs proces stroom wilt maken, selecteert u **moment opname** op de actie balk. Dit is bijvoorbeeld handig als u van een teamlid wilt delen en opmerkingen over het proces wilt ontvangen.  
> - Gebruik de mini kaart om snel naar verschillende onderdelen van het proces te navigeren. Dit is handig wanneer u een gecompliceerd proces hebt dat op het scherm schuift.  
> - Als u een beschrijving voor het bedrijfs proces wilt toevoegen, selecteert u **Details** onder de naam van het proces in de linkerbovenhoek van het venster bedrijfs proces stroom. U kunt Maxi maal 2000 tekens gebruiken.  
  
<a name="BKMK_Editbusinessprocessflows"></a>   
## <a name="edit-a-business-process-flow"></a>Een bedrijfs proces stroom bewerken  
 Als u bedrijfs proces stromen wilt bewerken, opent u Solution Explorer, selecteert u **processen**en selecteert u vervolgens de stroom van het **bedrijfs proces** in de lijst met processen die u wilt bewerken.  
  
 Wanneer u de naam selecteert van de bedrijfs proces stroom die u wilt bewerken in de lijst met processen, wordt deze in de ontwerp functie geopend, waar u de gewenste updates kunt aanbrengen. Vouw **Details** uit onder de naam van het proces om het een nieuwe naam te geven of een beschrijving toe te voegen en aanvullende informatie weer te geven.  
  
 ![Uitgebreide Details sectie van een bedrijfs proces stroom](media/business-process-flow-details.png "Uitgebreide Details sectie van een bedrijfs proces stroom")  
  
  
## <a name="other-things-to-know-about-business-process-flows"></a>Andere zaken die u moet weten over bedrijfs proces stromen
 **Fases bewerken**  
Bedrijfs proces stromen kunnen Maxi maal 30 fasen hebben.    
  
U kunt de volgende eigenschappen van een fase toevoegen of wijzigen:  
  
- **Fase naam**  
  
- **Entiteit**. U kunt de entiteit voor elke fase wijzigen, behalve de eerste.  
  
- **Fase categorie**. Met een categorie kunt u fasen groeperen op basis van een type actie. Het is handig voor rapporten waarmee records worden gegroepeerd op het stadium waarin ze zich bevinden. De opties voor de categorie fase zijn afkomstig uit de algemene optieset van de fase categorie. U kunt extra opties toevoegen aan deze algemene optieset en zo nodig de labels van bestaande instellingen wijzigen. U kunt deze opties ook verwijderen als u wilt, maar u wordt aangeraden de bestaande opties te hand haven. Het is niet mogelijk om exact dezelfde optie terug toe te voegen als u deze verwijdert. Als u niet wilt dat ze worden gebruikt, wijzigt u het label in niet gebruiken.  
  
- **Relatie**. Voer een relatie in wanneer de voor gaande fase in het proces is gebaseerd op een andere entiteit. Voor het stadium dat momenteel wordt gedefinieerd, kiest u **relaties selecteren** om een relatie te identificeren die moet worden gebruikt bij het verplaatsen tussen de twee fasen. U kunt het beste een relatie selecteren voor de volgende voor delen:  
  
    -   Voor relaties zijn vaak kenmerk toewijzingen gedefinieerd waarmee gegevens tussen records automatisch worden overgedragen, waardoor de gegevens invoer wordt geminimaliseerd.  
  
    -   Wanneer u **volgende fase** selecteert op de werk balk van een record, worden alle records die gebruikmaken van de relatie, weer gegeven in de proces stroom, waardoor het hergebruik van records in het proces wordt bevorderd. Daarnaast kunt u werk stromen gebruiken om het maken van records te automatiseren, zodat de gebruiker deze eenvoudigweg selecteert in plaats van er een te maken om het proces verder te stroom lijnen.  
  
**Stappen bewerken**  
 Elke fase kan Maxi maal 30 stappen bevatten.    
  
**Vertakking toevoegen**  
Zie [bedrijfsproces stromen uitbreiden met vertakkingen](enhance-business-process-flows-branching.md)voor meer informatie over het toevoegen van een vertakking aan een fase.  
  
Als u een bedrijfs proces stroom beschikbaar wilt maken voor personen die u wilt gebruiken, moet u de proces stroom best Ellen, beveiligings rollen inschakelen en deze activeren.  
  
**Volg orde van proces stroom instellen**  
 Als u meer dan één bedrijfs proces stroom voor een entiteit (record type) hebt, moet u instellen welk proces automatisch wordt toegewezen aan nieuwe records.. Selecteer in de opdracht balk **order proces stroom**. Voor nieuwe records of records waaraan nog geen proces stroom is gekoppeld, is de eerste bedrijfs proces stroom waartoe een gebruiker toegang heeft, de account die wordt gebruikt.  
  
**Beveiligings rollen inschakelen**  
Gebruikers hebben toegang tot een bedrijfs proces stroom, afhankelijk van de bevoegdheid die is gedefinieerd in de bedrijfs proces stroom in de beveiligingsrol die aan de gebruiker is toegewezen. 

Standaard kunnen alleen de beveiligings rollen **systeem beheerder** **en Systeemaanpasser een** nieuwe bedrijfsproces stroom weer geven. 

Als u bevoegdheden wilt opgeven voor een bedrijfsproces stroom, opent u de bedrijfs proces stroom voor bewerken en selecteert u vervolgens **beveiligings rollen bewerken** op de opdracht balk van de ontwerp functie voor bedrijfs processen. Zie stap 13 onder [een bedrijfs proces stroom maken](#create-a-business-process-flow) die eerder in dit onderwerp wordt vermeld.
  
**Inschakelen**  
Voordat iedereen de stroom voor bedrijfs processen kan gebruiken, moet u deze activeren. Selecteer in de opdracht balk de optie **activeren**. Nadat u de activering hebt bevestigd, is de bedrijfs proces stroom klaar voor gebruik. Als een bedrijfs proces stroom fouten bevat, kunt u deze niet activeren totdat de fouten zijn opgelost.  

## <a name="add-an-on-demand-action-to-a-business-process-flow"></a>Een actie op aanvraag toevoegen aan een bedrijfs proces stroom
De Dynamics 365 (online), versie 9,0-update introduceert een functie voor bedrijfsproces stroom: automatisering van bedrijfs processen met actie stappen. U kunt een knop toevoegen aan een bedrijfs proces stroom waarmee een actie of werk stroom wordt geactiveerd.

### <a name="add-on-demand-workflows-or-actions-using-an-action-step"></a>Werk stromen op aanvraag of acties toevoegen met behulp van een actie stap
Stel dat, als onderdeel van het proces voor opportuniteits kwalificatie, alle mogelijkheden door een aangewezen revisor moeten worden gecontroleerd door de contoso-organisatie. Vervolgens heeft de contoso-organisatie een actie gemaakt die: 

- Hiermee maakt u een taak record die is toegewezen aan de revisor van de kans. 
- Voegt ' gereed voor beoordeling ' toe aan het Opportunity-onderwerp. 

Daarnaast moet contoso deze acties op aanvraag kunnen uitvoeren. Als u deze taken wilt integreren in het proces voor opportuniteits kwalificatie, moeten de acties worden weer gegeven op de bedrijfs proces stroom voor verkoop kansen. Als u deze functie wilt inschakelen, selecteert u **als actie stap voor een bedrijfs proces stroom**.
![beschikbaar om te worden uitgevoerd als een bedrijfs proces stroom.](media/action-available-to-run.png)

Vervolgens wordt de actie stap toegevoegd aan de bedrijfs proces stroom van contoso. Vervolgens wordt de proces stroom gevalideerd en bijgewerkt.

![Actie die is toegevoegd aan de bedrijfs proces stroom van de verkoop kans.](media/add-action-to-bpf.png)

Nu kunnen leden van de Sales Force van Contoso de actie uitvoeren vanuit de stap voor het proces van **verkoop kansen kwalificeren** , op aanvraag, door **Execute**te selecteren.

![Actie uitvoeren.](media/action-execute.png)

> [!IMPORTANT]
> - Om een actie of werk stroom op aanvraag uit te voeren, moet de bedrijfs proces stroom een actie stap bevatten. Als met de actie stap een werk stroom wordt uitgevoerd, moet de werk stroom zo zijn geconfigureerd dat deze op aanvraag wordt uitgevoerd.
> - De entiteit die aan de actie of de werk stroom is gekoppeld, moet gelijk zijn aan de entiteit die aan de bedrijfs proces stroom is gekoppeld.

### <a name="limitation-of-using-action-steps-in-a-business-process-flow"></a>Beperking van het gebruik van actie stappen in een bedrijfs proces stroom

- Acties zijn niet beschikbaar als actie stappen als de invoer-of uitvoer parameters de typen entity, EntityCollection of Optionset (selectie lijst) zijn. Acties met meer dan één EntityReference-uitvoer parameter of een aantal EntityReference-invoer parameters zijn niet beschikbaar als actie stappen. Acties die niet zijn gekoppeld aan een primaire entiteit (globale actie), zijn niet beschikbaar als actie stappen.

## <a name="instant-flows-in-business-process-flows"></a>Directe stromen in bedrijfs processen

U kunt een **directe stroom** uitvoeren om terugkerende taken te automatiseren, documenten te genereren, goed keuringen te volgen, en meer, vanuit een fase van een bedrijfs proces.

### <a name="add-an-instant-flow-as-a-step-in-a-business-process"></a>Een directe stroom toevoegen als stap in een bedrijfs proces

Stel dat u printers verkoopt en u het **verkoop proces lead naar verkoop kansen** gebruikt om deals af te sluiten. Als onderdeel van dit proces zou u de team leider in staat stellen om Voorst Ellen te beoordelen en goed te keuren die het verkoop team samenbrengt in een eerdere fase van de bedrijfs proces stroom voordat het wordt gedeeld met de klant.

Hiervoor moet u twee dingen doen:
1. Bouw een onmiddellijke stroom die de controle en goed keuring van het voor stel van het team aanvraagt.
1. Voeg de Instant flow toe als een stap in het **verkoop proces van leads naar verkoop kansen**.

> [!TIP]
> Alleen [oplossingen bewuste stromen](https://docs.microsoft.com/flow/overview-solution-flows) kunnen als een stap in een bedrijfs proces worden toegevoegd. 

### <a name="build-an-instant-flow"></a>Een directe stroom bouwen

1. Selecteer in Microsoft Flow **oplossingen** in het navigatie menu.
1. Selecteer **standaard oplossing** in de lijst met oplossingen die worden weer gegeven. 
1. Selecteer het menu **+ Nieuw** en selecteer vervolgens **stroom** in de lijst die wordt weer gegeven.
1. Zoek de **common data service** -connector en selecteer deze.
1. Zoek naar en selecteer de trigger **Wanneer een record is geselecteerd** in de lijst met **common data service** triggers.
1. Stel de **omgeving** in op **standaard**en stel de **entiteits naam** in op **lead verkoopproces verkoop kansen**.
1. Voeg een tekst invoer veld toe aan de gebruiker om de koppeling naar het voor Stel in te voeren.

   ![Trigger voor directe stroom](media/instant-flow-trigger.png "Trigger voor directe stroom")

   Er is informatie nodig van het exemplaar van de bedrijfsproces stroom om context te bieden voor de goedkeurings aanvraag. Volg hiertoe de volgende stappen.

1. Voeg de actie **JSON parseren** toe. 
1. Stel **inhoud** in op **entiteit** door deze te selecteren in de lijst met dynamische waarden voor de trigger **Wanneer een record wordt geselecteerd** .
1. Plak de volgende inhoud in het veld **schema** .

    ```json
    {
        "type": "object",
        "properties": {
        "entity": {
            "type": "object",
            "properties": {
                "FlowsWorkflowLogId": {
                    "type": "string"
                },
                "BPFInstanceId": {
                    "type": "string"
                },
                "BPFInstanceEntityName": {
                    "type": "string"
                },
                "BPFDefinitionId": {
                    "type": "string"
                },
                "BPFDefinitionEntityName": {
                    "type": "string"
                },
                "StepId": {
                    "type": "string"
                },
                "BPFDefinitionName": {
                    "type": "string"
                },
                "BPFInstanceName": {
                    "type": "string"
                },
                "BPFFlowStageLocalizedName": {
                    "type": "string"
                },
                "BPFFlowStageEntityName": {
                    "type": "string"
                },
                "BPFFlowStageEntityCollectionName": {
                    "type": "string"
                },
                "BPFFlowStageEntityRecordId": {
                    "type": "string"
                },
                "BPFActiveStageId": {
                    "type": "string"
                },
                "BPFActiveStageEntityName": {
                    "type": "string"
                },
                "BPFActiveStageLocalizedName": {
                    "type": "string"
                }
            }
          }
        }
   }
   ```

   De dingen moeten er nu als volgt uitzien:

   ![JSON parseren](media/instant-flow-json-date.png "JSON parseren")

  1. Voeg de actie **record ophalen** toe vanuit de **common data service** -connector.
  1. Stel **omgeving** in op **(huidig)** , **entiteit naam** voor **verkoop kansen**en **item-id** naar **BPFFlowStageEntityRecordID**.

     ![Een record toevoegen](media/instant-flow-add-record.png)

     Nu we de gegevens hebben, definiëren we het goedkeurings proces door de **Start en wachten op een goedkeurings actie (v2)** toe te voegen en vervolgens de relevante gegevens in te vullen. Meer informatie over [goed keuringen]( sequential-modern-approvals.md) als u niet bekend bent.

     > [!TIP]
     > - Gebruik de kiezer voor dynamische inhoud om velden toe te voegen van de actie **record ophalen** om relevante informatie toe te voegen aan de goedkeurings aanvraag zodat goed keurders eenvoudig kunnen zien wat de aanvraag is. 
     > - Voeg het veld **BPFActiveStageLocalizedName** in de lijst met dynamische waarden toe om verdere context te bieden met betrekking tot de actieve fase waarin het bedrijfs proces zich bevindt.

     Uw **Start en wachten op een goedkeurings kaart (v2)** kan er ongeveer als volgt uitzien:

      ![Goedkeurings kaart](media/instant-flow-add-approval-action.png)

1. Sla tot slot de stroom op en schakel deze in.

### <a name="add-this-flow-as-a-step-in-the-lead-to-opportunity-sales-process"></a>Voeg deze stroom toe als stap in het verkoop proces van leads naar verkoop kansen.

Nu u de directe stroom hebt gemaakt, hoeft u deze alleen aan uw bedrijfsproces stroom toe te voegen. 

1. Open het **verkoop proces lead voor verkoop kansen** in de ontwerp functie voor bedrijfsproces stromen. 
1. Sleep de **stroom stap (preview)** **van de lijst** met **onderdelen** naar de voor Stel-fase.
1. Selecteer vervolgens het zoek pictogram in het veld **een stroom selecteren** om alle stromen weer te geven die u aan een bedrijfs proces stroom kunt toevoegen.
1. Selecteer een stroom in de lijst en sla uw wijzigingen op door de knop **Toep assen** onder aan het deel venster Eigenschappen te selecteren.
1. Selecteer tot slot de knop **bijwerken** om deze bedrijfsproces stroom te maken met de nieuwe stap voor directe stroom die beschikbaar is voor uw gebruikers.
  
## <a name="next-steps"></a>Volgende stappen

 - [Overzicht van bedrijfs proces stromen](business-process-flows-overview.md)  
 - [Zakelijke proces stromen verbeteren met vertakkingen](enhance-business-process-flows-branching.md)
 - [Overzicht van goed keuringen](sequential-modern-approvals.md)
 - [Gedetailleerde stappen voor het toevoegen van een directe stroom aan een bedrijfs proces stroom](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/instant-steps-business-process-flows)


