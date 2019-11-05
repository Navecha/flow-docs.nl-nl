---
title: Meer informatie over het maken van oplossingen met compatibele stromen | Microsoft Docs
description: Meer informatie over het maken van op oplossingen geschikte stromen.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/05/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 6cbd1ee543cfe5f54b61486eefbacbd5bb837f33
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546470"
---
# <a name="create-a-flow-in-a-solution"></a>Een stroom in een oplossing maken
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Stromen die u in een oplossing maakt, worden niet *-compatibele* stromen genoemd. Volg deze stappen om een oplossings bewuste stroom te maken.

## <a name="prerequisites"></a>Vereisten

U moet ten minste één oplossing hebben voordat u een oplossings bewuste stroom kunt maken.

## <a name="create-the-flow"></a>De stroom maken 

1. Meld u aan bij [Microsoft flow](https://flow.microsoft.com).
1. Selecteer **oplossingen** in de navigatie balk.

   ![](./media/create-flow-solution/select-solutions-from-left-nav.png)

1. Selecteer de oplossing waarin u de stroom wilt maken.

   ![](./media/create-flow-solution/new-solution-created.png)

1. Selecteer **+ Nieuw**en selecteer vervolgens **stroom**.

   ![](./media/create-flow-solution/select-new-flow.png)

   Microsoft Flow wordt geopend.

1. Gebruik de beschik bare connectors en triggers om uw stroom te bouwen.

   In dit voor beeld maken we een eenvoudige stroom waarmee een melding wordt verzonden wanneer een e-mail bericht in uw postvak in binnenkomt.
1. Zoek en selecteer **Office 365 Outlook**.
1. Selecteer de trigger **Wanneer een nieuwe e-mail binnenkomt** .
1. Selecteer **+ nieuwe stap**.
1. Selecteer de actie **Ik wil een mobiel bericht verzenden** .
1. Voeg het **onderwerp** dynamische token toe aan het **tekst** veld van het vak **Ik wil een mobiel bericht verzenden** .
1. Geef uw stroom een naam en sla de stroom op.

   Uw stroom moet er als volgt uitzien:

   ![](./media/create-flow-solution/new-email-notification-flow.png)
   
1. Selecteer **oplossingen** om uw stroom in de oplossing te bekijken:

   ![](./media/create-flow-solution/new-flow-inside-solution.png)

## <a name="learn-more"></a>Meer informatie

* [Een oplossing maken](./overview-solution-flows.md)
* [Een oplossing exporteren](./export-flow-solution.md)
* [Een oplossing importeren](./import-flow-solution.md)
* [Een stroom die geschikt is voor oplossingen bewerken](./edit-solution-aware-flow.md)
* [Een oplossings bewuste stroom verwijderen](./remove-solution-aware-flow.md)
