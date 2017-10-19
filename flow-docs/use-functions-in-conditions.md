---
title: Functies met voorwaarden gebruiken. | Microsoft Docs
description: 'Geavanceerde functies gebruiken zoals '
"\"and\"\",": 
"\"\"or\"\",": 
"\"\"empty\"\",": 
"\"\"less\"\"": 
and: 
"\"\"greater\"\"": 
with: 
microsoft: 
flow: 
conditions.": 
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
ms.date: 08/01/2017
ms.author: deonhe
ms.openlocfilehash: 26f8dd2f8f9c027584bba197d301e4c8a32b0857
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/15/2017
---
# <a name="use-functions-in-conditions-to-check-multiple-values"></a>Gebruik functies in voorwaarden om meerdere waarden te controleren
In dit overzicht leert u hoe u functies en **Voorwaarden** kunt gebruiken om in de **Geavanceerde modus** meerdere waarden te vergelijken.

Als u een stroom maakt, kunt u de kaart [**Voorwaarde**](add-a-condition.md#add-a-condition) in de standaardmodus gebruiken om snel een waarde met een andere waarde te vergelijken. Er zijn echter momenten waarop u meerdere waarden moet vergelijken. U wilt bijvoorbeeld de waarde van een paar kolommen in een werkblad of databasetabel controleren.

U kunt elke willekeurige combinatie van de volgende logische functies in uw voorwaarden gebruiken.

| Functie | Beschrijving | Voorbeeld |
| --- | --- | --- |
| <a href="#use-the-and-function">and</a> |Neemt twee argumenten en retourneert 'true' als beide waarden waar zijn.<br><b>Opmerking</b>: Beide argumenten moeten Booleaanse waarden zijn. |Deze functie retourneert 'false': <br>and(greater(1,10),equals(0,0)) |
| <a href="#use-the-or-function">or</a> |Neemt twee argumenten en retourneert 'true' als een van beide waarden waar is. <br><b>Opmerking</b>: Beide argumenten moeten Booleaanse waarden zijn. |Deze functie retourneert 'true':<br>or(greater(1,10),equals(0,0)) |
| equals |Retourneert 'true' als twee waarden gelijk zijn. |Deze functie retourneert bijvoorbeeld 'true' als parameter1 eenWaarde is:<br>equals(parameters('parameter1'), 'eenWaarde') |
| <a href="#use-the-less-function">less</a> |Neemt twee argumenten en retourneert 'true' als het eerste argument minder is dan het tweede argument. <br><b>Opmerking</b>: De ondersteunde typen zijn geheel getal, float en tekenreeks. |Deze functie retourneert 'true':<br>less(10,100) |
| lessOrEquals |Neemt twee argumenten en retourneert 'true' als het eerste argument minder is dan of gelijk is aan het tweede argument. <br><b>Opmerking</b>: De ondersteunde typen zijn geheel getal, float en tekenreeks. |Deze functie retourneert 'true':<br>lessOrEquals(10,10) |
| <a href="#use-the-greater-function">greater</a> |Neemt twee argumenten en retourneert 'true' als het eerste argument groter is dan het tweede argument. <br><b>Opmerking</b>: De ondersteunde typen zijn geheel getal, float en tekenreeks. |Deze functie retourneert 'false':<br>greater(10,10) |
| greaterOrEquals |Neemt twee argumenten en retourneert 'true' als het eerste argument groter is dan of gelijk is aan het tweede argument. <br><b>Opmerking</b>: De ondersteunde typen zijn geheel getal, float en tekenreeks. |Deze functie retourneert 'false':<br>greaterOrEquals(10,100) |
| <a href="#use-the-empty-function">empty</a> |Retourneert 'true' als het object, de matrix of de tekenreeks leeg is. |Deze functie retourneert 'true':<br>empty('') |
| not |Neemt twee argumenten en retourneert 'true' als beide argumenten onwaar zijn. <br><b>Opmerking</b>: Beide argumenten moeten Booleaanse waarden zijn. |Deze functie retourneert 'true':<br>not(contains('200 Success','Fail')) |
| if |Retourneert een specifieke waarde als de expressie tot 'true' of 'false' leidt. |Deze functie retourneert 'ja':<br>if(equals(1, 1), 'ja', 'nee') |

## <a name="prerequisites"></a>Vereisten
* Toegang tot Microsoft Flow.
* Een werkblad met de tabellen die later in dit overzicht worden beschreven. Sla uw werkblad op een locatie zoals Dropbox of Microsoft OneDrive op, zodat Microsoft Flow er toegang toe heeft.
* Microsoft Office 365 Outlook (we gebruiken Office 365 Outlook, maar u kunt elke ondersteunde e-mailservice in uw stromen gebruiken.)

## <a name="use-the-or-function"></a>De functie 'or' gebruiken
Soms moet uw werkstroom een actie uitvoeren als de waarde van een item waardeA **of** waardeB is. U kunt bijvoorbeeld de status van taken in een tabel op een werkblad bijhouden. Stel dat de tabel een kolom bevat met de naam *Status* en dat de mogelijke waarden in de kolom *Status* als volgt zijn:

* **voltooid**
* **geblokkeerd**
* **onnodig**
* **niet gestart**

Het werkblad kan er dan als volgt uitzien:

![voorbeeldwerkblad](./media/use-functions-in-conditions/spreadsheet-table.png)

Gezien het voorgaande werkblad wilt u mogelijk Microsoft Flow gebruiken om alle rijen te verwijderen waarin de kolom *Status* is ingesteld op *voltooid* of *onnodig*.

Laten we de stroom maken.

### <a name="start-with-a-blank-flow"></a>Begin met een lege stroom
1. Meld u aan bij [Microsoft Flow](https://flow.microsoft.com).
   
    ![aanmelden](includes/media/modern-approvals/sign-in.png)
2. Selecteer het tabblad **Mijn stromen**.
   
    ![mijn stromen selecteren](includes/media/modern-approvals/select-my-flows.png)
3. Selecteer **Maken van lege**.
   
    ![een stroom op basis van een lege stroom maken](includes/media/modern-approvals/blank-template.png)

### <a name="add-a-trigger-to-your-flow"></a>Voeg een trigger toe aan uw stroom
1. Zoek **Schema** en selecteer de trigger **Schema - Terugkeerpatroon**
   
    ![trigger voor schema](includes/media/schedule-trigger/schedule-trigger.png)
2. Stel in dat het schema één keer per dag wordt uitgevoerd.
   
    ![schema instellen](includes/media/schedule-trigger/set-schedule.png)

### <a name="select-the-spreadsheet-and-get-all-rows"></a>Selecteer het werkblad en haal alle rijen op
1. Selecteer **Nieuwe stap** > **Een actie toevoegen**.
   
    ![nieuwe stap](includes/media/new-step/action.png)
2. Zoek naar **rijen** en selecteer vervolgens **Excel - Rijen ophalen**.
   
    Opmerking: selecteer de actie 'rijen ophalen' die overeenkomt met het werkblad dat u gebruikt. Als u bijvoorbeeld Google Sheets gebruikt, selecteert u **Google Sheets - Rijen ophalen**.
   
    ![Rijen ophalen](includes/media/new-step/get-excel-rows.png)
3. Selecteer het mappictogram in het vak **Bestandsnaam**, blader en selecteer vervolgens het werkblad dat uw gegevens bevat.
   
    ![werkblad selecteren](includes/media/new-step/select-spreadsheet.png)
4. Selecteer in de lijst **Tabelnaam** de tabel die uw gegevens bevat.
   
    ![tabel selecteren](includes/media/new-step/select-table.png)

### <a name="check-the-status-column-of-each-row"></a>Controleer de statuskolom in elke rij
1. Selecteer **Nieuwe stap** > **Meer** > **Een item voor toepassen toevoegen aan elk(e)**.
   
    ![tabel selecteren](includes/media/new-step/apply-to-each.png)
2. Voeg het token **Waarde** toe aan het vak **Een uitvoer selecteren uit de vorige stappen**.
   
    ![tabel selecteren](includes/media/apply-to-each/add-value-token.png)
3. Selecteer **Een voorwaarde toevoegen** > **Bewerken in de geavanceerde modus**.
4. Voeg de volgende **or**-functie toe. Deze **or**-functie controleert de waarde van elke rij in de tabel (een rij wordt als een item gezien als deze in een functie wordt benaderd). Als de waarde in de kolom **status** *voltooid* **of** *onnodig* is, eindigt de **or**-functie als 'true'.
   
    De **or**-functie wordt als volgt weergegeven:
   
    ````@or(equals(item()?['status'], 'unnecessary'), equals(item()?['status'], 'completed'))````
   
    Uw **Voorwaarde**-kaart lijkt op deze afbeelding:
   
    ![afbeelding van or-functie](./media/use-functions-in-conditions/or-function.png)

### <a name="delete-matching-rows-from-the-spreadsheet"></a>Overeenkomende rijen verwijderen uit het werkblad
1. Selecteer **Een actie toevoegen** in de vertakking **INDIEN JA, NIETS DOEN** van de voorwaarde.
2. Zoek **Rij verwijderen** en selecteer **Excel - Rij verwijderen**.
   
    ![afbeelding voor rij verwijderen](includes/media/new-step/select-delete-excel-row.png)
3. Zoek in het vak **Bestandsnaam** naar het werkbladbestand dat de gegevens bevat die u wilt verwijderen. Selecteer dit bestand.
4. Selecteer in de lijst **Tabelnaam** de tabel die uw gegevens bevat.
5. Plaats het token **Rij-id** in het vak **Rij-id**.
   
    ![werkbladbestand](includes/media/new-step/delete-excel-row.png)

### <a name="name-the-flow-and-save-it"></a>Geef de stroom een naam en sla deze op
1. Geef uw stroom een naam en selecteer de knop **Stroom maken**.
   
    ![de stroom opslaan](./media/use-functions-in-conditions/name-and-save.png)

### <a name="run-the-flow-with-the-or-function"></a>De stroom uitvoeren met de or-functie
De stroom wordt uitgevoerd nadat u deze hebt opgeslagen. Als u het werkblad hebt gemaakt dat eerder in dit overzicht werd weergegeven, ziet u het volgende nadat de uitvoering is voltooid:

![or-functie voltooid](./media/use-functions-in-conditions/spreadsheet-table-after-or-function-runs.png)

Let op dat alle gegevens uit rijen waarvan de kolom Status 'voltooid' of 'onnodig' bevatte zijn verwijderd.

## <a name="use-the-and-function"></a>De and-functie gebruiken
Stel dat u een werkbladtabel hebt met twee kolommen. De kolomnamen zijn Status en Toegewezen. Stel daarnaast dat u alle rijen wilt verwijderen als de waarde in de kolom Status 'geblokkeerd' is en de waarde in de kolom Toegewezen 'John Wonder' is.  Volg alle eerdere stappen in dit overzicht om deze taak uit te voeren. Als u de kaart **Voorwaarde** in de geavanceerde modus bewerkt, moet u echter de **and**-functie gebruiken die hier wordt weergegeven:

````@and(equals(item()?['Status'], 'blocked'), equals(item()?['Assigned'], 'John Wonder'))````

Uw **Voorwaarde**-kaart lijkt op deze afbeelding:

![afbeelding van and-functie](./media/use-functions-in-conditions/and-function.png)

### <a name="run-the-flow-with-the-and-function"></a>De stroom uitvoeren met de and-functie
Als u de stappen hebt gevolgd, lijkt uw werkblad op de volgende afbeelding:

![voordat and wordt uitgevoerd](./media/use-functions-in-conditions/spreadsheet-table-before-and-function-runs.png)

Nadat uw stroom is uitgevoerd, lijkt uw werkblad op de volgende afbeelding:

![nadat and is uitgevoerd](./media/use-functions-in-conditions/spreadsheet-table-after-and-function-runs.png)

## <a name="use-the-empty-function"></a>De empty-functie gebruiken
U ziet dat er nu verschillende lege rijen in het werkblad zijn. U kunt ze verwijderen door de functie **empty** te gebruiken om alle rijen te vinden waarvan de kolommen Toegewezen en Status geen tekst bevatten.

Volg alle stappen onder het kopje **De and-functie gebruiken**, eerder in dit overzicht, om deze taak uit te voeren. Als u de kaart **Voorwaarde** in de geavanceerde modus bewerkt, moet u echter de empty-functie als volgt gebruiken:

````@and(empty(item()?['Status']), empty(item()?['Assigned']))````

Uw **Voorwaarde**-kaart lijkt op deze afbeelding:

![afbeelding van empty-functie](./media/use-functions-in-conditions/empty-function.png)

Nadat uw stroom is uitgevoerd, lijkt het werkblad op de volgende afbeelding:

![nadat empty is uitgevoerd](./media/use-functions-in-conditions/spreadsheet-table-after-empty-function-runs.png)

U ziet dat de extra regels uit de tabel zijn verwijderd.

## <a name="use-the-greater-function"></a>De greater-functie gebruiken
Stel dat u baseballtickets voor uw collega’s hebt gekocht en een werkblad gebruikt om te zorgen dat iedereen u terugbetaalt. U kunt snel een stroom maken die dagelijks een e-mail stuurt naar elke persoon die nog niet het volledige bedrag heeft betaald.

Gebruik de functie **greater** om de medewerkers te vinden die het volledige bedrag niet hebben betaald. U kunt vervolgens automatisch een vriendelijke herinneringse-mail sturen aan iedereen die nog niet het volledige bedrag heeft betaald.

Hier volgt een overzicht van het werkblad:

![overzicht van het werkblad](./media/use-functions-in-conditions/tickets-spreadsheet-table.png)

Hier ziet u de implementatie van de **greater**-functie, zodat alle personen zichtbaar zijn die minder dan het verschuldigde bedrag hebben betaald:

````@greater(item()?['Due'], item()?['Paid'])````

## <a name="use-the-less-function"></a>De less-functie gebruiken
Stel dat u baseballtickets voor uw collega’s hebt gekocht en een werkblad gebruikt om te zorgen dat iedereen u terugbetaalt op de afgesproken datum. U kunt een stroom maken die een herinneringse-mail stuurt naar iedere persoon die het volledige bedrag niet heeft betaald als de huidige datum minder dan één dag voor de vervaldatum ligt.

Gebruik de **and**-functie en de **less**-functie omdat er twee voorwaarden moeten worden gevalideerd:

| Te valideren voorwaarde | Te gebruiken functie | Voorbeeld |
| --- | --- | --- |
| Is het volledige bedrag terugbetaald? |greater |@greater(item()?['Due'], item()?['Betaald']) |
| Is de einddatum minder dan één dag verwijderd? |less |@less(item()?['DueDate'], addDays(utcNow(),1)) |

## <a name="combine-the-greater-and-less-functions-in-an-and-function"></a>De functies greater en less combineren in een and-functie
Gebruik de functie **greater** om vast te stellen welke medewerkers minder dan het volledige bedrag hebben betaald en gebruik de functie **less** om vast te stellen of de einddatum voor de betaling minder dan één dag van de huidige datum is verwijderd. U kunt vervolgens de functie **Een e-mail verzenden** gebruiken om een vriendelijke herinneringse-mail te sturen naar diegenen die het volledige bedrag nog niet hebben betaald als de einddatum minder dan één dag is verwijderd.

Hier volgt een overzicht van de werkbladtabel:

![overzicht van het werkblad](./media/use-functions-in-conditions/spreadsheet-table-due-date.png)

Hier volgt de implementatie van de **and**-functie die alle personen in kaart brengt die minder dan het verschuldigde bedrag hebben betaald wanneer de einddatum minder dan één dag van de huidige datum is verwijderd:

````@and(greater(item()?['Due'], item()?['Paid']), less(item()?['dueDate'], addDays(utcNow(),1)))````

## <a name="learn-more"></a>Meer informatie
Meer informatie over andere [functies](https://docs.microsoft.com/azure/logic-apps/logic-apps-workflow-definition-language#functions)

