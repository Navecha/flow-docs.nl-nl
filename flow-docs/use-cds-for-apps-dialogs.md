---
title: Dialoogvensters van Common Data Service gebruiken voor begeleide processen (afgeschaft) | Microsoft Docs
description: Dialoogvensters zijn de synchrone of interactieve processen die gegevens verzamelen en verwerken met behulp van stapsgewijze scripts om gebruikers door een proces te leiden
ms.custom: ''
ms.date: 10/31/2017
ms.reviewer: ''
ms.topic: article
ms.assetid: d17f8ae2-854b-4f67-a115-5a03d4f0b8ce
caps.latest.revision: 25
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 90bdbc0ecf9b778ec6da3e4cac2b32b44e361fb0
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2019
ms.locfileid: "64463664"
---
# <a name="use-common-data-service-dialogs-for-guided-processes-deprecated"></a>Dialoogvensters van Common Data Service gebruiken voor begeleide processen (afgeschaft)

[Dialoogvensters zijn afgeschaft](/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated). U moet dialoogvensters vervangen door bedrijfsprocesstromen of canvas-apps Meer informatie: [Dialoogvensters vervangen door bedrijfsprocesstromen of canvas-apps](replace-dialogs.md) 

Dialoogvensters zijn de synchrone of interactieve processen in Common Data Service die gegevens verzamelen en verwerken met behulp van stapsgewijze scripts om gebruikers door een proces te leiden. U kunt bijvoorbeeld dialoogvensters maken als richtlijn voor servicemedewerkers om incidenten op te lossen of te escaleren. Een vergelijkbare toepassing is het maken van dialoogvensters voor het standaardiseren van verkoopprocessen, zoals de kwalificatie van verkoopkansen en het beoordelen van potentiële klanten. Zie voor meer informatie [Use dialogs for guided processes](/dynamics365/customer-engagement/developer/use-dialogs-guided-processes) (Dialoogvensters gebruiken voor begeleide processen) in de handleiding voor ontwikkelaars van Dynamics 365 Customer Engagement.

## <a name="differences-between-workflows-and-dialogs"></a>Verschillen tussen werkstromen en dialoogvensters

De volgende tabel bevat informatie over de verschillen tussen werkstromen en dialoogvensters van Common Data Service.  


| Werkstromen     |    Dialoogvensters      |
|---------------|--------------|
|                                                                                                  Kunnen worden gestart door een gebruiker of automatisch.                                                                                                   |                                                                                          Moeten worden gestart door een gebruiker.                                                                                          |
|                                  Zijn asynchrone of realtime-processen die geen invoer van de gebruiker vereisen voor voltooiing. Asynchrone processen worden op de achtergrond uitgevoerd, terwijl realtime-processen onmiddellijk worden uitgevoerd.                                   | Zijn realtime-processen die invoer van de gebruiker vereisen voor voltooiing. Wanneer u deze processen uitvoert, wordt er een interface in de vorm van een wizard gepresenteerd zodat u de gewenste selecties kunt doen om de processen uit te voeren. |
|                                                    De entiteit waarin de details worden opgeslagen van een actieve asynchrone werkstroom is `AsyncOperation`, terwijl er een `Process` wordt gebruikt voor een realtime-werkstroom.                                                     |                                                       De entiteit waarin gegevens worden opgeslagen die worden gegenereerd door een actief dialoogvenster is `ProcessSession`.                                                       |
|                  Triggers worden ondersteund voor werkstromen. Een lijst met ondersteunde triggers vindt u in [Ondersteunde typen, triggers en entiteiten voor processen](/dynamics365/customer-engagement/developer/supported-types-triggers-entities-actions-processes).                   |                                                                                   Triggers worden niet ondersteund voor dialoogvensters.                                                                                    |
  
### <a name="see-also"></a>Zie ook
[Dialoogvensters vervangen door bedrijfsprocesstromen of canvas-apps](replace-dialogs.md)
