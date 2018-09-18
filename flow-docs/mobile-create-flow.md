---
title: Een stroom maken op uw telefoon | Microsoft Docs
description: U kunt een stroom maken op basis van een sjabloon waarmee bijvoorbeeld een pushmelding wordt verzonden wanneer u een e-mail ontvangt dat afkomstig is van een adres dat u opgeeft.
services: ''
suite: flow
documentationcenter: na
author: adiregev
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/18/2016
ms.author: adiregev
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f87320c61427957c02ff75675e4e15b938ac99f4
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2018
ms.locfileid: "44688324"
---
# <a name="create-a-flow-from-your-phone-by-using-microsoft-flow"></a>Een stroom maken op uw telefoon met Microsoft Flow
U kunt op uw telefoon een stroom maken door gebruik te maken van een sjabloon. Sjablonen vindt u door te zoeken in een lijst met services, door te bladeren door categorieën of door trefwoorden op te geven. Volg de stappen in dit onderwerp om een stroom te maken waarmee een pushmelding naar uw telefoon wordt verzonden wanneer u een e-mail van uw manager ontvangt.

Als u niet bekend bent met Microsoft Flow, [kunt u hier een overzicht lezen](getting-started.md).

## <a name="prerequisites"></a>Vereisten
* Een [account voor Microsoft Flow](sign-up-sign-in.md).
* De mobiele app voor Microsoft Flow voor [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) of [Windows Phone](https://aka.ms/flowmobilewindows) op een [ondersteund apparaat](getting-started.md#use-the-mobile-app). Op de afbeeldingen in dit artikel is de iPhone-versie van de app te zien, maar de interface op een Android- of Windows Phone-apparaat ziet er vergelijkbaar uit.
* Als u de sjabloon in dit onderwerp wilt gebruiken, hebt u daarnaast het volgende nodig:
  
  * Office 365-referenties.
  * Pushmeldingen moeten zijn ingeschakeld op uw telefoon.

## <a name="find-a-template"></a>Een sjabloon zoeken
1. Open de mobiele app en tik op **Bladeren** aan de onderkant van het scherm.
   
    ![Pictogram Bladeren](./media/mobile-create-flow/browse-icon.png)
   
    Ga op een van de volgende manieren te werk om een sjabloon te zoeken:
   
   * Geef een trefwoord op in het zoekvak boven in het scherm.
   * Tik op een optie in de lijst met services.
   * Schuif omlaag om de verschillende categorieën weer te geven en tik op een sjabloon in een categorie.
     
       ![Tabblad Bladeren](./media/mobile-create-flow/browse-tab.png)
     
     Voor deze zelfstudie opent u de sjabloon waarmee een pushmelding wordt verzonden wanneer u e-mail van uw manager ontvangt.
2. Tik in de lijst met services op **Alles weergeven**.
   
    ![Lijst met services weergeven](./media/mobile-create-flow/list-services.png)
3. Tik op het pictogram voor **Pushmelding**.
   
    ![Pushmeldingen](./media/mobile-create-flow/push-notifications.png)
4. Typ **e-mail** in de zoekbalk en tik op de sjabloon om een pushmelding te verzenden wanneer u een e-mail van uw manager ontvangt.
   
    ![Sjabloon kiezen](./media/mobile-create-flow/choose-template.png)
5. Tik in het scherm met details over de sjabloon die u hebt geselecteerd op **Deze sjabloon gebruiken**.
   
    ![Sjabloon bevestigen](./media/mobile-create-flow/confirm-template.png)

## <a name="finish-the-flow"></a>De stroom voltooien
1. Tik op **Aanmelden** als u hierom wordt gevraagd en geef uw referenties voor Office 365 Outlook, Office 365-gebruikers of beide op.
   
    ![Aanmelden bij Office 365](./media/mobile-create-flow/office-signin.png)
   
    U kunt de dezelfde verbindingen gebruiken wanneer u andere stromen maakt.
2. Tik in de rechterbovenhoek op **Volgende**.
   
    ![Op Volgende tikken](./media/mobile-create-flow/next.png)
   
    In het volgende scherm worden de triggergebeurtenis en alle resulterende acties weergegeven.
   
    ![Triggergebeurtenis en acties](./media/mobile-create-flow/flow-structure.png)
   
    Voor deze sjabloon wordt de stroom getriggerd door een nieuwe e-mail, waarmee uw gegevens worden opgehaald (waaronder het adres van uw manager) en wordt een pushmelding naar u verzonden wanneer u een e-mail van dat adres ontvangt. Sommige sjablonen moeten worden aangepast voor een juiste werking, maar deze sjabloon niet.
3. Typ eventueel een andere naam voor de stroom boven in het scherm.
   
    ![De naam van de stroom wijzigen](./media/mobile-create-flow/rename-flow.png)
4. Tik in de rechterbovenhoek op **Maken**.
   
    ![Stroom maken](./media/mobile-create-flow/create-flow.png)
   
    De stroom is gemaakt en met de stroom wordt gecontroleerd op e-mail van uw manager totdat u de stroom onderbreekt of verwijdert.

## <a name="next-steps"></a>Volgende stappen
* [De stroomactiviteit controleren](mobile-monitor-activity.md).
* [Uw stromen beheren](mobile-manage-flows.md).

