---
title: Informatie over hoe u oplossingsbewuste stromen maakt | Microsoft Docs
description: Informatie over hoe u oplossingsbewuste stromen maakt
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
ms.openlocfilehash: cbc6e3a8ffe50eb7ad27e80eba044957647a1da3
ms.sourcegitcommit: b41b45f6fa29a22e9a9a4d3c726a2321b2ff3cbf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/05/2018
ms.locfileid: "51025606"
---
# <a name="create-a-flow-in-a-solution"></a>Een stroom maken in een oplossing

Stromen die u in een oplossing maakt, worden ook wel *oplossingsbewuste* stromen genoemd. Volg deze stappen om een oplossingsbewuste stroom te maken.

## <a name="prerequisites"></a>Vereisten

U hebt ten minste één oplossing nodig om een oplossingsbewuste stroom te maken.

## <a name="create-the-flow"></a>De stroom maken 

1. Meld u aan bij [Microsoft Flow](https://flow.microsoft.com).
1. Selecteer **Oplossingen** in de navigatiebalk.

   ![](./media/create-flow-solution/select-solutions-from-left-nav.png)

1. Selecteer de oplossing waarin u uw stroom maakt.

   ![](./media/create-flow-solution/new-solution-created.png)

1. Selecteer **+ Nieuw** en selecteer vervolgens **Stroom**.

   ![](./media/create-flow-solution/select-new-flow.png)

   Microsoft Flow wordt geopend.

1. Gebruik de beschikbare connectors en triggers om uw stroom te bouwen.

   In dit voorbeeld bouwt u een eenvoudige stroom die een melding verstuurt wanneer er een e-mail in uw postvak binnenkomt.
1. Zoek naar en selecteer **Office 365 Outlook**.
1. Selecteer de trigger **Wanneer er een nieuwe e-mail binnenkomt**.
1. Selecteer **+ Nieuwe stap**.
1. Selecteer de actie **Ik wil een mobiele melding ontvangen**.
1. Voeg de dynamische token **Onderwerp** toe aan het veld **Tekst** in het venster **Ik wil een mobiele melding ontvangen**.
1. Geef de stroom een naam en sla de stroom vervolgens op.

   De stroom zou er als volgt uit moeten zien:

   ![](./media/create-flow-solution/new-email-notification-flow.png)
   
1. Selecteer **Oplossingen** om uw stroom in de oplossing te bekijken:

   ![](./media/create-flow-solution/new-flow-inside-solution.png)

## <a name="learn-more"></a>Meer informatie

* [Een oplossing maken](./overview-solution-flows.md)
* [Een oplossing exporteren](./export-flow-solution.md)
* [Een oplossing importeren](./import-flow-solution.md)
* [Een oplossingsbewuste stroom bewerken](./edit-solution-aware-flow.md)
* [Een oplossingsbewuste stroom verwijderen](./remove-solution-aware-flow.md)
