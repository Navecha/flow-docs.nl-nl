---
title: Meer informatie over verbinding maken met uw gegevens via verbindingen en on-premises gegevens gateways | Microsoft Docs
description: Verbindingen toevoegen of beheren met share point, SQL Server, OneDrive voor bedrijven, Sales Force, Office 365, OneDrive, Dropbox, Twitter, Google Drive en meer
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 1de8602cc573e800d721b6b70222df49cf1577e3
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544754"
---
# <a name="manage-connections-in-microsoft-flow"></a>Verbindingen in Microsoft Flow beheren
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Als u een verbinding maakt in Microsoft Flow, kunt u eenvoudig toegang krijgen tot uw gegevens terwijl u een stroom bouwt. Microsoft Flow bevat veelgebruikte verbindingen, waaronder share point, SQL Server, Office 365, OneDrive voor bedrijven, Sales Force, Excel, Dropbox, Twitter en meer. Verbindingen worden gedeeld met PowerApps, dus wanneer u een verbinding maakt in één product, wordt de verbinding weer gegeven in de andere.

U kunt bijvoorbeeld een verbinding gebruiken om deze taken uit te voeren:

* Een share point-lijst bijwerken.
* Gegevens ophalen uit een Excel-bestand in uw OneDrive voor bedrijven-of Dropbox-account.
* E-mail verzenden in Office 365.
* Een Tweet verzenden.

U kunt in meerdere scenario's een verbinding maken, zoals:

* Een [stroom maken op basis van een sjabloon](get-started-logic-template.md)
* Een [stroom van leeg](get-started-logic-flow.md) maken of een bestaande stroom bijwerken
* Rechtstreeks een verbinding maken op de [Microsoft flow-website][1]

In dit onderwerp wordt beschreven hoe u verbindingen beheert op de [website van Microsoft flow][1].

## <a name="add-a-connection"></a>Een verbinding toevoegen
1. Meld u op de [Microsoft flow-website][1]aan met uw werk-of organisatie account.
2. Selecteer in de rechter bovenhoek het tandwiel pictogram en selecteer vervolgens **verbindingen**.
   
    ![Verbindingen selecteren](./media/add-manage-connections/connections-menu.png)
3. Selecteer **verbinding maken**.
4. Selecteer in de lijst met **beschik bare verbindingen**de verbinding die u wilt instellen, zoals share point.
5. Selecteer de knop **verbinding maken** en voer vervolgens uw referenties in om de verbinding in te stellen.

Wanneer de verbinding is ingesteld, wordt deze weer gegeven in **Mijn verbindingen**.

## <a name="connect-to-your-data-through-an-on-premises-data-gateway"></a>Verbinding maken met uw gegevens via een on-premises gegevens gateway
Vanaf dit schrijven ondersteunen SQL Server en share Point server de on-premises gegevens gateway. Een verbinding maken die gebruikmaakt van een gateway:

1. Volg de stappen eerder in dit onderwerp om een verbinding toe te voegen.
2. Selecteer **SQL Server**in de lijst met **beschik bare verbindingen**en schakel vervolgens het selectie vakje **verbinding maken via on-premises gegevens gateway** in.
   
    ![Gateway selecteren](./media/add-manage-connections/select-gateway.png)
   
   > [!IMPORTANT]
   > Micro soft share point-gegevens gateways ondersteunen HTTP-verkeer, maar geen HTTPS-verkeer.
   > 
   > 
3. Geef de referenties voor de verbinding op en selecteer vervolgens de gateway die u wilt gebruiken.
   
    Zie [gateways beheren](gateway-manage.md) en [gateways begrijpen](gateway-reference.md)voor meer informatie.
   
    Wanneer de verbinding is ingesteld, wordt deze weer gegeven in **Mijn verbindingen**.

## <a name="delete-a-connection"></a>Een verbinding verwijderen
1. Ga naar de pagina **Mijn verbindingen** en selecteer het prullenbak pictogram voor de verbinding die u wilt verwijderen.
   
    ![Verbinding verwijderen](./media/add-manage-connections/delete-connection.png)
2. Selecteer **OK** om te bevestigen dat u de verbinding wilt verwijderen.
   
    ![Verwijdering bevestigen](./media/add-manage-connections/delete-confirmation.png)

Wanneer u een verbinding verwijdert, wordt deze verwijderd uit PowerApps en Microsoft Flow.

## <a name="update-a-connection"></a>Een verbinding bijwerken
U kunt een verbinding bijwerken die niet werkt omdat uw account Details of uw wacht woord is gewijzigd.

1. Selecteer op de pagina **Mijn verbindingen** de koppeling **wacht woord verifiëren** voor de verbinding die u wilt bijwerken.
   
    ![Wacht woord bevestigen](./media/add-manage-connections/verify-password.png)
2. Wanneer u hierom wordt gevraagd, werkt u de verbinding bij met de nieuwe referenties.

Wanneer u een verbinding bijwerkt, wordt deze bijgewerkt voor zowel PowerApps als Microsoft Flow.

## <a name="troubleshoot-a-connection"></a>Problemen met een verbinding oplossen
Afhankelijk van het beleid van uw organisatie moet u mogelijk hetzelfde account gebruiken om u aan te melden bij Microsoft Flow en een verbinding te maken met share point, Office 365 of OneDrive voor bedrijven.

U kunt zich bijvoorbeeld aanmelden bij Microsoft Flow met *yourname@outlook.com* , maar worden geblokkeerd wanneer u verbinding probeert te maken met share point met *yourname@contoso.com* . U kunt zich in plaats daarvan aanmelden bij Microsoft Flow met *yourname@contoso.com* en u kunt verbinding maken met share point.

<!--Reference links in article-->
[1]: https://flow.microsoft.com
