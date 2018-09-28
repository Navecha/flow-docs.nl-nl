---
title: Een bedrijfsprocesstroom maken in PowerApps | Microsoft Docs
description: Uitleg over het maken van een bedrijfsprocesstroom
ms.custom: ''
ms.date: 08/17/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: efe86ab3-430f-485a-b924-6ed82cfbb449
caps.latest.revision: 39
author: Mattp123
ms.author: matp
manager: kvivek
ms.openlocfilehash: 258fedabea816b9a20a8f768632e797dec576365
ms.sourcegitcommit: d3243c9f82c5e058919c5cb85d36d45f1f034411
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/17/2018
ms.locfileid: "43774256"
---
# <a name="tutorial-create-a-business-process-flow-to-standardize-processes"></a>Zelfstudie: Een bedrijfsprocesstroom maken om processen te standaardiseren

In deze zelfstudie leert u hoe u een bedrijfsprocesstroom maakt met PowerApps. Zie [Overzicht van bedrijfsprocesstromen](business-process-flows-overview.md) voor meer informatie over waarom u bedrijfsprocesstromen zou moeten gebruiken. Zie [Mobiele taakstroom maken](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-mobile-task-flow) voor meer informatie over het maken van een mobiele taakstroom.  
  
 Wanneer een gebruiker een bedrijfsprocesstroom start, worden de fasen en stappen van het proces weergegeven in de procesbalk bovenaan een formulier:  
  
 ![Bedrijfsproces met fasen](media/business-process-stages.png "Bedrijfsprocessen met fasen")  
  
 > [!TIP]
 >  Nadat u een definitie hebt gemaakt voor een bedrijfsprocesstroom, kunt u bepalen wie de instantie van de bedrijfsprocesstroom kan maken, lezen, bijwerken of verwijderen. Zo kunt u voor servicegerelateerde processen klantenservicemedewerkers volledige toegang verlenen om de instantie van de bedrijfsprocesstroom te wijzigen, maar verkopers alleen-lezentoegang tot de instantie geven zodat ze de activiteiten na de verkoop kunnen volgen voor hun voor klanten. Als u beveiliging wilt instellen voor een bedrijfsprocesstroomdefinitie die u maakt, selecteert u **Beveiligingsrollen inschakelen** op de actiebalk.  
  
<a name="BKMK_Createbusinessprocessflows"></a>   
## <a name="create-a-business-process-flow"></a>Een bedrijfsprocesstroom maken  
  
1. Open [Solution Explorer](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer).
  
2. Selecteer **Processen** in het linkernavigatiedeelvenster. 
  
3.  Selecteer **Nieuw** op de werkbalk **Acties**.  
  
4.  Vul in het dialoogvenster **Proces maken** de verplichte velden in:  
  
    -   Voer een procesnaam in. De naam van het proces hoeft niet uniek te zijn, maar moet wel zinvol zijn voor mensen die een proces moeten kiezen. U kunt dit later wijzigen.  
  
    -   Selecteer **Bedrijfsprocesstroom** in de lijst **Categorie**.  
  
         U kunt de categorie niet wijzigen nadat u het proces hebt gemaakt.  
  
    -   In de lijst **Entiteit** selecteert u de entiteit waarop u het proces wilt baseren.  
  
         De entiteit die u selecteert, is van invloed op de velden die beschikbaar zijn voor stappen die kunnen worden toegevoegd aan de eerste fase van de processtroom. Als u de gewenste entiteit niet kunt vinden, controleert u of de entiteit de optieset Bedrijfsprocesstromen (de velden worden gemaakt) bevat in de entiteitsdefinitie. U kunt dit niet wijzigen nadat u het proces hebt opgeslagen.  
  
5. Selecteer **OK**.  
  
     Het nieuwe proces wordt gemaakt en de ontwerpfunctie voor bedrijfsprocesstromen wordt geopend met een enkele fase die al voor u is gemaakt.  
  
 ![Het venster Bedrijfsprocesstroom met de belangrijkste elementen](media/business-process-flow-window-showing-main-elements.png "Het venster Bedrijfsprocesstroom met de belangrijkste elementen")  
  
6. **Fasen toevoegen.** Als uw gebruikers verdergaan van de ene bedrijfsfase naar een andere in het proces:  
  
    1.  Sleep een onderdeel **Fase** vanaf het tabblad **Onderdelen** en zet dit neer op een plusteken in de ontwerpfunctie.  
  
        ![Een bedrijfsprocesfase slepen](media/drag-business-process-stage.png "Een bedrijfsprocesfase slepen")  
  
    2.  Als u de eigenschappen wilt instellen voor een fase, selecteert u de fase en stelt u vervolgens de eigenschappen in op het tabblad **Eigenschappen** rechts op het scherm:  
  
        -   Voer een weergavenaam in.  
  
        -   U kunt desgewenst een categorie selecteren voor de fase.  De categorie (zoals **Kwalificeren** of **Ontwikkelen**) wordt weergegeven als een dubbele punthaak op de procesbalk.  
  
            ![Dubbele punthaak op bedrijfsprocesbalk](media/business-process-bar-chevron.png "Dubbele punthaak op bedrijfsprocesbalk")  
  
        -   Als u klaar bent met het wijzigen van de eigenschappen, selecteert u de knop **Toepassen**.  
  
7. **Stappen toevoegen aan een fase.** Als u de stappen in een fase wilt bekijken, selecteert u **Details** in de rechterbenedenhoek van de fase. Meer stappen toevoegen:  
  
    1.  Sleep het onderdeel **Stap** naar de fase vanaf het tabblad **Onderdelen**.  
  
        ![Stap toevoegen aan een fase in een bedrijfsproces](media/add-step-stage-business-process.png "Stap toevoegen aan een fase in een bedrijfsproces")  
  
    2.  Selecteer de stap en stel vervolgens eigenschappen in op het tabblad **Eigenschappen**:  
  
        1.  Voer een weergavenaam in voor de stap.  
  
        2.  Als u wilt dat gebruikers gegevens invoeren om een stap te voltooien, selecteert u het desbetreffende veld in de vervolgkeuzelijst.  
  
        3.  Selecteer **Vereist** als mensen het veld moeten invullen voordat ze de stap voltooien en doorgaan naar de volgende fase van het proces.  
  
        4.  Selecteer **Toepassen** wanneer u klaar bent.  
  
8. **Een vertakking (voorwaarde) toevoegen aan het proces.** Een vertakkingsvoorwaarde toevoegen:  
  
    1.  Sleep het onderdeel **Voorwaarde** op het tabblad **Onderdelen** naar een plusteken (+) tussen twee fasen.  
  
        ![Een voorwaarde toevoegen aan een bedrijfsprocesstroom](media/add-condition-business-process-flow.png "Een voorwaarde toevoegen aan een bedrijfsprocesstroom")  
  
    2.  Selecteer de voorwaarde en stel vervolgens eigenschappen in op het tabblad **Eigenschappen**: Zie [Bedrijfsprocesstromen verbeteren met vertakkingen](enhance-business-process-flows-branching.md) voor meer informatie over vertakkingseigenschappen. Wanneer u klaar bent met instellen van de eigenschappen voor de voorwaarde, selecteert u **Toepassen**.  
  
9. **Een werkstroom toevoegen.** Een werkstroom aanroepen:  
  
    1.  Sleep een onderdeel van **Werkstroom** vanaf het tabblad **Onderdelen** naar een fase of naar het item**Algemene werkstroom** in de ontwerpfunctie.   Waar u het onderdeel aan toevoegt, is afhankelijk van het volgende:  
  
       - **Sleep het onderdeel naar een fase** als u de werkstroom bij openen of afsluiten van de fase wilt activeren. Het werkstroomonderdeel moet worden gebaseerd op dezelfde primaire entiteit als de fase.  
  
       - **Sleep het onderdeel naar het item Algemene werkstroom** als u wilt dat de werkstroom wordt geactiveerd wanneer het proces wordt geactiveerd of wanneer het proces wordt gearchiveerd (wanneer de status wordt gewijzigd in **Voltooid** of **Afgebroken**). Het werkstroomonderdeel moet worden gebaseerd op dezelfde primaire entiteit als het proces.  
  
    2.  Selecteer de werkstroom en stel vervolgens eigenschappen in op het tabblad **Eigenschappen**:  
  
       1.  Voer een weergavenaam in.  
  
       2.  Selecteer wanneer de werkstroom moet worden geactiveerd.  
  
       3.  Zoek naar een bestaande actieve werkstroom op aanvraag die overeenkomt met de fase-entiteit of maak een nieuwe werkstroom door **Nieuw** te selecteren.  
  
       4.  Selecteer **Toepassen** wanneer u klaar bent.  
  
       Zie [Werkstroomprocessen](../common-data-service/workflow-processes.md) voor meer informatie over werkstromen.  
  
10. Als u de bedrijfsprocesstroom wilt valideren, selecteert u **Valideren** op de actiebalk.  
  
11. Als u het proces wilt opslaan als concept terwijl u eraan blijft werken, selecteert u **Opslaan** op de actiebalk.  
  
    > [!IMPORTANT]
    >  Zolang een proces een concept is, kan het niet worden gebruikt.  
  
12. Als u het proces wilt activeren en het toegankelijk wilt maken voor uw team, selecteert u **Activeren** op de actiebalk.  

13. Als u wilt bepalen wie het exemplaar van de bedrijfsprocesstroom kan maken, lezen, bijwerken of verwijderen, selecteert u **Beveiligingsrollen bewerken** op de opdrachtbalk van de ontwerpfunctie. Zo kunt u voor servicegerelateerde processen klantenservicemedewerkers volledige toegang verlenen om de instantie van de bedrijfsprocesstroom te wijzigen, maar verkopers alleen-lezentoegang tot de instantie geven zodat ze de activiteiten na de verkoop kunnen volgen voor hun voor klanten.

  Selecteer de naam van een rol op het scherm **Beveiligingsrollen** om de informatiepagina voor beveiligingsrollen te openen. Selecteer het tabblad Bedrijfsprocesstromen en wijs de gewenste bevoegdheden voor de bedrijfsprocesstroom toe aan een beveiligingsrol.

  > [!NOTE]
  > De beveiligingsrollen Systeembeheerder en Systeemaanpasser hebben standaard toegang tot nieuwe bedrijfsprocesstromen.

   ![Bevoegdheden toewijzen voor een bedrijfsprocesstroom](media/bpf-assign-privileges.png)

  Geef de bevoegdheden op door de juiste keuzerondjes te selecteren en klik op Opslaan. Zie [Bevoegdheden bedrijfsprocesstromen](business-process-flows-overview.md#BKMK_MultipleBPF) voor meer informatie over de bevoegdheden.

  Vergeet vervolgens niet de beveiligingsrol toe te wijzen aan juiste gebruikers binnen uw organisatie.

> [!TIP] 
>  Hier volgen een paar tips waarmee u rekening moet houden wanneer u aan uw taakstroom werkt in het venster van de ontwerpfunctie:  
>   
> - Als u een momentopname wilt maken van alles in het venster bedrijfsprocesstroom, selecteert u **Momentopname** op de actiebalk. Dit is bijvoorbeeld handig als u deze informatie met een teamlid wilt delen en feedback over het proces wilt krijgen.  
> - Gebruik het minioverzicht om snel naar verschillende onderdelen van het proces te navigeren. Dit is handig wanneer u een gecompliceerd proces hebt dat van het scherm schuift.  
> - Als u een beschrijving wilt toevoegen aan het bedrijfsproces, selecteert u **Details** onder de procesnaam in de linkerhoek van het bedrijfsprocesstroomvenster. U kunt maximaal 2000 tekens gebruiken.  
  
<a name="BKMK_Editbusinessprocessflows"></a>   
## <a name="edit-a-business-process-flow"></a>Een bedrijfsprocesstroom bewerken  
 Als u bedrijfsprocesstromen wilt bewerken, opent u Solution Explorer en selecteert u **Processen**. Selecteer vervolgens de **Bedrijfsprocesstroom** in de lijst met processen die u wilt bewerken.  
  
 Als u de naam van de bedrijfsprocesstroom die u wilt bewerken selecteert in de lijst met processen, wordt deze geopend in de ontwerpfunctie waarin u de stroom kunt bewerken. Vouw **Details** uit onder de naam van het proces om deze te wijzigen of een beschrijving toe te voegen en aanvullende informatie weer te geven.  
  
 ![Uitgevouwen details van een bedrijfsprocesstroom ](media/business-process-flow-details.png "Uitgevouwen details van een bedrijfsprocesstroom")  
  
  
## <a name="other-things-to-know-about-business-process-flows"></a>Andere zaken die u moet weten over bedrijfsprocesstromen
 **Fasen bewerken**  
Bedrijfsprocesstromen kunnen maximaal 30 fasen bevatten.    
  
U kunt de volgende fase-eigenschappen toevoegen of wijzigen:  
  
- **Fasenaam**  
  
- **Entiteit**. U kunt de entiteit voor elke fase wijzigen, behalve voor de eerste.  
  
- **Fasecategorie**. Met een categorie kunt u fasen groeperen op actietype. Dit is handig voor rapporten die records groeperen op de fase waar ze zich in bevinden. De opties voor de fasecategorie zijn afkomstig uit de algemene optieset Fasecategorie. U kunt extra opties voor deze algemene optieset toevoegen en de labels van bestaande opties desgewenst wijzigen. U kunt deze opties ook verwijderen als u wilt, maar we raden aan de bestaande opties te behouden. U kunt niet exact dezelfde optie weer toevoegen als u deze verwijdert. Als u niet wilt dat ze worden gebruikt, wijzigt u het label in Niet gebruiken.  
  
- **Relatie**. Voer een relatie in als de voorgaande fase in het proces is gebaseerd op een andere entiteit. Voor de fase die op dit moment wordt gedefinieerd, kiest u **Relaties selecteren** om een relatie te identificeren die moet worden gebruikt tijdens de overgang tussen de twee fasen. Het is raadzaam dat u een relatie selecteert voor de volgende voordelen:  
  
    -   Er zijn vaak kenmerktoewijzingen gedefinieerd voor relaties die automatisch gegevens overdragen tussen records en zo gegevensinvoer minimaliseren.  
  
    -   Wanneer u voor een record **Volgende fase** selecteert op de procesbalk, worden alle records die gebruikmaken van de relatie vermeld in de processtroom, waardoor het hergebruik van records in het proces wordt gepromoot. Bovendien kunt u werkstromen gebruiken om het maken van records te automatiseren zodat de gebruiker deze gewoon selecteert in plaats van er één te maken om het proces verder te stroomlijnen.  
  
**Stappen bewerken**  
 Elke fase kan maximaal 30 stappen bevatten.    
  
**Vertakking toevoegen**  
Zie [Bedrijfsprocesstromen verbeteren met vertakkingen](enhance-business-process-flows-branching.md) voor meer informatie over het toevoegen van een vertakking aan een fase.  
  
Als u een bedrijfsprocesstroom beschikbaar stelt voor gebruik door anderen, moet u de processtroom een volgorde geven, beveiligingsrollen inschakelen en de stroom activeren.  
  
**Processtroomvolgorde instellen**  
 Wanneer u meer dan één bedrijfsprocesstroom voor een entiteit (recordtype) hebt, moet u instellen welk proces automatisch wordt toegewezen aan nieuwe records. Selecteer **Processtroomvolgorde** op de opdrachtbalk. Voor nieuwe records of records waar nog geen processtroom aan zit gekoppeld, is de eerste bedrijfsprocesstroom waar een gebruiker toegang tot heeft, de processtroom die wordt gebruikt.  
  
**Beveiligingsrollen inschakelen**  
Gebruikers hebben toegang tot een bedrijfsprocesstroom, afhankelijk van de bevoegdheid die is gedefinieerd in de bedrijfsprocesstroom in de beveiligingsrol die is toegewezen aan de gebruiker. 

Standaard kunnen alleen personen met de beveiligingsrollen **Systeembeheerder** en **Systeemaanpasser** een nieuwe bedrijfsprocesstroom weergeven. 

Als u bevoegdheden voor een bedrijfsprocesstroom wilt opgeven, opent u de bedrijfsprocesstroom om deze te bewerken en selecteert u vervolgens **Beveiligingsrollen bewerken** op de opdrachtbalk van de ontwerpfunctie voor bedrijfsprocesstromen. Zie stap 13 bij [Bedrijfsprocesstroom maken](#create-a-business-process-flow) eerder in dit onderwerp.
  
**Activeren**  
Voordat iemand de bedrijfsprocesstroom kan gebruiken, moet u deze activeren. Selecteer **Activeren** op de opdrachtbalk. Nadat u de activering hebt bevestigd, is de bedrijfsprocesstroom klaar voor gebruik. Als een bedrijfsprocesstroom fouten bevat, kunt u de stroom niet activeren totdat de fouten zijn gecorrigeerd.  

## <a name="add-an-on-demand-action-to-a-business-process-flow"></a>Een actie op aanvraag toevoegen aan een bedrijfsprocesstroom
Versie 9.0 van Dynamics 365 (online) introduceert een nieuwe bedrijfsprocesstroomfunctie: automatisering van bedrijfsprocesstromen met actiestappen. U kunt een knop toevoegen aan een bedrijfsprocesstroom waarmee een actie of een werkstroom wordt geactiveerd.

### <a name="add-on-demand-workflows-or-actions-using-an-action-step"></a>Werkstromen of acties op aanvraag toevoegen met behulp van een actiestap
Stel dat de Contoso-organisatie als onderdeel van het kwalificatieproces voor mogelijkheden, vereist dat alle mogelijkheden moeten worden gecontroleerd door een speciaal aangestelde revisor. Vervolgens heeft de Contoso-organisatie een actie gemaakt waarmee het volgende wordt uitgevoerd: 

- Een taakrecord maken die wordt toegewezen aan de revisor van de verkoopkans. 
- De tekst Klaar voor beoordeling toevoegen aan het onderwerp van de verkoopkans. 

Contoso moet bovendien deze acties op aanvraag kunnen uitvoeren. Als u deze taken wilt integreren in het verkoopkanskwalificatieproces, moeten de acties worden weergegeven in de bedrijfsprocesstroom voor verkoopkansen. Als u deze functionaliteit wilt inschakelen, selecteert u **Als een actiestap in een bedrijfsprocesstroom**.
![Beschikbaar om uit te voeren als een bedrijfsprocesstroom.](media/action-available-to-run.png)

De actiestap wordt vervolgens toegevoegd aan de bedrijfsprocesstroom Contoso-verkoopkans. De processtroom wordt gevalideerd en bijgewerkt.

![De actie wordt toegevoegd aan bedrijfsprocesstroom voor de verkoopkans.](media/add-action-to-bpf.png)

Nu kunnen leden van het Contoso-verkoopteam de actie op aanvraag starten vanuit de bedrijfsprocesstap **Verkoopkanskwalificatie** door **Uitvoeren** te selecteren.

![Actie uitvoeren](media/action-execute.png)

> [!IMPORTANT]
> - Als u een actie of een werkstroom op aanvraag wilt kunnen uitvoeren, moet de bedrijfsprocesstroom een actiestap omvatten. Als de actiestap een werkstroom uitvoert, moet de werkstroom worden geconfigureerd om op aanvraag te kunnen worden uitgevoerd.
> - De entiteit die is gekoppeld aan de actie of werkstroom, moet dezelfde zijn als de entiteit die is gekoppeld aan de bedrijfsprocesstroom.

### <a name="limitation-of-using-action-steps-in-a-business-process-flow"></a>Beperking van het gebruik van actiestappen in een bedrijfsprocesstroom

- Acties zijn niet beschikbaar als actiestappen als de invoer- of uitvoerparameters het type Entity, EntityCollection of OptionSet (selectielijst) hebben. Acties met meer dan één EntityReference-uitvoerparameter of een willekeurig aantal EntityReference-invoerparameters zijn niet beschikbaar als actiestappen. Acties die niet zijn gekoppeld aan een primaire entiteit (globale actie) zijn niet beschikbaar als actiestappen.

  
## <a name="next-steps"></a>Volgende stappen  
 [Overzicht bedrijfsprocesstromen](business-process-flows-overview.md) </br>   
 [Bedrijfsprocesstromen verbeteren met vertakkingen](enhance-business-process-flows-branching.md)

