---
title: Azure Active Directory gebruiken met een aangepaste connector | Microsoft Docs
description: Lees hoe u een aangepaste connector voor Azure Resource Manager met Azure Active Directory-verificatie kunt maken.
services: 
suite: flow
documentationcenter: 
author: msftman
manager: anneta
editor: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/03/2016
ms.author: deonhe
ms.openlocfilehash: d98a3505ab7d667f5a64eed9a23041efec95b1d7
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/15/2017
---
# <a name="use-azure-active-directory-with-a-custom-connector-in-microsoft-flow"></a>Azure Active Directory in Microsoft Flow gebruiken met een aangepaste connector
Met Azure Resource Manager (ARM) kunt u de onderdelen van een oplossing op Azure beheren - onderdelen zoals databases, virtuele machines en web-apps. In deze zelfstudie leert u hoe in Azure Active Directory-verificatie kunt inschakelen, een van de ARM-API's als een aangepaste connector kunt registreren, en hiermee vervolgens in Microsoft Flow verbinding kunt maken. Dit is handig als u Azure-resources als onderdeel van een stroom wilt beheren. Zie voor meer informatie over ARM [Overzicht van Azure Resource Manager](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-overview).

## <a name="prerequisites"></a>Vereisten
* Een [Azure-abonnement](https://azure.microsoft.com/free/).
* Een [Microsoft Flow-account](https://flow.microsoft.com).
* Het [OpenAPI-voorbeeldbestand](http://pwrappssamples.blob.core.windows.net/samples/AzureResourceManager.json) dat in deze zelfstudie wordt gebruikt.

## <a name="enable-authentication-in-azure-active-directory"></a>Verificatie inschakelen in Azure Active Directory
Eerst moet een AAD-toepassing (Azure Active Directory) worden gemaakt waarmee de verificatie wordt uitgevoerd bij het aanroepen van het ARM-API-eindpunt.

1. Meld u aan bij [Azure Portal](https://portal.azure.com).  Als u meer dan één Azure Active Directory-tenant hebt, zorg er dan voor dat u bent aangemeld bij de juiste directory door te kijken naar uw gebruikersnaam in de rechterbovenhoek.
   
    ![Gebruikersnaam](./media/customapi-azure-resource-manager-tutorial/current-user.png)
2. Klik in het menu links op **More services** (Meer services).  Typ in het tekstvak **Filter** de tekst **Azure Active Directory** en klik vervolgens op **Azure Active Directory**.
   
    ![Azure Active Directory](./media/customapi-azure-resource-manager-tutorial/azureaad.png)
   
    De Azure Active Directory-blade wordt geopend.   
3. Klik in het menu dat verschijnt op de Azure Active Directory-blade op **App registrations** (App-registraties).
   
    ![App-registraties](./media/customapi-azure-resource-manager-tutorial/azureapplication.png)
4. Klik in de lijst met geregistreerde toepassingen op **Toevoegen**.
   
    ![Knop toevoegen](./media/customapi-azure-resource-manager-tutorial/add-app-btn.png)   
5. Typ een naam voor uw toepassing, laat **Web-app / API** geselecteerd en typ vervolgens voor **Aanmeldings-URL** `https://login.windows.net`.  Klik op **Maken**.  
   
    ![Nieuw app-formulier](./media/customapi-azure-resource-manager-tutorial/newapplication.png)
6. Klik op de nieuwe toepassing in de lijst.
   
    ![Nieuwe app in lijst](./media/customapi-azure-resource-manager-tutorial/newapplication2.png)
   
    De blade Geregistreerde app wordt geopend.  Noteer de **toepassings-id**.  We hebben deze op een later tijdstip weer nodig.
7. De blade Instellingen wordt tevens geopend.  Als dit niet het geval is, klikt u op de knop **Instellingen**.
   
    ![De knop Instellingen](./media/customapi-azure-resource-manager-tutorial/settings-btn.png)
8. Klik op de blade Instellingen op **Antwoord-URL's**. Voeg in de lijst van URL's `https://msmanaged-na.consent.azure-apim.net/redirect` toe en klik op **Opslaan**.
   
    ![Antwoord-URL’s](./media/customapi-azure-resource-manager-tutorial/reply-urls.png)
9. Klik op de blade Instellingen op **Vereiste machtigingen**.  Klik op de blade Vereiste machtigingen op **Toevoegen**.
   
    ![Vereiste machtigingen](./media/customapi-azure-resource-manager-tutorial/permissions.png)
   
    De blade API-toegang toevoegen wordt geopend.
10. Klik op **Een API selecteren**. Klik in de blade die wordt geopend op de optie voor de Azure Service Management-API en klik op **Selecteren**.
    
    ![Een API selecteren](./media/customapi-azure-resource-manager-tutorial/permissions2.png)
11. Klik op **Machtigingen selecteren**.  Klik onder *Gedelegeerde machtigingen* op **Access Azure Service Management as organization users** (Toegang verkrijgen tot Azure Service Management als organisatiegebruikers) en klik vervolgens op **Selecteren**.
    
    ![Gedelegeerde machtigingen](./media/customapi-azure-resource-manager-tutorial/permissions3.png)
12. Klik op de blade API-toegang toevoegen op **Gereed**.
13. Als u weer op de blade Instellingen bent, klikt u op **Sleutels**.  Typ op de blade Sleutels een beschrijving voor de sleutel, selecteer een vervalperiode in en klik vervolgens op **Opslaan**.  Uw nieuwe sleutel wordt weergegeven.  Noteer de sleutelwaarde. Ook deze hebt u op een later tijdstip nodig.  U kunt nu Azure Portal sluiten.
    
    ![Een sleutel maken](./media/customapi-azure-resource-manager-tutorial/configurekeys.png)

## <a name="add-the-connection-in-microsoft-flow"></a>De verbinding toevoegen in Microsoft Flow
Nu de AAD-toepassing is geconfigureerd, gaan we de aangepaste connector toevoegen.

1. Klik in de [Microsoft Flow web-app](https://flow.microsoft.com/) op de knop **Instellingen** in de rechterbovenhoek van de pagina (het pictogram lijkt op een tandrad).  Klik vervolgens op **Aangepaste connectors**.
   
    ![Zoeken naar aangepaste connectors](./media/customapi-azure-resource-manager-tutorial/finding-custom-apis.png)  
2. Klik op **Aangepaste connector maken**.  
   
    U wordt gevraagd de eigenschappen van de API op te geven.  
   
   | Eigenschap | Beschrijving |
   | --- | --- |
   | Naam |Klik boven aan de pagina op **Naamloos** en geef de stroom een naam. |
   | OpenAPI-bestand |Blader naar het [ARM OpenAMI-voorbeeldbestand](http://pwrappssamples.blob.core.windows.net/samples/AzureResourceManager.json). |
   | API-pictogram uploaden |Klik op **Pictogram uploaden** om een afbeeldingsbestand voor het pictogram te selecteren. Een PNG- of JPG-afbeelding van maximaal 1 MB is toegestaan. |
   | Beschrijving |Typ een beschrijving van uw aangepaste connector (optioneel). |
   
    ![Een aangepaste connector maken](./media/customapi-azure-resource-manager-tutorial/create-custom-api.png)  
   
    Selecteer **Doorgaan**.
3. Omdat het OpenAPI-bestand onze AAD-toepassing gebruikt voor verificatie, moet in het volgende scherm informatie over de toepassing worden opgegeven aan Flow.  Type onder **Client-id** de **toepassings-id** van AAD die u eerder hebt genoteerd.  Gebruik voor clientgeheim de **sleutel**.  En typ ten slotte voor **Resource-URL** `https://management.core.windows.net/`.
   
   > [!IMPORTANT]
   > Zorg ervoor dat Resource-URL exact zoals hierboven vermeld wordt overgenomen, inclusief de afsluitende slash.
   > 
   > 
   
    ![OAuth-instellingen](./media/customapi-azure-resource-manager-tutorial/oauth-settings.png)
   
    Klik na het invoeren van beveiligingsgegevens op het vinkje (**&#x2713;**) naast de naam van de stroom boven aan deze pagina om de aangepaste connector te maken.
4. Uw aangepaste connector wordt nu weergegeven onder **Aangepaste connectors**.
   
    ![Beschikbare API's](./media/customapi-azure-resource-manager-tutorial/list-custom-apis.png)  
5. Nu de aangepaste connector is geregistreerd, moet u een verbinding met de aangepaste connector maken, zodat deze kan worden gebruikt in uw apps en stromen.  Klik op de **+** aan de rechterkant van de naam van uw aangepaste connector en vul vervolgens het aanmeldingsscherm in.

> [!NOTE]
> De voorbeeld-OpenAPI omvat niet de volledige set ARM-bewerkingen en bevat momenteel alleen de bewerking [List all subscriptions](https://msdn.microsoft.com/library/azure/dn790531.aspx) (Een lijst met alle abonnementen weergeven).  U kunt deze OpenAPI bewerken of een ander OpenAPI-bestand maken met de [online OpenAPI-editor](http://editor.swagger.io/).
> 
> Dit proces kan worden gebruikt voor toegang tot een RESTful-API die is geverifieerd met AAD.
> 
> 

## <a name="next-steps"></a>Volgende stappen
Zie [Beginnen met bouwen met Microsoft Flow](get-started-logic-flow.md) voor meer informatie over het maken van een stroom.

Als u vragen wilt stellen of opmerkingen wilt maken over aangepaste connectors, kunt u [lid worden van onze community](https://aka.ms/flow-community).

