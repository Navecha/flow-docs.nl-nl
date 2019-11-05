---
title: Overzicht van oplossingen die geschikt zijn voor de oplossing | Microsoft Docs
description: Meer informatie over de voor delen van het maken van stromen in oplossingen.
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
ms.openlocfilehash: 19eb7d051c4d1438ec45305620e369b5499252a0
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548568"
---
# <a name="overview"></a>Krijgt
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Wanneer u uw stromen in een [oplossing](https://docs.microsoft.com/powerapps/maker/common-data-service/solutions-overview)host, worden ze draagbaar, waardoor het lastig is om ze en alle onderdelen van de ene omgeving naar de andere te verplaatsen. Een typische use-case is voor een onafhankelijke software leverancier (ISV) voor het ontwikkelen van stromen in een sandbox-omgeving en het verplaatsen van die stromen naar een test omgeving. Na het testen verplaatst de ISV de stromen naar een productie omgeving voor clients die deze stromen aanschaffen. Dit proces is veel eenvoudiger wanneer u uw stromen in oplossingen maakt, en vervolgens de oplossingen en hun inhoud verplaatst.

Stromen die u in een oplossing maakt, worden op *oplossingen gebaseerde* stromen genoemd. U kunt meerdere stromen toevoegen in één oplossing.

> [!NOTE] 
> U kunt niet-compatibele stromen (stromen die niet in een oplossing zijn gemaakt) verplaatsen naar een oplossing.

## <a name="prerequisites"></a>Vereisten

U moet de volgende onderdelen hebben voor het maken van oplossingen en voor oplossingen geschikte stromen:

- [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)
- Een omgeving met versie 9.1.0.267 of hoger.

  Als u uw versie wilt controleren, gaat u naar [Microsoft flow-beheer centrum](https://admin.flow.microsoft.com), selecteert u **omgevingen**, selecteert u de omgeving waarin u geïnteresseerd bent en selecteert u vervolgens het tabblad **Details** .

## <a name="create-a-solution"></a>Een oplossing maken

Volg deze stappen om een oplossing te maken:

1. Meld u aan bij [Microsoft flow](https://flow.microsoft.com).
1. Selecteer **oplossingen** in de navigatie balk.

   ![](./media/overview-solution-flows/select-solutions-from-left-nav.png)

1. Selecteer **+ nieuwe oplossing**.

   ![](./media/overview-solution-flows/select-new-solution.png)

1. Geef alle vereiste informatie op voor uw nieuwe oplossing, inclusief **weergave naam**, **Uitgever**, **versie**en **naam**. Het is ook een goed idee om een beschrijving van uw oplossing te geven.

   ![](./media/overview-solution-flows/new-solution.png)

1. Selecteer **opslaan en sluiten** in het menu bovenaan.

   ![](./media/overview-solution-flows/save-and-close-solution.png)

   Uw nieuwe oplossing kan er als volgt uitzien:

   ![](./media/overview-solution-flows/new-solution-created.png)

   > [!TIP]
   > Selecteer **oplossingen** om de lijst met oplossingen te vernieuwen als uw nieuwe oplossing niet wordt weer gegeven.

## <a name="learn-more"></a>Meer informatie

- [Een stroom in een oplossing maken](./create-flow-solution.md)
- [Een oplossing exporteren](./export-flow-solution.md)
- [Een oplossing importeren](./import-flow-solution.md)
- [Een stroom die geschikt is voor oplossingen bewerken](./edit-solution-aware-flow.md)
- [Een oplossings bewuste stroom verwijderen](./remove-solution-aware-flow.md)
