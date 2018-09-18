---
title: Meer informatie over het beheren van uw gegevens via verbindingen en on-premises gegevensgateways | Microsoft-Docs
description: U kunt verbindingen toevoegen en beheren met SharePoint, SQL Server, OneDrive voor Bedrijven, Salesforce, Office 365, OneDrive, Dropbox, Twitter, Google Drive en meer.
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
ms.openlocfilehash: bdfa1072bca2afc7c608a4dbf68b8f598dff89f1
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689106"
---
# <a name="manage-connections-in-microsoft-flow"></a>Verbindingen beheren in Microsoft Flow
Als u een verbinding maakt in Microsoft Flow, kunt u tijdens het maken van een stroom eenvoudig toegang krijgen tot uw gegevens. Microsoft Flow bevat veelgebruikte verbindingen, waaronder SharePoint, SQL Server, Office 365, OneDrive voor Bedrijven, Salesforce, Excel, Dropbox en Twitter. Verbindingen worden gedeeld met PowerApps. Als u een verbinding maakt in het ene product, wordt de verbinding ook weergegeven in het andere.

U kunt een verbinding bijvoorbeeld gebruiken om deze taken uit te voeren:

* Een SharePoint-lijst bijwerken.
* Gegevens ophalen uit een Excel-bestand in uw OneDrive voor Bedrijven- of Dropbox-account.
* E-mail verzenden in Office 365.
* Een tweet verzenden.

U kunt in meerdere scenario's verbindingen maken, zoals de volgende:

* Een stroom maken [op basis van een sjabloon](get-started-logic-template.md)
* Een [volledig nieuwe stroom](get-started-logic-flow.md) maken of een bestaande stroom bijwerken
* Rechtstreeks op de [Microsoft Flow-website][1] een verbinding maken

In dit onderwerp ziet u hoe u verbindingen beheert op de [Microsoft Flow-website][1].

## <a name="add-a-connection"></a>Een verbinding toevoegen
1. Meld u op de [Microsoft Flow-website][1] aan met uw werk- of organisatieaccount.
2. Selecteer het tandwielpictogram in de rechterbovenhoek en selecteer vervolgens **Verbindingen**.
   
    ![Verbindingen selecteren](./media/add-manage-connections/connections-menu.png)
3. Selecteer **Verbinding maken**.
4. Selecteer in de lijst **Beschikbare verbindingen** de verbinding die u wilt instellen, bijvoorbeeld SharePoint.
5. Selecteer de knop **Verbinding maken** en voer uw referenties in voor het instellen van de verbinding.

Als de verbinding is ingesteld, wordt deze weergegeven bij **Mijn verbindingen**.

## <a name="connect-to-your-data-through-an-on-premises-data-gateway"></a>Verbinding maken met uw gegevens via een on-premises gegevensgateway
Op het moment dat deze tekst wordt geschreven, bieden SQL Server en SharePoint Server ondersteuning voor de on-premises gegevensgateway. Ga als volgt te werk om een verbinding te maken waarin gebruik wordt gemaakt van een gateway:

1. Volg de stappen eerder in dit onderwerp om een verbinding toe te voegen.
2. Selecteer **SQL Server** in de lijst met **beschikbare verbindingen** en schakel het selectievakje **Verbinding maken via een on-premises gegevensgateway** in.
   
    ![Gateway selecteren](./media/add-manage-connections/select-gateway.png)
   
   > [!IMPORTANT]
   > Microsoft SharePoint-gegevensgateways ondersteunen wel HTTP-verkeer, maar geen HTTPS-verkeer.
   > 
   > 
3. Geef de referenties voor de verbinding op en selecteer vervolgens de gateway die u wilt gebruiken.
   
    Zie de Engelstalige artikelen [Manage gateways](gateway-manage.md) (Gateways beheren) en [Understand gateways](gateway-reference.md) (Gateways) voor meer informatie.
   
    Als de verbinding is ingesteld, wordt deze weergegeven bij **Mijn verbindingen**.

## <a name="delete-a-connection"></a>Een verbinding verwijderen
1. Ga naar de pagina **Mijn verbindingen** en selecteer het prullenbakpictogram voor de verbinding die u wilt verwijderen.
   
    ![Verbinding verwijderen](./media/add-manage-connections/delete-connection.png)
2. Selecteer **OK** om te bevestigen dat u de verbinding wilt verwijderen.
   
    ![Verwijderen bevestigen](./media/add-manage-connections/delete-confirmation.png)

Als u een verbinding verwijdert, wordt deze verwijderd uit PowerApps en uit Microsoft Flow.

## <a name="update-a-connection"></a>Een verbinding bijwerken
Als een verbinding niet werkt omdat er wijzigingen zijn opgetreden in uw accountdetails of uw wachtwoord, kunt u de verbinding bijwerken.

1. Selecteer op de pagina **Verbindingen** de koppeling **Wachtwoord bevestigen** voor de verbinding die u wilt bijwerken.
   
    ![Wachtwoord bevestigen](./media/add-manage-connections/verify-password.png)
2. Werk uw verbinding bij met de nieuwe referenties als u hierom wordt gevraagd.

Als u een verbinding bijwerkt, wordt deze bijgewerkt voor PowerApps en voor Microsoft Flow.

## <a name="troubleshoot-a-connection"></a>Problemen met een verbinding oplossen
Afhankelijk van het beleid van uw organisatie moet u mogelijk hetzelfde account gebruiken om u aan te melden bij Microsoft Flow en om een verbinding te maken met SharePoint, Office 365 of OneDrive voor Bedrijven.

Mogelijk moet u zich bij Microsoft Flow bijvoorbeeld aanmelden met *yourname@outlook.com*, maar wordt u geblokkeerd als u probeert verbinding maken met SharePoint met *yourname@contoso.com*. U kunt zich in plaats daarvan bij Microsoft Flow aanmelden met *yourname@contoso.com* en dan verbinding maken met SharePoint.

<!--Reference links in article-->
[1]: https://flow.microsoft.com
