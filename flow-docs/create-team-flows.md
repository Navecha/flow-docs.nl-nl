---
title: Informatie over het toevoegen van andere eigenaren aan een stroom en het maken van teamstromen | Microsoft Docs
description: Met Microsoft Flow kunt u terugkerende taken eenvoudig automatiseren. U kunt gebruikers of groepen toevoegen als eigenaren en gezamenlijk stromen ontwerpen en beheren.
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
ms.openlocfilehash: 238ef8eac80d3259981cb11cc21e3b05eb83e0ec
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689727"
---
# <a name="create-team-flows"></a>Teamstromen maken
Maak een teamstroom door anderen in uw organisatie als eigenaren toe te voegen. Alle eigenaren van een teamstroom kunnen deze acties uitvoeren:

* De geschiedenis van de stroom weergeven (dat wil zeggen, elke uitvoering).
* De eigenschappen van de stroom weergeven (bijvoorbeeld starten of stoppen van de stroom, eigenaren toevoegen of referenties voor een verbinding bijwerken).
* Ee definitie van de stroom bewerken (bijvoorbeeld een actie of een voorwaarde toevoegen of verwijderen).
* Andere eigenaren toevoegen of verwijderen (maar niet de maker van de stroom).
* De stroom verwijderen.

Als u de maker of een eigenaar van een teamstroom bent, wordt de stroom weergegeven op het tabblad **Teamstromen** van [Microsoft Flow](https://flow.microsoft.com).

![tabblad teamstromen](./media/create-team-flows/addowner5.png)

> [!NOTE]
> Gedeelde verbindingen kunnen **alleen** worden in de stroom waarin ze zijn gemaakt.
> 
> 

Eigenaren kunnen de services in een stroom gebruiken, maar niet de referenties wijzigen voor een verbinding die door een andere eigenaar is gemaakt.

## <a name="prerequisites"></a>Vereisten
U moet een [betaald Microsoft Flow-abonnement](https://flow.microsoft.com/pricing/) hebben om een teamstroom te kunnen maken. Bovendien moet u de maker of eigenaar zijn om eigenaren van een teamstroom te kunnen toevoegen of verwijderen.

## <a name="create-a-team-flow"></a>Een teamstroom maken
Voer deze stappen uit om een teamstroom te maken of meer eigenaren aan een teamstroom toe te voegen.

1. Meld u aan bij [Microsoft Flow](https://flow.microsoft.com) en selecteer **Mijn stromen**.
2. Selecteer het pictogram Personen voor de stroom die u wilt aanpassen:
   
    ![team-pictogram](./media/create-team-flows/addowner1.png)
3. Voer de naam, het e-mailadres of groepsnaam in van de persoon of groep die u wilt toevoegen als een eigenaar:
   
    ![de gebruiker zoeken](./media/create-team-flows/addowner2.png)
4. Selecteer de gebruiker die u een eigenaar wilt maken in de lijst die wordt weergegeven:
   
    ![de gebruiker selecteren](./media/create-team-flows/addowner3.png)
   
     De gebruiker of groep die u hebt geselecteerd, wordt een eigenaar van de stroom:
   
    ![nieuwe eigenaar](./media/create-team-flows/addowner4.png)
   
     U hebt nu een teamstroom gemaakt.

##<a name="add-a-list-as-a-co-owner"></a>Een lijst toevoegen als een mede-eigenaar

U kunt SharePoint-lijsten toevoegen als mede-eigenaren van een stroom, zodat iedereen met bewerkingstoegang tot de lijst automatisch bewerkingstoegang krijgt voor de stroom. Zodra de stroom wordt gedeeld, kunt u een koppeling naar de stroom distribueren.

## <a name="remove-an-owner"></a>Een eigenaar verwijderen
> [!IMPORTANT]
> Als u een eigenaar verwijdert waarvan de referenties worden gebruikt voor toegang tot Microsoft Flow-services, moet u de referenties voor die verbindingen bijwerken om ervoor te zorgen dat de stroom correct blijft werken.
> 
> 

1. Selecteer het pictogram Personen voor de stroom die u wilt aanpassen:
   
    ![pictogram personen selecteren](./media/create-team-flows/removeowner1.png)
2. Selecteer het pictogram **Verwijderen** voor de eigenaar die u wilt verwijderen:
   
    ![verwijderen selecteren](./media/create-team-flows/removeowner2.png)
3. Selecteer **Deze eigenaar verwijderen** in het bevestigingsdialoogvenster:
   
    ![verwijderen bevestigen](./media/create-team-flows/removeowner3.png)
4. De gebruiker of groep die u hebt verwijderd, wordt niet meer vermeld als een eigenaar van de stroom:
   
    ![gebruiker verwijderd](./media/create-team-flows/removeowner4.png)

## <a name="embedded-and-other-connections"></a>Ingesloten en andere verbindingen
De verbinding die worden gebruikt in een stroom, worden onderverdeeld in twee categorieën:

* **Ingesloten verbindingen**: deze verbindingen worden gebruikt in de stroom.
* **Andere verbindingen**: deze verbinding zijn gedefinieerd voor een stroom, maar worden niet in de stroom gebruikt.

Als u een verbinding niet meer gebruikt in een stroom, wordt die verbinding verplaatst naar de lijst **Andere verbindingen** waar de verbinding blijft staan totdat een eigenaar de verbinding opnieuw opneemt in de stroom.

De lijst met verbindingen wordt weergegeven onder de lijst met eigenaren bij de eigenschappen van een stroom:

![ingesloten verbindingen](./media/create-team-flows/embeddedconnections.png)

