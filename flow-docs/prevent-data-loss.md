---
title: Inleiding tot beleid voor preventie van gegevensverlies (DLP). | Microsoft Docs
description: Inleiding tot beleid voor preventie van gegevensverlies voor Microsoft Flow.
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/24/2016
ms.author: deonhe
ms.openlocfilehash: 29eaa9299e09c641538ab8f9dfbc9954bca66a3b
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/15/2017
---
# <a name="data-loss-prevention-dlp-policies"></a>Beleid voor preventie van gegevensverlies (DLP)
## <a name="what-is-a-data-loss-prevention-policy"></a>Wat is beleid voor preventie van gegevensverlies?
De gegevens van een organisatie zijn essentieel voor het succes. De gegevens moeten direct beschikbaar zijn voor de besluitvorming, maar moeten worden beveiligd, zodat deze niet worden gedeeld met doelgroepen die geen toegang mogen hebben. Voor het beveiligen van deze gegevens biedt Microsoft Flow (Flow) de mogelijkheid om beleidsregels te maken welke consumentservices/connectorspecifieke zakelijke gegevens mogen worden gedeeld, en deze af te dwingen. Deze beleidsregels waarin wordt gedefinieerd hoe gegevens kunnen worden gedeeld, worden beleid voor preventie van gegevensverlies (DLP) genoemd.

## <a name="why-create-a-dlp-policy"></a>Waarom maakt u een DLP-beleid?
U kunt een DLP-beleid maken om helder te definiëren welke zakelijke gegevens van consumentservices mogen worden gedeeld. Mogelijk wil een organisatie die gebruikmaakt van Flow niet dat de zakelijke gegevens die zijn opgeslagen in SharePoint automatisch worden gepubliceerd naar de Twitter-feed. Om dit te voorkomen, kunt u een DLP-beleid maken waarmee het gebruik van SharePoint-gegevens als bron voor tweets wordt geblokkeerd.

## <a name="benefits-of-a-dlp-policy"></a>Voordelen van een DLP-beleid
* Zorgt ervoor dat gegevens in de hele organisatie op een uniforme wijze worden beheerd  
* Voorkomt dat belangrijke zakelijke gegevens per ongeluk wordt gepubliceerd naar services als sociale mediasites.   

## <a name="managing-dlp-policies"></a>DLP-beleid beheren
**Vereisten**  
Als u DLP-beleid wilt maken, bewerken of verwijderen, zijn de volgende items vereist: 

* Machtigingen voor omgevingsbeheerders of tenantbeheerders. In het [onderwerp over omgevingen](environments-overview-admin.md) vindt u meer informatie over machtigingen.  
* Een [Flow P2-licentie](billing-questions.md).  

## <a name="create-a-dlp-policy"></a>Een DLP-beleid maken
**Vereisten**  
Als u een DLP-beleid wilt maken, moet u machtigingen hebben voor ten minste één omgeving.  

Volg de onderstaande stappen om een DLP-beleid te maken waarmee wordt voorkomen dat gegevens die zijn opgeslagen in uw bedrijfs-SharePoint worden gepubliceerd naar Twitter:  

1. Selecteer op het tabblad Gegevensbeleid de koppeling **Nieuw beleid**:  
   ![Aanmelden](./media/prevent-data-loss/create-policy-1.png)    
2. Voer de naam in voor het DLP-beleid als *Beveiligde gegevenstoegang voor Contoso* in het label **Naam gegevensbeleid** boven aan de pagina die wordt geopend:   
   ![Aanmelden](./media/prevent-data-loss/create-policy-2.png)  
3. Selecteer de [omgeving](environments-overview-admin.md) op het tabblad **Van toepassing op**.  
   **Opmerking:** als omgevingsbeheerder kunt u slechts beleidsregels maken die betrekking hebben op één omgeving. Als tenantbeheerder kunt u een beleid maken dat van toepassing is op alle omgevingen, een of meer geselecteerde omgevingen of alle omgevingen met uitzondering van een bepaalde verzameling:  
   ![Aanmelden](./media/prevent-data-loss/create-policy-3.png)  
4. Selecteer het tabblad **Gegevensgroepen**:  
   ![Aanmelden](./media/prevent-data-loss/create-policy-4.png)  
5. Selecteer de koppeling **+ Toevoegen** binnen het groepsvak **Alleen bedrijfsgegevens**:    
   ![Aanmelden](./media/prevent-data-loss/create-policy-5.png)  
6. Selecteer de **SharePoint**- en **Salesforce**-services op de pagina **Services toevoegen**:  
   ![Aanmelden](./media/prevent-data-loss/create-policy-6.png)  
7. Selecteer de knop **Services toevoegen** om services toe te voegen die zakelijke gegevens mogen delen:    
   ![Aanmelden](./media/prevent-data-loss/create-policy-7.png)  
8. Selecteer **Beleid opslaan**:  
   ![Aanmelden](./media/prevent-data-loss/create-policy-8.png)  
9. Na enkele ogenblikken wordt uw nieuwe DLP-beleid weergegeven in de lijst met beleidsregels voor preventie van gegevensverlies:  
   ![Aanmelden](./media/prevent-data-loss/create-policy-9.png)  
10. **Optioneel**: verzendt een e-mail of ander bericht naar uw team waarin u hen erop attent maakt dat er een nieuw DLP-beleid beschikbaar is.

U hebt nu een DLP-beleid gemaakt waarmee de app gegevens kan delen tussen SharePoint en Saleforce en waarmee het delen van gegevens met andere services wordt geblokkeerd.  

**Opmerking**: Als u een service toevoegt aan een gegevensgroep, wordt deze automatisch uit de andere gegevensgroep verwijderd. Als Twitter zich bijvoorbeeld momenteel bevindt in de gegevensgroep met **alleen zakelijke gegevens**, en u niet wilt dat zakelijke gegevens met Twitter worden gedeeld, voegt u de Twitter-service toe aan de gegevensgroep waarin **geen zakelijke gegevens zijn toegestaan**. Hiermee wordt Twitter verwijderd uit de gegevensgroep met alleen zakelijke gegevens.  

## <a name="data-sharing-violations"></a>Fouten bij het delen van gegevens
Als u het hierboven beschreven DLP-beleid hebt gemaakt, ontvangt een gebruiker die een stroom maakt waarmee de gegevens worden gedeeld tussen Salesforce (in de gegevensgroep met **alleen zakelijke gegevens**) en Twitter (in de gegevensgroep waarin **geen zakelijke gegevens zijn toegestaan**) de melding dat de stroom tijdelijk is **onderbroken** vanwege een conflict met het beleid voor preventie van gegevensverlies.  
![stroom maken](./media/prevent-data-loss/10.png)  

Als uw gebruikers contact met u opnemen over de onderbroken stromen, kunt u het volgende overwegen:  

1. Voor dit voorbeeld geldt dat u het DLP-beleid kunt bewerken wanneer er een geldige zakelijke reden is om zakelijke gegevens te delen tussen SharePoint en Twitter.  
2. Vraag de gebruiker om de stroom te bewerken zodat de stroom voldoet aan het DLP-beleid.  
3. Vraag de gebruiker de onderbroken status van stroom te handhaven totdat er een beslissing is genomen over het delen van gegevens tussen deze twee entiteiten.  

## <a name="find-a-dlp-policy"></a>Een DLP-beleid vinden
### <a name="admins"></a>Beheerders
Beheerders kunnen de zoekfunctie gebruiken in het Beheercentrum om specifiek DLP-beleid te vinden.  

**OPMERKING** beheerders moeten alle DLP-beleidsregels publiceren zodat gebruikers in de organisatie zich bewust zijn van de beleidsregels voordat ze stromen maken.

### <a name="makers"></a>Makers
Als u geen beheerdersmachtigingen hebt en graag meer wilt weten over DLP-beleidsregels in uw organisatie, neemt u contact op met de beheerder. Ook in het [onderwerp over makersomgevingen](environments-overview-maker.md) vindt u meer informatie  

**OPMERKING** alleen beheerders kunnen DLP-beleid bewerken of verwijderen.  

## <a name="edit-a-dlp-policy"></a>Een DLP-beleid bewerken
1. Start het beheercentrum door te bladeren naar https://admin.flow.microsoft.com.  
2. Selecteer in het beheercentrum dat wordt gestart de koppeling **Gegevensbeleid** aan de linkerkant.  
   ![Aanmelden](./media/prevent-data-loss/2.png)  
3. Zoek in de lijst met bestaand DLP-beleid en selecteer de knop Bewerken naast het beleid dat u wilt bewerken:  
   ![Aanmelden](./media/prevent-data-loss/3.png)  
4. Breng de gewenste wijzigingen aan. U kunt bijvoorbeeld de omgeving of de services in de gegevensgroepen wijzigen.  
5. Selecteer **Beleid opslaan** om uw wijzigingen op te slaan:  
   ![Aanmelden](./media/prevent-data-loss/create-policy-8.png)  

Het beleid is nu bijgewerkt. U kunt bevestigen dat de wijzigingen zijn aangebracht aan het beleid door het beleid op te zoeken in de lijst met beleidsregels voor preventie van gegevensverlies en de eigenschappen ervan te controleren.   

**Opmerking** DLP-beleidsregels die zijn gemaakt door tenantbeheerders kunnen worden bekeken door omgevingsbeheerders, maar kunnen niet worden bewerkt door deze omgevingsbeheerders.  

## <a name="delete-a-dlp-policy"></a>Een DLP-beleid verwijderen
1. Start het beheercentrum door te bladeren naar https://admin.flow.microsoft.com.  
2. Selecteer in het beheercentrum dat wordt gestart de koppeling **Gegevensbeleid** aan de linkerkant.  
   ![Aanmelden](./media/prevent-data-loss/2.png)  
3. Zoek in de lijst met bestaand DLP-beleid en selecteer de knop Verwijderen naast het beleid dat u wilt verwijderen:  
   ![Aanmelden](./media/prevent-data-loss/3-delete.png)  
4. Bevestig dat u het beleid echt verwijderen door de knop **Verwijderen** te selecteren:  
   ![Aanmelden](./media/prevent-data-loss/4.png)  

Het beleid is nu verwijderd. Selecteer de koppeling **Gegevensbeleid** aan de linkerkant en bekijk de lijst met beleidsregels om te controleren of het beleid niet meer voorkomt in de lijst met beleidsregels voor preventie van gegevensverlies.   

## <a name="dlp-policy-permissions"></a>Machtigingen voor DLP-beleid
Alleen tenant- en omgevingsbeheerders kunnen DLP-beleid maken en wijzigen. In het onderwerp over [omgevingen](environments-overview-admin.md) vindt u meer informatie over machtigingen.  

## <a name="next-steps"></a>Volgende stappen
* [Meer informatie over omgevingen](environments-overview-admin.md)  
* [Meer informatie over Microsoft Flow](getting-started.md)  
* [Meer informatie over het beheercentrum](introduction-to-the-admin-center.md)  

