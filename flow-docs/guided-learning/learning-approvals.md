---
title: Goedkeuringsaanvragen met Microsoft Flow | Microsoft Docs
description: Informatie over hoe u een goedkeuringswerkstroom kunt beheren met Microsoft Flow.
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
featuredvideoid: o-pgEBW3fOI
courseduration: 14m
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2016
ms.author: deonhe
ms.openlocfilehash: 049b713ed653ab5555e5f48f63e46cce7f3207ee
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/15/2017
---
# <a name="approval-requests"></a>Goedkeuringsaanvragen
Naast het **ontvangen van meldingen**, het **kopiëren van bestanden** en het **verzamelen van gegevens** kunt u Microsoft Flow ook gebruiken voor het **stroomlijnen van uw goedkeuringsprocessen**.

## <a name="vacation-scenario"></a>Vakantiescenario
Stel, u bent een **manager** en vraagt uw teamleden hun **vakantieaanvragen** in te dienen via een **SharePoint-lijst**. U wilt een **goedkeuringsproces** rond deze lijst met items maken, zodat nieuwe vakantieaanvragen **snel kunnen worden verwerkt** en de aanvrager **automatisch een melding ontvangt**.  

## <a name="sharepoint-and-microsoft-flow"></a>SharePoint en Microsoft Flow
**SharePoint** heeft Microsoft Flow **ingebouwd**.  Van uw **SharePoint-lijst** klikt u op de vervolgkeuzelijst **Stroom** en vervolgens op **Een stroom maken**.

![Stroom maken](./media/learning-approvals/new-flow.png)   

In het **menu aan de rechterkant** zoekt u een **sjabloon** zoals hier.

![Goedkeuringssjabloon](./media/learning-approvals/approval-template.png)

## <a name="using-the-template"></a>De sjabloon gebruiken
De **SharePoint**-trigger in de sjabloon wordt **vooraf ingevuld** met de gegevens uit uw lijst.  Het enige wat u hoeft te doen, is een **e-mailadres** toevoegen voor de **goedkeurder**.  Het **oorspronkelijke SharePoint-item blijft ongewijzigd**.  Hiertoe voegt u de actie **SharePoint - Item bijwerken** toe.

![Item bijwerken](./media/learning-approvals/update-item.png)

Hoe zit het met de vertakking **indien geen** van *emailScope verzenden*?  Standaard gebeurt er niets.  U kunt eventueel een actie toevoegen zodat de auteur van de aanvraag een bericht ontvangt dat de aanvraag is afgewezen. 

![Indien geen](./media/learning-approvals/if-no.png)

## <a name="next-lesson"></a>Volgende les
Laten we bekijken wat u in deze sectie hebt geleerd.

