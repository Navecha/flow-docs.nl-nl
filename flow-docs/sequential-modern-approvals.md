---
title: Een moderne goedkeurings werk stroom maken met meerdere goed keurders | Microsoft Docs
description: 'Een moderne goedkeurings werk stroom maken met meerdere goed keurders '
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
ms.date: 06/08/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 269239bd3fbb07c78bf316f9e58003690c63d878
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548987"
---
# <a name="manage-sequential-approvals-with-microsoft-flow"></a>Sequentiële goed keuringen beheren met Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Voor sommige werk stromen moet vooraf goed keuring worden ingesteld voordat de definitieve goed keurder is vereist voor het afmelden. Het is bijvoorbeeld mogelijk dat een bedrijf een sequentieel goedkeurings beleid heeft dat vooraf goed keuring vereist voor facturen van $1000,00 voordat ze door de afdeling Financiën worden goedgekeurd.

In dit scenario maken we een sequentiële goedkeurings stroom waarmee vakantie aanvragen van werk nemers worden beheerd.

> [!NOTE]
> Share point wordt hier alleen als voor beeld gebruikt. het is niet vereist om goedkeurings stromen te maken. U kunt een van de meer dan 200 Services gebruiken waarmee Microsoft Flow integreert om uw stromen te bezorgen.


## <a name="detailed-steps-in-the-flow"></a>Gedetailleerde stappen in de stroom
De stroom:

1. Wordt gestart wanneer een werk nemer vakantie aanvragen maakt in een [share point online-lijst](https://support.office.com/article/Introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7).
2. Voegt de vakantie aanvraag toe aan het goedkeurings centrum en verzendt de aanvraag per e-mail naar de vooraf-fiatteur.
3. E-mailt de beslissing vooraf goed keuring aan de werk nemer.
4. Werkt de share point online-lijst bij met de beslissing en opmerkingen van de vooraf-fiatteur.
   
   Opmerking: als de aanvraag vooraf is goedgekeurd, wordt de stroom voortgezet met de volgende stappen:
5. De aanvraag wordt verzonden naar de definitieve goed keurder.
6. E-mailt de definitieve beslissing voor de werk nemer.
7. Hiermee wordt de share point-lijst bijgewerkt met de definitieve beslissing.

In deze afbeelding vindt u een overzicht van de voor gaande stappen:

   ![Visio-diagram van de stroom](./media/sequential-modern-approvals/visio-overview.png)

## <a name="prerequisites"></a>Vereisten
[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

Voor de doel einden van dit scenario moet de share point online-lijst die u maakt, de volgende kolommen bevatten:

   ![Share point-lijst kolommen](./media/sequential-modern-approvals/sharepoint-columns.png)

Noteer de naam en de URL van de share point online-lijst. We gebruiken deze items later wanneer u de trigger **share point-wanneer een nieuw item wordt gemaakt** configureert.

## <a name="create-your-flow-from-the-blank-template"></a>Uw stroom maken op basis van de lege sjabloon
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Een trigger toevoegen
[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

   ![share point-info](./media/sequential-modern-approvals/select-sharepoint-site-info.png)

## <a name="get-the-manager-for-the-person-who-created-the-vacation-request"></a>De manager ophalen voor degene die de vakantie aanvraag heeft gemaakt
[!INCLUDE [add-get-manager-action](includes/add-get-manager-action.md)]

1. Geef een naam op voor uw stroom en selecteer **stroom maken** om het werk dat we tot nu toe hebben gedaan, op te slaan.
   
    ![stroom opslaan](./media/sequential-modern-approvals/save.png)
   
   > [!NOTE]
   > Selecteer regel matige **stroom bijwerken** van de bovenkant van het scherm om de wijzigingen in uw stroom op te slaan.
   > 
   > 
   
    ![Update-actie selecteren](./media/sequential-modern-approvals/update.png)

Na elke opslag bewerking selecteert u **stroom bewerken** vanaf de bovenkant van het scherm en gaat u verder met het maken van wijzigingen.

## <a name="add-an-approval-action-for-pre-approvals"></a>Een goedkeurings actie voor voorafgaande goed keuringen toevoegen
[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

Opmerking: met deze actie wordt de aanvraag vóór goed keuring verzonden naar het e-mail adres in het vak **toegewezen aan** .

## <a name="add-a-condition"></a>Een voor waarde toevoegen
[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

> [!NOTE]
> Deze voor waarde controleert de reactie van de actie **een goed keuring starten** .
> 
> 

## <a name="add-an-email-action-for-pre-approvals"></a>Een e-mail actie toevoegen voor voorafgaande goed keuringen
[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![vooraf goedgekeurde e-mail sjabloon configureren](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-pre-approved-requests"></a>Een bijwerk actie voor vooraf goedgekeurde aanvragen toevoegen
[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

   ![artikel configuratie bijwerken](./media/sequential-modern-approvals/configure-update-item.png)

## <a name="get-the-pre-approvers-manager"></a>De Manager van de vooraf-fiatteur ophalen
1. Gebruik de stappen [voor het ophalen van de Manager voor de persoon die de vakantie-aanvraag heeft gemaakt](sequential-modern-approvals.md#get-the-manager-for-the-person-who-created-the-vacation-request) , en stel vervolgens een andere actie voor **Get Manager** in. Deze keer wordt de Manager van de vooraf-fiatteur opgehaald.
2. De kaart **Manager ophalen 2** moet er als volgt uitzien wanneer u klaar bent. Zorg ervoor dat u het **e-mail** token van de categorie **Manager ophalen** gebruikt voor het **toevoegen van dynamische inhoud van de apps en services die worden gebruikt in deze stroom** kaart.
   
   ![Manager van vooraf-fiatteur ophalen](includes/media/modern-approvals/get-pre-approver-manager.png)

## <a name="add-the-final-approval-action"></a>De definitieve goedkeurings actie toevoegen
1. Gebruik de stappen [voor het toevoegen van een goed keuring voor voorafgaande goed keuringen](sequential-modern-approvals.md#add-an-approval-action-for-pre-approvals) die we eerder hebben gedaan en configureer vervolgens een andere actie voor **het starten van een goed keuring** . Met deze actie wordt een e-mail verzoek verzonden voor definitieve goed keuring.
2. Wanneer u klaar bent, moet de kaart eruitzien als deze afbeelding:
   
    ![de goed keuring configureren](./media/sequential-modern-approvals/provide-approval-config-info.png)

## <a name="add-the-final-approval-condition"></a>De uiteindelijke goedkeurings voorwaarde toevoegen
1. Herhaal de stappen in [toevoegen om een voor waarde](sequential-modern-approvals.md#add-a-condition) toe te voegen en configureer vervolgens een **voor waarde** die de beslissing van de definitieve goed keurder controleert.

## <a name="send-email-with-final-approval"></a>E-mail met definitieve goed keuring verzenden
1. Gebruik de stappen voor het toevoegen van [een e-mail actie voor het toevoegen van voorafgaande goed keuringen](sequential-modern-approvals.md#add-an-email-action-for-pre-approvals) en configureer vervolgens een actie die een e-mail bericht verzendt wanneer vakantie aanvragen worden goedgekeurd.
2. Wanneer u klaar bent, moet uw kaart eruitzien als deze afbeelding:
   
   ![e-mail sjabloon voor definitieve goed keuring](./media/sequential-modern-approvals/vacatioin-request-approved-email-template.png)

## <a name="update-sharepoint-with-approval"></a>Share point bijwerken met goed keuring
1. Gebruik de stappen voor het toevoegen van [een update-actie voor vooraf goedgekeurde aanvragen](sequential-modern-approvals.md#add-an-update-action-for-pre-approved-requests) om toe te voegen en configureer vervolgens een actie die share point bijwerkt wanneer de vakantie aanvraag is goedgekeurd.
2. Wanneer u klaar bent, moet de kaart eruitzien als deze afbeelding:
   
    ![artikel configuratie bijwerken](./media/sequential-modern-approvals/configure-update-item-approved.png)

## <a name="send-email-with-pre-approval-rejection"></a>E-mail met toestemming voor goed keuring verzenden
[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

   ![configuratie voor geweigerde aanvragen](./media/sequential-modern-approvals/configure-rejected-email.png)

Opmerking: deze actie moet worden toegevoegd aan de vertakking **Indien nee, niets doen** onder de kaart **voor waarde** .

## <a name="update-sharepoint-with-pre-approval-rejection"></a>Share point bijwerken met afwijzing vóór goed keuring
[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   ![share point bijwerken voor geweigerde aanvragen](./media/sequential-modern-approvals/update-sharepoint-with-rejection.png)

## <a name="send-email-with-final-rejection"></a>E-mail met definitieve afwijzing verzenden
1. Gebruik de stappen in [E-mail verzenden met toestemming voor goed keuring](sequential-modern-approvals.md#send-email-with-pre-approval-rejection) voor toevoegen en vervolgens een actie configureren die een e-mail verzendt wanneer de vakantie aanvraag wordt afgewezen door de definitieve goed keurder.
   
    Opmerking: deze actie moet worden toegevoegd aan de vertakking **Indien nee, niets doen** onder de kaart **voor waarde 2** .
2. Wanneer u klaar bent, moet de kaart eruitzien als deze afbeelding:
   
   ![configuratie voor geweigerde aanvragen](./media/sequential-modern-approvals/final-rejection-email-card.png)

## <a name="update-sharepoint-with-final-rejection"></a>Share point bijwerken met definitieve afwijzing
1. Volg de stappen in [share point bijwerken met toestemming voor goed keuring](sequential-modern-approvals.md#update-sharepoint-with-pre-approval-rejection) voor toevoegen en vervolgens een actie configureren die share point bijwerkt als de definitieve goed keurder de vakantie aanvraag afwijst.
2. Wanneer u klaar bent, moet de kaart eruitzien als deze afbeelding:
   
   ![artikel kaart bijwerken](./media/sequential-modern-approvals/final-rejection-update-sharepoint.png)
3. Selecteer **stroom bijwerken** om het werk dat we hebben uitgevoerd, op te slaan.
   
   ![Update-actie selecteren](./media/sequential-modern-approvals/update.png)

Als u de bewerking hebt gevolgd, moet uw stroom eruitzien als deze afbeelding:

![overzicht van flow](./media/sequential-modern-approvals/completed-flow.png)

Nu u de stroom hebt gemaakt, wordt deze in actie weer gegeven.

## <a name="request-an-approval"></a>Een goed keuring aanvragen
[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]

Uw aanvraag moet er ongeveer als volgt uitzien:

![vakantie aanvraag](./media/sequential-modern-approvals/vacation-request.png)

## <a name="view-pending-approval-requests"></a>Goedkeurings aanvragen in behandeling weer geven
[!INCLUDE [view-pending-approvals](includes/view-pending-approvals.md)]

## <a name="pre-approve-a-request"></a>Een aanvraag vooraf goed keuren
[!INCLUDE [approve-request-from-different-locations](includes/approve-request-from-different-locations.md)]

## <a name="approve-the-request"></a>De aanvraag goed keuren
De stappen voor het goed keuren van een aanvraag zijn identiek aan de stappen voor het [vooraf goed keuren van een aanvraag](sequential-modern-approvals.md#pre-approve-a-request)

Opmerking: de definitieve goed keurder haalt de vakantie aanvraag pas op nadat de aanvraag vooraf is goedgekeurd.

## <a name="reject-a-request"></a>Een aanvraag afwijzen
[!INCLUDE [reject-a-request](includes/reject-a-request.md)]

## <a name="more-information"></a>Meer informatie
[Overzicht van de moderne goed keuringen voor één goed keurder](modern-approvals.md)

