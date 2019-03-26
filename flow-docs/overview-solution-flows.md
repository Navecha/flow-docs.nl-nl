---
title: Overzicht van oplossingsbewuste stromen | Microsoft Docs
description: Hier vindt u informatie over de voordelen van stromen in oplossingen maken.
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
ms.openlocfilehash: 8b0e64317b868dc32ede173329fa2f88ed53de76
ms.sourcegitcommit: 24da014ea8db8e59f097c4622d1e2cca9a4d1709
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2019
ms.locfileid: "58352985"
---
# <a name="overview"></a>Overzicht

Wanneer u uw stromen host in een [oplossing](https://docs.microsoft.com/powerapps/maker/common-data-service/solutions-overview), worden de stromen verplaatsbaar, waardoor het geen moeite kost om de oplossingen en alle onderdelen ervan te verplaatsen van één omgeving naar de andere. Een typisch gebruiksscenario is het voorbeeld van een onafhankelijke softwareleverancier (independent software vendor, ISV) die stromen ontwikkeld in een sandbox-omgeving en die stromen verplaatst naar een testomgeving. Nadat het testen is voltooid, verplaatst de ISV de stromen naar een productie-omgeving voor klanten die deze stromen aanschaffen. Dit proces is veel eenvoudiger wanneer u uw stromen in oplossingen maakt en de oplossingen en de inhoud ervan verplaatst.

Stromen die u binnen een oplossing maakt, worden ook wel *oplossingsbewuste* stromen genoemd. U kunt meerdere stromen toevoegen aan één enkele oplossing.

> [!NOTE] 
> Het is niet mogelijk om oplossingsonbewuste stromen (stromen die niet in een oplossing zijn gemaakt) te verplaatsen naar een oplossing.

## <a name="prerequisites"></a>Vereisten

U hebt de volgende onderdelen nodig om oplossingen en oplossingsbewuste stromen te maken:

- [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)
- Een omgeving met versie 9.1.0.267 of nieuwer.

  Als u uw versie wilt controleren, gaat u naar het [Microsoft Flow-beheercentrum](https://admin.flow.microsoft.com), selecteert u **Omgevingen** en de omgeving waarin u bent geïnteresseerd en vervolgens selecteert u het tabblad **Details**.

## <a name="create-a-solution"></a>Een oplossing maken

Volg deze stappen om een oplossing te maken:

1. Meld u aan bij [Microsoft Flow](https://flow.microsoft.com).
1. Selecteer **Oplossingen** in de navigatiebalk.

   ![](./media/overview-solution-flows/select-solutions-from-left-nav.png)

1. Selecteer **+ Nieuwe oplossing**

   ![](./media/overview-solution-flows/select-new-solution.png)

1. Geef alle voor uw oplossing vereiste informatie op, waaronder een **Weergavenaam**, **Uitgever**, **Versie** en **Naam**. Het is ook een goed idee om een beschrijving van uw oplossing op te geven.

   ![](./media/overview-solution-flows/new-solution.png)

1. Selecteer **Opslaan en sluiten** in het menu bovenaan.

   ![](./media/overview-solution-flows/save-and-close-solution.png)

   De nieuwe oplossing ziet er mogelijk als volgt uit:

   ![](./media/overview-solution-flows/new-solution-created.png)

   > [!TIP]
   > Als uw nieuwe oplossing niet verschijnt, selecteert u **Oplossingen** om de lijst oplossingen te verversen.

## <a name="learn-more"></a>Meer informatie

- [Een stroom maken in een oplossing](./create-flow-solution.md)
- [Een oplossing exporteren](./export-flow-solution.md)
- [Een oplossing importeren](./import-flow-solution.md)
- [Een oplossingsbewuste stroom bewerken](./edit-solution-aware-flow.md)
- [Een oplossingsbewuste stroom verwijderen](./remove-solution-aware-flow.md)
