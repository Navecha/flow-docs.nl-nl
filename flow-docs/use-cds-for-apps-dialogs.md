---
title: Common Data Service-dialoog vensters gebruiken voor begeleide processen (afgeschaft) | MicrosoftDocs
description: Dialoog vensters zijn de synchrone of interactieve processen die informatie verzamelen en verwerken door gebruik te maken van Step-by-Step-scripts om gebruikers via een proces door te sturen
ms.custom: ''
ms.date: 10/31/2017
ms.reviewer: ''
ms.topic: article
ms.service: flow
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
ms.openlocfilehash: 05f0b9b72f2f9e2d7f02356ec40eeb520214a0cb
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548744"
---
# <a name="use-common-data-service-dialogs-for-guided-processes-deprecated"></a>Common Data Service-dialoog vensters gebruiken voor begeleide processen (afgeschaft)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

[Dialoog vensters zijn afgeschaft](/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated). U dient dialoog vensters te vervangen door bedrijfs proces stromen of canvas-apps. Meer informatie: [dialoog vensters vervangen met bedrijfs proces stromen of canvas-apps](replace-dialogs.md) 

Dialoog vensters zijn de synchrone of interactieve processen in Common Data Service die informatie verzamelen en verwerken door gebruik te maken van Step-by-Step-scripts om gebruikers via een proces te leiden. U kunt bijvoorbeeld dialoog vensters maken die fungeren als richt lijn voor uw service vertegenwoordigers voor het oplossen van problemen en het aansturen van aanvragen. Op dezelfde manier kunt u dialoog vensters maken voor het standaardiseren van verkoop processen, zoals opportuniteits kwalificatie en lead Score.

## <a name="differences-between-workflows-and-dialogs"></a>Verschillen tussen werk stromen en dialoog vensters

De volgende tabel bevat informatie over de verschillen tussen Common Data Service werk stromen en dialoog vensters.  


| stroom     |    Dialoog vensters      |
|---------------|--------------|
|                                                                                                  Kan worden gestart door een gebruiker of kan worden geautomatiseerd.                                                                                                   |                                                                                          Moet door een gebruiker worden gestart.                                                                                          |
|                                  Zijn asynchrone of realtime processen en vereisen niet dat gebruikers invoer wordt uitgevoerd om te worden voltooid. Asynchrone processen worden op de achtergrond uitgevoerd terwijl realtime processen direct worden uitgevoerd.                                   | Zijn realtime processen waarvoor gebruikers invoer moet worden uitgevoerd om te worden voltooid. Wanneer u deze processen uitvoert, wordt een wizard-achtige interface weer gegeven, zodat u de juiste selecties kunt maken om de processen uit te voeren. |
|                                                    De entiteit die de details van een actieve asynchrone werk stroom opslaat, wordt `AsyncOperation` terwijl een `Process` wordt gebruikt voor een realtime werk stroom.                                                     |                                                       De entiteit die gegevens opslaat die zijn gegenereerd door een actief dialoog venster is de entiteit `ProcessSession`.                                                       |
|                  Triggers worden ondersteund voor werk stromen. Zie [ondersteunde typen, triggers en entiteiten voor processen](/dynamics365/customer-engagement/developer/supported-types-triggers-entities-actions-processes)voor een lijst met ondersteunde triggers.                   |                                                                                   Triggers worden niet ondersteund voor dialoog vensters.                                                                                    |
  
### <a name="see-also"></a>Zie ook
[Dialoog vensters vervangen door bedrijfs proces stromen of canvas-apps](replace-dialogs.md)
