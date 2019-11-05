---
title: Meer informatie over het toevoegen van andere eigen aren aan een stroom en het maken van team stromen | Microsoft Docs
description: Microsoft Flow maakt het eenvoudig om terugkerende taken te automatiseren. U kunt gebruikers of groepen toevoegen als eigen aren en samen werken met hen om stromen te ontwerpen en te beheren.
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
ms.date: 04/21/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f2a986568a44f8329e55fc62aef4705207cdfc49
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547626"
---
# <a name="create-team-flows"></a>Team stromen maken
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Maak een team stroom door anderen in uw organisatie als eigen aren toe te voegen. Alle eigen aren van een team stroom kunnen deze acties uitvoeren:

* De geschiedenis van de stroom weer geven (dat wil zeggen, elke uitvoering).
* De eigenschappen van de stroom beheren (bijvoorbeeld om de stroom te starten of te stoppen, eigen aren toe te voegen of referenties voor een verbinding bij te werken).
* Bewerk de definitie van de stroom (bijvoorbeeld een actie of een voor waarde toevoegen of verwijderen).
* Andere eigen aren toevoegen en verwijderen (maar niet de maker van de stroom).
* Verwijder de stroom.

Als u de maker of eigenaar van een team stroom bent, vindt u deze vermeld op het tabblad **team stromen** op [Microsoft flow](https://flow.microsoft.com).

![tabblad team stromen](./media/create-team-flows/addowner5.png)

> [!NOTE]
> Gedeelde verbindingen kunnen **alleen** worden gebruikt in de stroom waarin ze zijn gemaakt.
> 
> 

Eigen aren kunnen services in een stroom gebruiken, maar kunnen niet de referenties wijzigen voor een verbinding die door een andere eigenaar is gemaakt.

## <a name="prerequisites"></a>Vereisten
U moet een [betaald Microsoft flow-abonnement](https://flow.microsoft.com/pricing/) hebben om een team stroom te kunnen maken. Daarnaast moet u de maker of eigenaar zijn om eigen aren toe te voegen aan of te verwijderen uit een team stroom.

## <a name="create-a-team-flow"></a>Een team stroom maken
Volg deze stappen om een team stroom te maken of om meer eigen aren toe te voegen aan een team stroom.

1. Meld u aan bij de [Microsoft flow](https://flow.microsoft.com)en selecteer vervolgens **mijn stromen**.
2. Selecteer het pictogram personen voor de stroom die u wilt wijzigen:
   
    ![pictogram team](./media/create-team-flows/addowner1.png)
3. Voer de naam, het e-mail adres of de groeps naam in voor de persoon of groep die u wilt toevoegen als een eigenaar:
   
    ![zoeken naar de gebruiker](./media/create-team-flows/addowner2.png)
4. Selecteer in de lijst die wordt weer gegeven de gebruiker aan wie u een eigenaar wilt maken:
   
    ![De gebruiker selecteren](./media/create-team-flows/addowner3.png)
   
     De gebruiker of groep die u hebt geselecteerd, wordt een eigenaar van de stroom:
   
    ![nieuwe eigenaar](./media/create-team-flows/addowner4.png)
   
     Gefeliciteerd &mdash; uw team stroom is gemaakt.

## <a name="add-a-list-as-a-co-owner"></a>Een lijst toevoegen als mede-eigenaar

U kunt share point-lijsten toevoegen als mede-eigen aars aan een stroom, zodat iedereen met bewerkings toegang tot de lijst automatisch bewerkings toegang tot de stroom krijgt. Zodra de stroom is gedeeld, kunt u er gewoon een koppeling naar distribueren.

> [!TIP]
> Gebruik een lijst wanneer de stroom is verbonden met share point en gebruik een groep in andere gevallen.
>

## <a name="remove-an-owner"></a>Een eigenaar verwijderen

> [!IMPORTANT]
> Wanneer u een eigenaar verwijdert waarvan de referenties worden gebruikt voor toegang tot Microsoft Flow Services, moet u de referenties voor die verbindingen bijwerken zodat de stroom goed blijft werken.
> 
> 

1. Selecteer het pictogram personen voor de stroom die u wilt wijzigen:
   
    ![pictogram personen selecteren](./media/create-team-flows/removeowner1.png)
2. Selecteer het **Verwijder** pictogram voor de eigenaar die u wilt verwijderen:
   
    ![Selecteer verwijderen](./media/create-team-flows/removeowner2.png)
3. Selecteer in het bevestigings dialoogvenster de optie **deze eigenaar verwijderen**:
   
    ![verwijdering bevestigen](./media/create-team-flows/removeowner3.png)
4. Gefeliciteerd &mdash; de gebruiker of groep die u hebt verwijderd, wordt niet meer vermeld als een eigenaar van de stroom:
   
    ![gebruiker verwijderd](./media/create-team-flows/removeowner4.png)


## <a name="update-connection-owner"></a>Eigenaar van de verbinding bijwerken

Mogelijk moet u de eigenaar van een verbinding in een stroom wijzigen als u de bestaande eigenaar verwijdert. Volg deze stappen om de eigenaar van een stroom te scha kelen:

1. Selecteer **gegevens** in het deel venster aan de linkerkant.
1. Selecteer **verbindingen**.
1. Zoek de verbinding die u wilt bijwerken en selecteer deze.
1. Selecteer **...** (meer opdrachten) op de verbinding die u hebt geselecteerd en selecteer vervolgens **overschakelen naar ander account**.
1. Volg de stappen om een ander account voor de verbinding te gebruiken.

## <a name="embedded-and-other-connections"></a>Inge sloten en andere verbindingen

Verbindingen die in een stroom worden gebruikt, worden onderverdeeld in twee categorieën:

* **Inge sloten** &mdash; deze verbindingen worden gebruikt in de stroom.
* **Andere** &mdash; deze verbindingen zijn gedefinieerd voor een stroom, maar worden niet gebruikt.

Als u stopt met het gebruik van een verbinding in een stroom, wordt die verbinding weer gegeven in de lijst **andere** verbindingen, waar deze wordt bewaard totdat een eigenaar deze opnieuw in de stroom heeft opgenomen.

Volg de stappen om de [eigenaar van een verbinding](./create-team-flows.md#update-connection-owner) bij te werken voor het wijzigen van de Inge sloten verbindingen.

De lijst met verbindingen wordt weer gegeven onder de lijst met eigen aren in de eigenschappen van een stroom:

![Inge sloten verbindingen](./media/create-team-flows/embeddedconnections.png)

