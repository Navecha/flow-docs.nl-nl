---
title: Microsoft Flow voor Enter prise-ontwikkel aars, Isv's en partners | Microsoft Docs
description: Een inleiding tot het ontwikkelen van oplossingen voor Microsoft Flow.
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2018
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: f26143533e84bc3ea8bc0784fef3c56eeb0551e1
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547837"
---
# <a name="microsoft-flow-for-enterprise-developers-isvs-and-partners"></a>Microsoft Flow voor bedrijfs ontwikkelaars, Isv's en partners
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Als ontwikkelaar kunt u Microsoft Flow uitbreiden, waardoor er nog krachtiger oplossingen voor organisaties en klanten mogelijk zijn.

## <a name="microsoft-flow-for-enterprise-developers"></a>Microsoft Flow voor bedrijfs ontwikkelaars

Als bedrijfs ontwikkelaar kunt u uw organisatie in staat stellen om robuuste oplossingen op basis van Microsoft Flow te bouwen:

- **Bouw aangepaste connectors**: ontwikkel aangepaste connectors om verbinding te maken met de gegevens en webservices van uw organisatie via Microsoft flow. [Meer informatie](https://docs.microsoft.com/connectors/custom-connectors/)

- **Bouw Azure functions**: Craft Azure functions om apps uit te breiden met aangepaste logica aan de server zijde. [Meer informatie](/azure/azure-functions/app-service-export-api-to-powerapps-and-flow)

- **Insluiten Microsoft flow**: u kunt Microsoft flow rechtstreeks insluiten in uw website-ervaring om geïntegreerde oplossingen, halen werk stromen of processen te maken waarbij personen in uw organisatie al hun werk doen. [Meer informatie](embed-flow-dev.md)

## <a name="microsoft-flow-for-isvs-and-microsoft-partners"></a>Microsoft Flow voor Isv's en micro soft-partners

Als een micro soft-partner of Independent Software Vendor (ISV) kunt u de acceptatie van klanten versnellen door uw producten uit te breiden om te integreren met de gegevens en bedrijfs processen van uw klanten en om werk stromen toe te voegen en aan te passen om bedrijfs processen te automatiseren als onderdeel van uw modules. Nadat u de onderstaande zeven stappen hebt voltooid, kan uw toepassing gebruikmaken van een robuuste werk stroom engine voor de Cloud schaal die verbinding kan maken met 200 en verschillende services.

| Partition | Wizardstap | Wanneer dit nodig is? |
| --- | --- | --- |
| Softwareontwikkeling | 1. een aangepaste connector maken voor uw gegevens | Als u uw eigen ISV-gegevens beschikbaar wilt maken voor PowerApps of Microsoft Flow |
| Softwareontwikkeling | 2. Voeg ondersteuning toe voor uw toepassing om gebruikers te verifiëren met Azure Active Directory (Azure AD) | Als u de Microsoft Flow gebruikers interface of lijst in Microsoft AppSource wilt insluiten | 
| Softwareontwikkeling | 3. de Microsoft Flow gebruikers interface insluiten in uw toepassing met behulp van onze op het web gebaseerde IFRAME | Als u het maken van een stroom of het beheer wilt toevoegen aan uw toepassing | 
| Softwareontwikkeling | 4. stroom sjablonen maken en publiceren | Als u stromen vooraf wilt maken voor uw klanten | 
| Softwareontwikkeling | 5. toepassings logica toevoegen om programmatische stromen te implementeren | Als u uw vooraf gemaakte stromen automatisch wilt implementeren voor uw klanten | 
| Deel | 6. Verleen uw klanten licenties voor Microsoft Flow via het Microsoft Cloud Solution Provider-programma | Als uw klanten geen Office 365-of Dynamics 365-licenties hebben |
| Deel | 7. vermeld uw oplossing op Microsoft AppSource | Aanbevolen om de zicht baarheid van uw ISV-oplossing te verg Roten |

### <a name="1-connecting-to-your-apis-or-enabling-customers-to-connect-to-your-apis"></a>1. verbinding maken met uw Api's of klanten in staat stellen verbinding te maken met uw Api's

Als ISV maakt u vaak eigen gegevens die klanten via uw stromen kunnen benaderen. U kunt toegang tot uw gegevens beschikbaar maken via een aangepaste connector. [Meer informatie](https://docs.microsoft.com/connectors/custom-connectors/)

Nadat u een connector hebt gemaakt, kunt u deze op twee manieren beschikbaar maken voor uw klanten:
- De connector kan worden geïmplementeerd in de Tenant van de klant via REST Api's of Power shell.
- Als u de aangepaste connector openbaar beschikbaar wilt maken voor alle gebruikers, kunt u uw connector voor certificering indienen. [Meer informatie](https://docs.microsoft.com/connectors/custom-connectors/submit-certification)

### <a name="2-authentication"></a>2. verificatie 

Voor het aanroepen van REST Api's en het insluiten van geverifieerde gebruikers interface, moet uw toepassing gebruikmaken van de federatieve eenmalige aanmelding van Azure AD om eind gebruikers en klanten te verifiëren. [Hier](https://identity.microsoft.com/) vindt u informatie over het inschakelen van Aad Federated SSO. We bieden geen ondersteuning voor niet-geverifieerde toegang of toegang tot andere id-providers dan Azure AD. 

### <a name="3-embedding-ui-components"></a>3. UI-onderdelen insluiten

Sluit Microsoft Flow in uw app in om een diep gaande integratie binnen de context in te scha kelen tussen uw app en alle andere services die Microsoft Flow ondersteunt. [Meer informatie](embed-flow-dev.md)

### <a name="4-create-and-publish-flow-templates"></a>4. stroom sjablonen maken en publiceren

Zodra u een connector hebt, moet u sjablonen publiceren die laten zien hoe u uw service kunt gebruiken. Deze sjablonen dienen als voor beelden die gebruikers kunnen gebruiken om te leren en vervolgens uit te breiden naar hun eigen unieke werk stromen. [Meer informatie](../publish-a-template.md)

### <a name="5-deployment"></a>5. implementatie

Als u eind gebruikers toegang wilt geven tot stromen die ze automatisch kunnen gebruiken, implementeert u de stromen in de Azure AD-Tenant van de gebruiker. Gebruik een implementatie pakket dat u implementeert met behulp van onze REST Api's of Power shell. [Meer informatie](https://docs.microsoft.com/powerapps/export-import-packages)

### <a name="6-licensing"></a>6. licentie verlening

Als uw klanten al beschikken over Office 365 of Dynamics 365 en deze licenties zijn gekoppeld aan de identiteiten die gebruikers aanmelden met Azure AD, zijn er geen aanvullende licentie vereisten voor u. Als uw klanten echter geen gebruikmaken van Office 365 of Dynamics 365, moet u voor Microsoft Flow gebruik rechten verwerven, zodat ze een licentie hebben om de Inge sloten onderdelen in uw toepassing te gebruiken.

We bieden het [Microsoft Cloud Solution Provider](https://partner.microsoft.com/cloud-solution-provider) -programma om licenties te verkrijgen namens uw klanten. Er zijn twee verschillende [prijs plannen](https://flow.microsoft.com/pricing/) beschikbaar voor Microsoft flow, die u moet controleren op plan-en functie gegevens.

### <a name="7-list-on-appsource"></a>7. lijst op AppSource

Zodra u Microsoft Flow in uw toepassing hebt geïntegreerd, kunt u deze weer geven op AppSource. Met AppSource kunt u nieuwe leads voor uw bedrijf genereren door een app te bouwen en deze te publiceren naar AppSource voor nieuwe klanten om de schijf te testen. [Meer informatie](dev-appsource-test-drive.md)
