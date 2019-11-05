---
title: Een goedkeurings stroom maken waarvoor iedereen goed keuring moet hebben | Microsoft Docs
description: Maak een goedkeurings stroom waarvoor iedereen moet goed keuren of één persoon om een aanvraag af te wijzen.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/27/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 191792c356dc6b5e3a285a16050a306d4e6039f2
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545189"
---
# <a name="create-an-approval-flow-that-requires-everyone-to-approve"></a>Een goedkeurings stroom maken waarvoor iedereen goed keuring moet hebben
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

In dit scenario ziet u hoe u een goedkeurings werk stroom maakt waarvoor iedereen (alle toegewezen goed keurders) toestemming moet geven voor het goed keuren van een vakantie aanvraag, maar een fiatteur de volledige aanvraag kan afwijzen.

Dit type goedkeurings werk stroom is nuttig in een organisatie waarvoor de Manager van een persoon en de Manager van de Manager zijn vereist om beide ermee in te stemmen om een vakantie aanvraag te kunnen goed keuren. Een manager kan de aanvraag echter afwijzen zonder de invoer van de andere persoon.

> [!NOTE]
> Hoewel deze walkthrough een scenario voor vakantie goedkeuringen markeert, kunt u dit type goedkeurings stroom gebruiken in elke situatie waarbij meerdere goed keurders een aanvraag moeten goed keuren.
>
>

## <a name="prerequisites"></a>Vereisten

* Toegang tot [Microsoft flow](https://flow.microsoft.com), Microsoft Office 365 Outlook en Microsoft Office 365-gebruikers.
* Een share point- [lijst](https://support.office.com/article/SharePoint-lists-I-An-introduction-f11cd5fe-bc87-4f9e-9bfe-bbd87a22a194).

    In dit scenario wordt ervan uitgegaan dat u een share point-lijst hebt gemaakt die wordt gebruikt voor het aanvragen van vakanties. Zie het overzicht van [parallelle goed keuringen](parallel-modern-approvals.md) voor een uitgebreid voor beeld waarin wordt uitgelegd hoe uw share point-lijst eruit kan zien.
* Vertrouwd met de basis beginselen van het maken van stromen.

    U kunt controleren hoe [acties, triggers](multi-step-logic-flow.md#add-another-action)en [voor waarden](add-condition.md)worden toegevoegd. Bij de volgende stappen wordt ervan uitgegaan dat u weet hoe u deze acties moet uitvoeren.

> [!NOTE]
> Hoewel we share point en Office 365 Outlook in dit overzicht worden gebruikt, kunt u andere services gebruiken, zoals Zendesk, Sales Force, Gmail of een van de meer dan [200 services](https://flow.microsoft.com/connectors/) die Microsoft flow ondersteunt.
>
>

## <a name="create-the-flow"></a>De stroom maken

> [!NOTE]
> Als u nog geen verbinding met share point of Office 365 hebt gemaakt, volgt u de instructies wanneer u wordt gevraagd om u aan te melden.
>
>

In deze walkthrough wordt gebruikgemaakt van tokens. Als u de lijst met tokens wilt weer geven, tikt of klikt u op een invoer besturings element en zoekt u naar het token in de lijst met **dynamische inhoud** die wordt geopend.

Meld u aan bij [Microsoft flow](https://flow.microsoft.com)en voer de volgende stappen uit om uw stroom te maken.

1. Selecteer **mijn stromen** > **leeg te maken**in de rechter bovenhoek van het scherm.
1. Voeg de trigger **share point-wanneer een item is gemaakt of gewijzigd** toe.
1. Voer het **site adres** in voor de share point-site die als host fungeert voor uw lijst met vakantie aanvragen en selecteer vervolgens de **naam**van de lijst lijst.
1. Voeg de actie **Office 365-gebruikers-Get Manager V2** toe, selecteer het vak **gebruiker (UPN)** en voeg hieraan het token **gemaakt door e-mail** toe.

    Het token **gemaakt door e-mail** bevindt zich onder de categorie **Wanneer een item is gemaakt of gewijzigd** van de lijst met **dynamische inhoud** . Dit token biedt dynamisch toegang tot gegevens over de Manager voor de persoon die het item heeft gemaakt in share point.

1. Voeg nog een andere **Office 365-gebruikers-Manager V2-** actie toe en voeg het token **e-mail** toe aan het vak **gebruiker (UPN)** .

    De **e-mail** token bevindt zich in de categorie **Get Manager V2 2** van de lijst met **dynamische inhoud** . Dit token biedt dynamisch toegang tot het e-mail adres voor de Manager van de Manager.

    U kunt ook de naam van de kaart **Manager V2 2 ophalen** wijzigen in iets als ' niveau van beheer overs Laan '.
1. Voeg de actie **een goed keuring starten** toe en selecteer vervolgens **iedereen uit de lijst met toewijzingen** in de lijst **goedkeurings type** .

   > [!IMPORTANT]
   > Als een fiatteur afkeurt, wordt de goedkeurings aanvraag beschouwd als afgewezen voor alle goed keurders.
   >
   >
1. Gebruik de volgende tabel als richt lijn voor het volt ooien van de kaart voor het **starten van een goed keuring** .

   | Aan | Beschrijvingen |
   | --- | --- |
   |  Goedkeurings type |Gebruik **iedereen uit de lijst met toegewezen** om aan te geven dat een van de goed keurders de aanvraag kan goed keuren of afwijzen. </p>Gebruik **iedereen uit de lijst met toegewezen** om aan te geven dat een aanvraag alleen wordt goedgekeurd als iedereen ermee akkoord gaat en de aanvraag wordt geweigerd als één persoon deze weigert. |
   |  Hoofd |De titel van de goedkeurings aanvraag. |
   |  Toegewezen aan |De e-mail adressen van de goed keurders. |
   |  Nadere |Aanvullende informatie die u wilt verzenden naar de goed keurders die worden weer gegeven in het veld **toegewezen aan** . |
   |  Item koppeling |Een URL naar het goedkeurings item. In dit voor beeld is dit een koppeling naar het item in share point. |
   |  Beschrijving van item koppeling |Een beschrijving van de tekst voor de **item koppeling**. |

   > [!TIP]
   > De actie **een goed keuring starten** biedt verschillende tokens, inclusief **antwoord** -en **antwoord samenvatting**. Gebruik deze tokens in uw stroom om te zorgen voor een uitgebreide rapportage van de resultaten van een uitvoering van een goedkeurings aanvraag stroom.
   >
   >

    De kaart een **goed keuring starten** is een sjabloon voor de goedkeurings aanvraag die wordt verzonden naar goed keurders. Configureer deze op een manier die geschikt is voor uw organisatie. Hier volgt een voor beeld.

    ![een goed keuring starten](media/all-assigned-must-approve/start-an-approval-card.png)

1. Voeg de actie **Office 365 Outlook-een E-mail verzenden** toe en configureer deze vervolgens om een e-mail te verzenden met de resultaten van de aanvraag.

    Hier volgt een voor beeld van hoe de kaart **een E-mail verzenden** eruit kan zien.

    ![een e-mail verzenden](media/all-assigned-must-approve/send-an-email-card.png)

> [!NOTE]
> Acties die volgen op de actie **een goed keuring starten** , worden uitgevoerd op basis van uw selectie in de lijst **goedkeurings type** op de kaart **een goed keuring starten** . De volgende tabel geeft een overzicht van het gedrag op basis van uw selectie.
>
>

| Goedkeurings type | Tabtoets |
| --- | --- |
| Iedereen van de lijst met toegewezen |Acties die volgen op de actie **een goed keuring starten** , worden uitgevoerd nadat een van de fiatteurs beslist. |
| Iedereen van de lijst met toegewezen |Acties die volgen op de actie **een goed keuring starten** , worden uitgevoerd nadat een fiatteur weigert of iedereen de aanvraag goedkeurt. |

Typ aan de bovenkant van het scherm een naam voor de stroom in het vak **stroom naam** en selecteer **stroom maken** om deze op te slaan.

Gefeliciteerd, uw stroom is voltooid. Als u de bewerking hebt gevolgd, lijkt de stroom op deze afbeelding.

![algehele stroom afbeelding](media/all-assigned-must-approve/overall-flow.png)

Telkens wanneer een item wordt toegevoegd aan uw share point-lijst of als een item wordt gewijzigd, wordt de stroom geactiveerd en worden er goedkeurings aanvragen verzonden naar alle goed keurders die worden vermeld in het vak **toegewezen aan** van de kaart **een goed keuring starten** . Uw stroom verzendt goedkeurings aanvragen via de mobiele app van Microsoft Flow en via e-mail. De persoon die het item in share point maakt, ontvangt een e-mail met een samen vatting van de resultaten, waarmee duidelijk wordt aangegeven of de aanvraag is goedgekeurd of afgewezen.

Hier volgt een voor beeld van de goedkeurings aanvraag die naar elke goed keurder wordt verzonden.

![goedkeurings aanvraag](media/all-assigned-must-approve/approval-request.png)

Hier volgt een voor beeld van hoe een antwoord en een antwoord samenvatting eruitzien nadat de stroom is uitgevoerd.

![antwoord tokens](media/all-assigned-must-approve/response-output.png)

## <a name="learn-more-about-approvals"></a>Meer informatie over goed keuringen

* [Moderne goed keuringen voor één goed keurder](modern-approvals.md)
* [Sequentiële moderne goed keuringen](sequential-modern-approvals.md)
* [Parallelle moderne goed keuringen](parallel-modern-approvals.md)
* [Goed keuringen en de micro soft-Common Data Service](common-data-model-approve.md)
* [Aanvragen onderweg goed keuren](mobile-approvals.md)
