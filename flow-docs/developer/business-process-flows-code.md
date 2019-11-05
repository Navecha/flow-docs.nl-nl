---
title: Werken met bedrijfs proces stromen met behulp van code | MicrosoftDocs
description: Meer informatie over hoe u via programma code kunt werken met zakelijke proces stromen om efficiënter en gestroomlijnde bedrijfs processen te maken.
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
ms.openlocfilehash: 5ce11084cb9a430899fd0a4b672e009c0dc22d25
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547734"
---
# <a name="work-with-business-process-flows-using-code"></a>Werken met bedrijfs proces stromen met behulp van code
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Met een *bedrijfs proces stroom* kunt u efficiënter en gestroomlijnde verkoop-, service-en bedrijfs processen maken. Er wordt een visualisatie van uw bedrijfs proces gemaakt door speciale besturings elementen boven aan de entiteit formulieren te plaatsen. Gebruikers worden begeleid door verschillende stadia van de verkoop-, marketing-of service processen tot aan de voltooiing. Elk proces ondersteunt meerdere fasen en stappen. U kunt stappen toevoegen of verwijderen, de volg orde van de stadia wijzigen of nieuwe entiteiten toevoegen aan de stroom van het bedrijfs proces.  
  
Verschillende instanties voor bedrijfsproces stromen kunnen gelijktijdig worden uitgevoerd op dezelfde entiteits record. Gebruikers kunnen scha kelen tussen gelijktijdige exemplaren van bedrijfs processen en hun werk hervatten in een huidige fase van het proces. 

In dit onderwerp vindt u informatie over hoe u programmatisch kunt werken met bedrijfsproces stromen.

> [!NOTE]
> U hoeft geen code te schrijven voor het werken met bedrijfsproces stromen. Zie [overzicht van bedrijfsproces stromen](../business-process-flows-overview.md) voor meer informatie over het gebruik van de gebruikers interface voor het maken en beheren van bedrijfs processen.  

<a name="PrereqsBPF"></a>   
## <a name="prerequisites-for-business-process-flow"></a>Vereisten voor bedrijfsproces stroom 

Aangepaste entiteiten en entiteiten die bijgewerkte UI-formulieren hebben, kunnen deel uitmaken van de bedrijfs proces stroom. De eigenschap <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsAIRUpdated> van de bijgewerkte gebruikers interface-entiteiten is ingesteld op `true`. 

Als u een entiteit wilt inschakelen voor de stroom van bedrijfs processen, stelt u de eigenschap <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBusinessProcessEnabled> in op `true`.

> [!IMPORTANT]
>  Het inschakelen van een entiteit voor een bedrijfs proces stroom is een eenrichtings proces. U kunt deze niet omkeren.

   
<a name="DefineBPF"></a>   
## <a name="define-business-process-flow"></a>Bedrijfs proces stroom definiëren
  
Gebruik de ontwerp functie voor bedrijfs processen om een bedrijfs proces stroom te definiëren. Meer informatie: [een bedrijfs proces stroom maken](../create-business-process-flow.md)

Een bedrijfs proces stroom record wordt standaard gemaakt in de `Draft` status.  

Een definitie van een bedrijfs proces stroom wordt opgeslagen in de entiteit <xref:Microsoft.Dynamics.CRM.workflow> en de fase-informatie voor de bedrijfs proces stroom wordt opgeslagen in de <xref:Microsoft.Dynamics.CRM.processstage> entiteit.
  
<a name="ActivateBPF"></a>   
## <a name="activate-business-process-flow"></a>Bedrijfs proces stroom activeren  
 Voordat u de proces stroom kunt gebruiken, moet u deze activeren. Als u deze wilt activeren, moet u beschikken over de `prvActivateBusinessProcessFlow` bevoegdheid voor de `Workflow` entiteit. Gebruik het <xref:Microsoft.Xrm.Sdk.Messages.UpdateRequest> bericht om de status van de entiteits record `Workflow` in te stellen op `Activated`. Meer informatie: [gespecialiseerde bewerkingen uitvoeren met update](/dynamics365/customer-engagement/developer/org-service/perform-specialized-operations-using-update) 

 > [!NOTE]
 > U kunt ook de ontwerp functie voor bedrijfs processen gebruiken om een bedrijfs proces stroom te activeren. 

<a name="BPFEntity"></a>   
## <a name="business-process-flow-entity"></a>Entiteit bedrijfs proces stroom 
 Wanneer u een definitie van een bedrijfsproces stroom hebt geactiveerd door de status van de bijbehorende `Workflow` entiteits record te wijzigen of door de ontwerp functie voor bedrijfs processen te gebruiken, wordt er automatisch een aangepaste entiteit met de volgende naam gemaakt om het geactiveerde bedrijf op te slaan proces flow-instanties: ' *\<activesolutionprefix >* _ *\<unieke naam >* ', waarbij de uniekheid wordt afgeleid van de door u opgegeven locatie.  
  
 Als u bijvoorbeeld ' mijn aangepaste BPF ' hebt opgegeven als de naam van de stroom definitie van het bedrijfs proces en de standaard Uitgever (nieuw) gebruikt voor uw actieve oplossing, is de naam van de aangepaste entiteit die is gemaakt voor het opslaan van proces instanties ' new_mycustombpf '.  
  
 Als de `uniquename` waarde niet beschikbaar is voor een definitie van een bedrijfs proces stroom, bijvoorbeeld als de bedrijfs proces stroom is geïmporteerd als onderdeel van de oplossing uit een eerdere versie, wordt de standaard naam van de aangepaste entiteit '`\<activesolutionprefix>_bpf_<GUID_BPF_Definition>`:  
  
> [!IMPORTANT]
>  De voorbeeld records voor bedrijfs processen gebruiken systeem entiteiten voor het opslaan van de bijbehorende instantie records van de bedrijfs proces stroom.  
>   
>  Nieuwe bedrijfsproces stroom definities die u maakt, gebruiken echter aangepaste entiteiten om de instantie records op te slaan zoals eerder is uitgelegd. 

U kunt de naam van uw bedrijfs proces stroom-entiteit ophalen met behulp van een van de volgende manieren:

- **Met behulp van de gebruikers interface**: gebruik de aanpassings interface om naar uw bedrijfs proces stroom entiteit te bladeren:

    ![](media/bpf-entity-name.png)
- **De Web-API**gebruiken: gebruik de volgende aanvraag:

    **Schot**

    ```
    GET [Organization URI]/api/data/v9.0/workflows?$filter=name eq 'My Custom BPF'&$select=uniquename HTTP/1.1
    ```

    **Beantwoord**
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
- **De organisatie service**gebruiken: gebruik het volgende code voorbeeld:

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
> De eigenschap <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBPFEntity> is `true` voor bedrijfs proces stroom-entiteiten. U kunt alle bedrijfs proces stroom entiteiten in uw exemplaar ophalen door de volgende Web API-aanvraag uit te voeren:
> ```http
> GET [Organization URI]/api/data/v9.0/EntityDefinitions?$select=SchemaName,LogicalName,DisplayName&$filter=IsBPFEntity eq true HTTP/1.1
> ```

<a name="BPFSecurity"></a>   
## <a name="manage-security-for-business-process-flows"></a>Beveiliging voor bedrijfs proces stromen beheren

De aangepaste entiteit die automatisch wordt gemaakt bij het activeren van een bedrijfsproces stroom voor het opslaan van bedrijfs processen, voldoet aan het standaard beveiligings model als voor een andere aangepaste entiteit in Common Data Service. Dit betekent dat de bevoegdheden die voor deze entiteiten zijn verleend, de runtime machtigingen definiëren voor gebruikers voor bedrijfsproces stromen.

De entiteit voor de aangepaste bedrijfs proces stroom heeft een organisatie bereik. Met de normale bevoegdheden Create, retrieve, update en Delete voor deze entiteit definieert u de machtigings gebruikers op basis van hun toegewezen rollen. Wanneer de aangepaste entiteit bedrijfs proces stroom is gemaakt, worden alleen de beveiligings rollen **systeem beheerder** **en Systeemaanpasser verleend** aan de groep, en moet u expliciet machtigingen verlenen aan de nieuwe entiteit bedrijfs proces stroom (voor voor beeld van **Mijn aangepaste BPF**) voor andere beveiligings rollen zoals vereist.

![](media/bpf-privileges.png)

<a name="ManageBPF"></a>   
## <a name="create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances"></a>Entiteit records voor een bedrijfs proces stroom maken, ophalen, bijwerken en verwijderen (proces exemplaren)  
 De aangepaste entiteit die automatisch wordt gemaakt bij het activeren van een bedrijfs proces stroom definitie, slaat alle proces exemplaren voor de definitie van de bedrijfs proces stroom op. De aangepaste entiteit ondersteunt het standaard programmatisch maken en beheren van records (proces exemplaren) met behulp van Web API en CRM 2011-eind punt.

> [!IMPORTANT]
> Overschakelen naar een ander proces exemplaar voor een entiteits record wordt alleen ondersteund via de gebruikers interface (client) of via een programma met behulp van de informatie die beschikbaar is in deze sectie. U kunt het `SetProcess` bericht (<xref href="Microsoft.Dynamics.CRM.SetProcess?text=SetProcess Action" /> of <xref:Microsoft.Crm.Sdk.Messages.SetProcessRequest>) niet meer gebruiken om processen programmatisch te scha kelen (Stel een andere bedrijfs proces stroom in als het actieve proces exemplaar) voor de doel entiteits record. 

 In het volgende voor beeld ziet u dat er sprake is van een bedrijfsproces stroom voor een cross-entiteit, ' My Custom BPF ', met 3 fasen: S1: account, S2: account en S3: contact. 

 ![](media/sample-bpf.png)
 
### <a name="retrieve-all-the-records-instances-for-a-business-process-flow-entity"></a>Alle records (instanties) ophalen voor een entiteit van een bedrijfs proces stroom
 Als de naam van de entiteit bedrijfs proces stroom ' new_mycustombpf ' is, gebruikt u de volgende query om alle records (proces exemplaren) op te halen voor de entiteit bedrijfs proces stroom:  
  
```http
GET [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
```

U kunt op dit moment geen instanties in uw antwoord ontvangen, omdat er geen is. Voer deze aanvraag uit nadat u een exemplaar van de bedrijfs proces stroom definitie hebt gemaakt verderop in dit onderwerp.

> [!NOTE]
> Zie de vorige sectie [bedrijfs proces stroom](#business-process-flow-entity)als u wilt weten hoe u de naam van de entiteit bedrijfs proces stroom kunt ophalen.
  
### <a name="create-a-business-process-flow-entity-record-process-instance"></a>Een entiteits record voor een bedrijfs proces stroom maken (proces exemplaar) 

Maak een bedrijfsproces stroom entiteits record (proces exemplaar) programmatisch als u wilt overschakelen naar een andere bedrijfs proces stroom voor een entiteits record zonder de gebruikers interface te gebruiken. 

Als u een entiteits record voor een bedrijfs proces stroom wilt maken, moet u de volgende waarden opgeven: 
- Koppel de entiteits record van de bedrijfs proces stroom aan een primaire entiteits record door de navigatie-eigenschap met één waarde in te stellen met behulp van de `@odata.bind` aantekening. Als u wilt weten welke naam van de navigatie-eigenschap verwijst naar de record van de primaire entiteit voor de stroom definitie van uw bedrijfs proces, gebruikt u het [CSDL $metadata-document](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document). 
- Koppel de entiteits record van de bedrijfs proces stroom aan een geldige fase die is opgegeven in de definitie van de bedrijfs proces stroom door de navigatie-eigenschap met één waarde in te stellen met behulp van de `@odata.bind` annotatie. Als u wilt weten hoe de naam van de navigatie-eigenschap (meestal `activestageid`) die verwijst naar de fase record voor de definitie van uw bedrijfs proces stroom, gebruikt u het [CSDL $metadata-document](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document).

    U kunt ook informatie over alle fasen voor een bedrijfs proces stroom definitie ophalen met behulp van de volgende Web API-aanvraag, ervan uitgaande dat de ID van de bedrijfs proces stroom definitie 2669927e-8ad6-4f95-8a9a-f1008af6956f is:

    **Schot**

    ```http
    GET [Organization URI]/api/data/v9.0/processstages?$select=stagename&$filter=processid/workflowid eq 2669927e-8ad6-4f95-8a9a-f1008af6956f HTTP/1.1
    ```

    **Beantwoord**

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

Gebruik vervolgens de volgende aanvraag om een exemplaar te maken van de definitie van de bedrijfs proces stroom voor een account record (ID = a176be9e-9a68-e711-80e7-00155d41e206) en de actieve fase ingesteld als de eerste fase van het proces exemplaar, S1 (ID = 9a9185f5-b75b-4bbb-9c2b-a6626683b99b):

**Schot**

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

**Beantwoord**

```http
HTTP/1.1 204 No Content
OData-Version: 4.0
OData-EntityId: [Organization URI]/api/data/v9.0/new_mycustombpfs(cc3f721b-026e-e811-80ff-00155d513100)
```

Houd er rekening mee dat als u een exemplaar van de bedrijfs proces stroom definitie wilt maken en de actieve fase is ingesteld als een ***andere*** fase dan de eerste fase, moet u ook `traversedpath` in uw aanvraag opgeven. Doorlopend pad is de door komma's gescheiden teken reeks van proces fase-id's die de bezochte fasen van het exemplaar van de bedrijfs proces stroom vertegenwoordigen. Met de volgende aanvraag wordt een exemplaar gemaakt voor een account record (ID = 679b2464-71b5-e711-80f5-00155d513100) en een actieve fase ingesteld als de tweede fase, S2 (ID = 19a11fc0-3398-4214-8522-cb2a97f66e4b).

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

### <a name="update-a-business-process-flow-entity-record-process-instance"></a>Een entiteits record voor een bedrijfs proces stroom bijwerken (proces exemplaar)

U kunt een proces exemplaar bijwerken om naar het volgende of vorige stadium te gaan, een proces exemplaar te verlaten, een proces exemplaar opnieuw te activeren of een proces exemplaar te volt ooien. 

#### <a name="stage-navigation"></a>Fase navigatie

Als u naar een andere fase wilt gaan, moet u een record van het proces exemplaar bijwerken om de actieve fase-ID te wijzigen en het doorlopende pad bij te werken. Houd er rekening mee dat u alleen moet overstappen op het volgende of vorige stadium tijdens het bijwerken van een exemplaar van een bedrijfs proces stroom.

Als u de fase navigatie wilt uitvoeren, hebt u de ID nodig van het exemplaar van de bedrijfsproces stroom dat u wilt bijwerken. Als u alle exemplaren van uw bedrijfsproces stroom wilt ophalen, raadpleegt u [alle records (instanties) voor een bedrijfsproces stroom entiteit eerder ophalen](#retrieve-all-the-records-instances-for-a-business-process-flow-entity) .

Ervan uitgaande dat de ID van het proces exemplaar dat u wilt bijwerken dc2ab599-306d-e811-80ff-00155d513100 is, gebruikt u de volgende aanvraag om de actieve fase bij te werken van S1 naar S2:

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

#### <a name="change-the-state-of-a-process-instance-abort-reactivate-or-finish"></a>De status van een proces exemplaar wijzigen: afbreken, opnieuw activeren of volt ooien 

Een proces exemplaar kan een van de volgende statussen hebben: **actief**, **voltooid**of **afgebroken**. De status wordt bepaald door de volgende kenmerken van de record van het proces exemplaar:

- **State**code: hier wordt de status van het proces exemplaar weer gegeven.

    |Value|adres|
    |-----|-----|
    |0,3    |Actief|
    |i    |Inactieve|

- **status**code: geeft informatie weer over de status van het proces exemplaar.

    |Value|adres|
    |-----|-----|
    |i    |Actief|
    |twee    |Geïnstalleerd|
    |3D    |Afgebroken|

Als u een proces exemplaar wilt **afbreken** , gebruikt u de volgende aanvraag om de `statecode` en `statuscode` waarden op de juiste wijze in te stellen:

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
> U kunt een proces exemplaar in elk stadium afbreken.

Als u een proces exemplaar opnieuw wilt activeren, moet u de `statecode` en `statuscode` waarden in de bovenstaande code vervangen door respectievelijk **0** en **1** .

Ten slotte kunt u de status van een proces exemplaar zo instellen dat deze is **voltooid**. Dit is alleen mogelijk in de laatste fase van een proces exemplaar. vervang de `statecode` en `statuscode` waarden in de bovenstaande code respectievelijk **0** en **2** .

#### <a name="cross-entity-navigation"></a>Navigatie in meerdere entiteiten

Voor navigatie in meerdere entiteiten in dit voor beeld moet u het actieve stadium van het proces exemplaar instellen op de laatste fase, S3 (ID = a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a), het overlopende pad bijwerken en een contact record als primaire entiteits record instellen zoals per de definitie van de bedrijfs proces stroom.

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

### <a name="delete-a-business-process-flow-entity-record-process-instance"></a>Een entiteits record voor een bedrijfs proces stroom verwijderen (proces exemplaar)

Gebruik de volgende Web API-aanvraag:

**Schot**

```http
DELETE [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1
```  

**Beantwoord**

Als de record bestaat, krijgt u een normaal antwoord met de status 204 om aan te geven dat het verwijderen is voltooid. Als de entiteit niet wordt gevonden, ontvangt u een antwoord met de status 404.

## <a name="use-retrieveprocessinstances-and-retrieveactivepath-messages"></a>RetrieveProcessInstances-en RetrieveActivePath-berichten gebruiken

Gebruik het `RetrieveProcessInstances` bericht (<xref href="Microsoft.Dynamics.CRM.RetrieveProcessInstances?text=RetrieveActivePath Function" /> of <xref:Microsoft.Crm.Sdk.Messages.RetrieveProcessInstancesRequest>) om alle bedrijfsproces stroom exemplaren voor een entiteits record op te halen voor alle bedrijfsproces definities. De bedrijfsproces stroom instanties die voor een entiteit worden geretourneerd, worden geordend op basis van het `modifiedon` kenmerk voor het exemplaar. Zo is het meest recent gewijzigde exemplaar van de bedrijfs proces stroom de *eerste* record in de geretourneerde verzameling. Het meest recent gewijzigde exemplaar van de bedrijfs proces stroom is de instantie die actief is op de gebruikers interface voor een entiteits record.  
  
Elke instantie record van een bedrijfsproces stroom die wordt geretourneerd voor een entiteits record als gevolg van het gebruik van het `RetrieveProcessInstances` bericht slaat de ID van de actieve fase op in het `processstageid` kenmerk dat kan worden gebruikt om het actieve stadium te vinden en vervolgens naar het vorige of volgende stadium te gaan. Als u dit wilt doen, moet u eerst het actieve pad van een exemplaar van een bedrijfsproces stroom en de beschik bare fasen in het proces stroom exemplaar zoeken met behulp van het `RetrieveActivePath` bericht (<xref href="Microsoft.Dynamics.CRM.RetrieveActivePath?text=RetrieveActivePath Function" /> of <xref:Microsoft.Crm.Sdk.Messages.RetrieveActivePathRequest>).   
  
 Zodra u de actieve fase en de gegevens van het actieve pad voor een exemplaar van een bedrijfsproces stroom hebt, kunt u de informatie gebruiken om over te stappen op een vorige of volgende fase in het actieve pad. Voorwaartse navigatie van fasen moet worden uitgevoerd, dat wil zeggen, dat wil zeggen dat u alleen naar de volgende fase in het actieve pad moet gaan.   
  
 Zie voor [Beeld: werken met bedrijfsproces stromen](sample-work-business-process-flows.md)voor het volledige voor beeld van het gebruik van deze twee methoden en voor het navigeren met fase ring met behulp van de [organisatie service](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata). 

<a name="ApplyBPF"></a>   
## <a name="apply-business-process-flow-while-creating-an-entity-record"></a>Bedrijfs proces stroom Toep assen tijdens het maken van een entiteits record

Deze sectie bevat informatie over het standaard gedrag voor het Toep assen van bedrijfs proces stromen naar nieuwe entiteits records die zijn gemaakt in Common Data Service, en hoe u deze kunt negeren om een bedrijfsproces stroom van uw keuze toe te passen op nieuwe entiteits records.

Voor een entiteit waarvoor meerdere bedrijfsproces stromen zijn gedefinieerd, past het systeem standaard een bedrijfsproces stroom toe op de nieuwe entiteits record met behulp van de volgende logica voor meerdere stappen:
1. Identificeer alle bedrijfsproces stromen die van toepassing zijn op de nieuwe entiteit record op basis van het **werk stroom. PrimaryEntity** -kenmerk van de definitie records van de bedrijfs proces stroom.
2. Identificeer de bedrijfsproces stroom definities waartoe de huidige gebruiker toegang heeft. Zie [beveiliging voor bedrijfsproces stromen beheren](#BPFSecurity) eerder in dit onderwerp voor meer informatie over hoe toegang tot een bedrijfs proces stroom wordt bepaald en beheerd.<br/>  
3. Voor alle bedrijfsproces stroom definities in het systeem gelden globale orders per entiteit. De volg orde van de bedrijfs proces stroom wordt opgeslagen in het kenmerk **workflow. ProcessOrder** . De definities van de bedrijfs proces stroom voor een entiteit worden gesorteerd op basis van deze volg orde en de waarde met de laagste volg orde wordt gekozen.
4. Ten slotte, als de entiteits record wordt gemaakt op basis van een zakelijke app (app-module), wordt er nog één filter niveau toegepast om de bedrijfs proces stroom te kiezen die automatisch moet worden toegepast op de nieuwe entiteits record. Wanneer gebruikers in een app werken, kunnen ze alleen toegang krijgen tot relevante entiteiten, bedrijfs proces stromen, weer gaven en formulieren waartoe ze toegang hebben op basis van de beveiligings rollen die aan de zakelijke app zijn toegewezen. 
    - Als de zakelijke app geen bedrijfsproces stroom bevat, wordt bedrijfs proces stroom toegepast, zoals wordt uitgelegd tot stap 3.
    - Als de bedrijfs-app een of meer bedrijfs processen heeft, zijn alleen de bedrijfs proces stromen die in de app aanwezig zijn, van toepassing. In dit geval, wanneer de gebruiker binnen een context van een zakelijke app werkt, wordt de lijst met bedrijfsproces stromen uit stap 3 verder gefilterd naar de processen die deel uitmaken van de zakelijke app die aanwezig zijn in de app-module en worden gesorteerd op basis van de volg orde van het proces. 
    - Als er geen bedrijfsproces stroom beschikbaar is in een bedrijfs-app voor de entiteit, of een bedrijf waartoe de gebruiker toegang heeft, wordt er geen bedrijfs proces stroom toegepast voor de nieuwe entiteits record.

U kunt de standaard logica van bedrijfs proces stromen die automatisch worden toegepast, overschrijven naar nieuwe entiteits records. Als u dit wilt doen, stelt u het kenmerk **ProcessID** van de entiteit in op een van de volgende waarden bij het maken van een nieuwe entiteits record:
- Stel in op **GUID. empty** om het instellen van een bedrijfs proces stroom voor nieuwe entiteits records over te slaan. U kunt dit doen als u bulksgewijze entiteits records maakt, maar u niet wilt dat bedrijfsproces stroom hierop wordt toegepast.
- Stel deze in op een specifieke bedrijfs proces stroom-entiteit (als entiteits verwijzing). In dit geval wordt de opgegeven bedrijfs proces stroom toegepast in plaats van de standaard logica.

Als u geen waarde voor het kenmerk **ProcessID** instelt tijdens het maken van een nieuwe entiteits record, wordt de standaard logica toegepast zoals eerder is uitgelegd.

> [!NOTE]
> Het overschrijven van de standaard logica van bedrijfs proces stromen die automatisch worden toegepast op nieuwe entiteits records wordt alleen programmatisch ondersteund. U kunt dit niet doen met behulp van de gebruikers interface.

## <a name="legacy-process-related-attributes-in-entities"></a>Verouderde proces-gerelateerde kenmerken in entiteiten

De verouderde aan het proces gerelateerde kenmerken (zoals **ProcessID**, **StageId**en **TraversedPath**) op entiteiten die zijn ingeschakeld voor bedrijfsproces stromen, zijn al afgeschaft. Het bewerken van deze verouderde proces kenmerken voor de doel entiteit records biedt geen garantie voor de consistentie van de status van de bedrijfs processen en is ***geen*** ondersteund scenario. De aanbevolen manier is de kenmerken van de entiteit bedrijfs proces stroom te gebruiken zoals eerder is uitgelegd in de sectie [records voor bedrijfs proces stroom maken, ophalen, bijwerken en verwijderen (proces exemplaren)](#create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances)

De enige uitzonde ring hierop is het programmatisch wijzigen van het kenmerk **ProcessID** tijdens het maken van een entiteits record om de standaard toepassing van de bedrijfs proces stroom te overschrijven naar de nieuwe record, zoals wordt uitgelegd in de vorige sectie: [bedrijf Toep assen proces stroom tijdens het maken van een entiteits record](#ApplyBPF).

<a name="BKMK_clientSideScript"></a>   
## <a name="client-side-programmability-support-for-business-process-flows"></a>Programmeer bare ondersteuning aan de client zijde voor bedrijfsproces stromen  
 Er is een client-side-object dat u kunt gebruiken om te communiceren met bedrijfsproces stromen in uw formulier scripts. Bedrijfs proces stromen activeren client-side-gebeurtenissen telkens wanneer een proces wordt toegepast op een record, het stadium wordt gewijzigd of de status wordt gewijzigd in `Active`, `Finished`of `Aborted`. Meer informatie: [formContext. data. Process (API-verwijzing van client)](/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process.md)  
  
<a name="BKMK_MaxSettings"></a>   
## <a name="maximum-number-of-processes-stages-and-steps"></a>Maximum aantal processen, fasen en stappen  
 Per entiteit is de standaard waarde voor het maximum aantal actieve proces stromen van het bedrijf 10. U kunt een andere waarde opgeven met behulp van het kenmerk `Organization.MaximumActiveBusinessProcessFlowsAllowedPerEntity`. Als de waarde echter groter is dan 10, wordt er mogelijk een afname van de prestaties van uw systeem weer gegeven wanneer u overschakelt naar een ander proces of een record opent met een toegewezen bedrijfsproces stroom. Dit kan bijzonder merkbaar zijn als processen meerdere entiteiten omvatten.  
  
 De volgende instellingen zijn niet aanpasbaar:  
  
-   Het maximum aantal fasen per entiteit in het proces is 30.  
  
-   Het maximum aantal stappen in elke fase is 30.  
  
-   Het maximum aantal entiteiten dat kan deel nemen aan de proces stroom is 5.  

