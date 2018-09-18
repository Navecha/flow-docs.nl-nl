---
title: Een goedkeuringslus maken met de Common Data Service | Microsoft Docs
description: Maak een entiteit, een stroom en een app die samenwerken, zodat revisoren bestanden die zijn toegevoegd aan Dropbox, kunnen goedkeuren of afwijzen.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/22/2016
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 6c48d79138dfdafa94e56380343840d6aa0fcbb5
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690854"
---
# <a name="build-an-approval-loop-by-using-microsoft-flow-and-the-microsoft-common-data-service"></a>Maak een goedkeuringslus met Microsoft Flow en de Microsoft Common Data Service
Met de Common Data Service hebt u een methode in handen waarmee u stromen kunt opzetten waarbij informatie is opgeslagen in een database die onafhankelijk is van een stroom. Dit kan het beste worden geïllustreerd met goedkeuringen. Als u de status van de goedkeuring in een entiteit opslaat, kan uw stroom daar boven op werken.

In dit voorbeeld zet u een goedkeuringsproces op dat begint wanneer een gebruiker een bestand toevoegt aan Dropbox. Wanneer het bestand wordt toegevoegd, wordt informatie hierover weergegeven in een app. Een revisor kan de wijziging vervolgens goedkeuren of afwijzen. Wanneer de revisor de wijziging heeft goedgekeurd of afgewezen, wordt er een e-mailmelding verzonden en worden de afgewezen bestanden verwijderd uit Dropbox.

Door de stappen in dit gedeelte te volgen, maakt u het volgende:

* Een **aangepaste entiteit** met informatie over elk bestand dat is toegevoegd aan Dropbox en of het bestand is goedgekeurd, afgewezen of in behandeling is.
* Een **stroom** die informatie over een nieuw bestand in Dropbox toevoegt aan de aangepaste entiteit, een e-mail verzendt wanneer het bestand is goedgekeurd of afgewezen en de afgewezen bestanden verwijdert. Met deze stappen leert u hoe u zelf een dergelijke stroom maakt, maar u kunt ook een sjabloon gebruiken.
* Een **app** waarin een revisor nieuwe bestanden in Dropbox kan goedkeuren of afwijzen. U gebruikt PowerApps om deze app automatisch te genereren op basis van de velden in de aangepaste entiteit.

**Vereisten**

* Registreren voor [Microsoft Flow](sign-up-sign-in.md) en [PowerApps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/).
* Verbinding maken met Dropbox en Office 365 Outlook, zoals beschreven in [Gegevensverbindingen beheren](https://powerapps.microsoft.com/tutorials/add-manage-connections/).

## <a name="build-the-entity"></a>De entiteit maken
1. Meld u aan op [powerapps.com](https://web.powerapps.com).
2. Als de linkernavigatiebalk niet standaard wordt weergegeven, klikt of tikt u op het pictogram met drie horizontale lijnen in de linkerbovenhoek.
   
    ![Linkernavigatiebalk openen](./media/common-data-model-approve/hamburger-icon.png)
3. Klik of tik in de linkernavigatiebalk op **Beheren** en vervolgens op **Entiteiten**.
   
    ![Entiteiten beheren](./media/common-data-model-approve/manage-entities.png)
4. Klik of tik op **Mijn database maken** als dit wordt weergegeven.
   
    ![Database maken](./media/common-data-model-approve/create-database.png)
5. Klik of tik rechtsboven op **Nieuwe entiteit**.
   
    ![Entiteit maken](./media/common-data-model-approve/new-entity.png)
   
    Als uw browservenster niet is gemaximaliseerd, wordt deze knop mogelijk op een andere plaats weergegeven.
6. Geef bij **Entiteitnaam** een naam zonder spaties op die niet wordt gebruikt voor een andere entiteit in de database.
   
    Als u dit voorbeeld exact wilt volgen, geeft u **ReviewDropboxFiles** op.
   
    ![Naam van entiteit opgeven](./media/common-data-model-approve/entity-name.png)
7. Geef bij **Weergavenaam** een aangepaste naam op.
   
    ![Weergavenaam opgeven](./media/common-data-model-approve/display-name.png)
8. Klik of tik op **Volgende**.
   
    ![Knop Volgende](./media/common-data-model-approve/next-button.png)

## <a name="add-fields-to-the-entity"></a>Velden toevoegen aan de entiteit
1. Klik of tik rechtsboven op **Veld toevoegen**.
   
    ![Veld toevoegen](./media/common-data-model-approve/add-field.png)
2. In de lege rij die onder aan de lijst met velden verschijnt, stelt u de eigenschappen in van het veld **Goedkeurder**. (Wanneer u deze eigenschappen instelt, kunt u met de Tab-toets naar de volgende kolom gaan.)
   
   * In de kolom **Weergavenaam** typt u **Goedkeurder**.
   * In de kolom **Naam** typt u **ApproverEmail**.
   * In de kolom **Type** klikt of tikt u op de optie **E-mail**.
   * In de kolom **Vereist** schakelt u het selectievakje in.
     
     ![Veld Goedkeurder](./media/common-data-model-approve/approver-field.png)
3. In de volgende rij stelt u de eigenschappen in van het veld **Status**:
   
   * In de kolom **Weergavenaam** typt u **Status**.
   * In de kolom **Naam** typt u **Status**.
   * In de kolom **Type** klikt of tikt u op de optie **Tekst**.
   * In de kolom **Eigenschappen** laat u de standaardwaarde staan.
   * In de kolom **Vereist** schakelt u het selectievakje in.
     
     ![Veld Status](./media/common-data-model-approve/status-field.png)
4. In de volgende rij stelt u de eigenschappen in van het veld **FileID**:
   
   * In de kolom **Weergavenaam** typt u **Bestands-id**.
   * In de kolom **Naam** typt u **FileID**.
   * In de kolom **Type** klikt of tikt u op de optie **Tekst**.
   * In de kolom **Eigenschappen** laat u de standaardwaarde staan.
   * In de kolom **Uniek** schakelt u het selectievakje in.
   * In de kolom **Vereist** schakelt u het selectievakje in.
     
     ![Veld FileID](./media/common-data-model-approve/fileid-field.png)
5. Klik of tik aan de rechterkant op het weglatingsteken (...) voor het veld **FileID** en vervolgens op **Instellen als titelveld**.
   
    ![Titelveld instellen](./media/common-data-model-approve/set-title-field.png)
6. Klik of tik linksonder op **Maken**.
   
    ![Een entiteit maken](./media/common-data-model-approve/create-button.png)
7. (Optioneel) Als de lijst met entiteiten weer wordt weergegeven, maximaliseert u het browservenster en klikt of tikt u op de kolomkop **Type**. De lijst wordt gesorteerd en de aangepaste entiteiten, zoals die u zojuist hebt gemaakt, worden bovenaan weergegeven.

## <a name="sign-in-and-create-a-flow"></a>Aanmelden en een stroom maken
1. Open de [Microsoft Flow-portal](https://flow.microsoft.com).
2. Maximaliseer uw browservenster en klik of tik rechtsboven op **Aanmelden**.
   
    ![Knop Aanmelden voor Microsoft Flow](./media/common-data-model-approve/signin-flow.png)
3. In het bovenste menu rechts selecteert u de omgeving die u hebt gemaakt in de database in powerapps.com.
   
    **Opmerking**: als u niet dezelfde omgeving selecteert, wordt uw entiteit niet weergegeven.
4. Klik of tik linksboven op **Mijn stromen**.
   
    ![Knop Mijn stromen](./media/common-data-model-approve/myflows-button.png)
5. Klik of tik rechtsboven op **Nieuwe stroom maken**.
   
    ![Knop Nieuwe stroom maken](./media/common-data-model-approve/create-flow.png)

## <a name="start-when-a-file-is-added"></a>Starten wanneer een bestand wordt toegevoegd
1. Typ of plak **Dropbox** in het vak **Zoeken naar meer triggers** en klik of tik op **Dropbox - wanneer een bestand wordt gemaakt**.
   
    ![Trigger maken](./media/common-data-model-approve/create-trigger.png)
2. Onder **Map** klikt of tikt u op het mappictogram en bladert u naar de map waar de bestanden worden toegevoegd.
   
    ![Map kiezen](./media/common-data-model-approve/folder-icon.png)

## <a name="add-data-to-the-entity"></a>Gegevens toevoegen aan de entiteit
1. Klik of tik op **Nieuwe stap** en vervolgens op **Een actie toevoegen**.
   
    ![Een actie toevoegen](./media/common-data-model-approve/add-action.png)
2. Typ of plak **Common Data Service** in het vak met de tekst **Zoeken naar meer acties** en klik of tik vervolgen op **Common Data Service - Object maken**.
   
    ![Een object maken in de Common Data Service](./media/common-data-model-approve/cdm-create-object.png)
3. Onder **De entiteit** typt of plakt u **Beoordelen** en klikt of tikt u op **Dropbox-bestanden bekijken**.
   
    ![De entiteit kiezen](./media/common-data-model-approve/choose-entity-flow.png)
4. Onder **Titel** klikt of tikt u in het vak en vervolgens op **Bestandsnaam** in de lijst met parametertokens om dit token toe te voegen aan het veld.
   
    ![Token Bestandsnaam toevoegen](./media/common-data-model-approve/add-filename-token.png)
5. Onder **Goedkeurder** typt of plakt u het e-mailadres van degene die de bestanden zal beoordelen.
   
    **Opmerking**: geef uw eigen adres op om het testen van de stroom gemakkelijker te maken. U kunt dit later wijzigen wanneer de stroom gereed is voor werkelijk gebruik.
   
    ![Goedkeurder toevoegen](./media/common-data-model-approve/add-approver.png)
6. Onder **Status** typt of plakt u **In behandeling**.
   
    ![Standaardstatus toevoegen](./media/common-data-model-approve/add-default-status.png)
7. Onder **Bestands-id** klikt of tikt u in het vak en vervolgens op **Bestands-id** in de lijst met parametertokens om dit token toe te voegen aan het veld.
   
    ![Token Bestands-id toevoegen](./media/common-data-model-approve/add-file-identifier.png)

## <a name="check-whether-the-file-has-been-reviewed"></a>Controleren of het bestand is beoordeeld
1. Onder de actie **Object maken** klikt of tikt u op **Nieuwe stap**, **Meer** en dan op **Een item voor do until toevoegen**.
   
    ![Een item voor do until toevoegen](./media/common-data-model-approve/add-do-until.png)
2. Links boven de actie **Do until** klikt of tikt u in het vak **Een waarde kiezen**.
   
    ![Een waarde kiezen](./media/common-data-model-approve/choose-value.png)
   
    **Opmerking**: als het browservenster niet is gemaximaliseerd, klikt of tikt u in het bovenste vak op **Een waarde kiezen**.
3. Onder **Uitvoer van Object maken** klikt of tikt u op **Status** om dit parametertoken toe te voegen aan het veld.
   
    ![Token Status toevoegen](./media/common-data-model-approve/add-status.png)
4. Open de lijst in het midden van de actie **Do until** en klik of tik vervolgens op **is niet gelijk aan**.
   
    ![Is niet gelijk aan specificeren](./media/common-data-model-approve/is-not-equal.png)
5. Rechts boven de actie **Do until** typt of plakt u **In behandeling** in het vak **Een waarde kiezen**.
   
    ![Te volgen status specificeren](./media/common-data-model-approve/do-until-not-pending.png)
   
    **Opmerking**: als het browservenster niet is gemaximaliseerd, klikt of tikt u in het onderste vak op **Een waarde kiezen**.
6. Klik of tik onder aan de actie **Do until** op **Een actie toevoegen**.
   
    ![Actie toevoegen aan een item voor do until](./media/common-data-model-approve/add-action-in-dountil.png)
7. In het vak **Zoeken naar meer acties** typt u **Algemeen**. Klik of tik vervolgens op **Common Data Service - Object ophalen**.
   
    ![Een object ophalen](./media/common-data-model-approve/get-object.png)
8. Klik of tik onder **De naamruimte** op uw database.
9. Onder **De entiteit** typt of plakt u **Beoordelen** en klikt of tikt u op **Dropbox-bestanden bekijken**.
   
    ![Entiteit kiezen](./media/common-data-model-approve/choose-entity-flow.png)
10. Onder **Object-id** klikt of tikt u in het vak en vervolgens op het parametertoken **Bestands-id** om dit toe te voegen aan het veld.
    
     ![Object-id toevoegen](./media/common-data-model-approve/add-object-id.png)

## <a name="check-whether-the-item-has-been-approved"></a>Controleren of het item is goedgekeurd
1. Onder de actie **Do until** klikt of tikt u op **Nieuwe stap** en vervolgens op **Een voorwaarde toevoegen**.
   
    ![Voorwaarde toevoegen](./media/common-data-model-approve/add-condition.png)
2. Linksboven in de voorwaarde klikt of tikt u in het vak **Een waarde kiezen**.
   
    ![Linksboven in voorwaarde](./media/common-data-model-approve/condition-upper-left.png)
   
    **Opmerking**: als het browservenster niet is gemaximaliseerd, klikt of tikt u in het bovenste vak op **Een waarde kiezen**.
3. Onder **Uitvoer van Object ophalen** klikt of tikt u op het parametertoken **Status** om dit toe te voegen aan het veld.
   
    ![Status toevoegen aan voorwaarde](./media/common-data-model-approve/add-status-to-condition.png)
4. Rechtsboven in de voorwaarde typt of plakt u **Goedgekeurd** in het vak **Een waarde kiezen**.
   
    ![Controleren of de status is ingesteld op Goedgekeurd](./media/common-data-model-approve/status-equals-approved.png)
   
    **Opmerking**: als het browservenster niet is gemaximaliseerd, typt of plakt u **Goedgekeurd** in het onderste vak waarin **Een waarde kiezen** staat.

## <a name="send-notification-mail"></a>E-mailmelding verzenden
1. Onder **Zo ja, niets doen** klikt of tikt u op **Een actie toevoegen**.
   
    ![Zo ja, een actie toevoegen](./media/common-data-model-approve/if-yes-action.png)
2. In het vak **Zoeken naar meer acties** typt of plakt u **e-mail verzenden** en klikt of tikt u op **Office 365 Outlook - een e-mail verzenden**.
   
    ![Zo ja, e-mail verzenden](./media/common-data-model-approve/if-yes-send-mail.png)
3. Onder **Aan** typt of plakt u het adres van degene aan wie u een melding wilt sturen wanneer een item is geaccepteerd.
   
    **Opmerking**: geef uw eigen adres op om het testen van de stroom gemakkelijker te maken. U kunt dit later wijzigen wanneer de stroom gereed is voor werkelijk gebruik.
   
    ![Ontvanger goedkeuring](./media/common-data-model-approve/approval-recipient.png)
4. Onder **Onderwerp** klikt of tikt u in het vak en vervolgens op het parametertoken **Bestandsnaam** om dit toe te voegen aan het veld.
   
    ![De bestandsnaam opgeven als onderwerp van de e-mail](./media/common-data-model-approve/subject-is-file-name.png)
5. Onder **Hoofdtekst** typt of plakt u **Het item is goedgekeurd.**
   
    ![Hoofdtekst van goedkeuringsmail](./media/common-data-model-approve/approval-body.png)
6. Herhaal stap 1-5 voor **Zo niet, niets doen**, maar gebruik **Het item is afgewezen.** als hoofdtekst van de e-mail.
   
    ![Hoofdtekst van afwijzingsmail](./media/common-data-model-approve/rejection-body.png)

## <a name="delete-rejected-files"></a>Afgewezen bestanden verwijderen
1. Onder de velden voor de afwijzingsmail klikt of tikt u op **Een actie toevoegen**.
   
    ![Verwijderingsactie toevoegen](./media/common-data-model-approve/add-delete-action.png)
2. Typ of plak **Dropbox** in het vak **Zoeken naar meer acties** en klik of tik op **Dropbox - bestand verwijderen**.
   
    ![Bestand verwijderen uit Dropbox](./media/common-data-model-approve/dropbox-delete-file.png)
3. Onder **Bestand** klikt of tikt u in het vak en vervolgens op het parametertoken **Bestands-id** om dit toe te voegen aan het veld.
   
    ![Bestand kiezen om te verwijderen](./media/common-data-model-approve/identify-file-delete.png)

## <a name="save-the-flow"></a>De stroom opslaan
1. Boven aan het scherm typt of plakt u een naam voor de stroom die u maakt en klikt of tikt u vervolgens op **Stroom maken**.
   
    ![Stroom opslaan](./media/common-data-model-approve/save-flow.png)
2. Klik of tik op **Sluiten** en vervolgens op **Gereed**.
3. Voeg in Dropbox ten minste twee bestanden toe aan de map die u hebt opgegeven: één om goedkeuring te testen en één om afwijzing te testen.

## <a name="build-the-app"></a>De app maken
1. Meld u aan op [powerapps.com](https://web.powerapps.com) en klik of tik onder aan de linkernavigatiebalk op **Nieuwe app**.
   
    ![Een app in een browser maken](./media/common-data-model-approve/new-app-button.png)
2. In het dialoogvenster dat wordt geopend, kiest u PowerApps Studio voor Windows of PowerApps Studio voor het web.
3. Als u PowerApps Studio voor Windows hebt geopend, klikt of tikt u in de linkernavigatiebalk op **Nieuw**.
4. Onder **Een app maken op basis van uw gegevens** klikt of tikt u op **Telefoonindeling** in de tegel **Common Data Service**.
   
    ![App maken](./media/common-data-model-approve/afd-cdm.png)
5. Typ of plak **Beoordelen** in het vak **Zoeken**.
   
    ![Zoeken naar een entiteit](./media/common-data-model-approve/search-entities.png)
6. Onder **Een entiteit kiezen** klikt of tikt u op **ReviewDropboxFiles**.
   
    ![Een entiteit kiezen](./media/common-data-model-approve/choose-entity.png)
7. Klik of tik rechtsonder op **Verbinding maken**.
   
    ![Knop Verbinding maken](./media/common-data-model-approve/connect-button.png)
8. Als het welkomstscherm van de rondleiding wordt weergegeven, kunt u de rondleiding volgen om vertrouwd te raken met PowerApps (of op **Overslaan** klikken of tikken).
   
    ![Rondleiding](./media/common-data-model-approve/quick-tour.png)
   
    U kunt de rondleiding later altijd nog volgen door linksboven op het vraagteken te klikken of tikken en vervolgens op **Rondleiding volgen**.
9. (Optioneel) Versleep de schuifregelaar onder aan het scherm om in te zoomen, zodat de app beter te zien is.
   
    ![Zoomen](./media/common-data-model-approve/zoom-control.png)

## <a name="customize-the-app"></a>De app aanpassen
1. Klik of tik in de rechternavigatiebalk op de indeling met een koptekst en een beschrijving.
   
    ![Knop Verbinding maken](./media/common-data-model-approve/choose-layout.png)
2. Op **BrowseScreen** klikt of tikt u onder de zoekbalk om het grotere besturingselement voor het tekstvak te selecteren.
   
    ![Koptekst selecteren](./media/common-data-model-approve/select-header.png)
3. Open in het rechterdeelvenster de onderste lijst door op de pijl-omlaag te klikken of tikken.
   
    ![Vervolgkeuzelijst openen](./media/common-data-model-approve/open-dropdown.png)
4. Klik of tik in de onderste lijst op **Titel** om de bestandsnaam van de toegevoegde bestanden weer te geven.
   
    ![Koptekstgegevens instellen](./media/common-data-model-approve/set-heading.png)
5. Open in het rechterdeelvenster de bovenste lijst en klik of tik vervolgens op **Status** om de status van elk bestand weer te geven.
   
    ![Hoofdtekstgegevens instellen](./media/common-data-model-approve/set-body.png)

## <a name="test-the-overall-solution"></a>De algehele oplossing testen
1. Open de voorbeeldmodus in PowerApps door linksboven op de afspeelknop te klikken of tikken.
   
    ![Voorbeeldmodus openen](./media/common-data-model-approve/open-preview.png)
2. Klik of tik op de pijl bij het eerste bestand in de lijst om de details van dat bestand weer te geven.
   
    ![Scherm Details openen](./media/common-data-model-approve/open-details.png)
3. Klik of tik rechtsboven op het potloodpictogram om de details van het bestand te wijzigen.
   
    ![Scherm Bewerken openen](./media/common-data-model-approve/edit-record.png)
4. In het vak **Status** typt of plakt u **Goedgekeurd**.
   
    ![Een bestand goedkeuren](./media/common-data-model-approve/change-status.png)
5. Klik of tik rechtsboven op het vinkje om de wijzigingen op te slaan en terug te keren naar het scherm Details.
   
    ![Wijzigingen opslaan](./media/common-data-model-approve/save-record.png)
   
    U ontvangt binnen een paar minuten een e-mailbericht waarin staat dat het bestand is goedgekeurd.
6. Klik of tik rechtsboven op de knop Terug om terug te keren naar het scherm Bladeren.
   
    ![Terug naar het scherm Bladeren](./media/common-data-model-approve/back-arrow.png)
7. Klik of tik op de pijl bij het andere bestand in de lijst om de details van dat bestand weer te geven.
   
    ![Scherm Details openen](./media/common-data-model-approve/open-details.png)
8. Klik of tik rechtsboven op het potloodpictogram om de details van het bestand te wijzigen.
   
    ![Scherm Bewerken openen](./media/common-data-model-approve/edit-record.png)
9. In het vak **Status** typt of plakt u **Afgewezen** (of iets anders, maar niet **Goedgekeurd**, **Goedgekeur**, **Goedgekeurt** of een andere variatie).
   
    ![Bestand afwijzen](./media/common-data-model-approve/reject-file.png)
10. Klik of tik rechtsboven op het vinkje om de wijzigingen op te slaan en terug te keren naar het scherm Details.
    
     ![Wijzigingen opslaan](./media/common-data-model-approve/save-record.png)
    
     U ontvangt binnen een paar minuten een e-mailbericht waarin staat dat het bestand is afgewezen en het bestand wordt verwijderd uit Dropbox.

