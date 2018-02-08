---
title: Microsoft Flow voor ontwikkelaars in organisaties, ISV's en partners | Microsoft Docs
description: Een inleiding tot het ontwikkelen van oplossingen voor Microsoft Flow.
services: 
suite: flow
documentationcenter: na
author: mgblythe
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2018
ms.author: mblythe
ms.openlocfilehash: 3e6a6e0e369f8d89dcf834b4225dfd5aa4758dd7
ms.sourcegitcommit: b943fa83d7ca2d1a313c0c7b2cf0d7e4a9528b85
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/05/2018
---
# <a name="microsoft-flow-for-enterprise-developers-isvs-and-partners"></a>Microsoft Flow voor ontwikkelaars in organisaties, ISV's en partners

Als ontwikkelaar kunt u Microsoft Flow uitbreiden zodat u nog krachtigere oplossingen kunt ontwikkelen voor organisaties en klanten.

## <a name="microsoft-flow-for-enterprise-developers"></a>Microsoft Flow voor ontwikkelaars in organisaties

Als ontwikkelaar in een organisatie kunt u uw organisatie in staat stellen om robuuste, op maat gemaakte oplossingen te maken met Microsoft Flow:

- **Maak aangepaste connectors**: Ontwikkel aangepaste connectors om gegevens en webservices van uw organisatie te koppelen via Microsoft Flow. [Meer informatie](https://docs.microsoft.com/connectors/custom-connectors/)

- **Maak Azure Functions**: Ontwikkel Azure Functions om apps uit te breiden met aangepaste logica aan de serverzijde. [Meer informatie](https://docs.microsoft.com/azure/azure-functions/functions-flow-scenario)

- **Sluit Microsoft Flow in**: Maak geïntegreerde oplossingen door Microsoft Flow rechtstreeks in de website-ervaring in te sluiten en maak duidelijk zichtbaar bij welke werkstromen of processen mensen in uw organisatie met hun werk betrokken zijn. [Meer informatie](embed-flow-dev.md)

## <a name="microsoft-flow-for-isvs-and-microsoft-partners"></a>Microsoft Flow voor ISV's en Microsoft-partners

Als Microsoft-partner of Independent Software Vendor (ISV) kunt u een snellere acceptatie door de klant bewerkstelligen door uw producten zo uit te breiden dat deze worden geïntegreerd met de gegevens en bedrijfsprocessen van uw klanten en door werkstromen toe te voegen en aan te passen om bedrijfsprocessen als onderdeel van de toepassing te automatiseren. Nadat u de onderstaande zeven stappen hebt voltooid, kan uw toepassing gebruikmaken van een robuuste engine voor werkstromen op cloudschaal waarmee verbinding met meer dan 200 verschillende services kan worden gemaakt.

| Fase | Stap | Wanneer nodig? |
| --- | --- | --- |
| Ontwikkeling | 1. Een aangepaste connector ontwikkelen voor uw gegevens | Als u uw ISV-gegevens beschikbaar wilt maken voor PowerApps of Microsoft Flow |
| Ontwikkeling | 2. Ondersteuning voor uw toepassing toevoegen om gebruikers met Azure Active Directory (Azure AD) te verifiëren | Als u de Microsoft Flow-gebruikersinterface wilt insluiten of wilt vermelden in Microsoft AppSource | 
| Ontwikkeling | 3. De Microsoft Flow-gebruikersinterface insluiten in uw toepassing met behulp van onze web-iframe | Als u het maken of beheren van stromen wilt opnemen in uw toepassing | 
| Ontwikkeling | 4. Stroomsjablonen maken en publiceren | Als u vooraf stromen voor uw klanten wilt maken | 
| Ontwikkeling | 5. Toepassingslogica toevoegen om programmatisch stromen te implementeren | Als u automatisch vooraf gemaakte stromen voor uw klanten wilt implementeren | 
| Distributie | 6. Uw klanten licenties verlenen voor Microsoft Flow via het Microsoft Cloud Solution Provider-programma | Als uw klanten niet beschikken over Office 365- of Dynamics 365-licenties |
| Distributie | 7. Uw oplossing op Microsoft AppSource vermelden | Aanbevolen om de zichtbaarheid van uw ISV-oplossing te verhogen |

### <a name="1-connecting-to-your-apis-or-enabling-customers-to-connect-to-your-apis"></a>1. Verbinding maken met uw API's OF inschakelen dat klanten verbinding kunnen maken met uw API's

Als ISV hebt u vaak eigen gegevens waartoe klanten toegang moeten krijgen via uw stromen. U kunt toegang tot uw gegevens beschikbaar maken door middel van een aangepaste connector. [Meer informatie](https://docs.microsoft.com/en-us/connectors/custom-connectors/)

Als de connector is gemaakt, kan deze op twee manieren beschikbaar worden gemaakt voor uw klanten:
- De connector kan worden geïmplementeerd in de tenant van de klant via REST API's of PowerShell.
- Als u de aangepaste connector openbaar beschikbaar wilt maken voor alle gebruikers, kunt u uw connector voor certificering indienen. [Meer informatie](https://docs.microsoft.com/connectors/custom-connectors/submit-certification)

### <a name="2-authentication"></a>2. Verificatie 

Voor het aanroepen van REST API's en insluiten van een geverifieerde gebruikersinterface moet uw toepassing federatieve eenmalige aanmelding van Azure AD gebruiken om eindgebruikers en klanten te verifiëren. [Hier](https://identity.microsoft.com/) vindt u informatie over het inschakelen van federatieve SSO van AAD. We bieden geen ondersteuning voor niet-geverifieerde toegang of toegang met andere identiteitsproviders dan Azure AD. 

### <a name="3-embedding-ui-components"></a>3. Onderdelen van de gebruikersinterface insluiten

Sluit Microsoft Flow in uw app in om een diepgaande integratie binnen de context in te schakelen tussen uw app en alle andere services die Microsoft Flow ondersteunt. [Meer informatie](embed-flow-dev.md)

### <a name="4-create-and-publish-flow-templates"></a>4. Stroomsjablonen maken en publiceren

Zodra u over een connector beschikt, moet u sjablonen publiceren die laten zien hoe uw service moet worden gebruikt. Deze sjablonen dienen als voorbeelden die door gebruikers gebruikt kunnen worden, en vervolgens kunnen worden uitgebreid naar hun eigen unieke werkstromen. [Meer informatie](publish-a-template.md)

### <a name="5-deployment"></a>5. Implementatie

Als u eindgebruikers toegang wilt verlenen voor stromen die automatisch kunnen worden gebruikt, implementeert u de stromen in de Azure AD-tenant van de gebruiker. Gebruik een implementatiepakket dat u implementeert met onze REST API's of PowerShell. [Meer informatie](https://docs.microsoft.com/powerapps/export-import-packages)

### <a name="6-licensing"></a>6. Licentieverlening

Als uw klanten al werken met Office 365 of Dynamics 365 en de licenties zijn gekoppeld aan de identiteiten die worden gebruikt om met Azure AD aan te melden, hoeft u niet aan aanvullende licentievereisten te voldoen. Als uw klanten echter niet met Office 365 of Dynamics 365 werken, moet u namens uw klanten gebruiksrechten voor Microsoft Flow verkrijgen, zodat ze een licentie hebben om die ingesloten onderdelen in uw toepassing te gebruiken.

Wij bieden het [Microsoft Cloud Solution Provider](https://partner.microsoft.com/en-US/cloud-solution-provider)-programma om licenties namens uw klanten te verkrijgen. Er zijn twee verschillende [prijsplannen](https://flow.microsoft.com/pricing/) beschikbaar voor Microsoft Flow. Raadpleeg deze voor informatie over de plannen en functies.

### <a name="7-list-on-appsource"></a>7. Vermelden op AppSource

Nadat u Microsoft Flow in uw toepassing hebt geïntegreerd, kunt u het vermelden op AppSource. Met AppSource kunt u nieuwe leads voor uw bedrijf genereren door een app te bouwen en deze naar AppSource te publiceren om door nieuwe klanten te worden uitgeprobeerd. [Meer informatie](dev-appsource-test-drive.md)
