---
title: Stromen maken vanuit het start paneel van OneDrive voor bedrijven | Microsoft Docs
description: Maak stromen in het start paneel van OneDrive voor bedrijven.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/25/2019
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: d7ed30741fcc85fea87f5be2d76a8150a0c42100
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548582"
---
# <a name="create-flows-from-the-onedrive-for-business-launch-panel"></a>Stromen maken vanuit het start paneel van OneDrive voor bedrijven
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Vergelijkbaar met het [Start paneel van Microsoft flow in share point](https://flow.microsoft.com/blog/introducing-flow-launch-panel-in-sharepoint-lists-and-libraries/), kunt u stromen uitvoeren op specifieke bestanden in OneDrive voor bedrijven. 

Met deze functie kan de persoon die de stroom uitvoert, hun eigen referenties gebruiken. Dit is met name van toepassing op stromen die zijn gemaakt door een IT-afdeling. 

Gebruikers kunnen ook een prompt ontvangen voor runtime-invoer, zoals **goed keurder** of **bericht**, dat tekst, bestand, e-mail adres, Booleaanse waarde of getal kan zijn.

In dit scenario maken we een eenvoudige stroom die gebruikmaakt van een van de vele [sjablonen in OneDrive voor bedrijven](https://flow.microsoft.com/search/?q=OneDrive) om goed keuring van een bestand door de Manager van de aanvrager aan te vragen.

## <a name="create-a-flow-that-requests-manager-approval-for-a-file-in-onedrive-for-business"></a>Een stroom maken die goed keuring door Manager aanvraagt voor een bestand in OneDrive voor bedrijven

1. Meld u aan bij OneDrive voor bedrijven.
1. Zoek en selecteer het bestand waarin u de stroom wilt maken.
1. Selecteer de koppeling **acties weer geven** (drie punten).
1. Selecteer **flow** > **een stroom te maken**.

     ![stroom maken](./media/onedrive-launch-panel/create-flow.png) 

1. Selecteer een van de sjablonen.

    In dit voor beeld selecteert u de **goed keuring van mijn manager aanvragen voor de geselecteerde bestands** sjabloon.

     >[!TIP]
     >Meld u aan bij alle connectors die aanvragen dat u zich aanmeldt.

1. Selecteer **door gaan**.
1. Breng de gewenste wijzigingen aan in de sjabloon en sla de stroom op met een naam die u gemakkelijk kunt onthouden.

## <a name="run-the-flow"></a>De stroom uitvoeren

1. Meld u aan bij OneDrive voor bedrijven.
1. Zoek en selecteer het bestand waarop de goed keuring van de aanvraag Manager wordt goedgekeurd.
1. Selecteer de koppeling **acties weer geven** (drie punten).
1. Selecteer **stroom**. U ziet de stroom die u eerder hebt gemaakt.
1. Selecteer de stroom die u eerder hebt gemaakt.

     ![Uw stroom uitvoeren](./media/onedrive-launch-panel/run-flow.png)


>[!TIP]
>In deze walkthrough ziet u hoe u een stroom maakt op basis van een sjabloon, maar u kunt ook een stroom van leeg maken om een van de honderden connectors te gebruiken die beschikbaar zijn in Microsoft Flow.

## <a name="learn-more"></a>Meer informatie

- [Aan de slag met Microsoft Flow](getting-started.md) 
- [Stromen met meerdere stappen maken](multi-step-logic-flow.md)
