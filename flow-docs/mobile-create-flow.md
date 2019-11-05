---
title: Een stroom maken op uw telefoon | Microsoft Docs
description: Een stroom maken op basis van een sjabloon die bijvoorbeeld een push melding verzendt wanneer u een e-mail ontvangt van een adres dat u opgeeft
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
ms.openlocfilehash: 095b3a7f6565afff0a944bb08aee8f3a06ea114b
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73549043"
---
# <a name="create-a-flow-from-your-phone-by-using-microsoft-flow"></a>Een stroom maken op uw telefoon met behulp van Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Maak een stroom op basis van uw telefoon met behulp van een sjabloon, die u kunt vinden door te zoeken in een lijst met Services, door te bladeren naar categorieën of tref woorden op te geven. Volg de stappen in dit onderwerp om een stroom te maken waarmee een push melding naar uw telefoon wordt verzonden wanneer u e-mail van uw manager ontvangt.

Als u niet bekend bent met Microsoft Flow, kunt u [een overzicht krijgen](getting-started.md).

## <a name="prerequisites"></a>Vereisten
* Een [account voor Microsoft flow](sign-up-sign-in.md).
* De mobiele app Microsoft Flow voor [Android](https://aka.ms/flowmobiledocsandroid), [IOS](https://aka.ms/flowmobiledocsios)of [Windows Phone](https://aka.ms/flowmobilewindows) op een [ondersteund apparaat](getting-started.md#use-the-mobile-app). De afbeeldingen in dit onderwerp zijn gebaseerd op de iPhone-versie van de app, maar de interface op een Android-apparaat of Windows Phone is vergelijkbaar.
* Als u de sjabloon wilt gebruiken die in dit onderwerp wordt getoond, hebt u ook het volgende nodig:
  
  * Office 365-referenties.
  * Push meldingen zijn ingeschakeld op uw telefoon.

## <a name="find-a-template"></a>Een sjabloon zoeken
1. Open de mobiele app en tik onder aan het scherm op **Bladeren** .
   
    ![Blader pictogram](./media/mobile-create-flow/browse-icon.png)
   
    U kunt op een van de volgende manieren een sjabloon vinden:
   
   * Geef een tref woord op in het zoekvak boven aan het scherm.
   * Tik op een optie in de lijst met Services.
   * Schuif omlaag om een aantal categorieën weer te geven en tik vervolgens op een sjabloon in een categorie.
     
       ![Tabblad Bladeren](./media/mobile-create-flow/browse-tab.png)
     
     Voor deze zelf studie opent u de sjabloon waarmee een push melding wordt verzonden wanneer u e-mail van uw manager ontvangt.
2. Tik in de lijst met Services op **alles weer geven**.
   
    ![Lijst met services weer geven](./media/mobile-create-flow/list-services.png)
3. Tik op het pictogram voor **Push meldingen**.
   
    ![Push meldingen](./media/mobile-create-flow/push-notifications.png)
4. Typ in de zoek balk **e-mail**en tik op de sjabloon om een push melding te verzenden wanneer u een bericht van uw manager ontvangt.
   
    ![Sjabloon kiezen](./media/mobile-create-flow/choose-template.png)
5. Tik in het scherm met details over de sjabloon die u hebt geselecteerd, op **deze sjabloon gebruiken**.
   
    ![Sjabloon bevestigen](./media/mobile-create-flow/confirm-template.png)

## <a name="finish-the-flow"></a>De stroom volt ooien
1. Als u hierom wordt gevraagd, tikt u op **Aanmelden**en geeft u uw referenties op voor Office 365 Outlook, Office 365-gebruikers of beide.
   
    ![Aanmelden bij Office 365](./media/mobile-create-flow/office-signin.png)
   
    U kunt dezelfde verbindingen gebruiken wanneer u andere stromen maakt.
2. Tik in de rechter bovenhoek op **volgende**.
   
    ![Tik op volgende](./media/mobile-create-flow/next.png)
   
    In het volgende scherm worden de trigger gebeurtenis en alle resulterende acties weer gegeven.
   
    ![Trigger gebeurtenis en acties](./media/mobile-create-flow/flow-structure.png)
   
    Voor deze sjabloon wordt de stroom door nieuwe e-mail geactiveerd, waarmee uw gegevens worden opgehaald (met inbegrip van het adres van uw manager) en u een push melding ontvangt wanneer u e-mail van dat adres ontvangt. Sommige sjablonen moeten zodanig worden aangepast dat deze goed werken, maar deze sjabloon niet.
3. Beschrijving Typ een andere naam voor de stroom aan de bovenkant van het scherm.
   
    ![De naam van de stroom wijzigen](./media/mobile-create-flow/rename-flow.png)
4. Tik in de rechter bovenhoek op **maken**.
   
    ![stroom maken](./media/mobile-create-flow/create-flow.png)
   
    Uw stroom wordt gemaakt en er wordt gecontroleerd op e-mail van uw manager totdat u de stroom onderbreekt of verwijdert.

## <a name="next-steps"></a>Volgende stappen
* [Controleer uw stroom activiteit](mobile-monitor-activity.md).
* [Uw stromen beheren](mobile-manage-flows.md).

