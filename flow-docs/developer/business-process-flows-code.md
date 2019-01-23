---
title: Werken met bedrijfsprocesstromen met behulp van code | Microsoft Docs
description: Leer hoe u programmatisch kunt werken met bedrijfsprocesstromen om efficiëntere en beter gestroomlijnde bedrijfsprocessen te maken.
ms.custom: ''
ms.date: 07/09/2018
ms.reviewer: ''
ms.service: flow
ms.topic: article
ms.assetid: 67d8cf80-9f77-4804-97a1-cf9f61417e83
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 4fcbca859d167e82229aa60f96f5122912e5cca3
ms.sourcegitcommit: c7c9add30d5bf1ab6bd5b55b802fd28618b38411
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/17/2019
ms.locfileid: "54362973"
---
# <a name="work-with-business-process-flows-using-code"></a>Werken met bedrijfsprocesstromen met behulp van code

Een *bedrijfsprocesstroom* stelt u in staat om efficiëntere en meer gestroomlijnde verkoop-, service- en andere bedrijfsprocessen te maken. U maakt een visualisatie van het bedrijfsproces door speciale besturingselementen aan de bovenzijde van de entiteitsformulieren te plaatsen. Gebruikers worden door verschillende fasen van verkoop, marketing of service geleid om tot afronding van het proces te komen. Elk proces biedt ondersteuning voor meerdere fasen en stappen. U kunt stappen toevoegen of verwijderen, de volgorde van fasen wijzigen of nieuwe entiteiten toevoegen aan de bedrijfsprocesstroom.  
  
Er kunnen tegelijkertijd verschillende exemplaren van bedrijfsprocesstromen worden uitgevoerd op basis van dezelfde entiteitsrecord. Gebruikers kunnen schakelen tussen gelijktijdige exemplaren van bedrijfsprocessen en hun werk in een huidige fase in het proces hervatten. 

Dit onderwerp bevat informatie over hoe u programmatisch kunt werken met bedrijfsprocesstromen.

> [!NOTE]
> U hoeft geen code te schrijven om te werken met bedrijfsprocesstromen. Zie [Overzicht bedrijfsprocesstromen](../business-process-flows-overview.md) voor meer informatie over het gebruik van de gebruikersinterface voor het maken en beheren van bedrijfsprocesstromen.  

<a name="PrereqsBPF"></a>   
## <a name="prerequisites-for-business-process-flow"></a>Vereisten voor bedrijfsprocesstromen 

Aangepaste entiteiten en entiteiten met bijgewerkte gebruikersinterfaceformulieren kunnen deelnemen aan de bedrijfsprocesstroom. Bijgewerkte gebruikersinterface entiteiten hebben de waarde `true` voor de eigenschap <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsAIRUpdated>. 

Als u een entiteit wilt inschakelen voor de bedrijfsprocesstroom, stelt u de eigenschap <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBusinessProcessEnabled> in op `true`.

> [!IMPORTANT]
>  Het inschakelen van een entiteit voor een bedrijfsprocesstroom is een onomkeerbare handeling. U kunt de entiteit niet meer uitschakelen voor de stroom.

   
<a name="DefineBPF"></a>   
## <a name="define-business-process-flow"></a>Bedrijfsprocesstroom definiëren
  
Gebruik de ontwerpfunctie voor het visueel samenstellen van een bedrijfsprocesstroom. Meer informatie: [Een bedrijfsprocesstroom maken](../create-business-process-flow.md)

Een record met een bedrijfsprocesstroom wordt standaard gemaakt met de status `Draft`.  

De definitie van een bedrijfsprocesstroom wordt opgeslagen in de entiteit <xref:Microsoft.Dynamics.CRM.workflow> en de fase-informatie voor de bedrijfsprocesstroom wordt opgeslagen in de entiteit <xref:Microsoft.Dynamics.CRM.processstage>.
  
<a name="ActivateBPF"></a>   
## <a name="activate-business-process-flow"></a>Bedrijfsprocesstroom activeren  
 U kunt een processtroom pas gebruiken nadat u de stroom hebt geactiveerd. Hiervoor moet u over de bevoegdheid `prvActivateBusinessProcessFlow` beschikken voor de entiteit `Workflow`. Gebruik het bericht <xref:Microsoft.Xrm.Sdk.Messages.UpdateRequest> om de status van de record van de `Workflow`-entiteit in te stellen op `Activated`. Meer informatie: [Gespecialiseerde bewerkingen uitvoeren met Update](/dynamics365/customer-engagement/developer/org-service/perform-specialized-operations-using-update) 

 > [!NOTE]
 > U kunt ook de ontwerpfunctie voor bedrijfsprocesstromen gebruiken om een bedrijfsprocesstroom te activeren. 

<a name="BPFEntity"></a>   
## <a name="business-process-flow-entity"></a>Entiteit van bedrijfsprocesstroom 
 Nadat u de definitie van een bedrijfsprocesstroom hebt geactiveerd door de status van de bijbehorende record van de `Workflow`-entiteit te wijzigen of met behulp van de ontwerpfunctie voor bedrijfsprocesstromen, wordt er automatisch een aangepaste entiteit met de volgende naam gemaakt voor het opslaan van de geactiveerde exemplaren van de bedrijfsprocesstroom: '*\<activesolutionprefix>*_*\<uniquename>*', waarbij de waarde voor uniquename wordt afgeleid van de naam die u opgeeft.  
  
 Als u bijvoorbeeld 'Mijn aangepaste BPF' hebt opgegeven als de naam van de definitie van de bedrijfsprocesstroom en u de standaarduitgever (nieuw) gebruikt voor uw actieve oplossing, is 'nieuw_mijnaangepastebpf' de naam van de aangepaste entiteit die wordt gemaakt voor het opslaan van procesexemplaren.  
  
 Als de waarde `uniquename` niet beschikbaar is voor de definitie van een bedrijfsprocesstroom, bijvoorbeeld als de bedrijfsprocesstroom is geïmporteerd als onderdeel van de oplossing van een eerdere versie, wordt de standaardnaam van de aangepaste entiteit `\<activesolutionprefix>_bpf_<GUID_BPF_Definition>`:  
  
> [!IMPORTANT]
>  De voorbeeldrecords van bedrijfsprocesstromen gebruiken systeementiteiten voor het opslaan van de bijbehorende records van exemplaren van de bedrijfsprocesstromen.  
>   
>  Nieuwe definities van bedrijfsprocesstromen die u maakt, gebruiken echter aangepaste entiteiten gebruiken voor het opslaan van de records van het exemplaar, zoals eerder is beschreven. 

U kunt de naam van de entiteit van uw bedrijfsprocesstroom op de volgende manieren ophalen:

- **Met de gebruikersinterface**: Gebruik de aanpassingsinterface om naar uw bedrijfsprocesstroomentiteit te bladeren:

    ![](media/bpf-entity-name.png)
- **Met de web-API**: Gebruik de volgende aanvraag:

    **Aanvraag**

    ```
    GET [Organization URI]/api/data/v9.0/workflows?$filter=name eq 'My Custom BPF'&$select=uniquename HTTP/1.1
    ```

    **Respons**
    ```
    {  
    "@odata.context":"[Organization URI]/api/data/v9.0/$metadata#workflows(uniquename)",
    "value":[  
         {  
             "@odata.etag":"W/\"1084677\"",
             "uniquename":"new_mycustombpf",
             "workflowid":"2669927e-8ad6-4f95-8a9a-f1008af6956f"
         }
      ]
    }
    ```
- **Met de Organisatieservice**: Gebruik het volgende codevoorbeeld:

    ```c#
    QueryExpression query = new QueryExpression
    {
        EntityName = "workflow",
        ColumnSet = new ColumnSet("uniquename"),
        Criteria = new FilterExpression
        {
            Conditions =
            {
                new ConditionExpression
                {
                    AttributeName = "name",
                    Operator = ConditionOperator.Equal,
                    Values = { "My Custom BPF" }
                }
            }
        }
    };
    Workflow Bpf = (Workflow)_serviceProxy.RetrieveMultiple(query).Entities[0]; 
    ```
> [!NOTE]
> De eigenschap <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBPFEntity> is `true` voor bedrijfsprocesstroomentiteiten. U kunt alle bedrijfsprocesstroomentiteiten in uw instantie ophalen door de volgende web-API-aanvraag uit te voeren:
> ```http
> GET [Organization URI]/api/data/v9.0/EntityDefinitions?$select=SchemaName,LogicalName,DisplayName&$filter=IsBPFEntity eq true HTTP/1.1
> ```

<a name="BPFSecurity"></a>   
## <a name="manage-security-for-business-process-flows"></a>Uw beveiliging voor bedrijfsprocesstromen beheren

De aangepaste entiteit die automatisch wordt gemaakt bij het activeren van een bedrijfsprocesstroom voor het opslaan van bedrijfsprocesstroominstanties voldoet aan het standaardbeveiligingsmodel voor elke andere aangepaste entiteit in Customer Engagement. Dit betekent dat de runtime-machtigingen voor gebruikers voor bedrijfsprocesstromen worden gedefinieerd door de machtigingen die voor deze entiteiten worden verleend.

De aangepaste bedrijfsprocesstroomentiteit heeft organisatiebereik. De machtiging die de gebruiker zou hebben op basis van de rollen die aan de gebruiker zijn toegewezen, wordt gedefinieerd door de standaardmachtigingen voor het maken, ophalen, bijwerken en verwijderen voor deze entiteit. Bij het maken van de aangepaste bedrijfsprocesstroomentiteit krijgen standaard alleen de beveiligingsrollen **systeembeheerder** en **systeemaanpasser** er toegang toe en moet u zo nodig expliciet machtigingen verlenen aan de nieuwe bedrijfsprocesstroomentiteit (bijvoorbeeld **My Custom BPF**) voor andere beveiligingsrollen.

![](media/bpf-privileges.png)

<a name="ManageBPF"></a>   
## <a name="create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances"></a>Entiteitsrecords voor bedrijfsprocesstromen maken, ophalen, bijwerken en verwijderen (procesexemplaren)  
 In de aangepaste entiteit die automatisch wordt gemaakt bij het activeren van een bedrijfsprocesstroomdefinitie, worden alle procesexemplaren voor de bedrijfsprocesstroomdefinitie opgeslagen. De aangepaste entiteit biedt ondersteuning voor het standaard programmatisch maken en beheren van records (procesexemplaren) met behulp van de web-API en het CRM 2011-eindpunt.

> [!IMPORTANT]
> Overschakelen naar een ander procesexemplaar voor een entiteitsrecord wordt alleen ondersteund via de gebruikersinterface (client) of programmatisch met behulp van de informatie die beschikbaar is in deze sectie. U kunt niet meer gebruikmaken van het bericht `SetProcess` (<xref href="Microsoft.Dynamics.CRM.SetProcess?text=SetProcess Action" /> of <xref:Microsoft.Crm.Sdk.Messages.SetProcessRequest>) om programmatisch van proces te wisselen (een andere bedrijfsprocesstroom instellen als het actieve procesexemplaar) voor het doelentiteitsrecord. 

 Hier volgt een voorbeeld van een entiteitsoverschrijdende bedrijfsprocesstroom, 'My Custom BPF', die uit drie fasen bestaat: S1:Account, S2:Account en S3:Contact. 

 ![](media/sample-bpf.png)
 
### <a name="retrieve-all-the-records-instances-for-a-business-process-flow-entity"></a>Alle records (instanties) ophalen voor een bedrijfsprocesstroomentiteit
 Als de naam van uw bedrijfprocesstroomentiteit new_mycustombpf is, gebruikt u de volgende query om alle records (procesexemplaren) op te halen voor uw bedrijfsprocesstroomentiteit:  
  
```http
GET [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
```

Het is mogelijk dat er op dit moment geen exemplaren worden vermeld in de respons omdat die er niet zijn. Voer deze aanvraag uit nadat u verderop in dit onderwerp een exemplaar van uw definitie van de bedrijfsprocesstroom hebt gemaakt.

> [!NOTE]
> Zie de eerdere sectie [Entiteit van bedrijfsprocesstroom](#business-process-flow-entity) om te lezen hoe u de naam van de entiteit van uw bedrijfsprocesstroom kunt ophalen.
  
### <a name="create-a-business-process-flow-entity-record-process-instance"></a>Entiteitsrecord voor bedrijfsprocesstroom (procesexemplaar) maken 

U kunt via een programma een entiteitsrecord voor een bedrijfsprocesstroom (procesexemplaar) maken als u wilt overschakelen naar een andere bedrijfsprocesstroom voor een entiteitsrecord zonder de gebruikersinterface te hoeven gebruiken. 

Om een entiteitsrecord voor een bedrijfsprocesstroom te maken, moet u de volgende waarden opgeven: 
- Koppel de entiteitsrecord voor de bedrijfsprocesstroom aan een primair entiteitsrecord door de navigatie-eigenschap met één waarde in te stellen met de annotatie `@odata.bind`. Als u de naam wilt opvragen van de navigatie-eigenschap die verwijst naar de primaire entiteitsrecord voor de definitie van uw bedrijfsprocesstroom, raadpleegt u het document [CSDL $metadata](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document). 
- Koppel de entiteitsrecord voor de bedrijfsprocesstroom aan een geldige fase die is opgegeven in de definitie van de bedrijfsprocesstroom door de navigatie-eigenschap met één waarde in te stellen met de annotatie `@odata.bind`. Als u de naam (meestal `activestageid`) wilt opvragen van de navigatie-eigenschap die verwijst naar de faserecord voor de definitie van uw bedrijfsprocesstroom, raadpleegt u het document [CSDL $metadata](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document).

    U kunt ook informatie over alle fasen voor de definitie van een bedrijfsprocesstroom opvragen met behulp van de volgende web-API-aanvragen, ervan uitgaande dat de id van de definitie van uw bedrijfsprocesstroom 2669927e-8ad6-4f95-8a9a-f1008af6956f is:

    **Aanvraag**

    ```http
    GET [Organization URI]/api/data/v9.0/processstages?$select=stagename&$filter=processid/workflowid eq 2669927e-8ad6-4f95-8a9a-f1008af6956f HTTP/1.1
    ```

    **Respons**

    ```http
    {
        "@odata.context": "[Organization URI]/api/data/v9.0/$metadata#processstages(stagename)",
        "value": [
            {
                "@odata.etag": "W/\"858240\"",
                "stagename": "S1",
                "processstageid": "9a9185f5-b75b-4bbb-9c2b-a6626683b99b"
            },
            {
                "@odata.etag": "W/\"858239\"",
                "stagename": "S3",
                "processstageid": "a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a"
            },
            {
                "@odata.etag": "W/\"858238\"",
                "stagename": "S2",
                "processstageid": "19a11fc0-3398-4214-8522-cb2a97f66e4b"
            }
        ]
    }
    ```

Gebruik daarna de volgende aanvraag om een exemplaar van de definitie van uw bedrijf bedrijfsprocesstroom te maken voor een accountrecord (id=a176be9e-9a68-e711-80e7-00155d41e206) en de actieve fase ingesteld als de eerste fase van het procesexemplaar, S1 (id=9a9185f5-b75b-4bbb-9c2b-a6626683b99b):

**Aanvraag**

```http
POST [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
Content-Type: application/json; charset=utf-8 
OData-MaxVersion: 4.0 
OData-Version: 4.0 
Accept: application/json 

{
    "bpf_accountid@odata.bind": "/accounts(a176be9e-9a68-e711-80e7-00155d41e206)",
    "activestageid@odata.bind": "/processstages(9a9185f5-b75b-4bbb-9c2b-a6626683b99b)"    
}
```

**Respons**

```http
HTTP/1.1 204 No Content
OData-Version: 4.0
OData-EntityId: [Organization URI]/api/data/v9.0/new_mycustombpfs(cc3f721b-026e-e811-80ff-00155d513100)
```

Als u een exemplaar van de definitie van uw bedrijfsprocesstroom wilt maken met de actieve fase ingesteld als een ***andere*** fase dan de eerste fase, moet u ook `traversedpath` opgeven in uw aanvraag. Dit argument bestaat uit een tekenreeks van door komma's gescheiden id's van procesfasen die uitgevoerde fasen van het exemplaar van het bedrijfsprocesstroom aangeven. Met de volgende aanvraag wordt een exemplaar gemaakt voor een accountrecord (id=679b2464-71b5-e711-80f5-00155d513100) en de actieve fase ingesteld als de tweede fase, S2 (id=19a11fc0-3398-4214-8522-cb2a97f66e4b).

```http
POST [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
Content-Type: application/json; charset=utf-8 
OData-MaxVersion: 4.0 
OData-Version: 4.0 
Accept: application/json 

{
    "bpf_accountid@odata.bind": "/accounts(679b2464-71b5-e711-80f5-00155d513100)",
    "activestageid@odata.bind": "/processstages(19a11fc0-3398-4214-8522-cb2a97f66e4b)",
    "traversedpath":"9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b"   
}
```

### <a name="update-a-business-process-flow-entity-record-process-instance"></a>Entiteitsrecord voor bedrijfsprocesstroom (procesexemplaar) bijwerken

U kunt een procesexemplaar bijwerken om het te verplaatsen naar de volgende of vorige fase, of om een procesexemplaar af te breken, opnieuw te activeren of te voltooien. 

#### <a name="stage-navigation"></a>Fasenavigatie

Als u naar een andere fase wilt navigeren, moet u een record voor een procesexemplaar bijwerken om de id van de actieve fase te wijzigen en het betreffende traversalpad dienovereenkomstig bij te werken. U mag alleen naar de volgende of vorige fase gaan tijdens het bijwerken van een exemplaar van een bedrijfsprocesstroom.

Om fasenavigatie uit te voeren, hebt u de id nodig van het exemplaar van de bedrijfsprocesstroom die u wilt bijwerken. Als u alle exemplaren van de bedrijfsprocesstroom wilt ophalen, raadpleegt u [Alle records (exemplaren) voor de entiteit van een bedrijfsprocesstroom ophalen](#retrieve-all-the-records-instances-for-a-business-process-flow-entity) eerder in dit artikel.

Ervan uitgaande dat de id van het procesexemplaar dat u wilt bijwerken dc2ab599-306d-e811-80ff-00155d 513100 is, gebruikt u de volgende aanvraag om de actieve fase bij te werken van S1 naar S2:

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1
Content-Type: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0

{
    "activestageid@odata.bind": "/processstages(19a11fc0-3398-4214-8522-cb2a97f66e4b)",
    "traversedpath": "9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b"
}
```

#### <a name="change-the-state-of-a-process-instance-abort-reactivate-or-finish"></a>Wijzig de status van het procesexemplaar: Afbreken, Opnieuw activeren, of Voltooien 

Een procesexemplaar kan een van de volgende statussen hebben: **Actief**, **Voltooid** of **Afgebroken**. De status wordt bepaald door de volgende kenmerken in de record voor het procesexemplaar:

- **statuscode**: Toont de status van het procesexemplaar.

    |Waarde|Label|
    |-----|-----|
    |0    |Active|
    |1    |Inactive|

- **statuscode**: Toont informatie over de status van het procesexemplaar.

    |Waarde|Label|
    |-----|-----|
    |1    |Active|
    |2    |Finished|
    |3    |Aborted|

Als u een procesexemplaar **afbreken**, gebruikt u de volgende aanvraag om de waarden voor `statecode` en `statuscode` op de gewenste manier in te stellen:

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1   
Content-Type: application/json   
OData-MaxVersion: 4.0   
OData-Version: 4.0 
  
{ 
    "statecode" : "1", 
    "statuscode": "3" 
}
```
 
> [!NOTE]
> U kunt een procesexemplaar tijdens elke fase afbreken.

Op dezelfde manier kunt u een procesexemplaar opnieuw activeren. U vervangt de waarden voor `statecode` en `statuscode` in de bovenstaande code dan door respectievelijk **0** en **1**.

Ten slotte kunt u de status van een procesexemplaar instellen op **Finished**. Dit is alleen mogelijk in de laatste fase van een procesexemplaar. Vervang hiervoor de waarden voor `statecode` en `statuscode` in de bovenstaande code door respectievelijk **0** en **2**.

#### <a name="cross-entity-navigation"></a>Navigatie tussen entiteiten

Voor navigatie tussen entiteiten in dit voorbeeld moet u de actieve fase van het procesexemplaar instellen op de laatste fase, S3 (id=a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a), het traversalpad dienovereenkomstig bijwerken en de record van een contactpersoon instellen als de primaire entiteitsrecord zoals in de definitie van de bedrijfsprocesstroom.

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1   
Content-Type: application/json   
OData-MaxVersion: 4.0   
OData-Version: 4.0 
  
{
    "activestageid@odata.bind": "/processstages(a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a)",
    "traversedpath":"9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b,a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a",
    "bpf_contactid@odata.bind": "/contacts(0e3f10b0-da33-e811-80fc-00155d513100)"
}
``` 

### <a name="delete-a-business-process-flow-entity-record-process-instance"></a>Entiteitsrecord voor bedrijfsprocesstroom (procesexemplaar) verwijderen

Gebruik de volgende web-API-aanvraag:

**Aanvraag**

```http
DELETE [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1
```  

**Respons**

Als de record bestaat, krijgt u een normale respons met de status 204 om aan te geven dat het verwijderen is gelukt. Als de entiteit niet wordt gevonden, krijgt u een respons met de status 404.

## <a name="use-retrieveprocessinstances-and-retrieveactivepath-messages"></a>RetrieveProcessInstances- en RetrieveActivePath-berichten gebruiken

Gebruik het bericht `RetrieveProcessInstances` (<xref href="Microsoft.Dynamics.CRM.RetrieveProcessInstances?text=RetrieveActivePath Function" /> of <xref:Microsoft.Crm.Sdk.Messages.RetrieveProcessInstancesRequest>) om alle exemplaren van een bedrijfsprocesstroom op te halen voor een entiteitsrecord van alle definities van bedrijfsprocessen. De exemplaren van een bedrijfsprocesstroom die worden geretourneerd voor een entiteit worden gerangschikt op basis van het kenmerk `modifiedon` voor het exemplaar. Zo zal het meest recent gewijzigde exemplaar van de bedrijfsprocesstroom de *eerste* record zijn in de geretourneerde verzameling. Het meest recent gewijzigde exemplaar van de bedrijfsprocesstroom is het exemplaar dat in de gebruikersinterface actief is voor een entiteitsrecord.  
  
Elke record voor het exemplaar van een bedrijfsprocesstroom die wordt geretourneerd voor een entiteitsrecord als gevolg van het gebruik van het bericht `RetrieveProcessInstances` slaat de id van de actieve fase op in het kenmerk `processstageid`, dat kan worden gebruikt voor het vinden van de actieve fase, waarna naar de vorige of volgende fase wordt overgeschakeld. Hiervoor moet u eerst het actieve pad van het exemplaar van een bedrijfsprocesstroom vinden en de fasen die beschikbaar zijn in het exemplaar van de processtroom. Dit kan met behulp van het bericht `RetrieveActivePath` (<xref href="Microsoft.Dynamics.CRM.RetrieveActivePath?text=RetrieveActivePath Function" /> of <xref:Microsoft.Crm.Sdk.Messages.RetrieveActivePathRequest>).   
  
 Als u weet wat de actieve fase is en beschikt over gegevens van het actieve pad voor een exemplaar van een bedrijfsprocesstroom, kunt u aan de hand van deze gegevens naar een vorige of volgende fase in het actieve pad gaan. Voorwaartse navigatie van fasen moet op volgorde gebeuren. Dit houdt in dat u alleen naar de volgende fase in het actieve pad mag overschakelen.   
  
 Voor het volledige codevoorbeeld waarin het gebruik van deze twee methoden en fasenavigatie met behulp van de [Organisatieservice](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata) wordt gedemonstreerd, raadpleegt u [Voorbeeld: Werken met bedrijfsprocesstromen](sample-work-business-process-flows.md). 

<a name="ApplyBPF"></a>   
## <a name="apply-business-process-flow-while-creating-an-entity-record"></a>Bedrijfsprocesstroom toepassen tijdens het maken van een entiteitsrecord

Deze sectie bevat informatie over het standaardgedrag voor het automatisch toepassen van bedrijfsprocesstromen op nieuwe entiteitsrecords die zijn gemaakt in Customer Engagement en hoe u dit gedrag kunt overschrijven om een bedrijfsprocesstroom van uw keuze toe te passen voor nieuwe entiteitsrecords.

De standaardinstelling is dat voor een entiteit waarvoor meerdere bedrijfsprocesstromen zijn gedefinieerd, een bedrijfsprocesstroom op de nieuwe entiteitsrecord wordt toegepast door het systeem die wordt bepaald door de volgende multistapslogica:
1. Identificeer alle bedrijfsprocesstromen die van toepassing zijn op de nieuwe entiteitsrecord, op basis van het kenmerk **Workflow.PrimaryEntity** van de records met de definitie van de bedrijfsprocesstromen.
2. Identificeer de definities van de bedrijfsprocesstromen waartoe de huidige gebruiker toegang heeft. Zie [Beveiliging beheren voor bedrijfsprocesstromen](#BPFSecurity) eerder in dit onderwerp voor informatie over hoe de toegang tot een bedrijfsprocesstroom wordt bepaald en beheerd.<br/>  
3. Alle definities van bedrijfsprocesstromen in het systeem zijn onderhevig aan een globale volgorde per entiteit. De volgorde van de bedrijfsprocesstromen wordt opgeslagen in het kenmerk **Workflow.ProcessOrder**. De definities van de bedrijfsprocesstroom voor een entiteit worden op basis van deze volgorde gesorteerd en de definitie met de laagste positie wordt geselecteerd.
4. Als de entiteitsrecord wordt gemaakt van een bedrijfs-app (app-module), is het zo dat er nog één filterniveau wordt toegepast om de bedrijfsprocesstroom te kiezen die automatisch wordt toegepast op de nieuwe entiteitsrecord. Als gebruikers werken in een app, hebben ze alleen toegang tot relevante entiteiten, bedrijfsprocesstromen, weergaven en formulieren waartoe ze toegang hebben op basis van de beveiligingsrollen die aan de bedrijfs-app zijn toegewezen. 
    - Als de bedrijfs-app geen bedrijfsprocesstroom bevat, wordt een bedrijfsprocesstroom toegepast zoals wordt beschreven tot stap 3.
    - Als de bedrijfs-app een of meer bedrijfsprocesstromen heeft, zijn alleen de bedrijfsprocesstromen die aanwezig zijn in de app van toepassing. Wanneer de gebruiker werkt in de context van een bedrijfs-app, wordt de lijst met bedrijfsprocesstromen uit stap 3 in dit geval verder gefilterd op de stromen die deel uitmaken van de bedrijfs-app die aanwezig zijn in de app-module, en worden deze gesorteerd op de procesvolgorde. 
    - Als in een bedrijfs-app geen bedrijfsprocesstroom beschikbaar is voor de entiteit of alleen een stroom waartoe de gebruiker geen toegang heeft, wordt er geen bedrijfsprocesstroom toegepast voor de nieuwe entiteitsrecord.

U kunt de standaardlogica voor het automatisch toepassen van bedrijfsprocesstromen op nieuwe entiteitsrecords uitschakelen. Om dit te doen, stelt u het kenmerk **ProcessId** van de entiteit in op een van de volgende waarden tijdens het maken van een nieuwe entiteitsrecord:
- Stel het kenmerk in op **Guid.Empty** om het instellen van een bedrijfsprocesstroom voor nieuwe entiteitsrecords over te slaan. Dit is bijvoorbeeld handig als u bulksgewijs entiteitsrecords maakt, maar geen bedrijfsprocesstroom op de records wilt toepassen.
- Stel het kenmerk in op een specifieke entiteit van een bedrijfsprocesstroom (als een verwijzing naar een entiteit). In dit geval geldt past het systeem de opgegeven bedrijfsprocesstroom toe in plaats van de standaardlogica.

Als u geen waarde instelt voor het kenmerk **ProcessId** tijdens het maken van een nieuwe entiteitsrecord, past het systeem de standaardlogica toe, zoals die eerder is beschreven.

> [!NOTE]
> U kunt de standaardlogica voor het automatisch toepassen van bedrijfsprocesstromen op nieuwe entiteitsrecords uitschakelen, maar dit kan alleen programmatisch. Dit kan dus niet via de gebruikersinterface.

## <a name="legacy-process-related-attributes-in-entities"></a>Verouderde procesgerelateerde kenmerken in entiteiten

De verouderde procesgerelateerde kenmerken (zoals **ProcessId**, **StageId** en **TraversedPath**) voor entiteiten die zijn ingeschakeld voor bedrijfsprocesstromen zijn al afgeschaft. Het manipuleren van deze verouderde procesgerelateerde kenmerken voor doelentiteitsrecords is dan ook geen garantie voor consistentie van de status van de bedrijfsprocesstroom en is ***geen*** ondersteund scenario. De aanbevolen manier is om de kenmerken van de entiteit voor de bedrijfsprocesstroom te gebruiken, zoals eerder is uitgelegd in de sectie [Entiteitsrecords voor bedrijfsprocesstromen maken, ophalen, bijwerken en verwijderen (procesexemplaren)](#create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances).

De enige uitzondering hierop is het programmatisch wijzigen van het kenmerk **ProcessId** tijdens het maken van een entiteitsrecord om de standaardtoepassing van de bedrijfsprocesstroom te overschrijven met het nieuwe record. Dit wordt uitgelegd in de vorige sectie: [Bedrijfsprocesstroom toepassen tijdens het maken van een entiteitsrecord](#ApplyBPF).

<a name="BKMK_clientSideScript"></a>   
## <a name="client-side-programmability-support-for-business-process-flows"></a>Programmeerondersteuning aan clientzijde voor bedrijfsprocesstromen  
 Er is een object dat u aan de clientzijde kunt gebruiken voor interactie met bedrijfsprocesstromen in uw formulierscripts. Bedrijfsprocesstromen activeren gebeurtenissen aan de clientzijde telkens wanneer er een proces wordt toegepast op een record, de fase wordt gewijzigd of de status van de fase wordt gewijzigd in `Active`, `Finished` of `Aborted`. Meer informatie: [formContext.data.process (naslag voor client-API)](/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process.md)  
  
<a name="BKMK_MaxSettings"></a>   
## <a name="maximum-number-of-processes-stages-and-steps"></a>Maximum aantal processen, fasen en stappen  
 Per entiteit is de standaardwaarde voor het maximum aantal geactiveerde bedrijfsprocesstromen 10. U kunt een andere waarde opgeven met behulp van het kenmerk `Organization.MaximumActiveBusinessProcessFlowsAllowedPerEntity`. Als de waarde echter groter is dan 10, heeft dit mogelijk gevolgen voor de prestaties van uw systeem wanneer u schakelt tussen processen of een record opent waaraan een bedrijfsprocesstroom is toegewezen. Dit kan met name zo zijn als processen meerdere entiteiten omspannen.  
  
 De volgende instellingen kunnen niet worden aangepast:  
  
-   Het maximum aantal fasen per entiteit in het proces is 30.  
  
-   Het maximum aantal stappen in elke fase is 30.  
  
-   Het maximum aantal entiteiten dat kan deelnemen in de processtroom is 5.  

