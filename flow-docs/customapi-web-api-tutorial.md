---
title: Een aangepaste connector ontwikkelen voor een Web API | Microsoft Docs
description: Meer informatie over het maken van een ASP.NET Web-API met Azure Active Directory-verificatie in Microsoft Flow
services: 
suite: flow
documentationcenter: 
author: sunaysv
manager: anneta
editor: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/06/2016
ms.author: sunayv
ms.openlocfilehash: fef904b02d4b0f028edba236b73e19155b6f4919
ms.sourcegitcommit: f3236f9f1ec050cda0d9c3e2b9c356132b2a2594
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/30/2018
---
# <a name="build-a-custom-connector-for-a-web-api-in-microsoft-flow"></a>Een aangepaste connector ontwikkelen voor een Web API in Microsoft Flow
In deze zelfstudie leert u hoe u kunt beginnen met het ontwikkelen van een ASP.NET Web-API, deze host op Azure-Web Apps, Azure Active Directory-verificatie inschakelt en de ASP.NET Web-API registreert in Microsoft Flow. Nadat de API is geregistreerd, kunt u er verbinding mee maken en aanroepen vanuit uw stroom. 

## <a name="prerequisites"></a>Vereisten
* Een [Azure-abonnement](https://azure.microsoft.com/free/).
* Een [PowerApps-account](https://powerapps.microsoft.com).
* [Visual Studio](https://www.visualstudio.com/vs/) 2013 of hoger.

## <a name="create-an-aspnet-web-api-and-deploy-it-to-azure"></a>Een ASP.NET Web-API maken en deze implementeren naar Azure
1. Klik in Visual Studio op **Bestand** > **Nieuw Project** als u een nieuwe C# ASP.NET-webtoepassing wilt maken.
   
    ![Nieuwe webtoepassing](./media/customapi-web-api-tutorial/newwebapp.png)
2. Selecteer de sjabloon **Web-API**.  Laat **Host in the cloud** (In de cloud hosten) ingeschakeld.  Klik op **Change Authentication** (Verificatie wijzigen).
   
    ![Nieuwe webprojectsjabloon](./media/customapi-web-api-tutorial/new-web-api.png)
3. Selecteer **Geen verificatie** en klik vervolgens op **OK**.
   
    ![Geen verificatie](./media/customapi-web-api-tutorial/noauth.png)
4. Klik op **OK** in het dialoogvenster **New ASP.NET Project** (Nieuw ASP.NET-project).  Het dialoogvenster Microsoft Azure-web-app configureren wordt weergegeven.
   
    ![Microsoft Azure web-app configureren](./media/customapi-web-api-tutorial/azure-publishing.png)]
   
    Selecteer uw Azure-account, typ een **Web-appnaam** (of behoud de standaardnaam) en selecteer uw Azure-**abonnement**.  Selecteer of maak een **App Service-plan** (een verzameling Web-apps binnen uw abonnement).  Selecteer of maak een **Resourcegroep** (een groep Azure-resources binnen uw abonnement).  Selecteer de regio waar de Web-app moet worden geïmplementeerd.  Selecteer of maak een Azure-**databaseserver** indien dit voor uw Web-API nodig is.  Klik ten slotte op **OK**.
5. Maak uw Web-API.
   
   > [!NOTE]
   > Als u nog geen code hebt die gereed is voor een Web-API, kunt u de zelfstudie [Getting Started with ASP.NET Web API 2 (C#)](https://www.asp.net/web-api/overview/getting-started-with-aspnet-web-api/tutorial-your-first-web-api) (Aan de slag met ASP.NET Web API 2 (C#)) doornemen.
   > 
   > 
6. Als u onze Web-API wilt koppelen aan PowerApps, moet u een [Swagger](http://swagger.io/)-bestand maken waarin de bewerkingen worden beschreven.  U kunt uw eigen OpenAPI schrijven met de [online editor](http://editor.swagger.io/), maar voor deze zelfstudie gebruikt u het open-sourcehulpprogramma [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle/blob/master/README.md).  Als u het pakket voor Swashbuckle Nuget wilt installeren in uw Visual Studio-project, klikt u op**Extra** > **NuGet Package Manager** > **Package Manager-console**, en typt u vervolgens de opdracht `Install-Package Swashbuckle` in de Package Manager-console.
   
    ![Swashbuckle-installatiepakket](./media/customapi-web-api-tutorial/swashbuckle-console.png)
   
   > [!TIP]
   > Als u uw Web-API-toepassing uitvoert nadat u Swashbuckle hebt geïnstalleerd, wordt er een OpenAPI-bestand gegenereerd op de URL `http://<your root URL>/swagger/docs/v1`.  Op `http://<your root URL>/swagger` is ook een gegenereerde gebruikersinterface beschikbaar.
   > 
   > 
7. Wanneer uw Web-API klaar is, publiceert u deze naar Azure. Als u wilt publiceren vanuit Visual Studio, klikt u met de rechtermuisknop op het webproject in Solution Explorer, klikt u op **Publiceren...** en volgt u de aanwijzingen in het dialoogvenster Publiceren.
8. Haal de OpenAPI JSON op door naar `https://<azure-webapp-url>/swagger/docs/v1` te gaan.  Sla de inhoud op als JSON-bestand.  Afhankelijk van uw browser moet u de tekst mogelijk in een leeg tekstbestand kopiëren en plakken.   
   
   > [!IMPORTANT]
   > Een OpenAPI-document met twee bewerkings-id’s is ongeldig. Als u het voorbeeldsjabloon C# gebruikt, wordt de bewerkings-id `Values_Get` twee keer herhaald. U kunt dit verhelpen door één exemplaar te wijzigen naar `Value_Get` en opnieuw te publiceren.
   > 
   > U kunt ook een [voorbeeld van een OpenAPI](https://pwrappssamples.blob.core.windows.net/samples/webAPI.json) downloaden uit deze zelfstudie. Zorg ervoor dat u voor gebruik de opmerkingen (vanaf `//`) verwijdert.
   > 
   > 

## <a name="set-up-azure-active-directory-authentication"></a>Azure Active Directory-verificatie instellen
U maakt nu twee AAD-toepassingen (Azure Active Directory) in Azure.  Zie de [Azure Resource Manager-zelfstudie](customapi-azure-resource-manager-tutorial.md#enable-authentication-in-azure-active-directory) voor een voorbeeld.

> [!IMPORTANT]
> Beide apps moeten zich in dezelfde map bevinden.
> 
> 

### <a name="first-aad-application-securing-the-web-api"></a>Eerste AAD-toepassing: de Web-API beveiligen
De eerste AAD-toepassing wordt gebruikt voor het beveiligen van de Web-API. Noem deze **webAPI**.  Volg de bovenstaande stappen van de zelfstudie (alleen de sectie 'Verificatie inschakelen in Azure Active Directory') met de volgende waarden:

* Aanmeldings-URL: `https://login.windows.net`
* Antwoord-URL: `https://<your-root-url>/.auth/login/aad/callback`
* U hebt geen clientsleutel nodig.
* U hoeft geen machtigingen over te dragen.
* **Belangrijk!** Noteer de toepassings-id.  U hebt deze op een later tijdstip weer nodig.

### <a name="second-aad-application-securing-the-custom-connector-and-delegated-access"></a>Tweede AAD-toepassing: de aangepaste connector en gedelegeerd toegang beveiligen
De tweede AAD-toepassing wordt gebruikt voor het beveiligen van de registratie van de aangepaste connector en het verkrijgen van gedelegeerde toegang tot de Web-API die wordt beveiligd door de eerste toepassing. Noem deze **webAPI-customAPI**.

* Aanmeldings-URL: `https://login.windows.net`
* Antwoord-URL: `https://msmanaged-na.consent.azure-apim.net/redirect`
* Voeg machtigingen toe voor gedelegeerde toegang tot de Web-API.
* Ook van deze toepassing hebt u op een later tijdstip de toepassing-id nodig. Noteer deze dus ook.
* Genereer een clientsleutel en sla deze op een veilige locatie op. Deze sleutel hebt u op een later tijdstip nodig.

## <a name="add-authentication-to-your-azure-web-app"></a>Verificatie toevoegen aan uw Azure-web-app
1. Meld u aan bij [Azure Portal](https://portal.azure.com) en zoek vervolgens de web-app die u in de eerste sectie hebt geïmplementeerd.
2. Klik op **Instellingen** en selecteer vervolgens **Verificatie / autorisatie**.
3. Schakel **App Service-verificatie** in en selecteer vervolgens **Azure Active Directory**.  Selecteer op de volgende blade **Express**.  
4. Klik op **Bestaande AD-app selecteren** en selecteer de **webAPI** AAD-toepassing die u eerder hebt gemaakt.

U kunt nu AAD gebruiken om uw webtoepassing te verifiëren.

## <a name="add-the-custom-connector-to-microsoft-flow"></a>De aangepaste connector toevoegen aan Microsoft Flow
1. Wijzig uw OpenAPI om het `securityDefintions`-object en de AAD-verificatie toe te voegen die u hebt gebruikt voor de web-app. De sectie van uw OpenAPI met de **host**eigenschap ziet er zo uit:

```javascript
// File header should be above here...

"host": "<your-root-url>",
"schemes": [
    "https"         //Make sure this is https!
],
"securityDefinitions": {
    "AAD": {
        "type": "oauth2",
        "flow": "accessCode",
        "authorizationUrl": "https://login.windows.net/common/oauth2/authorize",
        "tokenUrl" : "https://login.windows.net/common/oauth2/token",
        "scopes": {}
    }
},

// The rest of the OpenAPI follows...
```

1. Blader naar [Microsoft Flow](https://flow.powerapps.com) en voeg een aangepaste connector toe zoals beschreven in [Register and use custom connectors in Microsoft Flow](register-custom-api.md) (Aangepaste connectors registreren en gebruiken in Microsoft Flow).
2. Als u uw OpenAPI hebt geüpload, detecteert de wizard automatisch dat u AAD-verificatie gebruikt voor uw Web-API.
3. Configureer de AAD-verificatie voor de aangepaste connector.  
   
   * **Client-id**: *client-id van webAPI-CustomAPI*
   * **Client-id**: *clientsleutel van webAPI-CustomAPI*
   * **Aanmeldings-URL**: `https://login.windows.net`
   * **ResourceUri**: *client-id van webAPI*
4. Klik op **Maken** en maak een verbinding met de aangepaste connector.

## <a name="next-steps"></a>Volgende stappen
Doorloop de [Azure Resource Manager-zelfstudie over aangepaste connectors](customapi-azure-resource-manager-tutorial.md).

