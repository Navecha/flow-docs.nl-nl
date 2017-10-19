---
title: Een aangepaste connector met Postman beschrijven | Microsoft Docs
description: Een Postman Collection maken voor het registreren van aangepaste connectors
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
ms.date: 04/28/2017
ms.author: sunayv
ms.openlocfilehash: fe98999ea307367c7f3b032974fef9be6ca3f388
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/15/2017
---
# <a name="describe-a-custom-connector-with-postman"></a>Een aangepaste connector met Postman beschrijven
[Postman](https://www.getpostman.com/) is een hulpmiddel waarmee u sneller en gemakkelijker API’s kunt ontwikkelen. Deze zelfstudie laat zien hoe u een Postman Collection kunt maken die u vervolgens kunt gebruiken om gemakkelijk [aangepaste connectors](register-custom-api.md) in Microsoft Flow te maken.

## <a name="prerequisites"></a>Vereisten
* Installeer de [Postman-app](https://www.getpostman.com/apps).

## <a name="create-a-postman-collection"></a>Een Postman Collection maken
U gaat nu Postman Collection bouwen voor de [Tekstanalyse-API](https://www.microsoft.com/cognitive-services/text-analytics-api) van Azure Cognitive Services. Deze API identificeert de taal, de gevoelswaarde en belangrijke zinnen in de tekst waarop u de API uitvoert.

1. De eerste stap bij het maken van een Postman Collection bestaat eruit om een aanvraag te maken. Bij het maken van de aanvraag kunt u de HTTP-term, de aanvraag-URL, query- of padparameters, headers en de hoofdtekst instellen. Zie [Sending Requests](https://www.getpostman.com/docs/requests) (Aanvragen verzenden) in de documentatie bij Postman voor meer informatie. Voor het eindpunt van de Taal detecteren-API moet u de waarden als volgt instellen:
   
    ![Postman-aanvraag](./media/postman-collection/request.png)
   
    Details van parameters en gebruikte waarden:
   
   | Parameter | Waarde |
   | --- | --- |
   | Term |POST |
   | Aanvraag-URL |https://westus.api.cognitive.microsoft.com/text/analytics/v2.0/languages |
   | Parameters |numberOfLanguagesToDetect |
   | Autorisatie |'Geen Auth' |
   | Headers |Ocp-Apim-Subscription-Key = <your subscription key> <br/>Content-Type = application/json |
   | Hoofdtekst |<code>{<br/>&nbsp;&nbsp;&nbsp;"documents": [<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"id": "1",<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"text": "Hello World"<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}<br/>&nbsp;&nbsp;]<br/>}<code> |
2. Klik op **Send** (Verzenden) om de aanvraag te maken en een antwoord terug te ontvangen.
3. Klik op **Save** (Opslaan) om de aanvraag in een Postman Collection op te slaan.
   
    ![Postman-antwoord](./media/postman-collection/request-response-save.png)
4. Geef een **Request name** (Naam aanvraag) en **Request description** (Beschrijving aanvraag) op in het dialoogvenster **Save Request** (Aanvraag opslaan). Deze waarden gaat u gebruiken in uw aangepaste connector.
   
    ![Opgeslagen Postman Collection](./media/postman-collection/save-request-note.png)
   
    U kunt ook het antwoord op de aanvraag opslaan. Aangepaste connectors ondersteunen momenteel uitsluitend één antwoord per aanvraag. Als u meerdere antwoorden per aanvraag opslaat, wordt alleen het eerste gebruikt.
   
    ![Opslaan Postman-antwoord](./media/postman-collection/save-response.png)
5. Ga verder met het bouwen van uw Postman Collection door meer aanvragen en antwoorden te maken en op te slaan.
6. Als u klaar bent met het bouwen van de Postman Collection Postman voor alle aanvragen en antwoorden, exporteert u de verzameling.
   
    ![Exporteren met Postman](./media/postman-collection/export.png)
7. Kies **Collection v1** (Verzameling v1) als exportindeling.
   
    ![Exporteren met Postman](./media/postman-collection/export2.png)

U kunt deze Postman Collection nu gebruiken om een aangepaste connector in Microsoft Flow te maken.

> [!IMPORTANT]
> Als u een aangepaste connector uit een Postman-verzameling maakt, moet u de header `Content-type` uit de acties en triggers verwijderen. Deze wordt namelijk automatisch door Microsoft Flow toegevoegd. Verificatieheaders (zoals `Ocp-Apim-Subscription-Key`) moeten worden gedefinieerd in het gedeelte **Beveiliging** en uit de acties en triggers worden verwijderd. 
> 
> 

Zie voor meer informatie [Register and use custom connectors in Microsoft Flow](register-custom-api.md) (Aangepaste connectors registreren en gebruiken in Microsoft Flow).

