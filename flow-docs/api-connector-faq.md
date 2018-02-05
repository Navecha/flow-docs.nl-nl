---
title: Veelgestelde vragen over API-connector | Microsoft Docs
description: Vind antwoorden op vragen over vereisten, triggers en andere onderwerpen.
services: 
suite: flow
documentationcenter: na
author: asavaritayal
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/19/2017
ms.author: astay
ms.openlocfilehash: 1715700fa6a94bb35733865556a2c9be0ba3ce9f
ms.sourcegitcommit: f3236f9f1ec050cda0d9c3e2b9c356132b2a2594
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/30/2018
---
# <a name="api-connector-faq-microsoft-flow"></a>Veelgestelde vragen over API-connector (Microsoft Flow)
## <a name="requirements"></a>Vereisten
**V:** Kan ik een connector zonder REST-API's maken? </br>
**A:** Nee, uw service moet stabiele HTTP REST-API's ondersteunen om een connector te kunnen maken. 

**V:** Welke hulpprogramma's kan ik gebruiken om een connector te maken? </br>
**A:** Azure bevat functionaliteit en services die u kunt gebruiken om services weer te geven als een API, zoals Azure App Service voor het hosten, API Management en meer.

**V:** Welke verificatietypen worden ondersteund? </br>
**A:** U kunt de volgende ondersteunde verificatiestandaarden gebruiken:

* [OAuth 2.0](https://oauth.net/2/), waaronder [Azure Active Directory](https://azure.microsoft.com/develop/identity/) of specifieke services, zoals Dropbox, GitHub en SalesForce
* Algemene OAuth 2.0
* [Basisverificatie](https://swagger.io/docs/specification/authentication/basic-authentication/)
* [API-sleutel](https://swagger.io/docs/specification/authentication/api-keys/)

## <a name="triggers"></a>Triggers
**V:** Kan ik triggers maken zonder webhooks? </br>
**A:** Nee, aangepaste connectors voor Azure Logic Apps en Microsoft Flow ondersteunen alleen triggers met webhooks. Als u andere patronen wilt aanvragen voor implementatie, neemt u contact op met [condevhelp@microsoft.com](mailto:condevhelp@microsoft.com) met meer informatie over uw API.

## <a name="certification"></a>Certificering
**V**: Ik ben niet een Microsoft-partner of onafhankelijke softwareleverancier. Kan ik toch connectors maken? </br>
**A:** Ja, u kunt deze connectors registreren voor intern gebruik in uw organisatie. Als u een connector wilt certificeren en openbaar beschikbaar wilt maken, moet u eigenaar zijn van de onderliggende service of aantonen dat u expliciete rechten hebt voor het gebruik van de API.

## <a name="other"></a>Overig
**V:** Mijn API's gebruiken een dynamische host. Hoe kan ik deze implementeren met OpenAPI? </br>
**A:** Aangepaste connectors bieden geen ondersteuning voor dynamische hosts. Gebruik in plaats hiervan een statische host voor ontwikkel- en testdoeleinden. Als u uw connector wilt certificeren, vraagt u uw Microsoft-contactpersoon over dynamische implementatie.

**V:** Biedt u ondersteuning voor Postman Collection V2? </br>
**A:** Nee, momenteel wordt alleen Postman Collection V1 ondersteund.

**V:** Biedt u ondersteuning voor OpenAPI 3.0? </br>
**A:** Nee, momenteel wordt alleen OpenAPI 2.0 ondersteund.

