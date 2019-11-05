---
title: AVG voor micro soft-accounts (MSA) voor het Microsoft Flow van gegevens aanvragen Microsoft Docs
description: Meer informatie over het gebruik van Microsoft Flow om te reageren op AVG betrokkenen-aanvragen voor de detectie van gegevens voor micro soft-accounts.
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
ms.date: 5/16/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 06e88aa215089145f86f9027a6ad75b73c7cf627
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548100"
---
# <a name="respond-to-gdpr-data-subject-discovery-requests"></a>Reageren op aanvragen voor detectie van AVG-gegevens 
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

De eerste stap bij het reageren op een DSR-aanvraag is het vinden van de persoons gegevens die het onderwerp van de aanvraag zijn.
Hier volgt een samen vatting van de Microsoft Flow resources die persoonlijke gegevens bevatten voor een gebruiker die zich verifieert met hun micro soft-account (MSA).

|Resource|Doel|
|-----|-----|
|uitvoerings geschiedenis|Biedt de geschiedenis van de uitvoering van elke stroom gedurende de afgelopen 28 dagen. Deze gegevens omvatten de begin tijd, eind tijd, status en alle invoer-en uitvoer gegevens voor elke stroom uitvoering. Meer informatie over de geschiedenis van de uitvoering van de [stroom](https://flow.microsoft.com/blog/download-history-recurrence/).|
|Activiteitsfeed| Voorziet in een samen vatting van de activiteiten van elke stroom, met inbegrip van de uitvoerings status, fouten en meldingen.|
|Terugloop|De werk stroom logica voor een [stroom](https://docs.microsoft.com/flow/get-started-logic-flow).|
|Inbel|Wordt gebruikt door connectors en staat connectiviteit met Api's, systemen, data bases en meer toe. Meer informatie over [verbindingen](add-manage-connections.md).|

