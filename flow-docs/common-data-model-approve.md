---
title: Een goedkeurings-lus bouwen met de Common Data Service | Microsoft Docs
description: Maak een entiteit, een stroom en een app die samen werken, zodat revisoren bestanden kunnen goed keuren of afwijzen die zijn toegevoegd aan Dropbox.
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
ms.openlocfilehash: 4f58e5b3095769349e71e9ba8b203ea678981391
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546852"
---
# <a name="build-an-approval-loop-by-using-microsoft-flow-and-the-microsoft-common-data-service"></a>Bouw een goedkeurings herhalingslus met behulp van Microsoft Flow en de micro soft Common Data Service
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
De Common Data Service biedt u een manier om stromen te bouwen die gegevens bevatten die zijn opgeslagen in een Data Base, onafhankelijk van een stroom. Het beste voor beeld hiervan is met goed keuringen. Als u de status van de goed keuring in een entiteit opslaat, kan uw stroom hierop worden uitgevoerd.

In dit voor beeld maakt u een goedkeurings proces dat begint wanneer een gebruiker een bestand toevoegt aan Dropbox. Wanneer het bestand wordt toegevoegd, wordt er informatie over weer gegeven in een app, waarbij een revisor de wijziging kan goed keuren of afwijzen. Wanneer de revisor de wijziging goedkeurt of afwijst, wordt het e-mail bericht verzonden en worden de geweigerde bestanden verwijderd uit Dropbox.

Door de stappen in deze sectie te volgen, bouwt u het volgende:

* een **aangepaste entiteit** die informatie bevat over elk bestand dat wordt toegevoegd aan Dropbox en of de status van het bestand is goedgekeurd, afgewezen of in behandeling is.
* een **stroom** waarmee informatie wordt toegevoegd aan de aangepaste entiteit wanneer een bestand wordt toegevoegd aan Dropbox, e-mail verzendt wanneer het bestand is goedgekeurd of afgewezen en geweigerde bestanden verwijdert. Deze stappen laten zien hoe u een nieuwe stroom maakt, maar u kunt een vergelijk bare stroom maken op basis van een sjabloon.
* een **app** waarin een revisor bestanden kan goed keuren of afwijzen die zijn toegevoegd aan Dropbox. U gebruikt PowerApps voor het automatisch genereren van deze app op basis van de velden in de aangepaste entiteit.

**Vereisten**

* Meld u aan voor [Microsoft flow](sign-up-sign-in.md) en [PowerApps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/).
* Maak verbindingen met Dropbox en Office 365 Outlook, zoals wordt beschreven in [uw verbindingen beheren](https://powerapps.microsoft.com/tutorials/add-manage-connections/) .

## <a name="build-the-entity"></a>De entiteit bouwen
1. Meld u aan bij [powerapps.com](https://web.powerapps.com).
2. Als de linkernavigatiebalk niet standaard wordt weer gegeven, klikt of tikt u op het pictogram met drie horizontale lijnen in de linkerbovenhoek.
   
    ![Navigatie balk links openen](./media/common-data-model-approve/hamburger-icon.png)
3. Klik of tik in de linkernavigatiebalk op **beheren**en klik of tik vervolgens op **entiteiten**.
   
    ![Entiteiten beheren](./media/common-data-model-approve/manage-entities.png)
4. Als u hierom wordt gevraagd, klikt of tikt u op **mijn data base maken**.
   
    ![Data base maken](./media/common-data-model-approve/create-database.png)
5. Klik of tik in de rechter bovenhoek op **nieuwe entiteit**.
   
    ![Entiteit maken](./media/common-data-model-approve/new-entity.png)
   
    Als uw browser venster niet is gemaximaliseerd, kan deze knop op een andere plaats worden weer gegeven.
6. Geef onder **naam van entiteit**een naam op die geen spaties bevat en die geen andere entiteit in uw data base heeft.
   
    Als u dit voor beeld precies wilt volgen, geeft u **ReviewDropboxFiles**op.
   
    ![Entiteits naam opgeven](./media/common-data-model-approve/entity-name.png)
7. Geef onder **weergave naam**een beschrijvende naam op.
   
    ![Weergave naam opgeven](./media/common-data-model-approve/display-name.png)
8. Klik of tik op **volgende**.
   
    ![Knop volgende](./media/common-data-model-approve/next-button.png)

## <a name="add-fields-to-the-entity"></a>Velden toevoegen aan de entiteit
1. Klik of tik in de rechter bovenhoek op **veld toevoegen**.
   
    ![Veld toevoegen](./media/common-data-model-approve/add-field.png)
2. Stel in de lege rij onder in de lijst met velden de eigenschappen van een **fiatteur** veld in. (Wanneer u deze eigenschappen instelt, kunt u overschakelen naar de volgende kolom door op TAB te drukken.)
   
   * Typ **goed keurder**in de kolom **weergave naam** .
   * Typ **ApproverEmail**in de kolom **naam** .
   * Klik of tik in de kolom **type** op de optie **e-mail** .
   * Schakel in de kolom **vereist** het selectie vakje in.
     
     ![Veld goed keurder](./media/common-data-model-approve/approver-field.png)
3. In de volgende rij stelt u de eigenschappen in van een **status** veld:
   
   * Typ in de kolom **weergave naam** de **status**.
   * Typ **status**in de kolom **naam** .
   * Klik of tik in de kolom **type** op de optie **tekst** .
   * In de kolom **Eigenschappen** , behoud de standaard waarde.
   * Schakel in de kolom **vereist** het selectie vakje in.
     
     ![Status veld](./media/common-data-model-approve/status-field.png)
4. In de volgende rij stelt u de eigenschappen in van een **Bestands** -id-veld:
   
   * In de kolom **weergave naam** typt u **bestands-id**.
   * Typ **Bestands**-id in de kolom **naam** .
   * Klik of tik in de kolom **type** op de optie **tekst** .
   * In de kolom **Eigenschappen** , behoud de standaard waarde.
   * Schakel in de kolom **uniek** het selectie vakje in.
   * Schakel in de kolom **vereist** het selectie vakje in.
     
     ![Bestands-id-veld](./media/common-data-model-approve/fileid-field.png)
5. Klik of tik aan de rechter kant op het weglatings teken (...) voor het veld **Bestands** -id en klik of tik vervolgens op **instellen als titel veld**.
   
    ![Titel veld instellen](./media/common-data-model-approve/set-title-field.png)
6. Klik of tik in de linkerbenedenhoek op **maken**.
   
    ![Een entiteit maken](./media/common-data-model-approve/create-button.png)
7. Beschrijving Wanneer de lijst met entiteiten opnieuw wordt weer gegeven, maximaliseert u het browser venster als dit nog niet is gemaximaliseerd en klikt of tikt u op de kolomkop **type** . De lijst wordt gesorteerd met de aangepaste entiteiten, zoals de entiteit die u zojuist hebt gemaakt, die bovenaan wordt weer gegeven.

## <a name="sign-in-and-create-a-flow"></a>Meld u aan en maak een stroom
1. Open de [Microsoft flow Portal](https://flow.microsoft.com).
2. Maximaliseer uw browser venster als dit nog niet is gemaximaliseerd en klik of tik **in** de rechter bovenhoek op aanmelden.
   
    ![Aanmeldings knop voor Microsoft Flow](./media/common-data-model-approve/signin-flow.png)
3. In het menu rechtsboven selecteert u de omgeving waarin u de Data Base hebt gemaakt in powerapps.com.
   
    **Opmerking**: als u niet dezelfde omgeving selecteert, wordt uw entiteit niet weer geven.
4. Klik of tik in de linkerbovenhoek op **mijn stromen**.
   
    ![Knop mijn stromen](./media/common-data-model-approve/myflows-button.png)
5. Klik of tik in de rechter bovenhoek op **nieuwe stroom maken**.
   
    ![Knop nieuwe stroom maken](./media/common-data-model-approve/create-flow.png)

## <a name="start-when-a-file-is-added"></a>Starten wanneer een bestand wordt toegevoegd
1. Typ of plak **Dropbox**in het vak **zoeken naar meer triggers**en klik of tik op **Dropbox-wanneer een bestand wordt gemaakt**.
   
    ![Trigger maken](./media/common-data-model-approve/create-trigger.png)
2. Klik of tik onder **map**op het mappictogram en blader vervolgens naar de map waarin de bestanden worden toegevoegd.
   
    ![Map kiezen](./media/common-data-model-approve/folder-icon.png)

## <a name="add-data-to-the-entity"></a>Gegevens toevoegen aan de entiteit
1. Klik of tik op **nieuwe stap**en klik of tik vervolgens op **een actie toevoegen**.
   
    ![Een actie toevoegen](./media/common-data-model-approve/add-action.png)
2. Typ of plak **common data service**in het vak **zoeken naar meer acties**en klik of tik vervolgens op **common data service-object maken**.
   
    ![Een object maken in de Common Data Service](./media/common-data-model-approve/cdm-create-object.png)
3. Onder **de entiteit**, typt of plakt u **controle**en klikt of tikt u op **Dropbox-bestanden weer geven**.
   
    ![De entiteit kiezen](./media/common-data-model-approve/choose-entity-flow.png)
4. Onder **titel**klikt of tikt u in het vak en klikt of tikt u op **Bestands naam** in de lijst met parameter tokens om dit token toe te voegen aan het veld.
   
    ![Bestands naam token toevoegen](./media/common-data-model-approve/add-filename-token.png)
5. Typ of plak het e-mail adres van de persoon die de bestanden gaat controleren onder **goed keurder**.
   
    **Opmerking**: als u de stroom eenvoudiger wilt testen, moet u uw eigen adres opgeven. U kunt dit later wijzigen wanneer de stroom gereed is voor werkelijk gebruik.
   
    ![Goed keurder toevoegen](./media/common-data-model-approve/add-approver.png)
6. Typ of plak onder **status** **in behandeling**.
   
    ![Standaard status toevoegen](./media/common-data-model-approve/add-default-status.png)
7. Klik of tik onder **bestands-id**in het vak en klik of tik vervolgens op **bestands-id** in de lijst met parameter tokens om dit token toe te voegen aan het veld.
   
    ![Bestands-id-token toevoegen](./media/common-data-model-approve/add-file-identifier.png)

## <a name="check-whether-the-file-has-been-reviewed"></a>Controleren of het bestand is gecontroleerd
1. Klik of tik onder de actie **object maken** op **nieuwe stap**, klik of tik op **meer**, en klik of tik vervolgens op **een do until toevoegen**.
   
    ![Toevoegen tot](./media/common-data-model-approve/add-do-until.png)
2. In de linkerbovenhoek van de actie **do until** klikt of tikt u in het vak **een waarde kiezen**.
   
    ![Kies een waarde](./media/common-data-model-approve/choose-value.png)
   
    **Opmerking**: als het browser venster niet is gemaximaliseerd, klikt of tikt u in het bovenste vak met **een waarde kiezen**.
3. Onder **uitvoer van object maken**klikt of tikt u op **status** om dat parameter token toe te voegen aan het veld.
   
    ![Status token toevoegen](./media/common-data-model-approve/add-status.png)
4. Open de lijst in het midden van de actie **do until** en klik of tik vervolgens op **is niet gelijk aan**.
   
    ![De opgegeven waarde is niet gelijk aan](./media/common-data-model-approve/is-not-equal.png)
5. In de rechter bovenhoek van de actie **do until** typt of plakt u in **behandeling** in het vak **een waarde kiezen**.
   
    ![Te bekijken status opgeven](./media/common-data-model-approve/do-until-not-pending.png)
   
    **Opmerking**: als het browser venster niet is gemaximaliseerd, klikt of tikt u in het onderste vak met **een waarde kiezen**.
6. Klik of tik onder aan de actie **do until** op **een actie toevoegen**.
   
    ![Actie toevoegen binnen een do until](./media/common-data-model-approve/add-action-in-dountil.png)
7. In het vak **zoeken naar meer acties**typt u **Algemeen**. Klik of tik vervolgens op **common data service-object ophalen**.
   
    ![Een object ophalen](./media/common-data-model-approve/get-object.png)
8. Klik of tik onder **de naam ruimte**op uw data base.
9. Onder **de entiteit**, typt of plakt u **controle**en klikt of tikt u op **Dropbox-bestanden weer geven**.
   
    ![Entiteit kiezen](./media/common-data-model-approve/choose-entity-flow.png)
10. Klik of tik onder **object-id**in het vak en klik of tik vervolgens op het token voor de **bestands-id** -para meter om dit toe te voegen aan het veld.
    
     ![Object-id toevoegen](./media/common-data-model-approve/add-object-id.png)

## <a name="check-whether-the-item-has-been-approved"></a>Controleren of het item is goedgekeurd
1. Klik of tik onder de actie **do-until** op **nieuwe stap**en klik of tik vervolgens op **een voor waarde toevoegen**.
   
    ![Voor waarde toevoegen](./media/common-data-model-approve/add-condition.png)
2. In de linkerbovenhoek van de voor waarde klikt of tikt u in het vak **een waarde kiezen**.
   
    ![Linkerbovenhoek van voor waarde](./media/common-data-model-approve/condition-upper-left.png)
   
    **Opmerking**: als het browser venster niet is gemaximaliseerd, klikt of tikt u in het bovenste vak met **een waarde kiezen**.
3. Onder **uitvoer van object ophalen**klikt of tikt u op het parameter token **status** om dit toe te voegen aan het veld.
   
    ![Status aan voor waarde toevoegen](./media/common-data-model-approve/add-status-to-condition.png)
4. In de rechter bovenhoek van de voor waarde, typt of plakt u **goedgekeurd** in het vak **een waarde kiezen**.
   
    ![Controleer of de status is ingesteld op goedgekeurd](./media/common-data-model-approve/status-equals-approved.png)
   
    **Opmerking**: als het browser venster niet is gemaximaliseerd, typt of plakt u **goedgekeurd** in het onderste vak met **een waarde kiezen**.

## <a name="send-notification-mail"></a>E-mail melding verzenden
1. Onder **als Ja, niets doen**, klikt of tikt u op **een actie toevoegen**.
   
    ![Zo ja, een actie toevoegen](./media/common-data-model-approve/if-yes-action.png)
2. Typ of plak **e-mail verzenden**in het vak **zoeken naar meer acties**en klik of tik vervolgens op **Office 365 Outlook-een e-mail verzenden**.
   
    ![Zo ja, e-mail verzenden](./media/common-data-model-approve/if-yes-send-mail.png)
3. Onder **aan**, typt of plakt u het adres van de persoon die u op de hoogte wilt stellen wanneer een item wordt geaccepteerd.
   
    **Opmerking**: als u de stroom eenvoudiger wilt testen, moet u uw eigen adres opgeven. U kunt deze wijzigen wanneer de stroom gereed is voor werkelijk gebruik.
   
    ![Goedkeurings ontvanger](./media/common-data-model-approve/approval-recipient.png)
4. Onder **onderwerp**klikt of tikt u in het vak en klikt of tikt u op het token voor de **Bestands naam** parameter om dit toe te voegen aan het veld.
   
    ![Geef de bestands naam op als onderwerp van de e-mail](./media/common-data-model-approve/subject-is-file-name.png)
5. Onder **hoofd tekst**, typt of plakt u **het item is goedgekeurd.**
   
    ![Bericht tekst van goed keuring](./media/common-data-model-approve/approval-body.png)
6. Onder **als Nee, niets doen**, herhaalt u stap 1-5 in deze procedure, met uitzonde ring van de hoofd tekst van het e-mail bericht wanneer **het item is afgewezen.**
   
    ![Bericht tekst van afwijzing](./media/common-data-model-approve/rejection-body.png)

## <a name="delete-rejected-files"></a>Geweigerde bestanden verwijderen
1. Klik of tik onder de velden voor de afwijzings mail op **een actie toevoegen**.
   
    ![Verwijderings actie toevoegen](./media/common-data-model-approve/add-delete-action.png)
2. Typ of plak **Dropbox**in het vak **zoeken naar meer acties**en klik of tik op **Dropbox-bestand verwijderen**.
   
    ![Bestand verwijderen uit Dropbox](./media/common-data-model-approve/dropbox-delete-file.png)
3. Klik of tik onder **bestand**op in het vak en klik of tik op de para meter van de **bestands-id** -token om deze toe te voegen aan het veld.
   
    ![Te verwijderen bestand identificeren](./media/common-data-model-approve/identify-file-delete.png)

## <a name="save-the-flow"></a>De stroom opslaan
1. Typ of plak aan de bovenkant van het scherm een naam voor de stroom die u maakt, en klik of tik vervolgens op **stroom maken**.
   
    ![stroom opslaan](./media/common-data-model-approve/save-flow.png)
2. Klik of tik op **sluiten** en klik of tik op **gereed**.
3. Voeg in Dropbox ten minste twee bestanden toe aan de map die u hebt opgegeven: één om goed keuring te testen en één om de weigering te testen.

## <a name="build-the-app"></a>De app bouwen
1. Meld u aan bij [powerapps.com](https://web.powerapps.com)en klik of tik onder aan de linkernavigatiebalk op **nieuwe app** .
   
    ![Een app maken in een browser](./media/common-data-model-approve/new-app-button.png)
2. Klik of tik in het dialoog venster dat wordt weer gegeven op de optie om een PowerApps Studio te openen voor Windows of PowerApps Studio voor het web.
3. Als u PowerApps Studio voor Windows hebt geopend, klikt of tikt u op **Nieuw** in de linkernavigatiebalk.
4. Onder **een app maken op basis van uw gegevens**klikt of tikt u op **telefoon indeling** in de tegel **common data service** .
   
    ![App maken](./media/common-data-model-approve/afd-cdm.png)
5. Typ of plak **beoordeling**in het **zoekvak** .
   
    ![Een entiteit zoeken](./media/common-data-model-approve/search-entities.png)
6. Onder **Kies een entiteit**klikt of tikt u op **Dropbox-bestanden bekijken**.
   
    ![Een entiteit kiezen](./media/common-data-model-approve/choose-entity.png)
7. Klik of tik in de rechter benedenhoek op **verbinding maken**.
   
    ![Knop verbinding maken](./media/common-data-model-approve/connect-button.png)
8. Als het openings scherm van de intro-rond leiding wordt weer gegeven, kunt u de rond leiding volgen om vertrouwd te raken met PowerApps (of klik of tik op **overs Laan**).
   
    ![Rond leiding voor inleiding](./media/common-data-model-approve/quick-tour.png)
   
    U kunt de rond leiding altijd later volgen door op het vraag teken te klikken of tikken in de linkerbovenhoek en vervolgens te klikken of tikken op **de rond leiding**volgen.
9. Beschrijving Sleep de schuif regelaar aan de onderkant van het scherm om het zoom niveau te verg Roten zodat de app gemakkelijker te zien is.
   
    ![Zoom besturings element](./media/common-data-model-approve/zoom-control.png)

## <a name="customize-the-app"></a>De App aanpassen
1. Klik of tik in de rechter navigatie balk op de indeling die een koptekst en een beschrijving bevat.
   
    ![Knop verbinding maken](./media/common-data-model-approve/choose-layout.png)
2. Klik of tik in het **BrowseScreen**op net onder de zoek balk om het grotere besturings element voor het tekstvak te selecteren.
   
    ![Koptekst selecteren](./media/common-data-model-approve/select-header.png)
3. Open in het rechterdeel venster de onderste lijst door te klikken of tikken op de pijl-omlaag.
   
    ![Vervolg keuzelijst openen](./media/common-data-model-approve/open-dropdown.png)
4. Klik of tik in de onderste lijst op **titel** , zodat de bestands naam van de toegevoegde bestanden wordt weer gegeven.
   
    ![Kopregel gegevens instellen](./media/common-data-model-approve/set-heading.png)
5. Open in het rechterdeel venster de bovenste lijst en klik of tik vervolgens op **status** om de status van elk bestand weer te geven.
   
    ![Hoofd gegevens instellen](./media/common-data-model-approve/set-body.png)

## <a name="test-the-overall-solution"></a>De algemene oplossing testen
1. Open de voorbeeld modus in PowerApps door te klikken of tikken op de afspeel knop in de linkerbovenhoek.
   
    ![Preview-modus openen](./media/common-data-model-approve/open-preview.png)
2. Voor het eerste bestand in de lijst, klikt of tikt u op de pijl om de details van dat bestand weer te geven.
   
    ![Scherm Details openen](./media/common-data-model-approve/open-details.png)
3. Klik of tik in de rechter bovenhoek op het potlood pictogram om de details van het bestand te wijzigen.
   
    ![Open bewerkings scherm](./media/common-data-model-approve/edit-record.png)
4. In het vak **status** typt of plakt u **goedgekeurd**.
   
    ![Een bestand goed keuren](./media/common-data-model-approve/change-status.png)
5. Klik of tik in de rechter bovenhoek op het vinkje om de wijzigingen op te slaan en terug te keren naar het scherm Details.
   
    ![Wijzigingen opslaan](./media/common-data-model-approve/save-record.png)
   
    Over een paar minuten ontvangt u een e-mail met de mede deling dat het bestand is goedgekeurd.
6. Klik of tik in de rechter bovenhoek op de knop terug om terug te keren naar het Blader scherm.
   
    ![Terug naar het Blader scherm](./media/common-data-model-approve/back-arrow.png)
7. Voor het andere bestand in de lijst, klikt of tikt u op de pijl om de details van dat bestand weer te geven.
   
    ![Scherm Details openen](./media/common-data-model-approve/open-details.png)
8. Klik of tik in de rechter bovenhoek op het potlood pictogram om de details van het bestand te wijzigen.
   
    ![Open bewerkings scherm](./media/common-data-model-approve/edit-record.png)
9. Typ of plak in het vak **status de instelling** **geweigerd** (of alles behalve **goedgekeurd**, inclusief **Aproved** of **Approoved**).
   
    ![Bestand afwijzen](./media/common-data-model-approve/reject-file.png)
10. Klik of tik in de rechter bovenhoek op het vinkje om de wijzigingen op te slaan en terug te keren naar het scherm Details.
    
     ![Wijzigingen opslaan](./media/common-data-model-approve/save-record.png)
    
     Over een paar minuten ontvangt u een e-mail waarin staat dat het bestand is afgewezen en dat het bestand wordt verwijderd uit Dropbox.

