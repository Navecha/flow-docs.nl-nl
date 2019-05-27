---
title: Stromen worden nu opgeslagen in Common Data Service en gebruiken de uitgebreide Web-API
description: Stromen worden nu opgeslagen in Common Data Service en gebruiken de uitgebreide Web-API.
author: stepsic-microsoft-com
ms.reviewer: deonhe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: business-applications
ms.technology: ''
ms.author: stepsic
audience: Power user
ms.openlocfilehash: ede20606d1d5ba2a97217dfbcfb3c9fffec2c017
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2019
ms.locfileid: "64463576"
---
# <a name="microsoft-flow-web-api"></a>Web-API voor Microsoft Flow

Van nu af aan worden alle stromen opgeslagen in de Common Data Service en wordt er gebruikgemaakt van [de uitgebreide Web-API](https://docs.microsoft.com/powerapps/developer/common-data-service/webapi/perform-operations-web-api).

Deze inhoud bevat informatie over het beheren van stromen op het tabblad **Oplossingen** in Microsoft Flow. Op dit moment worden de stromen bij **Mijn stromen** niet ondersteund door deze API's.

## <a name="compose-http-requests"></a>HTTP-aanvragen opstellen

Als u aan de slag wilt met het maken van aanvragen, moet u eerst de URL maken. De indeling van de basis-URL van de Microsoft Flow Web-API is: `https://{Organization ID}.{Regional Subdomain}.dynamics.com/api/data/v9.1/`. De twee parameters zijn:

- De **organisatie-id** is een unieke naam voor de omgeving waarin uw stromen worden opgeslagen. De organisatie-id staat in de omgevingsschakelaar in de rechterbovenhoek van Microsoft Flow. Houd er rekening mee dat de **organisatie-id** afwijkt van de **omgevings-id** (dit is de GUID die wordt weergegeven in de URL van de stroom).

     ![Omgevingsschakelaaar](media/web-api/get-organization-id.png "Omgevingsschakelaar")

- Welk **regionale subdomein** van toepassing is, is afhankelijk van de locatie van uw omgeving. Wanneer u zich aanmeldt bij Microsoft Flow kunt u de regio van uw omgeving bekijken in de URL van de webpagina. Gebruik de regionaam om het respectieve subdomein te vinden in de volgende tabel:

     ![Flow-URL](media/web-api/get-region-name.png "Flow-URL")

     | Regio         | Subdomein   |
     | -------------- | ----------- |
     | Verenigde Staten  | crm         |
     | Zuid-Amerika  | crm2        |
     | Canada         | crm3        |
     | Europa         | crm4        |
     | Azië en Stille Oceaan   | crm5        |
     | Australië      | crm6        |
     | Japan          | crm7        |
     | India          | crm8        |
     | Amerikaanse overheid  | crm9        |
     | Verenigd Koninkrijk | crm11       |

U kunt de lijst met beschikbare exemplaren ook programmatisch ophalen met de methode [Exemplaren ophalen](https://docs.microsoft.com/rest/api/admin.services.crm.dynamics.com/instances/getinstances) in de Online Management-API.

Voor elke aanvraag voor de Web-API moeten de `Accept`- en `Content-type`-headers worden ingesteld op `application/json`.

Plaats tot slot de Azure AD Bearer-token in de `Authorization`-header. U kunt ook zelf [leren](https://docs.microsoft.com/powerapps/developer/common-data-service/authenticate-oauth) hoe u een Azure AD Bearer-token ophaalt voor Common Data Service. Kijk bijvoorbeeld eens naar deze aanvraag:

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows
Accept: application/json
Authorization: Bearer ey...
```

Het antwoord bevat de lijst met stromen uit die omgeving:

```http
{
    "@odata.context": "https://org00000000.crm0.dynamics.com/api/data/v9.1/$metadata#workflows",
    "value": [{
        "@odata.etag": "W/\"12116760\"",
        "category": 5,
        "statecode": 0,
        "workflowidunique": "00000000-0000-0000-0000-000000000001",
        "workflowid" : "00000000-0000-0000-0000-000000000002",
        "createdon": "2018-11-15T19:45:51Z",
        "_ownerid_value": "00000000-0000-0000-0000-000000000003",
        "modifiedon": "2018-11-15T19:45:51Z",
        "ismanaged": false,
        "name": "Sample flow",
        "_modifiedby_value": "00000000-0000-0000-0000-000000000003",
        "_createdby_value": "00000000-0000-0000-0000-000000000003",
        "type": 1,
        "description": "This flow updates some data in Common Data Service.",
        "clientdata": "{\"properties\":{\"connectionReferences\":{\"shared_commondataservice\":{\"source\":\"NotSpecified\",\"id\":\"/providers/Microsoft.PowerApps/apis/shared_commondataservice\",\"tier\":\"NotSpecified\"}},\"definition\":{...}},\"schemaVersion\":\"1.0.0.0\"}"
    }]
}
```

## <a name="list-flows"></a>Lijst met stromen

Zoals hierboven is beschreven, kunt u de lijst met werkstromen ophalen door `GET` aan te roepen bij `workflows`. Elke werkstroom heeft een aantal eigenschappen. De meest relevante eigenschappen zijn:

| Naam van eigenschap     | Beschrijving                                              |
| ----------------- | -------------------------------------------------------- |
| category          | De categorie van de stroom. De verschillende typen zijn: 0 - klassieke Common Data Service-werkstromen, 1 - klassieke Common Data Service-dialoogvensters, 2 - bedrijfsregels, 3 - klassieke Common Data Service-acties, 4 - zakelijke processtromen en 5 - geautomatiseerde, direct uit te voeren of geplande stromen. |
| statecode         | De status van de stroom. De status kan **0** zijn (uit) of **1** (aan).|
| workflowuniqueid  | De unieke id van deze installatie van de stroom. |
| workflowid        | De unieke id van een stroom binnen alle invoer. |
| createdon         | De datum waarop de stroom is gemaakt. |
| _ownerid_value    | De unieke id van de gebruiker of het team dat eigenaar is van de stroom. Dit is een id uit de entiteit systemusers van Common Data Service. |
| modifiedon        | De laatste keer dat de stroom is bijgewerkt. |
| ismanaged         | Geeft aan of de stroom is geïnstalleerd via een beheerde oplossing. |
| name              | De weergavenaam die u de stroom hebt gegeven. |
| _modifiedby_value | De laatste gebruiker die de stroom heeft bijgewerkt. Dit is een id uit de entiteit systemusers van Common Data Service. |
| _createdby_value  | De gebruiker die de stroom heeft gemaakt. Dit is een id uit de entiteit systemusers van Common Data Service. |
| type              | Geeft aan of een stroom actief is, of dat het een sjabloon is dat kan worden gebruikt voor het maken van aanvullende stromen. 1 - stroom, 2 - activering 3 - sjabloon. |
| beschrijving       | De door de gebruiker opgegeven beschrijving van de stroom. |
| clientdata        | De JSON van een object met tekenreekscodering. De JSON bevat de connectionReferences en de definitie van een stroom. |

U kunt ook specifieke eigenschappen aanvragen, de lijst stromen filteren en nog veel meer. Dit wordt beschreven in de [Common Data Service-API-documentatie voor het opvragen van gegevens](https://docs.microsoft.com/powerapps/developer/common-data-service/webapi/query-data-web-api). Met deze query worden bijvoorbeeld alleen geautomatiseerde, direct uit te voeren en geplande stromen geretourneerd die zich momenteel hier bevinden:

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows?$filter=category eq 5 and statecode eq 1
Accept: application/json
Authorization: Bearer ey...
```

## <a name="create-a-flow"></a>Een stroom maken

Roep `POST` aan voor de `workflows`-verzameling om een stroom te maken. De vereiste eigenschappen voor geautomatiseerde, direct uit te voeren en geplande stromen zijn: category, type, primaryentity en clientdata. Gebruik `none` voor de primaire entiteit van stromen van dit type.

U kunt ook een beschrijving opgeven en een statuscode opgeven.

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
        "category": 5,
        "statecode": 0,
        "name": "Sample flow name",
        "type": 1,
        "description": "This flow reads some data from Common Data Service.",
        "primaryentity":"none",
        "clientdata": "{\"properties\":{\"connectionReferences\":{\"shared_commondataservice\":{\"connectionName\":\"shared-commondataser-00000000-0000-0000-0000-000000000004\",\"source\":\"Invoker\",\"id\":\"/providers/Microsoft.PowerApps/apis/shared_commondataservice\"}},\"definition\":{\"$schema\": \"https:\/\/schema.management.azure.com\/providers\/Microsoft.Logic\/schemas\/2016-06-01\/workflowdefinition.json#\",\"contentVersion\": \"1.0.0.0\",\"parameters\": {\"$connections\": {\"defaultValue\": {},\"type\": \"Object\"},\"$authentication\": {\"defaultValue\": {},\"type\": \"SecureObject\"}},\"triggers\": {\"Recurrence\": {\"recurrence\": {\"frequency\": \"Minute\",\"interval\": 1},\"type\": \"Recurrence\"}},\"actions\": {\"List_records\": {\"runAfter\": {},\"metadata\": {\"flowSystemMetadata\": {\"swaggerOperationId\": \"GetItems_V2\"}},\"type\": \"ApiConnection\",\"inputs\": {\"host\": {\"api\": {\"runtimeUrl\": \"https:\/\/firstrelease-001.azure-apim.net\/apim\/commondataservice\"},\"connection\": {\"name\": \"@parameters('$connections')['shared_commondataservice']['connectionId']\"}},\"method\": \"get\",\"path\": \"\/v2\/datasets\/@{encodeURIComponent(encodeURIComponent('default.cds'))}\/tables\/@{encodeURIComponent(encodeURIComponent('accounts'))}\/items\",\"queries\": {\"$top\": 1},\"authentication\": \"@parameters('$authentication')\"}}},\"outputs\": {}}},\"schemaVersion\":\"1.0.0.0\"}"
}
```

Het belangrijkste gedeelte is de `clientdata`. Deze bevat de connectionReferences waar de stroom gebruik van maakt en de [definitie](https://docs.microsoft.com/azure/logic-apps/logic-apps-workflow-definition-language) van de stroom. De connectionReferences zijn de toewijzingen van elke verbinding waar de stroom gebruik van maakt.

Er zijn drie eigenschappen:

| Naam van eigenschap  | Beschrijving                                                 |
| -------------- | ----------------------------------------------------------- |
| connectionName | Hiermee wordt de verbinding geïdentificeerd. U kunt de connectionName bekijken door naar de pagina **Verbindingen** te gaan en de naam te kopiëren uit de URL van de verbinding. |
| source         | `Embedded` of `Invoker`. `Invoker` is alleen geldig voor direct uit te voeren stromen (waarbij een gebruiker een knop selecteert om de stroom uit te voeren). Dit geeft aan dat de eindgebruiker de verbinding zelf opgeeft. In dit geval wordt connectionName alleen gebruikt gedurende de ontwerptijd. Als de verbinding `Embedded` is, betekent dit dat de connectionName die u opgeeft altijd wordt gebruikt. |
| id             | De id van de connector. De id begint altijd met `/providers/Microsoft.PowerApps/apis/`, gevolgd door de naam van de connector. Deze kunt u kopiëren uit de URL van de verbinding, of u kunt de connector selecteren op de pagina **Connectors**. |

Wanneer u de aanvraag `POST` hebt uitgevoerd, ontvangt u de header `OData-EntityId`. Deze bevat de `workflowid` van uw nieuwe stroom.

## <a name="update-a-flow"></a>Een stroom bijwerken

U kunt `PATCH` aanroepen voor de werkstroom om deze bij te werken, in te schakelen of uit te schakelen. Gebruik de eigenschap `workflowid` om deze aanroepen uit te voeren. U kunt bijvoorbeeld de beschrijving en eigenaar van de stroom bijwerken met de volgende aanroep:

```http
PATCH https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows(00000000-0000-0000-0000-000000000002)
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "description" : "This flow will ensure consistency across systems.",
    "ownerid@odata.bind": "systemusers(00000000-0000-0000-0000-000000000005)",
}
```

> [!NOTE]
> Bij de syntaxis voor het wijzigen van de eigenaar wordt de indeling `odata.bind` gebruikt. Dit betekent dat in plaats van dat het veld \_ownerid_value rechtstreeks wordt gepatcht, u `@odata.bind` toevoegt aan de eigenschapnaam en u daarna de id verpakt met `systemusers()`.

In een ander voorbeeld kunt u een stroom met deze aanroep inschakelen:

```http
PATCH https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows(00000000-0000-0000-0000-000000000002)
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "statecode" : 1
}
```

### <a name="delete-a-flow"></a>Een stroom verwijderen

Een stroom verwijderen met een eenvoudige `DELETE`-aanroep:

```http
DELETE https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows(00000000-0000-0000-0000-000000000002)
Accept: application/json
Authorization: Bearer ey...
```

> [!NOTE]
> Het is niet mogelijk om stromen te verwijderen die zijn ingeschakeld. U moet eerst de stroom uitschakelen (zie **Een stroom bijwerken** hiervoor). Anders wordt de volgende foutmelding weergegeven: `Cannot delete an active workflow definition.`

## <a name="get-all-users-with-whom-a-flow-is-shared"></a>Alle gebruikers ophalen waarmee een stroom wordt gedeeld

Als u een lijst met gebruikers met toegang wilt bekijken, gebruikt u een *functie* uit Common Data Service. Met deze functie wordt één parameter uit `Target` gebruikt:

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/RetrieveSharedPrincipalsAndAccess(Target=@tid)?@tid={'@odata.id':'workflows(00000000-0000-0000-0000-000000000002)'}
Accept: application/json
Authorization: Bearer ey...
```

De parameter `Target` is een JSON-achtige tekenreeks met één eigenschap, genaamd `@odata.id`. Vervang in het bovenstaande voorbeeld de werkstroom-id. Het volgende wordt geretourneerd:

```http
{
    "@odata.context": "https://org00000000.crm0.dynamics.com/api/data/v9.1/$metadata#Microsoft.Dynamics.CRM.RetrieveSharedPrincipalsAndAccessResponse",
    "PrincipalAccesses": [
        {
            "AccessMask": "ReadAccess",
            "Principal": {
                "@odata.type": "#Microsoft.Dynamics.CRM.systemuser",
                "ownerid": "00000000-0000-0000-0000-000000000005"
            }
        }
    ]
}
```

## <a name="share-or-unshare-a-flow"></a>Een stroom delen of het delen ongedaan maken

U kunt stromen delen met de actie `GrantAccess`.

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/GrantAccess
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "Target" : {
        "@odata.type": "Microsoft.Dynamics.CRM.workflow",
        "workflowid" : "00000000-0000-0000-0000-000000000002"
    },
    "PrincipalAccess": {
        "Principal": {
            "@odata.type" : "Microsoft.Dynamics.CRM.systemuser",
            "ownerid" : "00000000-0000-0000-0000-000000000005"
        },
        "AccessMask": "ReadAccess"
    }
}
```

De parameter `AccessMask` staat in een veld met de volgende waarden voor verschillende machtigingsniveaus:

| Naam         | Beschrijving                                          |
| ------------ | ---------------------------------------------------- |
| Geen         | Geen toegang.                                           |
| ReadAccess   | Het recht om de stroom te lezen.                          |
| WriteAccess  | Het recht om de stroom bij te werken.                        |
| DeleteAccess | Het recht om de stroom te verwijderen.                        |
| ShareAccess  | Het recht om de stroom te delen.                         |
| AssignAccess | Het recht om de eigenaar van de stroom te wijzigen.           |

U kunt machtigingen met een komma combineren. U kunt bijvoorbeeld met `ReadAccess,WriteAccess` de mogelijkheid bieden om stromen zowel te lezen als bij te werken.

U kunt het delen van een stroom *opheffen* met de actie `RevokeAccess`. Hier volgt een voorbeeld:

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/RevokeAccess
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "Target" : {
        "@odata.type": "Microsoft.Dynamics.CRM.workflow",
        "workflowid" : "00000000-0000-0000-0000-000000000002"
    },
    "Revokee": {
        "@odata.type" : "Microsoft.Dynamics.CRM.systemuser",
        "ownerid" : "00000000-0000-0000-0000-000000000005"
    }
}
```

Met `RevokeAccess` worden alle machtigingen verwijderd die in `AccessMask` zijn verleend.

## <a name="export-flows"></a>Stromen exporteren

Gebruik de actie `ExportSolution` om stromen te exporteren naar een ZIP-bestand. Voeg eerst de stromen toe die u aan een [oplossing](https://flow.microsoft.com/blog/solutions-in-microsoft-flow/) wilt toevoegen.

Wanneer uw stroom zich in een oplossing bevindt, roept u de volgende actie aan:

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/ExportSolution
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "SolutionName" : "Awesome solution 1",
    "Managed": false
}
```

`ExportSolution` retourneert een tekenreeks met base 64-codering in de eigenschap `ExportSoutionFile`.

```http
{
    "@odata.context": "https://org00000000.crm0.dynamics.com/api/data/v9.1/$metadata#Microsoft.Dynamics.CRM.ExportSolutionResponse",
    "ExportSolutionFile": "UEsDBBQAAgAI..."
}
```

U kunt vervolgens dit bestand opslaan in broncodebeheer en/of een versiebeheer- of distributiesysteem naar keuze gebruiken.

## <a name="import-flows"></a>Stromen importeren

Roep de actie `ImportSolution` aan om een oplossing te importeren.

| Naam van eigenschap                    | Beschrijving                               |
| -------------------------------- | ----------------------------------------- |
| OverwriteUnmanagedCustomizations | Als er bestaande exemplaren van deze stromen aanwezig zijn in Common Data Service, moet deze markering op `true` worden ingesteld om ze te importeren. Als u dit niet doet, worden ze niet overschreven. |
| PublishWorkflows                 | Hiermee wordt aangegeven of er klassieke Common Data Service-werkstromen worden geactiveerd bij het importeren. Deze instelling geldt niet voor andere typen stromen. |
| ImportJobId                      | Biedt een nieuwe, unieke GUID om de importeertaak te volgen. |
| CustomizationFile                | Een op basis van base 64 gecodeerd ZIP-bestand dat de oplossing bevat. |

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/ImportSolution
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "OverwriteUnmanagedCustomizations": false,
    "PublishWorkflows" : true,
    "ImportJobId" : "00000000-0000-0000-0000-000000000006",
    "CustomizationFile" : "UEsDBBQAAgAI..."
}
```

Omdat het importeren lang duurt, is het antwoord op de ImportSolution-actie een `204 No content`. Als u de voortgang wilt bijhouden, roept u een `GET` voor het `importjobs`-object. Geef daarbij de `ImportJobId` op die u in de oorspronkelijke actie `ImportSolution` hebt gebruikt.

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/importjobs(00000000-0000-0000-0000-000000000006)
Accept: application/json
Authorization: Bearer ey...
```

Met deze aanroep wordt de status van de importbewerking geretourneerd, inclusief `progress` (het voltooiingspercentage), `startedon` en `completedon` (of het importeren is voltooid).

Wanneer het importeren is voltooid, moet u de verbindingen voor de stroom instellen omdat de `connectionNames` waarschijnlijk anders is in de doelomgeving (als de verbindingen überhaupt bestaan). Als u nieuwe verbindingen instelt in de doelomgeving, moet de eigenaar van de stromen ze in de Microsoft Flow-ontwerpfunctie maken. Als de verbindingen al zijn ingesteld in de nieuwe omgeving, kunt u de `clientData` van de stroom `PATCH` met de namen van de verbindingen.
