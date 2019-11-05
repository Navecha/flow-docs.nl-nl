---
title: Release opmerkingen | Microsoft Docs
description: Veelvoorkomende problemen en wat is er nieuw voor Microsoft Flow releases
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
ms.date: 08/31/2018
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 6c414538c31aa17ed5ab6ba1498812576a8024ae
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548851"
---
# <a name="release-notes"></a>Release opmerkingen
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="top-questions"></a>Beste vragen
1. Mijn stroom is mislukt. Hoe kan ik oplossen?
   
   1. De fout te identificeren. Ga eerst naar het meldingen pictogram boven aan de webportal of selecteer het tabblad **activiteit** in de mobiele app. U ziet nu uw stroom, en u kunt deze selecteren.
   2. U bekijkt nu de gegevens van de stroom. Zoek de stap met het rode uitroep teken. hier wordt het fout bericht voor uw stroom weer gegeven.
   3. Afhankelijk van het fout bericht moet u de stroom kunnen **bewerken** en herstellen. [Meer informatie over het oplossen van veelvoorkomende stroom storingen](fix-flow-failures.md).
2. Hoe kan ik een geavanceerde voor waarde of een expressie gebruiken?
   
   * Meer informatie over het [toevoegen van voor waarden](add-condition.md).
   * Als u meerdere cases in een stroom wilt, selecteert u **voor waarde toevoegen** binnen een bestaande voor waarde.
   * Maak een geavanceerde expressie door te verwijzen naar [een functie in Logic apps](https://docs.microsoft.com/rest/api/logic/definition-language).
3. Hoe werkt licentie verlening met Office 365?
   
   * Als u een Office 365-gebruiker bent, krijgt u volledige toegang tot het abonnement van de Microsoft Flow voor Office 365. Zie de [prijzen plannen voor Microsoft flow](https://flow.microsoft.com/pricing/) voor meer informatie.
   * Als u een beheerder bent, raadpleegt u informatie over [licentie verlening voor Microsoft flow](organization-q-and-a.md), met inbegrip van Office 365.

## <a name="known-issues"></a>Bekende problemen
1. Share point-lijsten op mijn sites en die niet van het type *aangepaste lijst* zijn, worden niet ondersteund. U kunt dit probleem omzeilen door een aangepaste lijst te maken op een standaard-share point-site.
2. Bestands triggers worden niet gestart voor bestanden die worden toegevoegd aan de geneste mappen in de map die u selecteert.

## <a name="whats-new"></a>Wat is er nieuw

> [!IMPORTANT]
>
> **Aankondiging van de release opmerkingen**
>
> Vraagt u zich af over toekomstige en onlangs uitgebrachte mogelijkheden van Microsoft Flow?
>[Bekijk de release opmerkingen van oktober 2018](https://docs.microsoft.com/business-applications-release-notes/October18/microsoft-flow/). We hebben alle details, end-to-end, van boven naar beneden vastgelegd, die u kunt gebruiken voor de planning. Bekijk voor meer informatie [elke wekelijkse release](https://docs.microsoft.com/business-applications-release-notes/powerplatform/released-versions/flow) met de functies en verbeteringen die deze bevat.
>
> De release opmerkingen vóór de release van oktober 2018 blijven hier aanwezig voor toekomstige verwijzingen, maar alle nieuwe releases worden alleen opgenomen in de bovenstaande locaties en niet op deze pagina.

### <a name="release-2018-09-24"></a>Release 2018-09-24

- **Beheerders toegang tot Help en ondersteuning** -open ondersteunings tickets voor Microsoft flow in het Power-platform beheer centrum en geef aanvullende informatie over uw werk stroom fout op.
- Nieuwe, **geontwerpde stroom Community** : zoeken naar wat u nodig hebt, is nog eenvoudiger geworden in de stroom community.
- **Verbeteringen aan de micro soft teams-connector** : nieuwe triggers voor micro soft teams zodat u een stroom kunt uitvoeren wanneer er nieuwe berichten in een kanaal zijn.
- **Meer share point-acties** : er zijn nieuwe acties voor het verplaatsen van bestanden en meer in de share point-connector.
- **Nieuwe rapporten van de admin Analytics** -omgeving en Tenant Wide Analytics die zijn toegevoegd aan het beheer centrum van het Business Application platform.
- **Power query-integratie** : er wordt een Power query-ervaring gebouwd waarmee makers van SQL Server shape kunnen maken van gegevens.

[Meer informatie en vragen](https://flow.microsoft.com/blog/support-tickets-teams-sharepoint/) over deze release.

### <a name="release-2018-08-31"></a>Release 2018-08-31

- **Test uw stroom met voorbeeld** gegevens van het gebruik van voorbeeld gegevens van connectors om uw stroom te testen wanneer u deze in de Microsoft flow Designer bouwt. Wanneer u de stroom met voorbeeld gegevens test, bevestigt u dat de stroom wordt uitgevoerd zoals verwacht wanneer deze naar productie wordt geïmplementeerd.
- **Vijf nieuwe connectors** : er zijn vier nieuwe connectors voor het beheer van apps toegevoegd. Powerapps voor app-makers, Power-platform voor beheerders, Powerapps voor beheerders, Microsoft flow voor beheerders en micro soft school Data Sync.

[Meer informatie en vragen](https://flow.microsoft.com/blog/test-data-management-connectors/) over deze release.

### <a name="release-2018-08-24"></a>Release 2018-08-24

- **Nieuwe sjablonen voor agenda synchronisatie** : nieuwe agenda sjablonen waarmee gebeurtenissen worden gekopieerd tussen Google Calendar en Office 365 of Outlook.com.
- **Ondersteuning voor meerdere waarden voor share point** -Lees-en schrijf bewerkingen voor velden met meerdere waarden in share point die keuze-, persoons-of opzoek typen zijn.
- **Goed keuringen verzenden namens andere gebruikers in uw organisatie** : goed keuringen verzenden namens andere gebruikers in uw organisatie, bijvoorbeeld de persoon die het bestand in de share point-lijst heeft geüpload, in plaats van de persoon die de stroom heeft gemaakt.
- **Meer invoer typen voor knop** -knoppen hebben twee nieuwe invoer typen: aantal en ja/nee.
- **Connector updates** : een nieuwe netdocument connector, verbeteringen voor Azure-connectors en meer.

[Meer informatie en vragen](https://flow.microsoft.com/blog/button-types-more/) over deze release.

### <a name="release-2018-08-02"></a>Release 2018-08-02

Het Microsoft Flow preview-programma is de manier om vroegtijdig toegang te krijgen tot de aanstaande functionaliteit en updates voor Microsoft Flow. Als u vroegtijdig toegang wilt krijgen tot de nieuwste functies, maakt en gebruikt u een omgeving in de preview-regio.

[Meer informatie en vragen](https://flow.microsoft.com/blog/flow-preview-program/) over deze release.

### <a name="release-2018-07-23"></a>Release 2018-07-23

- **Bouw en voer stromen uit vanuit Excel** : met de knop nieuwe **stroom** (toegankelijk via het tabblad **gegevens** van het lint) kunt u Automation-bewerkingen maken en activeren vanuit Microsoft flow op uw tabel gegevens in Excel. Automatische verwerking van gegevens of het kopiëren/importeren van gegevens.
- **Een bedrijfsproces stroom maken** : een bedrijfs proces stroom is een nieuw type stateful, Human-Interactive flow op basis van de common data service. Gebruik deze nieuwe stromen om een reeks fasen en stappen te definiëren die gebruikers kunnen volgen. Ze kunnen naar wens vooruit en achteruit gaan.
- **Een stroom maken voor micro soft to-do in Outlook Web app** : als iemand \@vermeld in Outlook Web app, wordt er een snelkoppeling weer gegeven om een stroom te maken. Deze stroom maakt automatisch taken voor de \@genoemde persoon in micro soft to-do, op basis van de inhoud van het e-mail bericht.
- **Ondersteuning voor share point-weer gave** : de share point-connector ondersteunt nu het selecteren van een specifieke share point-weer gave voor triggers en acties. Hiermee worden de kolommen gefilterd op alleen de velden in de geselecteerde weer gave.
- **Vier nieuwe Connect oren** -Azure IOT Central: een zeer schaal bare IOT-oplossing voor software-as-a-Service (SaaS)-Survey 123, LMS365 en ProjectWise design Integration.

[Meer informatie en vragen](https://flow.microsoft.com/blog/excel-bpf-todo-and-more/) over deze release.

### <a name="release-2018-06-29"></a>Release 2018-06-29

- **Aanvraag voor afmeldings stroom ingebouwd in share point** : wanneer u een bestand of item in share point selecteert, wordt er een nieuwe **aanvraag voor de afmeldings** stroom weer gegeven. Voor deze stroom is geen configuratie of installatie vereist en er wordt een afmeldings aanvraag met één klik verzonden.
- Er zijn **twee nieuwe Connect oren** toegevoegd: Cloud Connect Studio en PoliteMail.
- **Verbeteringen in de pagina geschiedenis en het maken van pagina's** : we vernieuwen de lijst met uitvoerings GESCHIEDENISS met een exacte uitvoerings tijd en de pagina maken door een nieuwe scenario video toe te voegen.

[Meer informatie en vragen](https://flow.microsoft.com/blog/request-sign-off-four-connectors/) over deze release.

### <a name="release-2018-06-08"></a>Release 2018-06-08

- **Power shell-cmdlets** : zowel stroom makers als Tenant beheerders kunnen nu Power shell gebruiken voor het programmatisch beheren van hun stromen.
- **Verbeteringen aan de werk stroom van teams** : de stroom bot in micro soft teams kan stroom knoppen uitvoeren en uw stromen beschrijven.
- **Drie nieuwe connectors** : er is ondersteuning toegevoegd voor marketo, ElasticOCR en DynamicSignal. 
- **Aanvullende** gegevens voor delen: extra informatie toegevoegd bij het delen of uitvoeren van gedeelde stromen, zodat u precies weet welke machtigingen andere mensen krijgen.
- **Share point-Url's automatisch afkorten** : wanneer u een share point-URL in de browser kopieert en plakt, kan deze extra tekst bevatten die zich buiten de site bevindt. deze tekst wordt automatisch verwijderd zodat u verbinding kunt maken met alleen de site.
- **Documentatie over AVG-aanvragen** : we hebben een uitgebreide gids en toolset voor ondernemingen gemaakt om aanvragen voor het indienen van gegevens te verwerken.

[Meer informatie en vragen](https://flow.microsoft.com/blog/powershell-flow-bot-marketo/) over deze release.

### <a name="release-2018-05-21"></a>Release 2018-05-21

- **Stromen ' eigendom van ' share point-lijsten en-bibliotheken** : stromen die werken met share point-lijsten en-bibliotheken kunnen worden gedeeld met die lijsten of bibliotheken. In plaats van te worden gedeeld met individuen of groepen, worden ze dus gedeeld met iedereen die toegang heeft tot de lijst. Wanneer gebruikers worden toegevoegd aan of verwijderd uit de lijst of bibliotheek, wordt het lidmaatschap hiervan automatisch gewijzigd.
- **Analyse van fout Details** : een nieuw Inge sloten rapport met informatie over alle fouten die zich in een stroom voordoen.
- **Stromen delen met office 365-groepen** : u kunt een Office 365 moderne groep de eigenaar van een stroom maken en u kunt knop stromen delen met Office 365-groepen, zodat iedereen in de groep de stroom kan uitvoeren.
- **Verbeteringen van de share point-connector** : er zijn twee nieuwe mogelijkheden voor share point-connectors die worden geactiveerd wanneer items of bestanden worden verwijderd en een http-eind punt aanroepen dat de share point-rest API ondersteunt.
- **Twee nieuwe connectors** -ondersteuning toegevoegd voor Azure Data Factory en mailparser

[Meer informatie en vragen](https://flow.microsoft.com/blog/share-with-sharepoint-office-365/) over deze release.

### <a name="release-2018-05-01"></a>Release 2018-05-01

- **Tekst met opmaak in goedkeurings berichten** : gebruik prijs verlaging om de goedkeurings gegevens op te maken die u verzendt.
- **Knoppen met meerdere selectie-ingangen** : Maak stroom knoppen die gebruikmaken van een meervoudige selectie lijst om meer dan één waarde tegelijk te verzamelen.
- **Werken met bredere stromen** : de mobiele app van Microsoft flow ondersteunt nu de weer gave liggend en de Web Designer heeft een horizontale schuif balk.

[Meer informatie en vragen](https://flow.microsoft.com/blog/rich-approvals-text-and-multiselect/) over deze release.

### <a name="release-2018-04-12"></a>Release 2018-04-12

- **Gegevens retour neren naar PowerApps vanuit een stroom** voor het maken van stromen die kan worden aangeroepen vanuit een app die is gemaakt met PowerApps en waarmee gegevens terug naar de app worden geretourneerd. Gebruik de visuele stroom ontwerper voor slepen en neerzetten om de logica te bouwen die u nodig hebt voor uw apps. 
- **Meerdere records toevoegen aan matrix invoer** : er is een opbouw functie voor lijsten toegevoegd aan Microsoft flow die kan worden gebruikt om meerdere bijlagen toe te voegen aan een e-mail bericht.
- **Test stromen met eerdere gegevens voor uitvoeren** : er is een nieuwe knop Test flow toegevoegd aan de ontwerp functie waarmee u uw stroom kunt testen met trigger gegevens uit eerdere stroom uitvoeringen.
- **Nieuwe velden werk stroom ()** : u hebt nu toegang tot de weergave naam van de omgevings naam en de stroom met de expressie werk stroom ().

[Meer informatie en vragen](https://flow.microsoft.com/blog/return-data-to-powerapps/) over deze release.

### <a name="release-2018-04-04"></a>Release 2018-04-04

- **Goed keuringen voor de common data service** moderne goed keuringen zijn gebaseerd op de meest recente versie van de common data service. Dit betekent dat u stromen kunt maken die de status van de goed keuringen lezen die u verzendt of ontvangt met de Common Data Service-connector.
- **Fouten zoeken in Toep assen op elke** -ga rechtstreeks naar fouten in lussen in de weer gave stroom uitvoering, zelfs wanneer er honderden items in de lus zijn.
- **Goed keuringen opnieuw toewijzen** : u kunt goed keuring toewijzen aan een andere persoon in uw organisatie om de goed keuring te delegeren. 
- **Lijsten met ruimten** : de Office 365 Outlook-Connector heeft acties toegevoegd om kamer gegevens in uw organisatie op te halen.
- **Details van stroom knoppen weer geven** : wanneer u een stroom uitvoert die met u is gedeeld, kunt u nu alle acties zien die door de stroom worden gebruikt.
- **Regio van het Verenigd Konink rijk** : omgevingen kunnen nu worden gemaakt voor het opslaan van hun gegevens in het Verenigd Konink rijk.
- **Twee nieuwe Connect oren** : er is ondersteuning toegevoegd voor de AtBot-beheer-en marketing-inhouds hub.
- **Nieuwe landings pagina voor documentatie** : de landings pagina van de documentatie is bijgewerkt zodat de inhoud is gegroepeerd op wie u bent: een beginner, een gevorderde gebruiker of een deskundige. 

[Meer informatie en vragen](https://flow.microsoft.com/blog/approvals-in-cds-and-seven-updates/) over deze release.

### <a name="release-2018-03-13"></a>Release 2018-03-13

- **Goedkeurings geschiedenis** : Bekijk alle goedkeurings aanvragen die u hebt verzonden, met inbegrip van de antwoorden, de opmerkingen die zijn verzonden en de exacte tijd waarop deze zijn opgetreden.
- **Vier nieuwe connectors** : Excel online (Business), Excel online (OneDrive), Azure SQL Data Warehouse en Pitney Bowes-reken machine toevoegen.
- **Knop Info voor dynamische inhoud** : Houd de muis aanwijzer boven dynamische inhoud om te zien waar deze zich bevindt en Bekijk de expressies zonder de volledige expressie-editor te openen.
- **Gelijktijdigheids beheer** : Schakel gelijktijdigheids beheer in om een bepaalde stroom op één keer uit te voeren.
- **Exponentieel opnieuw proberen** -een nieuw type beleid voor opnieuw proberen waarbij nieuwe pogingen exponentieel in de loop van de tijd worden herhaald.
- **Conformiteit** van de toegankelijkheid: er zijn nieuwe conformiteit-documenten uitgegeven die beschrijven hoe Microsoft flow voldoen aan de toegankelijkheids normen.

[Meer informatie en vragen](https://flow.microsoft.com/blog/approval-history-accessibility/) over deze release.

### <a name="release-2018-02-09"></a>Release 2018-02-09

- **Hoge Beschik baarheid van Gateway** : Maak Maxi maal beschik bare clusters van on-premises gegevens gateways om verbindingen tot stand te brengen wanneer één machine uitvalt.
- **Verbeterd toegepast op elke** -met Flow-abonnement 1 of flow-abonnement 2 proces tot 100.000 items in één run-en 50-acties parallel in toegepast op elke lus. 

[Meer informatie en vragen](https://flow.microsoft.com/blog/gateway-ha-increased-apply-to-each/) over deze release.

### <a name="release-2018-01-29"></a>Release 2018-01-29

- **Stroom in micro soft teams** : vanuit teams kunt u stromen maken en beheren, uw ontvangen en verzonden goed keuringen controleren en stromen direct starten in de teams bureau blad-app of op teams.Microsoft.com-meer [informatie](https://flow.microsoft.com/blog/microsoft-flow-in-microsoft-teams/).
- **Meldingen voor gedeelde bewerkingen** : wanneer een stroom die u bezit, wordt gewijzigd door een mede werker, ontvangt u een e-mail melding waarin u wordt geïnformeerd wie de stroom heeft gewijzigd.
- **Nieuwe expressies** -er zijn twee nieuwe sets expressies toegevoegd: een voor het parseren van url's en een andere voor het werken met JSON-objecten.
- **Drie nieuwe connectors** -deze week zijn er twee nieuwe Plumsail-connectors: Plumsail SP-en Plumsail-formulieren en een nieuwe connector voor kintone.

[Meer informatie en vragen](https://flow.microsoft.com/blog/shared-notifications-and-expressions/) over deze release.

### <a name="release-2018-01-17"></a>Release 2018-01-17

- **Office 365-profiel gegevens** -we hebben nieuwe acties toegevoegd aan de connector van Office 365-gebruikers die werkt met gebruikers profielen en foto's.
- **Toevoegen aan teken reeks variabelen** : u kunt toevoegen aan teken reeksen in lussen om tabellen of andere lijsten samen te stellen.
- **Infobip-connector** : Infobip is een service die communicatie op bedrijfs niveau mogelijk maakt, inclusief spraak oproepen en activering van inkomende SMS-berichten.

[Meer informatie en vragen](https://flow.microsoft.com/blog/o365-profile-infobip/) over deze release.

### <a name="release-2017-12-20"></a>Release 2017-12-20

Microsoft Flow Analytics is nu beschikbaar in alle Microsoft Flow regio's, wat betekent dat u meer inzicht kunt krijgen in de status van stromen die worden uitgevoerd in uw omgeving.

[Meer informatie en vragen](https://flow.microsoft.com/blog/announcing-microsoft-flow-analytics/) over deze release.


### <a name="release-2017-12-14"></a>Release 2017-12-14

- **Verbeteringen in Outlook-Connector** : u kunt een e-mail bericht als een EML-bestand opslaan, automatisch reageren op agenda-uitnodigingen en stromen activeren wanneer u in een e-mail thread wordt genoemd.
- **Verbeteringen in verbindingen** : Microsoft flow de meest recent gebruikte verbindingen te onthouden en geeft alle nieuw toegevoegde connectors weer.
- **Vijf nieuwe Connect oren** -Azure container instances, Azure Kusto,-taak, micro soft to-do en Plumsail-documenten toegevoegd.
- **Http-verbeteringen** : de http-actie ondersteunt nu gesegmenteerde code ring.

[Meer informatie en vragen](https://flow.microsoft.com/blog/outlook-connector-more/) over deze release.

### <a name="release-2017-12-05"></a>Release 2017-12-05

Het paneel Microsoft Flow starten is nu beschikbaar in alle regio's. In dit deel venster kunt u waarden toevoegen aan een stroom wanneer u deze in uw share point-lijst of document bibliotheek uitvoert.

[Meer informatie en vragen](https://flow.microsoft.com/blog/introducing-flow-launch-panel-in-sharepoint-lists-and-libraries/) over deze release.


### <a name="release-2017-11-28"></a>Release 2017-11-28

- **Beheerde meta** gegevens: gegevens lezen van en schrijven naar, kolommen in share point die gebruikmaken van de beheerde meta gegevens (ook wel. Taxonomie).
- Toevoegen **aan matrices** : Voeg items toe aan het einde van matrices met behulp van een nieuwe actie voor toevoegen aan matrix variabele.
- **Tago** : een nieuwe connector voor Tago, waarmee u eenvoudig elektronische apparaten kunt verbinden met externe gegevens om slimmere beslissingen te kunnen nemen met behulp van contextuele analyse.
- **iPhone x** : een nieuwe versie van de Microsoft flow-app die gebruikmaakt van het volledige scherm op de iPhone X en die een snelheids verbetering heeft voor het uploaden van afbeeldingen.

[Meer informatie en vragen](https://flow.microsoft.com/blog/managed-metadata-tago/) over deze release.

### <a name="release-2017-11-09"></a>Release 2017-11-09

- **Integratie met OneDrive voor bedrijven** : er is [nu een stroom knop in onedrive voor bedrijven](https://flow.microsoft.com/blog/microsoft-flow-integration-in-one-drive-for-business-and-new-connector-actions/) waarmee stromen kunnen worden gemaakt of geactiveerd voor geselecteerde bestanden of mappen.
- **Planner triggers** : Hiermee worden stromen gestart wanneer er een nieuwe taak wordt gemaakt, wanneer een taak aan u wordt toegewezen of wanneer deze is voltooid.
- **Share point-bijlagen** -werk met bijlagen in share point-lijst items: lijsten, downloaden, toevoegen of verwijderen van bijlagen.
- **Stroom beheer connector** : Maak stromen die het beheer van andere stromen in uw omgeving automatiseren (bijvoorbeeld door het toevoegen van machtigingen aan stromen automatisch).
- **Vier nieuwe Connect oren** -Azure Custom Vision service toevoegen, D & B Optimizer, Enadoc en Derdak SIGNL4. 
- **Meer connector acties** : Voer SQL-query's uit, krijg snellere e-mail triggers, gebruik een wille keurige methode met http met Azure AD en meer.

[Meer informatie en vragen](https://flow.microsoft.com/blog/planner-triggers-connector-improvements/) over deze release.

### <a name="release-2017-11-02"></a>Release 2017-11-02

- **Controle logboek registratie** : Microsoft flow controle gebeurtenissen zijn nu beschikbaar in Office 365 beveiligings-en compliancecentrum voor alle tenants.
- Met **flow-widget** wordt een probleem opgelost in de mobiele flow-app, waardoor knoppen niet in de widget worden geladen.

[Meer informatie en vragen](https://flow.microsoft.com/blog/security-and-compliance-center/) over deze release.

### <a name="release-2017-10-19"></a>Release 2017-10-19

- **Genest Toep assen op elke** -u kunt Toep assen op elke actie, filteren en selecteren in andere Toep assen op elke container actie.
- **Datum tijd acties** : nieuwe acties voor het verkrijgen van lokale tijden, het toevoegen, aftrekken of opmaken van tijden.
- **Vier nieuwe Connect oren** -content moderator, Docparser, micro soft Kaizala en Pitney Bowes-gegevens validatie toegevoegd.
- **Verbeterde verbindings ervaring** : meldingen in de Microsoft flow Portal wanneer een verbinding wordt verbroken en er uitgebreide verbindings Details zijn.
- **On-the-go-verzameling** : een nieuwe sjabloon verzameling voor [on-the-go-werk](https://flow.microsoft.com/collections/onthego/)rollen.
- **Invoer van de knop e** -mail adres: e-mail adressen van gebruikers verzamelen wanneer deze knoppen worden uitgevoerd.
- **Invoer van de knop bestand** : Hiermee worden geüploade bestanden, zoals Foto's, opgehaald van gebruikers wanneer ze knoppen uitvoeren.
- **Eerste uitvoering en automatische aanmelding** : verbeterde ervaring voor eerste uitvoering in de mobiele app, inclusief automatische aanmelding.
- **Snellere micro soft Forms-triggers** : formulieren worden veel sneller uitgevoerd dan vóór (eerder één keer per uur).
- **Via de knop invoer in sessies** : knoppen die op uw mobiele telefoon worden geactiveerd, onthouden eerdere invoer.
- **Feed voor mobiele activiteiten** : verbeterde activiteitsfeed zodat u meer gedetailleerde samen vattingen en probleemoplossings Details kunt gebruiken.

[Meer informatie en vragen](https://flow.microsoft.com/blog/nested-apply-to-each/) over deze release.

### <a name="release-2017-10-03"></a>Release 2017-10-03

- **Alle moeten worden goedgekeurd** : vereisen dat een goedkeurings aanvraag wordt verzonden naar meer dan één persoon om iedereen die de aanvraag heeft ontvangen om deze goed te keuren.
- **Nieuwe acties voor onedrive voor bedrijven** : Genereer pdf's voor bestanden die zijn opgeslagen in OneDrive voor bedrijven en vier andere nieuwe acties.
- **Apache Impala-connector** -Apache Impala (incubatiing) is de open source-systeem eigen analytische data base voor Apache Hadoop.
- **Stroom beschrijvingen toevoegen** : Geef uw stromen beschrijvingen zodat u ze kunt delen, zodat uw collega's een samen vatting van de stroom kunnen zien.

[Meer informatie en vragen](https://flow.microsoft.com/blog/all-must-approve-and-onedrive/) over deze release.

### <a name="release-2017-09-25---q3-update-for-microsoft-flow"></a>Release 2017-09-25-Q3 update voor Microsoft Flow

- Uitgebreide **share point-integratie in eerste release** : er zijn nieuwe ' in-the-box ' verzenden voor controle stromen en een stroom paneel voor het verzamelen van invoer wanneer u een stroom uitvoert voor de eerste release-tenants.
- **Dynamics 365-apps** -flow is nu geïntegreerd in de gebruikers interface voor Dynamics 365-apps, zoals Dynamics 365 Sales en Dynamics 365 Customer service.
- **Micro soft vertrouwens centrum** -Microsoft flow wordt vermeld in het vertrouwens centrum van micro soft, met certificeringen zoals HIPAA, ISO en soc.
- **Gebruiks analyse** : elke stroom heeft een inge sloten Power bi dash board met Basic Usage Analytics.
- **Controle logboek registratie in de eerste release** : alle Flow Management-gebeurtenissen worden geregistreerd in het Office 365 Security and Compliance Center voor de eerste release-tenants.
- **Zes nieuwe Connect oren** -toegevoegde LinkedIn-, Office 365-groepen, Skype voor bedrijven, Adobe Sign, Bizzy en Azure log Analytics gegevens verzameling.
- **SQL-triggers** -stromen uitvoeren wanneer een nieuwe rij wordt toegevoegd of een rij wordt bijgewerkt in een SQL-tabel.
- **On-premises aangepaste connectors** : aangepaste Connectors kunnen nu gebruikmaken van de on-premises gegevens gateway om verbinding te maken met interne eind punten in uw netwerk.

[Meer informatie en vragen](https://flow.microsoft.com/blog/q3-2017-update/) over deze release.

### <a name="release-2017-09-21"></a>Release 2017-09-21

- **Stroom geschiedenis downloaden** : down load de uitvoerings geschiedenis van een stroom als een CSV-bestand om te openen in Excel.
- **Geavanceerde terugkeer patronen** : Stel terugkerende schema's samen om uw stromen te activeren, bijvoorbeeld alleen trigger op werk dagen.
- **IntelliSense** : wanneer u in expressies typt, geeft IntelliSense suggesties voor para meters.
- **Vier nieuwe connectors** : toegevoegde connectors voor Azure AD http Services, Amazon Redshift, Azure Event grid Publish en FlowForma.
- **Koppelingen voor delen** : een nieuwe actie voor het genereren van deelbaare koppelingen voor OneDrive-bestanden of Azure Storage-blobs.

[Meer informatie en vragen](https://flow.microsoft.com/blog/download-history-recurrence/) over deze release.


### <a name="release-2017-08-25"></a>Release 2017-08-25
* **Document eigenschappen en meer voor share point** - de eigenschappen van de [share point-document bibliotheek lezen en instellen](https://flow.microsoft.com/blog/support-for-sharepoint-document-library-properties/), en extra velden gebruiken zoals koppelingen naar het share point-item.
* **Stroom verzamelingen** : stroom verzamelingen zijn een verzameling sjabloon verzamelingen, geordend op rol of verticaal.
* Opnieuw delen van de **knop** : wanneer u knoppen deelt met uw collega's, kunnen ze ze ook opnieuw delen met andere personen.
* **Lijsten van knoppen verzamelen** : Definieer vervolg keuzelijsten met opties die gebruikers kunnen kiezen wanneer ze op de knop tikken.
* **Zeven nieuwe connectors** : Aweber, Azure log Analytics, Azure Tables, DocFusion365, Azure Event grid, Azure Event hubs en StaffHub. 
* **Verbeteringen in de toegestane vertraging en MySQL** : Hiermee maakt of verbindt u kanalen in toegestane vertraging en kunt u schrijven naar MySQL-data bases.

[Meer informatie en vragen](https://flow.microsoft.com/blog/button-updates-seven-connectors/) over deze release.

### <a name="release-2017-08-02"></a>Release 2017-08-02
* **Schrijven naar persoons-, keuze-en opzoek velden** : het item maken van share point en update-item [bieden nu ondersteuning voor de mogelijkheid om](https://flow.microsoft.com/blog/setting-sharepoint-s-person-choice-and-lookup-fields/) persoons-, keuze-en opzoek velden in te stellen.
* **Meer actie-instellingen** : er is nu meer controle over de manier waarop triggers en acties worden uitgevoerd, waaronder het configureren van beleid voor opnieuw proberen en de paginering.
* **Vier nieuwe connectors** : u kunt nu Azure File Storage, elastische formulieren, Plivo en video indexer gebruiken.

[Meer informatie en vragen](https://flow.microsoft.com/blog/four-connector-action-settings/) over deze release.

### <a name="release-2017-07-27---q2-update-for-microsoft-flow"></a>Release 2017-07-27-Q2 update voor Microsoft Flow
* **Importeer en exporteer** /Exporteer en importeer stroom oplossingen in omgevingen of van testen naar productie. 
* **Expressies gebruiken in acties** : expressies invoeren in elke actie en inline-hulp krijgen bij het gebruik hiervan.
* **Verg root tot Azure Logic apps** : Sla uw stromen op als Azure Logic app-resource die kan worden geïmplementeerd via Visual Studio of de Azure Portal.
* **Zicht baarheid van beheerder** : down load Microsoft flow gebruik in uw Tenant om precies te begrijpen waar en hoe stromen worden gebruikt.
* **Stromen in dynamics 365** -stromen gebruiken binnen Dynamics 365 voor Operations & Financials, Business Edition.
* **Scenario's eenvoudiger vinden** : Blader door de connector en gebruik vervolgens elke trigger als een doorlopend punt voor het bouwen van stromen.

[Meer informatie en vragen](https://flow.microsoft.com/blog/q2-2017-update/) over deze release.

### <a name="release-2017-07-13"></a>Release 2017-07-13
* **Verbeterde sjabloon publicatie** : Publiceer elke stroom die u maakt, samen met de bijbehorende categorieën, naar de open bare galerie.
* **Gebeurtenissen ophalen in uw Outlook-agenda** : een nieuwe actie voor het retour neren van alle gebeurtenissen tussen twee tijdstippen in uw agenda.
* **Nieuwe mobiele functionaliteit** : voert stromen op aanvraag uit en voert mislukte uitvoeringen opnieuw uit in de mobiele app.
* **Dynamische vervolg keuzelijsten in aangepaste connectors** : Maak dynamische vervolg keuzelijsten, polling triggers en test uw aangepaste connectors.

[Meer informatie en vragen](https://flow.microsoft.com/blog/publishing-and-custom-connectors/) over deze release.

### <a name="release-2017-06-28"></a>Release 2017-06-28
* **Uw taal instellingen bijwerken** : u kunt zowel de taal als de regio die Microsoft Flow gebruikt, aanpassen via het menu instellingen.
* **Vijf nieuwe Connect oren** : er is ondersteuning toegevoegd voor Adobe Creative Cloud, Bing Maps, Bing Search, jotform en Freshservice.
* **Configureer time-outs** : Wijzig de tijd waarmee langlopende acties, zoals goed keuringen, worden uitgevoerd vóór de time-out en de stroom wordt voortgezet.
* **Opmerkingen toevoegen aan Outlook voor goed keuringen** : wanneer u een goedkeurings aanvraag ontvangt, kunt u opmerkingen geven zonder Outlook te verlaten.
* **Gloed kleuren van aangepaste connector** : u kunt nu een kleur invoeren voor uw aangepaste connectors die worden gebruikt voor de achtergrond.
* **Opslaan als voor team stromen** : kopieën maken van alle stromen, inclusief team stromen
* **Informatie over de stroom verwijderen** : wanneer u een stroom verwijdert, wordt de lijst met alle uitgevoerde uitvoeringen voor die stroom weer gegeven.
* **Filteren op de pagina connectors** : zoek naar de gewenste connectors op de pagina connectors en filter op type connector.

[Meer informatie en vragen](https://flow.microsoft.com/blog/language-settings-3-connectors/) over deze release.

### <a name="release-2017-06-19"></a>Release 2017-06-19
U kunt nu de status weer geven van alle goedkeurings aanvragen die u hebt verzonden. Daarnaast kunt u op al uw eigen goed keuringen rechtstreeks vanaf uw mobiele apparaat door bladeren en actie ondernemen.

[Meer informatie en vragen](https://flow.microsoft.com/blog/sent-requests-flow-mobile/) over deze release.

### <a name="release-2017-06-15"></a>Release 2017-06-15
* **Inhouds conversie** : een nieuwe connector waarmee HTML-inhoud kan worden omgezet in tekst zonder opmaak, handig voor het afhandelen van e-mail berichten met HTML-indeling.
* **Drie nieuwe data base-connectors** : alleen-lezen ondersteuning toegevoegd voor mysql, PostgreSQL en Teradata. Deze connectors maken verbinding via de on-premises gegevens gateway.
* **Drie andere connectors** : Maak verbinding met Azure-toepassing inzichten, Calendly en team projecten.
* **Betere visualisatie voor fout afhandeling** : stappen die worden uitgevoerd na fouten worden nu weer gegeven met rode gestippelde pijlen, zodat u ze eenvoudig kunt herkennen.
* **Detail venster voor uitvoering** : wanneer een stroom mislukt, is er nu een nieuw rechterdeel venster met een aantal handige stappen voor het corrigeren van uw stroom.

[Meer informatie en vragen](https://flow.microsoft.com/blog/seven-connectors-and-html/) over deze release.

### <a name="release-2017-06-04"></a>Release 2017-06-04
* **Ga voor Windows Phone** - [de mobiele app van Microsoft flow is uitgebracht voor algemene Beschik baarheid voor Windows Phone](https://flow.microsoft.com/blog/announcing-flow-windows-phone-app/).
* **E-mails over stroom fouten** : Ontvang een melding via e-mail wanneer er een stroom is die mislukt. Deze e-mail berichten worden slechts één keer per week verzonden en kunnen door de gebruiker worden in-of uitgeschakeld.
* **Selecteer een actie voor tabellen** : gebruik de nieuwe actie selecteren om de set kolommen te wijzigen die in de tabellen wordt opgenomen.
* **Micro soft Forms-connector** : micro soft Forms is een nieuw onderdeel van Office 365 education waarmee docenten en studenten snel en eenvoudig aangepaste quizzen kunnen maken, enquêtes, vragen lijsten, registraties en meer.
* **Office 365 Enter prise K1-abonnement** : PowerApps en Microsoft flow zijn nu opgenomen in het Office 365 Enter prise K1-abonnement met bepaalde quota's.
* **Http-headers zijn eenvoudiger** : net als bij de actie selecteren kunt u een header naam en header waarde opgeven door alleen de tekst vakken in de actie in te vullen.

[Meer informatie en vragen](https://flow.microsoft.com/blog/microsoft-forms-tables-flow-failures/) over deze release.

### <a name="release-2017-05-23"></a>Release 2017-05-23
* **Micro soft teams-connector** - [micro soft teams](https://flow.microsoft.com/blog/introducing-the-microsoft-teams-connector-for-flow/) is een werk ruimte op basis van chat in Office 365 waarmee mensen, gesp rekken en inhoud kunnen samen werken, samen met de hulpprogram ma's die teams nodig hebben, zodat ze eenvoudig kunnen worden gewerkt om meer te bereiken.
* **Widgets op Ios-en Android** -Microsoft flow-widgets zijn knop snelkoppelingen die u een gemakkelijke en snellere manier bieden voor het activeren van een knop, direct vanuit het Start scherm.
* **Stappen voor het afhandelen van fouten maken** : Definieer een of meer stappen die moeten worden uitgevoerd nadat een actie is mislukt. U kunt bijvoorbeeld onmiddellijk een melding ontvangen als uw stroom geen record in Dynamics 365 heeft gemaakt.
* **Geheel getal en zwevende variabelen** : Initialiseer en Verhoog of verlagen tellers binnen een stroom uitvoering om te tellen hoe vaak een bepaalde set logica wordt uitgevoerd.
* **Pagina stroom Details** : wanneer u een stroom in de lijst **mijn stromen** selecteert, ziet u een pagina met informatie over die stroom, zoals wie toegang heeft en de uitvoerings geschiedenis.
* **Quota voor het uitvoeren van de stroom voor beheerders** : beheerders kunnen nu het gebruik van de stroom uitvoering in een organisatie controleren op basis van het quotum voor het uitvoeren van een gemeen schappelijke bedrijf en een quotum analyse verkrijgen om te begrijpen welke licenties bijdragen aan hun quotum.
* **Verbeteringen van de HTTP-aanvraag trigger** : gebruik verschillende HTTP-methoden en voeg padsegmenten toe voor de aanvraag trigger.
* **Twee partner-connectors** : Microsoft flow kunt nu verbinding maken met parserer, een service voor het parseren van E-mail en Cognito formulieren, een online formulieren service.

[Meer informatie en vragen](https://flow.microsoft.com/blog/error-handling/) over deze release.

### <a name="release-2017-05-12"></a>Release 2017-05-12
* **Integratie van share point-document bibliotheken** : u kunt elk bestand in een document bibliotheek selecteren en een stroom starten, bijvoorbeeld om het naar uw manager te verzenden voor goed keuring [en nog veel meer](https://flow.microsoft.com/blog/flow-in-spo-document-libraries/).
* **Micro soft planner-connector** : met micro soft planner kunt u teams, taken, documenten en discussies eenvoudig samen stellen voor betere resultaten.
* **Beheer weergave van licenties** : beheerders kunnen alle Microsoft flow-en PowerApps-licenties (zowel proef versie en betaalde) in het Microsoft flow beheer centrum zien.
* **Powerapps Community** -abonnement: het powerapps Community-abonnement is een gratis abonnement voor personen voor het verkennen, leren en bouwen van vaardig heden voor PowerApps, Microsoft Flow en common data service.

[Meer informatie en vragen](https://flow.microsoft.com/blog/planner-community-and-licenses/) over deze release.

### <a name="release-2017-05-09"></a>Release 2017-05-09
* **Azure AD-connector** : er is een nieuwe connector voor het uitvoeren van beheerders acties van Microsoft flow, waaronder het maken van gebruikers of het toevoegen van deze aan groepen.
* **Verbeteringen in Office 365 Outlook** : stromen kunnen nu worden geactiveerd door gedeelde post vakken en e-mail verzenden naar een gedeeld postvak. Ze kunnen ook automatische antwoorden instellen of lezen.
* **Beschikbaar in Canada** : u kunt nu uw stromen maken in Canada.
* **Aangepaste API-webhooks maken** : aangepaste connector ontwikkelaars kunnen nu triggers toevoegen aan hun aangepaste api's met webhooks.
* **Eigen aars van stromen beheren in het beheer centrum** : omgevings beheerders kunnen de eigen aars van stromen beheren in het Microsoft flow-beheer centrum.
* **Naslag** informatie voor connector-documentatie-we hebben nu een [volledige Connector verwijzing naar docs.Microsoft.com](https://docs.microsoft.com/Connectors/).
* **Twee partner services** -er zijn twee nieuwe partner Services uitgebracht: Nexmo en Paylocity.

[Meer informatie en vragen](https://flow.microsoft.com/blog/canada-mailboxes-aad) over deze release.

### <a name="release-2017-04-27"></a>Release 2017-04-27
* **Stromen bouwen met parallelle stappen** -stromen maken met parallelle uitvoering: wat betekent dat u twee of meer stappen kunt uitvoeren die exact op hetzelfde moment worden uitgevoerd.
* **Vijf nieuwe services** die worden ondersteund-vijf nieuwe services: goed keuringen, Bench Mark-E-mail, capsule-CRM, LiveChat en Outlook-klanten beheer.
* **Controle pogingen voor acties** -Microsoft flow worden opnieuw geprobeerd wanneer er fouten zijn met Services. Nu ziet u hoeveel automatische nieuwe pogingen hebben plaatsgevonden en wat er is gebeurd.

[Meer informatie en vragen](https://flow.microsoft.com/blog/parallel-actions/) over deze release.

### <a name="release-2017-04-17---q1-update-for-microsoft-flow"></a>Release 2017-04-17-Q1 update voor Microsoft Flow
* **Moderne goedkeurings ervaring** : Maak werk stromen waar goed keurders veilig kunnen worden goedgekeurd vanuit de Microsoft flow mobiele app of via het Unified goed keuren centrum op de Microsoft flow-website.
* **Algemene Beschik baarheid team stromen** : meerdere mensen kunnen een stroom in combi natie met team stromen beheren, die nu algemeen beschikbaar zijn.
* **Bouw connectors voor Microsoft flow** : iedereen kan hun eigen Microsoft flow connector gratis verzenden voor de rest van de wereld om te gebruiken.
* **Een "dieet" ontwerper** : voor bepaalde sjablonen bevat een nieuwe versie van de ontwerp functie alleen de velden die nodig zijn voor het maken van een stroom, waardoor de ervaring wordt vereenvoudigd.

[Meer informatie en vragen](https://flow.microsoft.com/blog/q1-2017-update/) over deze release.

### <a name="release-2017-04-11"></a>Release 2017-04-11
* **Nieuwe acties voor het maken van tabellen en lijsten** -nieuwe HTML-tabel maken, CSV-tabel maken en acties samen voegen waarmee lijsten met items kunnen worden verwerkt (in plaats van de vorige Toep assen op elke).
* **Stappen invoegen overal** : u kunt nu ergens in de werk stroom een nieuwe stap invoegen zonder dat u hoeft te slepen en neer te zetten.
* **Vier nieuwe services** : stroom ondersteunt nu 10 tot 8 planning, Act!, Inoreader en de computer vision-API. Met de Computer Vision-API kunt u afbeeldingen verwerken om de tekst inhoud (OCR) te verkrijgen, of afbeeldingen automatisch labelen op basis van hun inhoud.

[Meer informatie en vragen](https://flow.microsoft.com/blog/html-tables-csvs-computer-vision/) over deze release.

### <a name="release-2017-04-03"></a>Release 2017-04-03
* **Windows Phone bèta** -het Windows Phone app-bèta programma is beschikbaar om een voor beeld te krijgen van de app op uw Windows Phone. [Meer informatie](https://flow.microsoft.com/blog/windows-phone-app-beta-is-now-available/).
* **MUHIMBI PDF** : u kunt nu micro soft Word-bestanden converteren naar PDF, water merken toevoegen, documenten samen voegen en meer met Muhimbi PDF. [Meer informatie](https://flow.microsoft.com/blog/convert-files-using-muhimbi/).
* **Trigger stromen van fysieke knoppen** : kondigt partnerschappen aan met twee van de toonaangevende producten in de fysieke knop ruimte: Flic by shortcut Labs en BTTN door het knop bedrijf. [Meer informatie](https://flow.microsoft.com/blog/physical-buttons/)

### <a name="release-2017-03-22"></a>Release 2017-03-22
* **Een kopie van uw stroom maken** : u kunt nu een kopie maken van uw stroom om te werken aan concept versies of een stroom dupliceren die u in het verleden hebt gemaakt.
* **Twee nieuwe services** : Voeg ondersteuning toe voor Toodledo: u kunt uw taken lijst beheren door het maken en bijwerken van een taak, en Zendesk, die een klanten service en een ticketing-platform voor ondersteuning biedt.

[Meer informatie en vragen](https://flow.microsoft.com/blog/make-a-copy/) over deze release.

### <a name="release-2017-03-15"></a>Release 2017-03-15
* **Knoppen delen met mede werkers** : u kunt nu stroom knoppen delen met anderen, zodat elke zakelijke gebruiker snel taken kan uitvoeren.
* **Trigger knoppen van het Start scherm** : snelkoppelingen naar flow knoppen van de Home-en lock-schermen van mobiele apparaten maken het sneller dan ooit om een stroom te activeren.
* **Team stromen in de Microsoft flow-app** : u kunt nu de stromen zien die andere eigen aren hebben in de Microsoft flow-app voor Ios of Android.

[Meer informatie en vragen](https://flow.microsoft.com/blog/button-sharing/) over deze release.

### <a name="release-2017-03-10"></a>Release 2017-03-10
* **Verbeterde ervaring voor aangepaste connectors** : u kunt nu een postman-verzameling gebruiken om een aangepaste connector te maken en acties te bewerken, toe te voegen en te testen.
* **Twee nieuwe services** : toegevoegde PowerApps-meldingen en PivotalTracker-ondersteuning.

[Meer informatie en vragen](https://flow.microsoft.com/blog/new-updates-custom-api/) over deze release.

### <a name="release-2017-02-27"></a>Release 2017-02-27
* **Uw stroom knoppen activeren** : u kunt stroom knoppen nu direct van Microsoft flow activeren. Als u de lijst met stromen wilt bekijken, selecteert u gewoon de '... ' en kiest u de opdracht nu uitvoeren.
* **Vijf nieuwe services** : er is ondersteuning toegevoegd Oracle database, intercom, FreshBooks, LeanKit en webmerge.

[Meer informatie en vragen](https://flow.microsoft.com/blog/trigger-flow-buttons-web/) over deze release.

### <a name="release-2017-02-21"></a>Release 2017-02-21
* **Omgevings stromen weer geven** : omgevings beheerders kunnen nu de volledige lijst met alle stromen in een bepaalde omgeving weer geven, en stromen inschakelen, uitschakelen of verwijderen.
* **Twee nieuwe services** : toegevoegde Azure Automation en Basecamp 2-ondersteuning.

[Meer informatie en vragen](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/) over deze release.

### <a name="release-2017-02-16"></a>Release 2017-02-16
* **Vijf nieuwe services** : er is ondersteuning toegevoegd voor Azure data Lake, bitbucket (een webhostingservice voor projecten die gebruikmaken van Git Revision Control), Eventbrite, Infusionsoft en pipe drive.
* **Aangepaste HTTP-verificatie** : in de flow Designer is het nu mogelijk om verificatie met aangepaste http-eind punten te gebruiken.
* **JSON-berichten parseren** : u kunt JSON-gegevens parseren van de HTTP-aanvraag trigger of die wordt geretourneerd door de http-actie.
* **Filter voor stroom uitvoering** : verbeterde filtering voor stroom uitvoeringen, met meer specifieke opties, waaronder het weer geven van stromen of geannuleerde uitvoeringen.

[Meer informatie en vragen](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/) over deze release.

### <a name="release-2017-02-06"></a>Release 2017-02-06
* **Team stromen** : team stromen maken het mogelijk voor meerdere personen om een stroom te beheren en als iemand een organisatie verlaat, kunnen de door hen gemaakte stromen worden uitgevoerd.
* **Aangepaste connectors delen** : aangepaste connectors, zoals team stromen, kunnen worden gedeeld en gezamenlijk worden beheerd in een organisatie.
* **Ondersteuning voor Gmail en Luis** : Maak verbinding met Gmail en Azure Cognitive Services Language Understanding intelligent service.

[Meer informatie en vragen](https://flow.microsoft.com/blog/team-flows/) over deze release.

### <a name="release-2017-01-30"></a>Release 2017-01-30
* **Invoer van de knop stroom** : met stroom knoppen kunnen nu gebruikers invoer worden ontvangen tijdens runtime, zodat de auteurs van de stroom gegevens kunnen definiëren die worden door gegeven wanneer op de knop wordt getikt.
* Met **Outlook-taken en HelloSign** -Outlook-taken service kunt u taken beheren, en HelloSign maakt veilige elektronische hand tekeningen mogelijk.

[Meer informatie en vragen](https://flow.microsoft.com/blog/button-user-inputs/) over deze release.

### <a name="release-2017-01-23"></a>Release 2017-01-23
* **Zoeken op service** : bladeren per service wanneer u een trigger of actie toevoegt om alle acties voor elke service weer te geven.
* **Switch-case** : Voeg switch blokken toe om meerdere vertakkingen van parallelle logica te hebben.
* **Meer e-mail acties** : nieuwe functionaliteit in Office 365 Outlook en Outlook.com services om te werken met gemarkeerde e-mail berichten.
* **Vijf nieuwe services** : Maak verbinding met lokale bestands systemen of netwerken, de betalings service Stripe, IBM Informix, IBM DB2 en UserVoice.

[Meer informatie en vragen](https://flow.microsoft.com/blog/search-by-service/) over deze release.

### <a name="release-2017-01-14"></a>Release 2017-01-14
* **Uitvoeringen opnieuw verzenden** : als een stroom is mislukt en u deze wilt herstellen en opnieuw wilt uitvoeren, kunt u de mislukte uitvoering opnieuw indienen.
* **Uitvoeringen annuleren** : wanneer een stroom vastloopt, kunt u de uitvoering nu expliciet annuleren.
* **Twee nieuwe services** : er is ondersteuning toegevoegd voor GoToTraining en GoToWebinar toevoegen.
* **Mobiele koppelingen** : u kunt sjablonen rechtstreeks vanuit de mobiele app delen, en we hebben een koppeling voor snel downloaden toegevoegd voor de apps boven aan de website.

[Meer informatie en vragen](https://flow.microsoft.com/blog/managing-runs/) over deze release.

### <a name="release-2016-12-29"></a>Release 2016-12-29
Microsoft Flow ondersteunt nu DocuSign voor het afhandelen van elektronische hand tekeningen en het beheer van digitale trans acties. SurveyMonkey, voor webgebaseerde enquêtes; en de OneNote-app voor het maken van notities (alleen voor zakelijke accounts).

[Meer informatie en vragen](https://flow.microsoft.com/blog/final-2016-services/) over deze release.

### <a name="release-2016-12-20"></a>Release 2016-12-20
* **Nu uitvoeren** : u kunt nu een terugkerende trigger op verzoek starten, bijvoorbeeld als u elke dag een gepland rapport hebt, maar u het rapport **nu** ook moet uitvoeren.
* **Zes nieuwe services** : bouw stromen die verbinding maken met MSN weer, medium, Google contact personen, buffer, oogst en TypeForm.

[Meer informatie en vragen](https://flow.microsoft.com/blog/run-now-and-six-more-services/) over deze release.

### <a name="release-2016-12-14"></a>Release 2016-12-14
U kunt nu waardevolle informatie gebruiken wanneer u een knop stroom start, zoals waar de knop is geactiveerd, door wie, op welk tijdstip en nog veel meer.

[Meer informatie en vragen](https://flow.microsoft.com/blog/button-trigger-tokens/) over deze release.

### <a name="release-2016-12-06"></a>Release 2016-12-06
* **Introductie van begeleide training** : Ga aan de slag met een geordende verzameling cursussen waarmee Video's met documentatie worden gekoppeld om u te helpen inzicht te krijgen in de uitgebreide en krachtige mogelijkheden van Microsoft flow.
* **Twee nieuwe services** : stromen kunnen nu gebruikmaken van Freshdesk, een oplossing voor klant ondersteuning en GoToMeeting, een hulp programma voor online vergaderingen.
* **Ondersteuning voor http-webhook** : een stroom kan nu een eind punt voor webhooks zijn die automatisch worden geregistreerd en de registratie ongedaan maakt.

[Meer informatie en vragen](https://flow.microsoft.com/blog/guided-learning-and-two-services/) over deze release.

### <a name="release-2016-11-23"></a>Release 2016-11-23
* **Ondersteuning voor Power bi waarschuwingen in flow** : Schakel inzicht in de actie in door stromen te activeren vanuit Power BI gegevens meldingen.
* **Verbeteringen voor mobiele toepassingen** : de mogelijkheid voor het maken van stromen uit niets, naast de al bestaande ervaring van het maken van sjablonen, is toegevoegd. Daarnaast hebben we de prestaties verbeterd wanneer de stroom uitvoeringen worden weer gegeven.
* **Acht nieuwe services** : u kunt nu verbinding maken met Azure Resource Manager, Azure queues, chatter, Disqus, Azure Cosmos DB, cognitive Services Face-API, HipChat en WordPress.

[Meer informatie en vragen](https://flow.microsoft.com/blog/power-bi-and-eight-other-services/) over deze release.

### <a name="release-2016-11-15"></a>Release 2016-11-15
* **Microsoft flow partner programma** -Microsoft flow heeft nu een Certified Partner-programma nodig om verbindingen te maken en te profiteren van de talen en ervaring van verschillende bedrijven met Microsoft flow over de hele wereld.
* **Zes nieuwe services** : we bieden u deze week ook zes Services. Dit is een asana, Campfire, EASYREDMINE, Jira, Redmine en Vimeo.

[Meer informatie en vragen](https://flow.microsoft.com/blog/partner-program-six-new-services/) over deze release.

### <a name="release-2016-10-31---general-availability"></a>Release 2016-10-31-algemene Beschik baarheid
* **Prijzen en licenties** : nu beschikbaar in zowel gratis als betaalde abonnementen, en opgenomen in Office 365 en Dynamics 365.
* **Microsoft flow beheer centrum** -klaar voor ondernemingen met het nieuwe beheer centrum. In het beheer centrum kunt u de omgevingen binnen de organisatie beheren.
* **Beleid voor preventie van gegevens verlies** : beheerders kunnen beleid voor preventie van gegevens verlies maken om de stroom van gegevens tussen services te beheren.
* **Beschik baarheid Android** : de Microsoft flow-telefoon-app is nu beschikbaar voor zowel IOS als Android. Met de app kunt u meldingen ontvangen, activiteiten controleren en stromen starten met het tikken van een knop.
* **Nieuwe ontwerp ervaring** : u kunt nu zoeken naar de dynamische inhoud die is door gegeven van stap in stap, waardoor het veel sneller verwijst naar de gegevens die u wilt.

[Meer informatie en vragen](https://flow.microsoft.com/blog/announcing-ga/) over deze release.

### <a name="release-2016-10-26"></a>Release 2016-10-26
* **Knop stromen** : er zijn talloze bewerkingen die we graag en overal kunnen activeren. Nu kunt u, met knop stromen, aan de slag met één klik op een knop, vanaf uw mobiele apparaat.
* **Aangekondigde omgevingen** : omgevingen zijn afzonderlijke ruimten voor het opslaan en beheren van de stromen van uw organisatie. Omgevingen zijn geografische locaties, wat betekent dat de stromen, apps en bedrijfs gegevens die zich binnen een omgeving bevinden in de regio waar de omgeving zich bevindt.
* **Zes nieuwe services** : Voeg ondersteuning toe voor Bit.ly, cognitive Services Text Analytics, Dynamics NAV, Dynamics 365 voor Financials, Insta paper en Pinterest.

[Meer informatie en vragen](https://flow.microsoft.com/blog/environments-for-makers/) over deze release.

### <a name="release-2016-10-16"></a>Release 2016-10-16
* **Aangepaste connectors bieden ondersteuning voor meer verificatie typen** : aangepaste connectors bieden nu ondersteuning voor API-sleutel verificatie en kunnen worden geverifieerd bij elke service die ondersteuning biedt voor de volledige OAuth 2,0-specificatie.
* Er zijn **drie nieuwe services ondersteund** : er is ondersteuning toegevoegd voor BaseCamp 3, Blogger en PagerDuty.
* **Verbeteringen in de ontwerp functie** : de prestaties zijn verbeterd. u kunt nu uw verbindingen bijwerken en herstellen vanuit de '... ' voor elke actie, en we hebben een nieuwe stap toegevoegd met de naam Terminate, die u kunt gebruiken om de uitvoering van een stroom te beëindigen.

[Meer informatie en vragen](https://flow.microsoft.com/blog/early-october-updates/) over deze release.

### <a name="release-2016-09-25"></a>Release 2016-09-25
Het maken van de stroom is nu beschikbaar via uw mobiele telefoons. Blader door de galerie met uitgebreide sjablonen, navigeer door de lijst met Services of selecteer een sjabloon categorie om in te zoomen. [Meer informatie en vragen](https://flow.microsoft.com/blog/mobile-creation/) over deze release.

### <a name="release-2016-09-22"></a>Release 2016-09-22
* **Microsoft Graph personen kiezen** : een nieuwe Microsoft Graph personen kiezer wordt rechtstreeks geïntegreerd in de gebruikers interface van Microsoft flow om u te helpen bij het kiezen van het juiste contact of e-mail adres.
* **Ondersteuning voor micro soft Dynamics AX** : vanuit uw stromen kunt u nu actie ondernemen voor uw Dynamics AX online Operations-gegevens, van het maken van nieuwe records voor het uitvoeren van query's op gegevens.
* **Twee nieuwe services van partners** : gebruik nu appFigures of onzichtbaar vanuit uw stromen.

[Meer informatie en vragen](https://flow.microsoft.com/blog/more-september-updates/) over deze release.

### <a name="release-2016-09-14"></a>Release 2016-09-14
* **Insluiten in uw website of app** : ontwikkel aars kunnen nu Microsoft flow rechtstreeks insluiten in hun apps of websites om hun gebruikers een eenvoudige manier te bieden om hun persoonlijke of professionele taken te automatiseren.
* **Een stroom gebruiken als een http-eind punt** : u kunt nu een stroom gebruiken als een HTTP-API. Er is een trigger met de naam aanvraag in de stroom en u kunt ervoor kiezen om te reageren op de binnenkomende aanvraag door een antwoord kaart toe te voegen.
* De **ondersteunings afdeling** van de TODO-taak geeft u een perspectief over alle projecten, op het werk en thuis.

[Meer informatie en vragen](https://flow.microsoft.com/blog/extend-web-site-application/) over deze release.

### <a name="release-2016-09-01"></a>Release 2016-09-01
Microsoft Flow nu beschikbaar voor iedereen: we hebben in eerste instantie het voor beeld geopend op alleen e-mail adressen van uw werk of school, zoals die worden gebruikt met Office 365 Business of Office 365 Enter prise. Vandaag kondigen we aan dat de preview officieel beschikbaar is, gratis voor alle gebruikers, ongeacht de e-mail berichten die u mogelijk hebt. [Meer informatie en vragen](https://flow.microsoft.com/blog/available-for-everyone/) over deze release.

### <a name="release-2016-08-31"></a>Release 2016-08-31
* **Geneste voor waarden** : u kunt nu een tweede voor waarde (of een derde, enz.) toevoegen binnen een andere.
* **Toep assen op elke** lus: een Toep assen op elke herhalingslus maakt het mogelijk om de lijst die u herhaalt, te beheren.
* **Do-until** -een do-until-lus kunt u een stap herhalen tot aan een bepaalde voor waarde wordt voldaan.
* **Filter matrices** : er is één systeem eigen filter stap die ervoor kan zorgen dat elk item in de lijst overeenkomt met een expressie die u definieert.
* **Teken reeks variabelen opstellen** : u kunt nu een teken reeks variabele opstellen.
* **Bereiken** : bereiken zijn een eenvoudige manier om twee of meer acties samen te groeperen.

[Meer informatie en vragen](https://flow.microsoft.com/blog/build-advanced-flows/) over deze release.

### <a name="release-2016-08-27"></a>Release 2016-08-27
* **Opmerkingen over de stappen** : opmerkingen maken het eenvoudig om elke afzonderlijke actie te voorzien van notities, zodat u gemakkelijk kunt onthouden wat de stroom nodig heeft
* **Ondersteuning voor Smart Sheet** -deze week hebben we ondersteuning toegevoegd om verbinding te maken met Smart Sheet. Smart Sheet is een service die het eenvoudig maakt om samen te werken aan werk bladen in de Cloud.
* **Gebruikers interface verfijnen bij het ontwerpen van stromen** : we hebben de stroom naam vooraan en gecentreerd gemaakt en de knop opslaan boven aan de pagina voor eenvoudige toegang verplaatst.

[Meer informatie en vragen](https://flow.microsoft.com/blog/add-comments-smartsheet/) over deze release.

### <a name="release-2016-08-18"></a>Release 2016-08-18
U kunt nu een voor beeld bekijken van de nieuwe ervaring met de moderne lijst van share point online met de integratie van Microsoft Flow. [Meer informatie en vragen](https://flow.microsoft.com/blog/microsoft-flow-integration-with-sharepoint-modern-lists-preview/) over deze release.

### <a name="release-2016-08-13"></a>Release 2016-08-13
* **Visual Studio Team Services** : met Flow kunt u nu verbinding maken met VSTS voor een groot aantal verschillende services, zoals O365 E-mail, toegestane vertraging, Trello en Wunderlist.
* **Verbeteringen in share point** : share point-lijsten ondersteunen een reeks gegevens typen van eenvoudige objecten zoals tekst en datum en tijd tot complexe objecten zoals persoon of groep, opzoeken en keuze.
* **Outlook-verbindingen van O365 testen** : wanneer u een nieuwe Outlook-verbinding voor o365 maakt, zullen we deze nu testen om er zeker van te zijn dat u er klaar voor bent om deze te gebruiken.
* **Booleaans besturings element** : we hebben ook een Boole-besturings element toegevoegd om te verduidelijken welke waarden u moet invoeren voor Boole-invoer velden, zoals het bevat bijlagen in de trigger wanneer er een nieuwe e-mail binnenkomt.

[Meer informatie en vragen](https://flow.microsoft.com/blog/visual-studio-team-services-enhancements-to-sharepoint-and-o365-outlook-and-boolean-control/) over deze release.

### <a name="release-2016-08-08"></a>Release 2016-08-08
Open bare preview-versie van de micro soft-Common Data Service geïntegreerd in Microsoft Flow. [Meer informatie en vragen](https://flow.microsoft.com/blog/flow-and-common-data-model/) over deze release.

### <a name="release-2016-08-05"></a>Release 2016-08-05
* **Share point on-premises** : net zoals bij share point online kunt u met vooraf gedefinieerde sjablonen en document bibliotheken stromen maken rond uw share point on-premises-lijsten of door ze helemaal zelf te bouwen.
* **Info-bellen in de ontwerp functie** : als u wilt weten wat de mogelijkheden van elke trigger en actie zijn, hebt u info-bellen toegevoegd boven elke stap van de stroom.

[Meer informatie en vragen](https://flow.microsoft.com/blog/sharepoint-on-premises-and-info-bubbles-2/) over deze release.

### <a name="release-2016-07-15"></a>Release 2016-07-15
* **Vier nieuwe services toegevoegd** : Maak verbinding met Google Calendar, Google tasks, YouTube en SparkPost.
* **De naam van uw acties wijzigen** : nu kunt u deze verschillende acties splitsen door ze een andere naam te geven.
* **Vertraging voor verschillende tijds perioden** : u kunt nu een wille keurig aantal seconden, minuten, uren of dagen selecteren.
* **Eenvoudiger te gebruiken mappen browser** : we hebben de mappen browser vereenvoudigd. Als u nu aan de linkerkant selecteert, wordt die map gekozen en wordt de map geopend, zodat u de submappen kunt selecteren.

[Meer informatie en vragen](https://flow.microsoft.com/blog/new-google-services-rename-more/) over deze release.

### <a name="release-2016-07-08"></a>Release 2016-07-08
On-premises connectiviteit voor Microsoft Flow met behulp van de on-premises gegevens gateway. Zo kunt u beveiligde verbindingen tot stand brengen met SQL Server en deze integreren met uw stromen. [Meer informatie en vragen](https://flow.microsoft.com/blog/on-premises-data-gateway/) over deze release.

### <a name="release-2016-07-02"></a>Release 2016-07-02
* **Ondersteuning voor Google Sheets** : in het verleden hebben we de mogelijkheid om Excel en Google Drive te gebruiken, maar deze week voegen we systeem eigen ondersteuning voor Google Sheets toe.
* **Snel** aan de slag met sjablonen: we hebben ook een aantal optimalisaties toegepast op de manier waarop u vanuit sjablonen kunt beginnen. Nu kunt u selecteren welke accounts u wilt gebruiken voor een sjabloon recht inline op de sjabloon pagina.
* **Verificatie verloopt niet voor share point en Office 365** -nu wordt uw toegang door Microsoft flow automatisch vernieuwd naar op Azure Active Directory gebaseerde services, zodat al uw stromen blijven werken in wachtwoord wijzigingen.

[Meer informatie en vragen](https://flow.microsoft.com/blog/more-june-updates/) over deze release.

### <a name="release-2016-06-20"></a>Release 2016-06-20
* **Introductie van de nieuwe mobiele app voor Microsoft flow** -vandaag, zijn we blij met het introduceren van een belang rijk onderdeel van onze aanbieding: een mobiele app kan nu worden gedownload op Ios (binnenkort ook op Android), zodat u de kracht hebt voor het beheren, volgen en verkennen van uw automatische werk stromen op elk gewenst moment en overal.  
* **Eenmalige aanmelding** : we hebben eenmalige aanmelding geïmplementeerd waarmee u zich kunt verifiëren bij Microsoft flow met andere micro soft-services zoals Office 365.

[Meer informatie en vragen](https://flow.microsoft.com/blog/welcome-to-flow-now-more-mobile/) over deze release.

### <a name="release-2016-06-18"></a>Release 2016-06-18
* **Nieuwe e-mail service** : u kunt nu rechtstreeks vanaf Microsoft flow e-mail verzenden, zonder dat u verbinding hoeft te maken met uw persoonlijke of zakelijke e-mail accounts binnen Microsoft flow.
* **Meldingen in de portal** : u ziet nu meldingen boven aan de Portal wanneer er iets met uw stromen wordt verbroken.
* **Alle activiteiten in de portal** : u kunt nu activiteiten bekijken voor al uw stromen door te klikken op het tabblad nieuwe activiteit op de flow-website.

[Meer informatie en vragen](https://flow.microsoft.com/blog/mail-and-all-activity/) over deze release.

### <a name="release-2016-05-27"></a>Release 2016-05-27
* **Bladeren door sjablonen per service** : er is nu een manier om alle services te zien die we ondersteunen (zonder dat u zich hoeft aan te melden). Op deze pagina ziet u een beschrijving van elk van de services en bekijkt u de sjablonen die we voor die service hebben.
* **Uw aangepaste connectors maken en gebruiken** : net zoals u aangepaste connectors in PowerApps kunt maken, kunt u ook rechtstreeks verbinding maken met uw eigen api's op flow.Microsoft.com:
* **Test uw stromen vóór het volt ooien** : wanneer u een stroom opslaat, kunt u nu de resultaten zien van de stroom bewerking Live op de pagina, als u de start actie uitvoert.

[Meer informatie en vragen](https://flow.microsoft.com/blog/may-updates-to-microsoft-flow/) over deze release.

### <a name="release-2016-05-07"></a>Release 2016-05-07
Er zijn twee nieuwe services toegevoegd: micro soft project online en Mandrill door MailChimp. [Meer informatie en vragen](https://flow.microsoft.com/blog/announcing-microsoft-flow-webinars/) over deze release.

### <a name="release-2016-04-27---public-preview"></a>Release 2016-04-27-open bare preview
Als u logische stromen hebt gebruikt als onderdeel van [Microsoft PowerApps](https://powerapps.microsoft.com), biedt de Microsoft flow preview-release verschillende nieuwe functies:

* U kunt nu een galerie met tien tallen sjablonen bekijken en sorteren op basis van populariteit, naam of publicatie datum.
* U kunt [uw eigen sjablonen publiceren](publish-a-template.md) in de galerie nadat u een stroom hebt aangepast.
* U kunt de geschiedenis voor elke controle en uitvoering van uw stroom zien.
* Wanneer u een stroom opslaat, kunt u [deze direct in actie bekijken](see-a-flow-run.md) door alleen de trigger actie uit te voeren.
* We hebben een [nieuwe community](https://go.microsoft.com/fwlink/?LinkID=787467) voor het bespreken van stromen of [het verzenden van uw ideeën](https://go.microsoft.com/fwlink/?LinkID=787474).

## <a name="next-steps"></a>Volgende stappen
Als u problemen ondervindt die nog niet worden behandeld in deze release opmerkingen of in de [Veelgestelde vragen](frequently-asked-questions.md), neemt u [contact](https://go.microsoft.com/fwlink/?LinkID=787479)op met [onze community](https://go.microsoft.com/fwlink/?LinkID=787467) voor vragen

