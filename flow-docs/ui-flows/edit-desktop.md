---
title: Meer informatie over het bewerken van de gebruikers interface van het bureau blad | Microsoft Docs
description: Meer informatie over het bewerken van de gebruikers interface van het bureau blad.
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
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: d5b7e186ae5c644f00f57946fff5ef3e946ba2ba
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589822"
---
# <a name="edit-desktop-ui-flows"></a>UI-stromen van bureau blad bewerken

[Dit onderwerp bevat voorlopige documentatie en kan worden gewijzigd.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Desktop-UI-flows automatiseert Windows Desktop-toepassingen. Raadpleeg de [bekende problemen](create-desktop.md#known-issues-and-solutions) voor meer informatie over problemen die u kunt uitvoeren in, tijdelijke oplossingen voor deze problemen en scenario's die niet worden ondersteund in deze preview-versie.

## <a name="prerequisites"></a>Vereisten
Een UI-stroom op het bureau blad. [Maak nu een gebruikersinterface stroom op het bureau blad](create-desktop.md#create-and-test-desktop-ui-flows) als u er geen wilt bewerken.

## <a name="edit-actions"></a>Acties bewerken

![Acties bewerken](../media/edit-desktop/edit-actions.png "Acties bewerken")

U kunt uw opname bewerken in:

-   Wijzig de waarde voor acties die hiermee worden ondersteund.
-   Een stap verwijderen.
-   De volledige opname verwijderen.
-   Wijzig de volg orde van acties met slepen en neerzetten. Wees voorzichtig met dit omdat het mogelijk de consistentie van de opname kan verstoren.

Geavanceerde para meters kunt u wijzigen:

-  De vertraging na de actie wordt uitgevoerd. U kunt bijvoorbeeld een vertraging van één seconde toevoegen door PT0S te wijzigen in PT1S. Dit kan handig zijn wanneer de doel toepassing een trage reactie tijd heeft die niet is voltooid voor de volgende stap van de gebruikers interface stroom.
-   De [kiezer](edit-desktop.md#set-the-selector) voor het element van de gebruikers interface van de doel groep.

## <a name="add-a-recording"></a>Een opname toevoegen

Mogelijk wilt u uw gebruikers interface-flow vastleggen in meerdere sessies. Nadat u de eerste opname hebt voltooid, kunt u als volgt door gaan:

1. Meld u aan bij [Automatische stroom](https://flow.microsoft.com).
1. Selecteer **mijn stromen** > **UI-stromen (preview-versie)** .
1. Selecteer de gebruikers interface stroom die u wilt bewerken.
   ![](../media/edit-desktop/select-ui-flow.png)
1. Selecteer **bewerken**. 
1. Selecteer **nieuwe stap**.

   ![Nieuwe stap](../media/edit-desktop/new-step.png "Nieuwe stap")

1. Selecteer de **record-app** in de lijst met acties.

   ![App opnemen](../media/edit-desktop/select-record-ui-actions.png "App opnemen")

1. Selecteer **starten recorder**.

   ![Start recorder selecteren](../media/create-windows-ui-flow/select-launch-recorder.png "Start recorder selecteren")

   Het besturings element recorder wordt boven aan het scherm weer gegeven.

   ![De recorder-Control](../media/create-windows-ui-flow/recorder-control.png "De recorder-Control")

1. Start de app die u wilt opnemen.

     >[!TIP]
     >Wanneer de muis aanwijzer over besturings elementen in de app wordt geleid, ziet u dat elk besturings element in een blauw kader wordt gemarkeerd. Wacht altijd op het blauwe hooglicht voordat u een besturings element selecteert.
     >
     >Als de blauwe markering niet rond het element wordt weer gegeven, wordt deze mogelijk niet juist opgenomen.

1. Selecteer **record** in het besturings element voor recorder.

1. Voer de stappen uit in de gebruikers interface van de app die u wilt opnemen en selecteer vervolgens **gereed** in het besturings element voor recorder.
1. Selecteer **Opslaan**en test vervolgens de gebruikers interface stroom.

## <a name="add-a-manual-action"></a>Een hand matige actie toevoegen

Zodra u een toepassing met ten minste één actie hebt geregistreerd, kunt u hand matig een van de volgende acties voor die toepassing toevoegen.

| **Optreden**          | **Heffen**                                                       |
|---------------------|-------------------------------------------------------------------|
| Toepassing sluiten   |                                                                   |
| Met de rechter muisknop         |                                                                   |
| Sleutels verzenden           | Sleutels en toetscombinaties verzenden, zoals CTRL + C.                             |
| Klik met de linkermuisknop          |                                                                   |
| Tekst ophalen            | Lees de tekst van een element van de gebruikers interface en gebruik deze als uitvoer. |
| Tekst invoeren          |                                                                   |
| Element ophalen ingeschakeld | Controleer of een element in de gebruikers interface is ingeschakeld of uitgeschakeld.         |
| Element wissen       | Wis de waarde in een bewerkbaar element van de gebruikers interface.             |
| Wachten op enkele seconden    | Wacht totdat u verdergaat met de volgende stap.                           |

Volg deze stappen om een hand matige actie toe te voegen:

1. Meld u aan bij [Automatische stroom](https://flow.microsoft.com).
1. Selecteer **mijn stromen** > **UI-stromen (preview-versie)** .
1. Selecteer de gebruikers interface stroom die u wilt bewerken.
   ![](../media/edit-desktop/select-ui-flow.png)
1. Selecteer **bewerken**. 
1. Selecteer de registratie kaart die de stappen bevat waaraan u een nieuwe stap wilt toevoegen.
   De kaart wordt uitgebreid en de opgenomen stappen worden weer gegeven.

   ![Opname kaart selecteren](../media/edit-desktop/manual-select-recording-card.png)

1. Selecteer **een actie toevoegen** op de record kaart, net onder de laatste vastgelegde stap.
   U ziet de lijst met hand matige acties die eerder in de procedure zijn beschreven. 

1. Selecteer de actie die u wilt toevoegen. Hier heb ik het **element ophalen ingeschakeld**, maar u kunt elke actie selecteren die zinvol is voor uw scenario.

   ![Selecteer een actie om het PNG-bestand toe te voegen.](../media/edit-desktop/select-action-to-add.png)

Zodra de actie is toegevoegd, moet u de **selector** instellen in de geavanceerde opties van de actie.

![Geavanceerde opties voor actie](../media/edit-desktop/action-advanced-options.png "Geavanceerde opties voor actie")

### <a name="set-the-selector"></a>De selector instellen

De selector identificeert het element van de gebruikers interface waarop de actie wordt uitgevoerd tijdens het afspelen. U wordt aangeraden deze informatie te kopiëren/plakken van een afzonderlijke stap die gericht is op hetzelfde element van de gebruikers interface, indien mogelijk.

De indeling van de selector is:

```json
{  
   "type":"WinUIA",
   "parameters":{  
      "elementStack":[  

      ],
      "elementXPath":""
   }
}
```

U moet de gegevens opgeven voor de velden **elemementStack** en **elementXPath** van het selector-element.

Hier volgt een voor beeld van hoe het **elemementStack** eruit kan zien.

![Element stack](../media/edit-desktop/elementstack.png "Element stack")

U kunt de **elementXPath** vastleggen met behulp van de [WinAppDriver-gebruikers interface-recorder](https://blogs.windows.com/windowsdeveloper/2018/06/20/introducing-winappdriver-ui-recorder/).

![Hulp programma WAD](../media/edit-desktop/wad-tool.png "Hulp programma WAD")

Verwijder het eerste element (alles vóór/Window) voordat u het resultaat in **elementXPath** van de selector gebruikt.

Test uw gebruikers interface stroom om te bevestigen dat de selector goed werkt.

## <a name="next-steps"></a>Volgende stappen

- Meer informatie over [het uitvoeren van de gebruikers interface stroom](run-ui-flow.md) die u zojuist hebt bewerkt.

- Als u meer wilt doen met UI-stromen, kunt u ook de gebruikers interface stromen uitproberen met [invoer-en uitvoer](inputs-outputs-web.md) parameters.

