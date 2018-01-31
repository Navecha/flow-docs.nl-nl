---
title: OpenAPI-extensies voor aangepaste connectors in Microsoft Flow | Microsoft Docs
description: De schema-uitbreidingen weergeven die zijn vereist om OpenAPI te laten werken met Microsoft Flow
services: 
suite: flow
documentationcenter: 
author: sunaysv
manager: anneta
editor: sunaysv
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/19/2017
ms.author: sunayv
ms.openlocfilehash: b8fdc04c16701c876d84e9761a48093fa5fb195c
ms.sourcegitcommit: f3236f9f1ec050cda0d9c3e2b9c356132b2a2594
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/30/2018
---
# <a name="openapi-extensions-for-custom-connectors-in-microsoft-flow"></a>OpenAPI-extensies voor aangepaste connectors in Microsoft Flow
## <a name="introduction"></a>Inleiding
Als u aangepaste connectors wilt maken voor Microsoft Flow, Azure Logic Apps, or Microsoft PowerApps, moet u een OpenAPI-definitiebestand opgeven. Dit is een taal-neutraal, machineleesbaar document waarin de bewerkingen en parameters van de API worden beschreven. Samen met de kant-en-klare functionaliteit van OpenAPI, kunt u deze OpenAPI-uitbreidingen ook opnemen wanneer u aangepaste connectors maakt voor Logic Apps en Flow:

* `summary`
* `x-ms-summary`
* `description`
* `x-ms-visibility`
* `x-ms-dynamic-values`
* `x-ms-dynamic-schema`

Hier vindt u meer informatie over deze uitbreidingen:

<a name="summary"></a>

## <a name="summary"></a>samenvatting
Hiermee geeft u de titel op voor de actie (bewerking). </br>
Van toepassing op: bewerkingen </br>
Aanbevolen: gebruik een *zin* voor `summary`. </br>
Voorbeeld: Wanneer een gebeurtenis wordt toegevoegd aan agenda of Een e-mailbericht verzenden

!['summary' voor elke bewerking](./media/custom-connector-openapi-extensions/summary.png)

``` json
"actions" {
  "Send_an_email": {
    /// Other action properties here...
    "summary": "Send an email",
    /// Other action properties here...
  }
},
```

## <a name="x-ms-summary"></a>x-ms-summary
Hiermee geeft u de titel op voor een entiteit. </br>
Van toepassing op: parameters, antwoordschema </br>
Aanbevolen: gebruik een *titel* voor `x-ms-summary`. </br>
Voorbeeld: Agenda-id, Onderwerp, Beschrijving van gebeurtenis enzovoort

!['x-ms-summary' voor elke entiteit](./media/custom-connector-openapi-extensions/x-ms-summary.png)

``` json
"actions" {
  "Send_an_email": {
    /// Other action properties here...
    "parameters": [ 
      {
        /// Other parameters here...
        "x-ms-summary": "Subject",
        /// Other parameters here...
      }
    ]
  }
},
```
<a name="description"></a>

## <a name="description"></a>beschrijving
Hiermee wordt een uitgebreide uitleg van de functionaliteit van de bewerking of de indeling en functie van een entiteit opgegeven. </br>
Van toepassing op: bewerkingen, parameters, antwoordschema </br>
Aanbevolen: gebruik een *zin* voor `description`. </br>
Voorbeeld: Deze bewerking wordt geactiveerd wanneer een nieuwe gebeurtenis wordt toegevoegd aan de agenda, Geef het onderwerp van de e-mail op enzovoort

!['description' voor elke bewerking of entiteit](./media/custom-connector-openapi-extensions/description.png)

``` json
"actions" {
  "Send_an_email": {
     "description": "Specify the subject of the mail",
     /// Other action properties here...
  }
},
```

<a name="visibility"></a>

## <a name="x-ms-visibility"></a>x-ms-visibility
Hiermee wordt de zichtbaarheid van de entiteit voor gebruiker opgegeven. </br>
Mogelijke waarden: `important`, `advanced` en`internal` </br>
Van toepassing op: bewerkingen, parameters, schema's

* `important`-bewerkingen en -parameters worden altijd eerst weergegeven voor de gebruiker.
* `advanced`-bewerkingen en -parameters zijn verborgen onder een aanvullend menu.
* `internal`-bewerkingen en -parameters zijn verborgen voor de gebruiker.

> [!NOTE]
> Voor parameters die `internal` en `required` zijn, **moet** u standaardwaarden opgeven.
> 
> 

Voorbeeld: in het menu **Meer informatie** en het menu **Geavanceerde opties weergeven** worden `advanced`-bewerkingen en -parameters verborgen.

!['x-ms-visibility' voor het weergeven of verbergen van bewerkingen en parameters](./media/custom-connector-openapi-extensions/x-ms-visibility.png)

``` json
"actions" {
  "Send_an_email": {
     /// Other action properties here...
     "parameters:": [
         {
           "name": "Subject",
           "type": "string",
           "description": "Specify the subject of the mail",
           "x-ms-summary": "Subject",
           "x-ms-visibility": "important",
           /// Other parameter properties here
         }
     ]
     /// Other action properties here...
  }
},
```

## <a name="x-ms-dynamic-values"></a>x-ms-dynamic-values
Hiermee wordt een ingevulde lijst weergegeven voor de gebruiker, zodat deze invoerparameters voor een bewerking kan selecteren. </br>
Van toepassing op: parameters </br>
Gebruik: voeg het object `x-ms-dynamic-values` toe aan de parameterdefinitie. Bekijk bijvoorbeeld dit [OpenAPI-voorbeeld](https://procsi.blob.core.windows.net/blog-images/sampleDynamicSwagger.json).

!['x-ms-dynamic-values' voor het weergeven van lijsten](./media/custom-connector-openapi-extensions/x-ms-dynamic-values.png)

### <a name="properties-for-x-ms-dynamic-values"></a>Eigenschappen voor x-ms-dynamic-values
| Naam | Vereist of optioneel | Beschrijving |
| --- | --- | --- |
| **operationID** |Vereist |De bewerking die moet worden aangeroepen voor het invullen van de lijst. |
| **value-path** |Vereist |Een padtekenreeks in het object binnen `value-collection` die naar de parameterwaarde verwijst. Als `value-collection` is niet opgegeven, wordt het antwoord geëvalueerd als een matrix. |
| **value-title** |Optioneel |Een padtekenreeks in het object binnen `value-collection` die naar de beschrijving van de waarde verwijst. Als `value-collection` is niet opgegeven, wordt het antwoord geëvalueerd als een matrix. |
| **value-collection** |Optioneel |Een padtekenreeks waarmee een matrix met objecten in de responslading wordt geëvalueerd |
| **parameters** |Optioneel |Een object waarvan de eigenschappen de invoerparameters opgeven die zijn vereist voor het aanroepen van een bewerking voor dynamic-values |

Hier volgt een voorbeeld met de eigenschappen in `x-ms-dynamic-values`:

``` json
"x-ms-dynamic-values": {
  "operationId": "PopulateDropdown",
  "value-path": "name",
  "value-title": "properties/displayName",
  "value-collection": "value",
  "parameters": {
     "staticParameter": "{value}",
     "dynamicParameter": {
        "parameter": "{value-to-pass-to-dynamicParameter}"
     }
  }
}
```

## <a name="example-all-the-openapi-extensions-up-to-this-point"></a>Voorbeeld: alle OpenAPI-uitbreidingen tot nu toe
``` json
"/api/lists/{listID-dynamic}": {
    "get": {
        "description": "Get items from a single list - uses dynamic values and outputs dynamic schema",
        "summary": "Gets items from the selected list",
        "operationID": "GetListItems",
        "parameters": [
           {
             "name": "listID-dynamic",
             "type": "string",
             "in": "path",
             "description": "Select the list from where you want outputs",
             "required": true,
             "x-ms-summary": "Select List",
             "x-ms-dynamic-values": {
                "operationID": "GetLists",
                "value-path": "id",
                "value-title": "name"
             }
           }
        ]
    }
}
```

## <a name="x-ms-dynamic-schema"></a>x-ms-dynamic-schema
Hiermee wordt aangegeven dat het schema voor de huidige parameter of reactie dynamisch is. Met dit object kan een bewerking worden aangeroepen die wordt gedefinieerd door de waarde van dit veld en kan het schema dynamisch worden ontdekt. Daarnaast kan de juiste gebruikersinterface worden weergegeven voor het verzamelen van gebruikersinvoer en kunnen beschikbare velden worden weergegeven. 

Van toepassing op: parameters, antwoord

Gebruik: voeg het object `x-ms-dynamic-schema` toe aan een aanvraagdefinitie of antwoordtekstdefinitie. Bekijk bijvoorbeeld dit [OpenAPI-voorbeeld](https://procsi.blob.core.windows.net/blog-images/sampleDynamicSwagger.json).

In dit voorbeeld ziet u hoe het invoerformulier verandert op basis van het item dat de gebruiker selecteert in de vervolgkeuzelijst:

!['x-ms-dynamic-schema' voor dynamische parameters](./media/custom-connector-openapi-extensions/x-ms-dynamic-schema.png)

En in dit voorbeeld ziet u hoe de uitvoer verandert op basis van het item dat de gebruiker selecteert in de vervolgkeuzelijst. In deze versie selecteert de gebruiker 'Auto's':

!['x-ms-dynamic-schema-response' voor geselecteerd item 'Auto's'](./media/custom-connector-openapi-extensions/x-ms-dynamic-schema-output1.png)

In deze versie selecteert de gebruiker 'Eten':

!['x-ms-dynamic-schema-response' voor geselecteerd item 'Eten'](./media/custom-connector-openapi-extensions/x-ms-dynamic-schema-output2.png)

### <a name="properties-for-x-ms-dynamic-schema"></a>Eigenschappen voor x-ms-dynamic-schema
| Naam | Vereist of optioneel | Beschrijving |
| --- | --- | --- |
| **operationID** |Vereist |De bewerking die moet worden aangeroepen voor het ophalen van het schema. |
| **parameters** |Vereist |Een object waarvan de eigenschappen de invoerparameters opgeven die zijn vereist voor het aanroepen van een bewerking voor dynamic-schema |
| **value-path** |Optioneel |Een padtekenreeks die verwijst naar de eigenschap met het schema. </br>Als dit niet wordt opgegeven, wordt ervan uitgegaan dat het antwoord het schema bevat in de eigenschappen van het hoofdobject. |
|  | | |

Hier volgt een voorbeeld van een dynamische parameter:

``` json
{
  "name": "dynamicListSchema",
  "in": "body",
  "description": "Dynamic schema for items in the selected list",
  "schema": {
    "type": "object",
    "x-ms-dynamic-schema": {
        "operationID": "GetListSchema",
        "parameters": {
          "listID": {
            "parameter": "listID-dynamic"
          }
        },
        "value-path": "items"
    }
  }
}
```

Hier volgt een voorbeeld van een dynamisch antwoord:

``` json
"DynamicResponseGetListSchema": {
   "type": "object",
   "x-ms-dynamic-schema": {
      "operationID": "GetListSchema",
      "parameters": {
         "listID": {
            "parameter": "listID-dynamic"
         }
      },
      "value-path": "items"
    }
}
```

## <a name="next-steps"></a>Volgende stappen
[Een aangepaste connector registreren](register-custom-api.md).

[Gebruik een ASP.NET Web-API](customapi-web-api-tutorial.md).

[Registreer een Azure Resource Manager-API](customapi-azure-resource-manager-tutorial.md).

