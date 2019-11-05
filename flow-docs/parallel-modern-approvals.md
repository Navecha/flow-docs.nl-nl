---
title: Een parallelle moderne goedkeurings werk stroom maken | Microsoft Docs
description: Een parallelle moderne goedkeurings werk stroom maken
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/09/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 6cbaaecf70e4f6549a790861130dcde0b5a888e6
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548957"
---
# <a name="create-parallel-approval-workflows-with-microsoft-flow"></a>Parallelle goedkeurings werk stromen maken met Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

In een parallelle goedkeurings werk stroom moeten meerdere personen items goed keuren, zoals facturen, aankoop orders, vakantie aanvragen, enzovoort. De goed keuring van elke persoon is onafhankelijk van alle andere goed keurders.

In dit scenario gebruiken we Microsoft Flow om een stroom te maken waarmee een parallelle goedkeurings werk stroom wordt geautomatiseerd. Met deze stroom wordt een vakantie aanvraag proces voor werk nemers geautomatiseerd dat goed keuring vereist van alle personen (of teams) die de werk nemer regel matig ondersteunt. Werk nemers gebruiken een [share point-lijst](https://support.office.com/article/Introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7) om vakantie aan te vragen. Vakantie goedkeuringen zijn vereist voor de directe manager van de werk nemer, het verkoop team en het team van human resources. Elke vakantie aanvraag wordt voor een beslissing doorgestuurd naar elke goed keurder. De stroom verzendt een e-mail met status wijzigingen en werkt vervolgens share point bij met de beslissingen.

## <a name="prerequisites"></a>Vereisten

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

De share point online-lijst die u maakt, moet de volgende kolommen bevatten:

   ![Share point-lijst kolommen](./media/parallel-modern-approvals/sharepoint-columns.png)

Noteer de naam en de URL van de share point online-lijst. We gebruiken deze items later om de **share point-wanneer een item wordt gemaakt** te configureren.

## <a name="create-your-flow-from-the-blank-template"></a>Uw stroom maken op basis van de lege sjabloon

[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Een trigger toevoegen

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

   ![Share point-info](includes/media/parallel-modern-approvals/select-sharepoint-site-info.png)

## <a name="get-the-manager-for-the-person-who-created-the-vacation-request"></a>De manager ophalen voor degene die de vakantie aanvraag heeft gemaakt

[!INCLUDE [add-get-manager-action](includes/add-get-manager-action.md)]

## <a name="name-and-save-your-flow"></a>Geef uw stroom een naam en sla deze op

1. Geef een naam op voor uw stroom en selecteer vervolgens het pictogram **Opslaan** om het werk dat we tot nu toe hebben gedaan, op te slaan.

   ![stroom opslaan](./media/parallel-modern-approvals/save.png)

> [!NOTE]
> Selecteer het pictogram **Opslaan** regel matig om de wijzigingen in uw stroom op te slaan.
> 
> 


## <a name="add-an-approval-action-for-immediate-manager"></a>Een goedkeurings actie voor direct Manager toevoegen

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!IMPORTANT]
> Met deze actie wordt de vakantie aanvraag verzonden naar het e-mail adres in het **toegewezen aan** vak, dus voeg het **e-mail** token toe vanuit de lijst van **Get Manager (v2)** .
> 
> 

## <a name="insert-a-parallel-branch-approval-action-for-the-sales-team"></a>Een goedkeurings actie voor een parallelle vertakking voor het verkoop team invoegen

1. Selecteer de pijl-omlaag die zich bevindt tussen de **Get Manager (v2)** en de kaarten voor het **starten van goed keuring** .
2. Selecteer het plus teken dat wordt weer gegeven op de pijl-omlaag nadat u deze hebt geselecteerd.
3. Selecteer **een parallelle vertakking toevoegen**.
4. Selecteer **een actie toevoegen**.

    ![Manager-configuratie ophalen](./media/parallel-modern-approvals/add-parallel-branch.png)
5. Zoek naar, selecteer en configureer een **goedkeurings** actie die de vakantie aanvraag naar het verkoop team verzendt. Zie de [stappen voor het toevoegen van een goedkeurings actie voor direct beheer](parallel-modern-approvals.md#add-an-approval-action-for-immediate-manager) als u niet zeker weet hoe u de actie **een goed keuring starten** kunt toevoegen.

> [!IMPORTANT]
> Gebruik het e-mail adres van het verkoop team in het **toegewezen aan** vak van de actie **een goed keuring starten 2** .
> 
> 

## <a name="insert-a-parallel-branch-approval-action-for-the-human-resources-team"></a>Een goedkeurings actie voor parallelle branches invoegen voor het team van human resources

1. Herhaal de stappen om [een parallelle vertakking voor het verkoop team](parallel-modern-approvals.md#insert-a-parallel-branch-approval-action-for-the-sales-team) in te voegen en vervolgens een **goedkeurings actie starten** te configureren om vakantie aanvragen te verzenden naar Human resources.

> [!IMPORTANT]
> Gebruik het e-mail adres van het Human Resources-team in het **toegewezen aan** vak van de actie **een goed keuring starten** .
> 
> 

Als u de volgende stap hebt gevolgd, moet uw stroom eruitzien als in dit voor beeld:

   ![stroom met parallelle vertakkingen](./media/parallel-modern-approvals/flow-with-parallel-branches.png)

## <a name="options-after-adding-parallel-branches"></a>Opties na toevoegen van parallelle vertakkingen

Nadat u acties aan parallelle vertakkingen hebt toegevoegd, hebt u twee opties voor het toevoegen van meer stappen aan uw stroom:

1. Gebruik de kleine knop **een nieuwe stap invoegen** (de ronde plus knop die wordt weer gegeven wanneer u een witruimte op een vertakking of het gebied direct onder een vertakking selecteert). Met deze knop voegt u een stap toe aan die **specifieke vertakking**. De stappen die u met deze knop toevoegt, worden uitgevoerd nadat deze specifieke vertakking is voltooid.
1. Gebruik de grotere knop **nieuwe stap** onder aan de hele werk stroom. De stappen die u met deze knop toevoegt, worden uitgevoerd nadat alle vertakkingen zijn voltooid.

In de volgende secties gebruiken we de kleine knop **een nieuwe stap invoegen** om deze stappen uit te voeren op elke vertakking:

* Voeg een voor waarde toe waarmee wordt gecontroleerd of de vakantie aanvraag is goedgekeurd of afgewezen.
* Een e-mail verzenden die de werk nemer van de beslissing informeert.
* De vakantie aanvraag in share point bijwerken met de goedkeurings beslissing.

Vervolgens gebruiken we de grotere knop **nieuwe stap** om een e-mail te verzenden met een overzicht van alle beslissingen over de vakantie aanvraag.

Laten we door gaan:

## <a name="add-a-condition-to-each-branch"></a>Een voor waarde toevoegen aan elke vertakking

1. Selecteer witruimte in de vertakking **een goed keuring starten** .
2. Selecteer de kleine knop **een nieuwe stap invoegen** (de ronde plus knop die wordt weer gegeven nadat u de witruimte in de vorige stap hebt geselecteerd).
3. Selecteer **een voor waarde toevoegen** in het menu dat wordt weer gegeven.
4. Selecteer het eerste vak op de kaart **voor waarde** en selecteer vervolgens het **antwoord** token in de categorie **een goed keuring starten** in de lijst met dynamische inhoud.

    ![voor waarde voor stroom met parallelle vertakkingen](./media/parallel-modern-approvals/configure-approval-condition.png)
5. Bevestig dat de lijst (in het midden van de **kaart voor waarde**) is ingesteld op **is gelijk aan**.
6. Voer **goed keuren** (deze tekst is hoofdletter gevoelig) in het laatste vak in.
7. De kaart van de voor waarde moet er nu uitzien als in dit voor beeld:

    ![voor waarde voor stroom met parallelle vertakkingen](includes/media/parallel-modern-approvals/condition-card.png)

   > [!NOTE]
   > Deze voor waarde controleert de reactie van de actie **een goed keuring starten** die naar de Manager van de werk nemer gaat.
   > 
   > 
8. Herhaal de voor gaande stappen op de vertakkingen **een goed keuring starten 2** (de goedkeurings aanvraag naar verkoop) en **een goed keuring starten 3** (de goedkeurings aanvraag voor human resources).

## <a name="add-email-actions-to-each-branch"></a>E-mail acties toevoegen aan elke vertakking

Voer de volgende stappen uit op de **If ja** -zijde van de vertakking **voor waarden** .

   Opmerking: in uw stroom worden de volgende stappen gebruikt om een e-mail te verzenden wanneer de aanvraag is goedgekeurd:

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![vooraf goedgekeurde e-mail sjabloon configureren](includes/media/parallel-modern-approvals/yes-email-config.png)

Als u een e-mail bericht wilt verzenden wanneer een aanvraag wordt afgewezen, gebruikt u de **if** -vertakking van de **voor waarde** en herhaalt u de voor gaande stappen om een sjabloon toe te voegen voor de weigerings-e-mail.

Herhaal de voor gaande stappen op de vertakkingen **een goed keuring starten 2** (de goedkeurings aanvraag naar verkoop) en **een goed keuring starten 3** (de goedkeurings aanvraag voor human resources).

## <a name="update-the-vacation-request-with-the-decision"></a>De vakantie aanvraag bijwerken met de beslissing

Voer de volgende stappen uit om share point bij te werken wanneer er beslissingen worden genomen.

   Opmerking: Zorg ervoor dat u deze stappen uitvoert op zowel de **Indien ja** als aan de **als er zich geen** zijden van de vertakking bevindt.

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

   ![artikel configuratie bijwerken](./media/parallel-modern-approvals/configure-update-item.png)

Herhaal de voor gaande stappen op de **een goed keuring starten 2** en **een goed keuring starten 3** vertakkingen.

## <a name="complete-the-flow"></a>De stroom volt ooien

1. Selecteer **nieuwe stap** > **een actie toe te voegen**

    ![artikel configuratie bijwerken](includes/media/parallel-modern-approvals/add-an-action-2-step.png)
1. Gebruik de stappen die eerder zijn gegeven om een e-mail te verzenden met een overzicht van de resultaten van elke goed keuring. Deze e-mail verzenden naar de werk nemer die vakantie heeft aangevraagd. De kaart kan er als volgt uitzien:

   ![artikel configuratie bijwerken](./media/parallel-modern-approvals/final-email-card.png)

## <a name="learn-more-about-modern-approvals"></a>Meer informatie over moderne goed keuringen

[Inleiding tot moderne goed keuringen](modern-approvals.md)

