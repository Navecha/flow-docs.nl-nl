---
title: Opmerkingen bij de release | Microsoft Docs
description: Veelvoorkomende problemen en nieuwe functies voor versies van Microsoft Flow
services: 
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/12/2018
ms.author: stepsic
ms.openlocfilehash: 57a86fa86633e040cf788443d54bd60cfd340844
ms.sourcegitcommit: 6308b1f4ec4ed18a8a7c89911a83cd2f12ed6dc4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/05/2018
---
# <a name="release-notes"></a>Releaseopmerkingen
## <a name="top-questions"></a>Belangrijkste vragen
1. Mijn stroom is mislukt. Hoe kan ik dit probleem oplossen?
   
   1. Spoor de fout op. Ga eerst naar het meldingenpictogram boven aan het webportal of selecteer het tabblad **Activiteit** in de mobiele app. U kunt hier uw stroom zien en deze selecteren.
   2. U ziet nu de details van de stroom. Zoek de stap met het pictogram met het rode uitroepteken. Hier moet u het foutbericht voor uw stroom zien.
   3. Afhankelijk van het foutbericht moet u de stroom kunnen **Bewerken** en herstellen. [Lees meer over het oplossen van gangbare stroomfouten](fix-flow-failures.md).
2. Hoe gebruik ik geavanceerde voorwaarden of een expressie?
   
   * Meer informatie over het [toevoegen van voorwaarden](add-condition.md).
   * Als u meerdere voorwaarden aan een stroom wilt toevoegen, klikt of tikt u vanuit een bestaande voorwaarde op **Voorwaarde toevoegen**.
   * Maak een geavanceerde expressie door te verwijzen naar [een functie in Logic Apps](https://docs.microsoft.com/rest/api/logic/definition-language).
3. Hoe werkt licentieverlening voor Office 365?
   
   * Als u Office 365 gebruikt, hebt u volledige toegang tot Microsoft Flow via het Office 365-abonnement. Zie de [prijzen en abonnementen voor Microsoft Flow](https://flow.microsoft.com/pricing/) voor meer informatie.
   * Als u een beheerder bent, raadpleegt u de informatie over de [licentieverlening voor Microsoft Flow](organization-q-and-a.md) voor onder andere Office 365.

## <a name="known-issues-and-resolutions"></a>Bekende problemen en oplossingen
1. SharePoint-lijsten op Mijn sites en SharePoint-lijsten die niet van het type *Aangepaste lijst* zijn, worden niet ondersteund. U kunt als tijdelijke oplossing voor dit probleem een aangepaste lijst maken op een standaard-SharePoint-site.
2. Stromen kunnen niet schrijven naar taxonomievelden in SharePoint-lijsten. Het beste is om een eenvoudig tekenreeksveld te gebruiken tot dit is opgelost.
3. Bestandstriggers worden niet gestart voor bestanden die worden toegevoegd in geneste mappen in de map die u selecteert.

## <a name="whats-new"></a>Wat is er nieuw?

### <a name="release-2018-02-09"></a>Release 09-02-2018

- **Hoge beschikbaarheid van gateway** - Maak maximaal beschikbare clusters van on-premises gegevensgateways om verbindingen in stand te houden wanneer één machine uitvalt.
- **Verbetering van Op elke lus toepassen** - Met Flow-abonnement 1 of Flow-abonnement 2 kunt u tot 100.000 items in één uitvoering en 50 acties tegelijkertijd verwerken in Op elke lus toepassen. 

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/gateway-ha-increased-apply-to-each/) over deze release.

### <a name="release-2018-01-29"></a>Release 29-01-2018

- **Stroom binnen Microsoft Teams** - Vanuit Teams kunt u stromen maken en beheren, uw ontvangen en verzonden goedkeuringen bekijken en stromen rechtstreeks in de desktop-app van Teams of op teams.microsoft.com starten. [Klik hier voor meer informatie](https://flow.microsoft.com/blog/microsoft-flow-in-microsoft-teams/).
- **Meldingen voor gedeelde bewerkingen** - Wanneer uw stroom door een collega wordt gewijzigd, krijgt u een e-mailbericht dat u vertelt wie welke stroom heeft gewijzigd.
- **Nieuwe expressies** - Er zijn twee nieuwe sets met expressies toegevoegd: één om URL's te parseren en een andere om met JSON-objecten te werken.
- **Drie nieuwe connectors** - Deze week zijn er twee nieuwe Plumsail-connectors bij gekomen: Plumsail SP en Plumsail Forms, plus een nieuwe connector voor kintone.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/shared-notifications-and-expressions/) over deze release.

### <a name="release-2018-01-17"></a>Release 17-01-2018

- **Office 365-profielgegevens** - We hebben nieuwe acties toegevoegd aan de connector voor Office 365-gebruikers, die werken met gebruikersprofielen en -foto's.
- **Toevoegen aan tekenreeksvariabelen** - U kunt dingen toevoegen aan tekenreeksen binnen lussen om tabellen of andere lijsten te maken.
- **Infobip-connector** - Infobip is een service die communicatie op zakelijk niveau mogelijk maakt, inclusief spraakoproepen en activering van inkomende sms-berichten.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/o365-profile-infobip/) over deze release.

### <a name="release-2017-12-20"></a>Versie van 20-12-2017

Microsoft Flow Analytics is nu beschikbaar in alle Microsoft Flow-regio's, wat betekent dat u meer inzicht kunt krijgen in de status van stromen die binnen uw omgeving worden uitgevoerd.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/announcing-microsoft-flow-analytics/) over deze release.


### <a name="release-2017-12-14"></a>Versie van 14-12-2017

- **Verbeteringen in Outlook connector**: u kunt een e-mailbericht opslaan als '.eml'-bestand, automatisch reageren op kalenderuitnodigingen en stromen activeren wanneer u in een e-mailthread wordt genoemd.
- **Verbeteringen van verbindingen**: Microsoft Flow onthoudt uw meest recent gebruikte verbindingen en toon alle nieuwe toegevoegde connectors.
- **Vijf nieuwe connectors**: er zijn exemplaren van Azure Container, Azure Kusto Metatask, Microsoft To-Do en Plumsail Documents toegevoegd.
- **HTTP-verbeteringen**: de HTTP-actie ondersteunt nu gesegmenteerde codering.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/outlook-connector-more/) over deze release.

### <a name="release-2017-12-05"></a>Versie van 05-12-2017

Het startpaneel van Microsoft Flow is nu in alle regio’s beschikbaar. In dit deelvenster kunt u waarden aan een stroom toevoegen wanneer u deze binnen uw SharePoint-lijst of documentenbibliotheek uitvoert.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/introducing-flow-launch-panel-in-sharepoint-lists-and-libraries/) over deze release.


### <a name="release-2017-11-28"></a>Versie van 28-11-2017

- **Beheerde metagegevens**: lees gegevens van en schrijf gegevens naar kolommen in SharePoint die gebruikmaken van het type Beheerde metagegevens (oftewel taxonomie).
- **Toevoegen aan matrices**: voeg items toe aan het einde van matrices met behulp van de nieuwe actie Toevoegen aan een matrixvariabele.
- **Tago**: een nieuwe connector voor Tago, voor een eenvoudige verbinding tussen elektronische apparaten en externe gegevens voor het stimuleren van slimmere beslissingen op basis van contextuele analyse.
- **iPhone X**: een nieuwe versie van de Microsoft Flow-app die gebruikmaakt van het volledige scherm van de iPhone X en waarin afbeeldingen sneller worden geüpload.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/managed-metadata-tago/) over deze release.

### <a name="release-2017-11-09"></a>Versie van 09-11-2017

- **Integratie van OneDrive voor Bedrijven**: er is [nu een stroomknop in OneDrive voor Bedrijven](https://flow.microsoft.com/blog/microsoft-flow-integration-in-one-drive-for-business-and-new-connector-actions/) waarmee u stromen op geselecteerde bestanden of mappen kunt maken of activeren.
- **Abonnementstriggers**: hiermee worden stromen gestart zodra een nieuwe taak is gemaakt, een taak aan u is toegewezen of een taak is voltooid.
- **SharePoint-bijlagen**: werk met bijlagen bij SharePoint-lijstitems: u kunt bijlagen weergeven, downloaden, toevoegen of verwijderen.
- **Stroombeheerconnector**: maak stromen die het beheer van andere stromen in uw omgeving automatiseren (voeg bijvoorbeeld automatisch machtigingen aan stromen toe).
- **Vier nieuwe connectors**: Azure Custom Vision Service, D&B Optimizer, Enadoc en Derdak SIGNL4 zijn toegevoegd. 
- **Meer connectoracties**: voer SQL-query’s uit, krijg snellere e-mailtriggers, gebruik een willekeurige methode met HTTP met Azure AD, etc.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/planner-triggers-connector-improvements/) over deze release.

### <a name="release-2017-11-02"></a>Versie van 02-11-2017

- **Auditlogboeken maken**: Microsoft Flow-auditgebeurtenissen zijn nu voor alle tenants beschikbaar in het Beveiligings- en nalevingscentrum van Office 365.
- **Oplossingen van problemen met stroomwidgets**: er is een probleem opgelost in de Flow Mobile-app dat ervoor zorgde dat knoppen niet werden geladen in de widget.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/security-and-compliance-center/) over deze release.

### <a name="release-2017-10-19"></a>Versie van 19-10-2017

- **Genest op elke toepassen**: u kunt acties van het type 'Toepassen op elke' toevoegen, filteren en selecteren in andere containeracties van het type 'Toepassen op elke'.
- **Datum/tijd-acties**: nieuwe acties voor het ophalen van de lokale tijd of het optellen, aftrekken of formatteren van tijden.
- **Vier nieuwe connectors**: Content Moderator, Docparser, Microsoft Kaizala en Pitney Bowes Data Validation zijn toegevoegd.
- **Verbeterde verbindingservaring**: u vindt meldingen in het stroomportal wanneer een verbinding wordt verbroken. Ook krijgt u uitgebreidere verbindingsdetails.
- **Mobiele verzameling**: een nieuwe sjabloonverzameling voor [werknemers die onderweg zijn](https://flow.microsoft.com/collections/onthego/).
- **Invoer van de knop E-mailadressen**: verzamel e-mailadressen van gebruikers wanneer ze op een knop drukken.
- **Invoer van de knop Bestand**: haal geüploade bestanden zoals foto’s van gebruikers op wanneer ze op een knop drukken.
- **Eerste uitvoering en automatisch aanmelden**: verbeterde ervaring bij eerste uitvoering op de mobiele app, inclusief automatisch aanmelden.
- **Snellere Microsoft Forms-triggers**: in Forms worden stromen veel sneller geactiveerd dan voorheen (dit duurde eerder een uur).
- **Knopinvoer over meerdere sessies**: knoppen die op uw mobiele telefoon worden geactiveerd, onthouden eerdere invoer.
- **Feed over mobiele activiteit**: verbeterde activiteitenfeed zodat u gedetailleerdere samenvattingen van uitvoeringen en details over probleemoplossing kunt krijgen.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/nested-apply-to-each/) over deze release.

### <a name="release-2017-10-03"></a>Versie van 03-10-2017

- **Iedereen moet goedkeuren**: vereis dat er een goedkeuringsverzoek naar meerdere personen moet worden verzonden zodat iedereen die het verzoek heeft ontvangen, dit moet goedkeuren.
- **Nieuw acties van OneDrive voor Bedrijven**: genereer PDF’s voor bestanden die op OneDrive voor Bedrijven is opgeslagen en vier andere nieuwe acties.
- **Apache Impala-connector**: Apache Impala (in ontwikkeling) is de open source, systeemeigen analysedatabase voor Apache Hadoop.
- **Stroombeschrijvingen toevoegen**: geef uw stromen een beschrijving, zodat uw collega’s een samenvatting krijgen van de mogelijkheden van de stroom wanneer u de stroom met anderen deelt.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/all-must-approve-and-onedrive/) over deze release.

### <a name="release-2017-09-25---q3-update-for-microsoft-flow"></a>Versie van 25-09-2017 - Update derde kwartaal voor Microsoft Flow

- **Diepere SharePoint-integratie in eerste versie**: er zijn nieuwe ‘ingesloten’ stromen voor verzenden ter beoordeling en een stroomdeelvenster voor het verzamelen van invoer wanneer u een stroom voor tenants van de eerste versie uitvoert.
- **Dynamics 365 voor Customer Engagement**: Flow is nu geïntegreerd in de gebruikersinterface voor Dynamics 365 voor Customer Engagement.
- **Microsoft Trust Center**: Flow wordt vermeld in het Microsoft Trust Center. Hierbij worden certificeringen zoals HIPAA, ISO en SOC weergegeven.
- **Gebruiksanalyse**: elke stroom beschikt over een ingebouwd Power BI-dashboard met basale analysegegevens over het gebruik.
- **Auditlogboeken maken voor eerste versie**: alle stroombeheergebeurtenissen worden vastgelegd in het Beveiligings- en nalevingscentrum van Office 365 voor tenants van de eerste versie.
- **Zes nieuwe connectors**: LinkedIn, Office 365 Groups, Skype voor Bedrijven, Adobe Sign, Bizzy en Azure Log Analytics Data Collection zijn toegevoegd.
- **SQL-triggers**: voer stromen uit wanneer een nieuwe rij wordt toegevoegd of een rij wordt bijgewerkt in een SQL-tabel.
- **Aangepaste connectors op locatie**: aangepaste connectors kunnen nu gebruikmaken van de gegevensgateway op locatie om verbinding te maken met interne eindpunten in uw netwerk.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/q3-2017-update/) over deze release.

### <a name="release-2017-09-21"></a>Versie van 21-09-2017

- **Geschiedenis van stromen downloaden**: download de uitvoeringsgeschiedenis van een stroom als CSV-bestand om het in Excel te kunnen openen.
- **Geavanceerd terugkeerpatroon**: bouw terugkeerschema’s om uw stromen te activeren, bijvoorbeeld alleen op werkdagen.
- **IntelliSense**: wanneer u expressies invoert, biedt IntelliSense suggesties voor parameters.
- **Vier nieuwe connectors**: er zijn connectors toegevoegd voor Azure AD HTTP services, Amazon Redshift, Azure Event Grid Publish en FlowForma.
- **Koppelingen delen**: een nieuwe actie voor het genereren van deelbare koppelingen voor OneDrive-bestanden of Azure Storage-blobs.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/download-history-recurrence/) over deze release.


### <a name="release-2017-08-25"></a>Release 25-08-2017
* **Documenteigenschappen en meer voor SharePoint** - [Eigenschappen van documentbibliotheek lezen en instellen in SharePoint](https://flow.microsoft.com/blog/support-for-sharepoint-document-library-properties/), en aanvullende velden gebruiken zoals koppelingen naar het SharePoint-item.
* **Flow-collecties** - Flow-collecties bestaan uit een set sjablooncollecties die zijn gesorteerd op rol of verticale bedrijfstak.
* **Knoppen opnieuw delen** - Als u knoppen met uw collega's deelt, kunnen zij de knoppen weer met andere mensen delen.
* **Lijsten van knoppen verzamelen** - Definieer vervolgkeuzelijsten met opties waaruit gebruikers kunnen kiezen als ze op de knop tikken.
* **Zeven nieuwe connectors** - AWeber, Azure Log Analytics, Azure Tables, DocFusion365, Azure Event Grid, Azure Event Hubs en StaffHub. 
* **Verbeteringen in Slack en MySQL** - Maak kanalen in Slack of neem eraan deel en schrijf naar MySQL-databases.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/button-updates-seven-connectors/) over deze release.

### <a name="release-2017-08-02"></a>Release 02-08-2017
* **Schrijven naar persoon-, keuze- en zoekactievelden** - De SharePoint-opties Item maken en Item bijwerken[ondersteunen nu de mogelijkheid om](https://flow.microsoft.com/blog/setting-sharepoint-s-person-choice-and-lookup-fields/) persoon-, keuze- en zoekactievelden in te stellen.
* **Meer actie-instellingen** - U hebt nu meer controle over hoe triggers en acties worden uitgevoerd, waaronder het configureren van beleid voor opnieuw proberen en van paginering.
* **Vier nieuwe connectors** -U kunt nu Azure File Storage, Elastic Forms, Plivo en Video Indexer gebruiken.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/four-connector-action-settings/) over deze release.

### <a name="release-2017-07-27---q2-update-for-microsoft-flow"></a>Release van 27-07-2017 - K2: update voor Microsoft Flow
* **Importeren en exporteren** - Stroomoplossingen van de ene omgeving naar de andere exporteren en importeren, of van test naar productie. 
* **Expressies gebruiken in acties** - Expressies invoeren in elke actie en inline-hulp krijgen bij het gebruik ervan.
* **Doorstromen naar Azure Logic Apps** - Uw stromen opslaan als Azure Logic App-resource die via Visual Studio of de Azure-portal kan worden geïmplementeerd.
* **Zichtbaarheid voor beheerder** -Het gebruik van Microsoft Flow downloaden in uw tenant, zodat u precies begrijpt waar en hoe stromen worden gebruikt.
* **Stromen in Dynamics 365** -Stromen gebruiken binnen Dynamics 365 for Finance and Operations, Business Edition.
* **Scenario's gemakkelijker vinden** - Bladeren door alle mogelijkheden van de connector en vervolgens een trigger gebruiken als vertrekpunt voor het bouwen van stromen.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/q2-2017-update/) over deze release.

### <a name="release-2017-07-13"></a>Release 13-07-2017
* **Publiceren van sjablonen verbeterd** -Elke stroom die u maakt, en de bijbehorende categorieën, publiceren naar de openbare galerie.
* **Gebeurtenissen in uw Outlook-agenda krijgen** - Een nieuwe actie voor het ophalen van alle gebeurtenissen tussen twee tijdstippen in uw agenda.
* **Nieuwe mobiele functionaliteit** - Stromen op aanvraag uitvoeren en een mislukte uitvoering opnieuw verzenden in de mobiele app.
* **Dynamische vervolgkeuzelijsten in aangepaste connectors** - Dynamische vervolgkeuzelijsten en pollingtriggers bouwen en uw aangepaste connectors testen.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/publishing-and-custom-connectors/) over deze release.

### <a name="release-2017-06-28"></a>Release van 28-06-2017
* **Werk uw taalinstellingen bij** - U kunt zowel de taal als de regio die Microsoft Flow gebruikt aanpassen via het menu Instellingen.
* **Vijf nieuwe connectors** - Ondersteuning toegevoegd voor Adobe Creative Cloud, Bing Maps, Bing Search, JotForm en Freshservice.
* **Configureer time-outs** - Wijzig de duur van langdurige acties, zoals goedkeuringen, voordat er een time-out optreedt en de stroom wordt voortgezet.
* **In Outlook opmerkingen bij goedkeuringen opnemen** - Wanneer u een goedkeuringsaanvraag ontvangt, kunt u er opmerkingen bij plaatsen zonder Outlook te verlaten.
* **Aangepaste kleuren voor connectors** - U kunt nu een kleur voor uw aangepaste connector invoeren. Deze zal voor de achtergrond worden gebruikt.
* **Opslaan als voor teamstromen** - Maak kopieën van stromen, met inbegrip van teamstromen
* **Verwijder informatie over stromen** - Als u een stroom verwijdert, ziet u een overzicht van alle actieve uitvoeringen voor die stroom.
* **Filteren op de pagina Connectors** - Zoek de connectors die u wilt op de pagina Connectors en filter op type connector.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/language-settings-3-connectors/) over deze release.

### <a name="release-2017-06-19"></a>Release van 19-06-2017
U kunt nu de status bekijken van alle openstaande goedkeuringsaanvragen die u hebt verzonden. Daarnaast kunt u direct vanaf uw mobiele apparaat bladeren door en bewerkingen uitvoeren voor alle openstaande goedkeuringen.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/sent-requests-flow-mobile/) over deze release.

### <a name="release-2017-06-15"></a>Release van 15-06-2017
* **Conversie van inhoud** -  Een nieuwe connector die HTML-inhoud kan omzetten in platte tekst; handig voor het verwerken van e-mails met HTML-indeling.
* **Drie nieuwe databaseconnectors** - Alleen-lezenondersteuning toegevoegd voor MySQL, PostgreSQL en Teradata. Deze connectors maken verbinding via de lokale gegevensgateway.
* **Drie andere connectors** - Maak verbinding met Azure Application Insights, Calendly en Teamwork Projects.
* **Betere visualisatie voor foutafhandeling** - Stappen die na fouten worden uitgevoerd, worden nu weergegeven met pijlen met een rode stippellijn, zodat u ze eenvoudig kunt herkennen.
* **Detailvenster voor uitvoeren** - Als een stroom mislukt, ziet u nu een nieuw deelvenster aan de rechterkant met daarin een aantal handige stappen voor het corrigeren van uw stroom.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/seven-connectors-and-html/) over deze release.

### <a name="release-2017-06-04"></a>Release van 04-06-2017
* **GA voor Windows Phone** - [De mobiele app voor Microsoft Flow is nu vrijgegeven voor algemene beschikbaarheid voor Windows Phone](https://flow.microsoft.com/blog/announcing-flow-windows-phone-app/).
* **E-mailberichten over fouten in de stroom** - Ontvang een melding via e-mail als er een stroom mislukt. Deze e-mailberichten voor fouten worden één keer per week verzonden en kunnen door de gebruiker worden in- en uitgeschakeld.
* **Selecteer een actie voor tabellen** -  Gebruik de nieuwe actie Selecteren om de set kolommen die in de tabellen moet worden opgenomen te wijzigen.
* **Connector voor Microsoft Forms** -  Microsoft Forms is een nieuw onderdeel van Office 365 Education waarmee docenten en studenten snel en eenvoudig aangepaste quizzen en enquêtes, vragenlijsten, registraties en meer kunnen maken.
* **Office 365 Enterprise K1-abonnement** - PowerApps en Microsoft Flow zijn nu opgenomen in het Office 365 Enterprise K1-abonnement en hebben een bepaald quotum.
* **HTTP-headers zijn eenvoudiger** - Net als met de actie Selecteren kunt u een naam en waarde voor de header invullen door gewoon de tekstvakken in te vullen tijdens de actie.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/microsoft-forms-tables-flow-failures/) over deze release.

### <a name="release-2017-05-23"></a>Release van 23-05-2017
* **Microsoft Teams-connector** - [Microsoft Teams](https://flow.microsoft.com/blog/introducing-the-microsoft-teams-connector-for-flow/) is een werkruimte voor chatgesprekken in Office 365 waar mensen, gesprekken en inhoud samenkomen. U vindt er alle hulpprogramma's die teams nodig hebben, zodat ze eenvoudig kunnen samenwerken en meer kunnen bereiken.
* **Widgets voor iOS en Android**: Microsoft Flow-widgets zijn knopsnelkoppelingen die u eenvoudiger en sneller toegang bieden tot functies vanaf het startscherm.
* **Foutafhandelingsstappen maken**: definieer een of meer stappen om uit te voeren nadat een actie is mislukt. Ontvang bijvoorbeeld een melding direct nadat een stroom is mislukt zodat er een record kan worden aangemaakt Dynamics 365.
* **Variabelen met gehele getallen en floatvariabelen**: initialiseer en verhoog of verlaag tellers in een stroomuitvoering om te tellen hoe vaak een bepaalde set logica wordt uitgevoerd.
* **Pagina stroomdetails**: wanneer u een stroom selecteert in de lijst **Mijn stromen** krijgt u een pagina te zien met informatie over die stroom, zoals wie er toegang toe heeft en wat de uitvoeringsgeschiedenis is.
* **Stroomuitvoeringsquota voor beheerders**: beheerders kunnen het gebruik van stroomuitvoering nu bewaken in een organisatie en het gebruik vergelijken met de reguliere uitvoeringsquota in het bedrijf. Ze kunnen ook quotaspecificaties bekijken om inzicht te krijgen in welke licenties bijdragen aan de quota.
* **HTTP-aanvraagactiveringsverbeteringen**: verschillende HTTP-methoden gebruiken en padsegmenten toevoegen voor de aanvraagactivering.
* **Twee partnerconnectors**: Microsoft Flow kan nu worden verbonden met Parserr, een e-mailparseerservice, en Cognito Forms, een onlineformulierenservice.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/error-handling/) over deze release.

### <a name="release-2017-05-12"></a>Release van 12-05-2017
* **Integratie van SharePoint-documentbibliotheken**: u kunt elk bestand in een documentbibliotheek selecteren en een stroom starten, bijvoorbeeld door het bestand voor goedkeuring naar uw manager te verzenden, [en nog veel meer doen](https://flow.microsoft.com/blog/flow-in-spo-document-libraries/).
* **Microsoft Planner-connector**: met Microsoft Planner kunt u teams, taken, documenten en conversaties eenvoudig samenbrengen voor betere resultaten.
* **Beheerdersweergave voor licenties**: beheerders kunnen alle Microsoft Flow- en PowerApps-licenties (proefversies en betaalde licenties) weergeven in het beheercentrum van Microsoft Flow.
* **PowerApps Community Plan**: het PowerApps Community Plan is een gratis plan voor individuele gebruikers die PowerApps, Microsoft Flow en Common Data Service willen verkennen en gebruiken en hun vaardigheden willen ontwikkelen.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/planner-community-and-licenses/) over deze release.

### <a name="release-2017-05-09"></a>Release 09-05-2017
* **Azure AD-connector** - er is een nieuwe connector voor het uitvoeren van beheerdersacties van Microsoft Flow, waaronder het maken van gebruikers en deze toevoegen aan groepen.
* **Verbeteringen aan Office 365 Outlook** - stromen kunnen nu worden geactiveerd door gedeelde postvakken en kunnen e-mails verzenden naar een gedeeld postvak. Ze kunnen ook automatische antwoorden instellen en lezen.
* **Beschikbaar in Canada** - u kunt nu ook in Canada uw stromen maken.
* **Aangepaste API-webhooks maken** - ontwikkelaars kunnen nu aangepaste connectors toevoegen aan hun aangepaste API's met webhooks.
* **Eigenaars van stromen beheren in het beheercentrum** - beheerders van omgevingen kunnen eigenaars van stromen beheren in het beheercentrum van Microsoft Flow.
* **Referentiemateriaal over connectors** - er is nu een [complete reeks referentiemateriaal over connectors beschikbaar op docs.microsoft.com](https://docs.microsoft.com/Connectors/).
* **Twee partnerservices** - er zijn twee nieuwe partnerservices uitgebracht: Nexmo en Paylocity.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/canada-mailboxes-aad) over deze release.

### <a name="release-2017-04-27"></a>Release van 27-04-2017
* **Stromen met parallelle stappen maken**: u kunt stromen met parallelle uitvoering maken om tegelijkertijd twee of meer stappen uit te voeren.
* **Ondersteuning van vijf nieuwe services**: er zijn vijf nieuwe services toegevoegd: Approvals, Benchmark Email, Capsule CRM, LiveChat en Outlook Customer Manager.
* **Nieuwe controlepogingen voor acties**: Wanneer er fouten met services optreden, worden er met Microsoft Flow nieuwe pogingen gedaan. U kunt nu het aantal automatische nieuwe pogingen en de details van wat er is gebeurd, weergeven.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/parallel-actions/) over deze release.

### <a name="release-2017-04-17---q1-update-for-microsoft-flow"></a>Release van 17-04-2017 - K1: update voor Microsoft Flow
* **Moderne goedkeuringservaringen**: u kunt nu werkstromen maken waarmee fiatteurs veilig in de mobiele Microsoft Flow-app of via het geïntegreerde goedkeuringencentrum op de Microsoft-Flow-website aanvragen kunnen goedkeuren.
* **Algemene beschikbaarheid van teamstromen**: de teamstromen, waarmee meerdere mensen gezamenlijk een stroom in eigendom kunnen hebben en kunnen beheren, zijn nu algemeen beschikbaar.
* **Connectors voor Microsoft Flow maken**: iedereen kan gratis een eigen Microsoft Flow-connector indienen zodat de rest van de wereld de connector kan gebruiken.
* **Een vereenvoudigde versie van de ontwerpfunctie**: voor bepaalde sjablonen toont een nieuwe versie van de ontwerpfunctie alleen de velden die nodig zijn voor het maken van een stroom waardoor de ervaring wordt vereenvoudigd.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/q1-2017-update/) over deze release.

### <a name="release-2017-04-11"></a>Release 11-04-2017
* **Nieuwe acties voor het samenstellen van tabellen en lijsten**: HTML-tabellen, CSV-tabellen en Join-acties maken die een lijst met items kunnen verwerken (in plaats van de vorige tabellen en acties waarmee alleen afzonderlijke items konden worden verwerkt).
* **Overal stappen invoegen**: u kunt een nieuwe stap nu overal in de werkstroom invoegen zonder slepen en neerzetten.
* **Vier nieuwe services**: Flow ondersteunt nu 10 to 8 Scheduling, Act!, Inoreader en de Computer Vision-API. Met de Computer Vision-API kunt u afbeeldingen verwerken om de tekstinhoud op te halen (OCR) of afbeeldingen automatisch een label geven op basis van de inhoud.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/html-tables-csvs-computer-vision/) over deze release.

### <a name="release-2017-04-03"></a>Release 03-04-2017
* **Windows Phone Beta**: de bètaversie van de Windows Phone-app is beschikbaar voor een voorbeeld van de app op uw Windows Phone. [Meer informatie](https://flow.microsoft.com/blog/windows-phone-app-beta-is-now-available/).
* **Muhimbi PDF**: u kunt nu Microsoft Word-bestanden naar PDF converteren, watermerken toevoegen, documenten samenvoegen en meer met Muhimbi PDF. [Meer informatie](https://flow.microsoft.com/blog/convert-files-using-muhimbi/).
* **Stromen activeren van fysieke knoppen**: samenwerkingsverband met twee vooraanstaande producten op het gebied van fysieke knoppen: Flic van Shortcut Labs en Bttn van The Button Corporation. [Meer informatie](https://flow.microsoft.com/blog/physical-buttons/)

### <a name="release-2017-03-22"></a>Release 22-03-2017
* **Een kopie maken van uw stroom**: u kunt nu een kopie van uw werkstroom maken om aan proefversies te werken of een stroom te dupliceren die u voorheen hebt gemaakt.
* **Twee nieuwe services**: ondersteuning voor Toodledo: beheer uw takenlijst door taken te maken en bij te werken, en Zendesk voor een klantenservice en een platform voor ondersteuningstickets.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/make-a-copy/) over deze release.

### <a name="release-2017-03-15"></a>Release van 15-03-2017
* **Knoppen delen met collega's**: u kunt nu stroomknoppen delen met andere personen zodat zakelijke gebruikers eenvoudig wordt om taken snel uit te voeren.
* **Knoppen activeren vanaf het startscherm**: met snelkoppelingen naar stroomknoppen op de start- en vergrendelingsschermen van mobiele apparaten kunt u stromen sneller dan ooit activeren.
* **Teamstromen in de Microsoft-Flow-app**: u kunt in de Microsoft-Flow-app voor iOS of Android nu stromen van andere eigenaren bekijken.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/button-sharing/) over deze release.

### <a name="release-2017-03-10"></a>Release van 10-03-2017
* **Verbeterde ervaring voor aangepaste connectors**: u kunt nu een Postman Collection-bestand gebruiken om een aangepaste connector te maken en acties te bewerken, toe te voegen en te testen.
* **Twee nieuwe services**: er is ondersteuning toegevoegd voor meldingen van PowerApps en voor PivotalTracker.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/new-updates-custom-api/) over deze release.

### <a name="release-2017-02-27"></a>Release van 27-02-2017
* **Stroomknoppen activeren**: U kunt stroomknoppen nu rechtstreeks vanaf de website van Microsoft Flow activeren. Ga hiervoor naar uw lijst met stromen en kies in het menu '...' de opdracht Nu uitvoeren.
* **Vijf nieuwe services**: er is ondersteuning toegevoegd voor Oracle Database, Intercom, FreshBooks, LeanKit en WebMerge.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/trigger-flow-buttons-web/) over deze release.

### <a name="release-2017-02-21"></a>Release van 21-02-2017
* **Stromen van de omgeving weergeven**: omgevingsbeheerders kunnen nu een volledige lijst met alle stromen binnen een bepaalde omgeving weergeven en stromen inschakelen, uitschakelen of verwijderen.
* **Twee nieuwe services**: er is ondersteuning toegevoegd voor Azure Automation en Basecamp 2.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/) over deze release.

### <a name="release-2017-02-16"></a>Release van 16-02-2017
* **Vijf nieuwe services**: er is ondersteuning toegevoegd voor Azure Data Lake, Bitbucket (een webhostingservice voor projecten met GIT-versiebeheer), Eventbrite, Infusionsoft en Pipedrive.
* **Aangepaste HTTP-verificatie**: u kunt in de stroomontwerpfunctie nu verificatie met aangepaste HTTP-eindpunten gebruiken.
* **JSON-berichten parseren**: u kunt de JSON-gegevens parseren die afkomstig zijn uit de HTTP-aanvraagtrigger of die worden geretourneerd met de HTTP-actie.
* **Filterfunctie voor stroomuitvoeringen**: de filterfunctie voor stroomuitvoeringen is verbeterd en bevat nu meer specifieke opties, waardoor u nu onder andere actieve stromen of geannuleerde uitvoeringen kunt weergeven.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/) over deze release.

### <a name="release-2017-02-06"></a>Release 06-02-2017
* **Teamstromen**: Met teamstromen kunnen meerdere mensen eigenaar zijn van een stroom en deze gezamenlijk beheren. Als iemand de organisatie verlaat, kunnen de gemaakte stromen nog steeds worden uitgevoerd.
* **Aangepaste connectors delen**: aangepaste connectors, zoals teamstromen, kunnen worden gedeeld en collectief worden beheerd in een organisatie.
* **Ondersteuning voor Gmail en LUIS**: maak verbinding met Gmail en met Language Understanding Intelligent Service van Azure Cognitive Services.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/team-flows/) over deze release.

### <a name="release-2017-01-30"></a>Release 30-01-2017
* **Invoer voor knoppen van stromen**: knoppen van stromen kunnen nu invoer van gebruikers ontvangen tijdens de uitvoering waardoor auteurs van stromen nu informatie kunnen definiëren die wordt doorgegeven wanneer op de knop wordt getikt.
* **Outlook-taken en HelloSign**: gebruik de service voor Outlook-taken voor het beheer van taken en HelloSign voor beveiligde elektronische handtekeningen.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/button-user-inputs/) over deze release.

### <a name="release-2017-01-23"></a>Release van 23-01-2017
* **Zoeken op service**: bladeren op basis van de service wanneer u een trigger of actie toevoegt om alle acties voor alle services weer te geven.
* **Schakeloptie**: schakelblokken toevoegen voor meerdere vertakkingen parallelle logica.
* **Meer e-mailacties**: nieuwe functionaliteit voor het werken met gemarkeerde e-mails in de services Office 365 Outlook en Outlook.com.
* **Vijf nieuwe services**: verbinding maken met lokale bestandssystemen of Network File Systems, de betalingsservice Stripe, IBM Informix, IBM DB2 en UserVoice.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/search-by-service/) over deze release.

### <a name="release-2017-01-14"></a>Release 14-01-2017
* **Uitvoeringen opnieuw indienen**: als een stroom mislukt en u dit probleem wilt verhelpen om de stroom opnieuw uit te voeren, kunt u de mislukte uitvoering opnieuw indienen.
* **Uitvoeringen annuleren**: als een stroom vastloopt, kunt u de uitvoering nu expliciet annuleren.
* **Twee nieuwe services**: ondersteuning voor GoToTraining en GoToWebinar toevoegen.
* **Mobiele koppelingen**: u kunt direct sjablonen delen vanuit de mobiele app en via de snelle downloadkoppeling die boven aan de website is toegevoegd voor de apps.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/managing-runs/) over deze release.

### <a name="release-2016-12-29"></a>Release 29-12-2016
Microsoft Flow ondersteunt nu DocuSign voor het afhandelen van elektronische handtekeningen en digitaal transactiebeheer, SurveyMonkey voor enquêtes op internet en de notitie-app OneNote (alleen voor zakelijke accounts).

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/final-2016-services/) over deze release.

### <a name="release-2016-12-20"></a>Release 20-12-2016
* **Nu uitvoeren** - u kunt nu een terugkerende trigger op verzoek starten - bijvoorbeeld als u een gepland rapport elke dag hebt, maar u het rapport ook **nu** moet uitvoeren.
* **Zes nieuwe services**: u kunt stromen ontwikkelen die verbinding maken met MSN weer, Medium, Google Contacten, Buffer, Harvest en TypeForm.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/run-now-and-six-more-services/) over deze release.

### <a name="release-2016-12-14"></a>Release 14-12-2016
U kunt nu gebruikmaken van waardevolle informatie wanneer u een knopstroom start, zoals waar de knop is geactiveerd, door wie, op welk tijdstip en nog veel meer.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/button-trigger-tokens/) over deze release.

### <a name="release-2016-12-06"></a>Release van 06-12-2016
* **Introductie van begeleide training**: ga aan de slag met geordende reeks cursussen waarin video’s aan documentatie worden gekoppeld zodat u meer inzicht krijgt in de uitgebreide en krachtige mogelijkheden van Microsoft Flow.
* **Twee nieuwe services**: voor stromen kan nu worden gebruikgemaakt van Freshdesk, een oplossing voor klantondersteuning, en GoToMeeting, een hulpprogramma voor onlinevergaderingen.
* **Ondersteuning voor HTTP-webhooks**: een stroom kan nu als eindpunt worden gebruikt voor webhooks die zichzelf automatisch registreren en de registratie automatisch weer opheffen.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/guided-learning-and-two-services/) over deze release.

### <a name="release-2016-11-23"></a>Release van 23-11-2016
* **Ondersteuning voor Power BI-waarschuwingen in Flow**: onderneem actie op basis van statistieken door via Power BI-gegevenswaarschuwingen stromen te activeren.
* **Verbeteringen voor de mobiele toepassing**: u beschikt al over de mogelijkheid om stromen op basis van een sjabloon te maken, maar u kunt u nu ook compleet nieuwe stromen maken. De prestaties tijdens het bekijken van stroomuitvoeringen is ook verbeterd.
* **Acht nieuwe services**: u kunt u verbinding maken met Azure Resource Manager, Azure Queues, Chatter, Disqus, Azure DocumentDB, de Cognitive Services Face-API, HipChat en Wordpress.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/power-bi-and-eight-other-services/) over deze release.

### <a name="release-2016-11-15"></a>Release van 15-11-2016
* **Microsoft Flow-partnerprogramma**: Microsoft Flow is nu voorzien van een gecertificeerd partnerprogramma om met anderen in contact te komen. Zo kunt u met Microsoft Flow overal ter wereld profiteren van de talenten en ervaringen van verschillende bedrijven.
* **Zes nieuwe services**: er worden deze week ook zes nieuwe services geïntroduceerd: Asana, Campfire, EasyRedmine, JIRA, Redmine en Vimeo.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/partner-program-six-new-services/) over deze release.

### <a name="release-2016-10-31---general-availability"></a>Release 2016-10-31: algemene beschikbaarheid
* **Prijzen en licenties**: nu beschikbaar met zowel gratis als betaalde abonnementen, en opgenomen in Office 365 en Dynamics 365.
* **Microsoft Flow-beheercentrum**: gereed voor bedrijfsomgevingen met het nieuwe Beheercentrum. U kunt de omgevingen binnen de organisatie beheren in het Beheercentrum.
* **Beleid voor preventie van gegevensverlies**: beheerders kunnen beleid maken voor preventie van gegevensverlies om gegevensstromen tussen services te beheren.
* **Beschikbaarheid voor Android**: De Microsoft Flow-telefoonapp is nu beschikbaar voor iOS en Android. Met de app kunt u met één tik op een knop meldingen ontvangen, activiteiten controleren en stromen starten.
* **Nieuwe designerervaringen**: u kunt de gepasseerde dynamische inhoud nu stap voor stap doorzoeken, waardoor u veel sneller inzage hebt in de gewenste gegevens.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/announcing-ga/) over deze release.

### <a name="release-2016-10-26"></a>Release 26-10-2016
* **Knopstromen**: er zijn talloze bewerkingen die we graag altijd en overal willen kunnen activeren. Met knopstromen kunt u deze bewerkingen met één klik uitvoeren vanaf uw mobiele apparaat.
* **Omgevingen aankondigen**: omgevingen zijn afzonderlijke ruimten voor het opslaan en beheren van de stromen van uw organisatie. Omgevingen zijn geologisch bepaald. Dit betekent dat de stromen, apps en bedrijfsgegevens die zich in een omgeving bevinden, zich ook bevinden in de regio waarin de omgeving zich bevindt.
* **Zes nieuwe services**: er is ondersteuning toegevoegd voor voor Bit.ly, Cognitive Services, Text Analytics, Dynamics NAV, Dynamics 365 voor Financiën, Instapaper en Pinterest.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/environments-for-makers/) over deze release.

### <a name="release-2016-10-16"></a>Release 16-10-2016
* **Aangepaste connectors bieden ondersteuning voor meer verificatietypen**: aangepaste connectors bieden nu ondersteuning voor verificatie van API-sleutels en kunnen worden geverifieerd bij elke service die ondersteuning biedt voor de volledige OAuth 2.0-specificatie.
* **Er worden drie nieuwe services ondersteund**: er is ondersteuning toegevoegd voor Basecamp 3, Blogger en PagerDuty.
* **Verbeteringen in de ontwerpfunctie**: de prestaties zijn verbeterd. U kunt nu uw verbindingen bijwerken en herstellen vanuit het menu '...' voor elke actie, en we hebben een nieuwe stap toegevoegd genaamd Beëindigen, waarmee u de uitvoering van een stroom kunt beëindigen.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/early-october-updates/) over deze release.

### <a name="release-2016-09-25"></a>Release 25-09-2016
Het maken van stromen is nu beschikbaar op mobiele telefoons. Blader door onze uitgebreide galerie met sjablonen, navigeer door de lijst met services of selecteer een sjablooncategorie en klik door tot de details ervan. [Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/mobile-creation/) over deze release.

### <a name="release-2016-09-22"></a>Release 22-09-2016
* **Microsoft Graph People Picker**: er is een nieuwe Microsoft Graph People Picker rechtstreeks in de Microsoft Flow-gebruikersinterface geïntegreerd, zodat u de juiste contactpersoon of het juiste e-mailadres kunt kiezen.
* **Ondersteuning voor Microsoft Dynamics AX**: u kunt nu vanuit uw stromen actie ondernemen op uw operationele Dynamics AX Online-gegevens, van het maken van nieuwe records tot het opvragen van gegevens.
* **Twee nieuwe services van partners**: u kunt nu appFigures of Insightly vanuit uw stromen gebruiken.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/more-september-updates/) over deze release.

### <a name="release-2016-09-14"></a>Release 14-09-2016
* **Insluiten in uw website of app**: ontwikkelaars kunnen Microsoft Flow nu insluiten in hun apps of websites, waarmee zij hun gebruikers een eenvoudige manier bieden om hun persoonlijke of professionele taken te automatiseren.
* **Een stroom gebruiken als een HTTP-eindpunt**: u kunt nu een stroom zelf als een HTTP-API gebruiken. Er is een trigger genaamd Aanvraag in de stroom en u kunt ervoor kiezen om te reageren op de inkomende aanvraag door een Reactie-kaart toe te voegen.
* **Ondersteuning voor Todoist**: Todoist geeft u overzicht van al uw projecten, zowel op het werk als thuis.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/extend-web-site-application/) over deze release.

### <a name="release-2016-09-01"></a>Release 01-09-2016
Microsoft Flow is nu beschikbaar voor iedereen. Wij hebben de preview-versie in eerste instantie alleen beschikbaar gesteld voor e-mailadressen van uw werk of school, zoals e-mailadressen die worden gebruikt bij Office 365 Business en Office 365 Enterprise. Maar vandaag maken wij bekend dat de preview officieel en gratis beschikbaar is voor alle gebruikers, ongeacht welk e-mailadres u hebt. [Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/available-for-everyone/) over deze release.

### <a name="release-2016-08-31"></a>Release 31-08-2016
* **Geneste voorwaarden**: u kunt nu een tweede (of derde, enz.) voorwaarde in een andere voorwaarde opnemen.
* **Op elke lus toepassen**: toepassen op elke lus zorgt ervoor dat u de lijst kunt beheren die u herhaalt.
* **Do-until**: met een do-until-lus kunt u een stap herhalen tot aan een bepaalde voorwaarde wordt voldaan.
* **Matrices met filters**: er is een systeemeigen filterstap die ervoor kan zorgen dat elk item in de lijst overeenkomt met een expressie die u definieert.
* **Tekenreeksvariabelen samenstellen**: u kunt nu een tekenreeksvariabele samenstellen.
* **Bereiken**: bereiken zijn een eenvoudige manier om twee of meer acties te groeperen.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/build-advanced-flows/) over deze release.

### <a name="release-2016-08-27"></a>Release 27-08-2016
* **Opmerkingen over stappen**: met opmerkingen kunnen gemakkelijk notities worden aangebracht bij elke afzonderlijke actie, zodat u gemakkelijk kunt onthouden wat de stroom nodig heeft
* **Ondersteuning voor Smartsheet**: deze week hebben we ondersteuning toegevoegd voor koppelingen met Smartsheet. Smartsheet is een service waarmee u gemakkelijk kunt samenwerken aan werkbladen in de cloud.
* **Gebruikersinterface voor het ontwerpen van stromen is verfijnd**: de stroomnaam is duidelijker gepositioneerd en de knop om mee op te slaan is naar boven op de pagina verplaatst zodat deze gemakkelijke toegankelijk is.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/add-comments-smartsheet/) over deze release.

### <a name="release-2016-08-18"></a>Release 18-08-2016
U kunt nu een preview van de nieuwe, moderne SharePoint Online-lijsten zien waarin de Microsoft Flow-integratie is opgenomen. [Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/microsoft-flow-integration-with-sharepoint-modern-lists-preview/) over deze release.

### <a name="release-2016-08-13"></a>Release 13-08-2016
* **Visual Studio Team Services**: met Flow kunt u nu VSTS aan diverse services koppelen, zoals e-mail van O365, Slack, Trello en Wunderlist.
* **Uitbreidingen van SharePoint**: SharePoint-lijsten bieden ondersteuning voor uiteenlopende gegevenstypen, van eenvoudige objecten zoals een regel tekst en datum/tijd, tot complexe objecten zoals Persoon of Groep, Opzoeken en Keuze.
* **O365 Outlook-koppelingen testen**: telkens wanneer u een nieuwe O365 Outlook-verbinding maakt, wordt deze nu getest om te controleren of u klaar bent om deze te gebruiken.
* **Beheer van booleaanse waarden**: wij hebben ook beheer van booleaanse waarden toegevoegd om te verduidelijken welke waarden u moet opgeven voor booleaanse invoervelden, zoals Heeft bijlagen in de trigger Wanneer er een nieuwe e-mail wordt ontvangen.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/visual-studio-team-services-enhancements-to-sharepoint-and-o365-outlook-and-boolean-control/) over deze release.

### <a name="release-2016-08-08"></a>Release 08-08-2016
Openbare preview-versie van de Microsoft Common Data Service is geïntegreerd in Microsoft Flow. [Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/flow-and-common-data-model/) over deze release.

### <a name="release-2016-08-05"></a>Release 08-05-2016
* **SharePoint on-premises**: net zoals bij SharePoint Online kunt u met behulp van vooraf gedefinieerde sjablonen of door nieuwe sjablonen te maken, stromen maken rond uw SharePoint on-premises lijsten en documentbibliotheken.
* **Infoballonnen in de ontwerpfunctie**: om de mogelijkheden van elke trigger en -actie uit te breiden, zijn er infoballonnen toegevoegd aan elke stap van uw stroom.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/sharepoint-on-premises-and-info-bubbles-2/) over deze release.

### <a name="release-2016-07-15"></a>Release 15-07-2016
* **Vier nieuwe services toegevoegd**: breng een koppeling tot stand tussen Google Calendar, Google Tasks, YouTube en SparkPost.
* **Wijzig de naam van uw acties**: u kunt nu onderscheid maken tussen deze verschillende acties door ze een andere naam te geven.
* **Vertraging voor verschillende tijdperioden**: u kunt nu een willekeurig aantal seconden, minuten, uren of dagen selecteren.
* **Eenvoudiger te gebruiken mappenverkenner**: wij hebben de mappenverkenner vereenvoudigd. Door nu links te selecteren, wordt die map gekozen, en door rechts te selecteren, wordt die map geopend, zodat u de submappen erin kunt kiezen.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/new-google-services-rename-more/) over deze release.

### <a name="release-2016-07-08"></a>Release 08-07-2016
On-premises connectiviteit voor Microsoft Flow met behulp van on-premises gegevensgateway. Hiermee kunt u beveiligde verbindingen maken met SQL Server en deze integreren in uw stromen. [Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/on-premises-data-gateway/) over deze release.

### <a name="release-2016-07-02"></a>Release 02-07-2016
* **Ondersteuning voor Google Sheets**: in het verleden had u zowel de mogelijkheid Excel als Google Drive te gebruiken, maar deze week voegen wij systeemeigen ondersteuning voor Google Sheets toe.
* **Snel aan de slag met sjablonen**: wij hebben ook enkele optimalisaties doorgevoerd in de manier waarop u met sjablonen aan de slag kunt gaan. Nu kunt u rechtstreeks op de sjabloonpagina selecteren welke accounts u wilt gebruiken voor een sjabloon.
* **Autorisatie voor SharePoint en Office 365 verloopt niet**: nu verlengt Microsoft Flow automatisch uw toegang tot op Azure Active Directory gebaseerde services, zodat al uw stromen blijven werken na een wachtwoordwijziging.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/more-june-updates/) over deze release.

### <a name="release-2016-06-20"></a>Release 20-06-2016
* **Maak kennis met de nieuwe mobiele app voor Microsoft Flow**: vandaag introduceren wij wederom een belangrijk onderdeel van ons product: er is nu een mobiele app beschikbaar die kan worden gedownload voor iOS (binnenkort ook voor Android) waarmee u uw geautomatiseerde werkstromen altijd en overal kunt beheren, volgen en verkennen.  
* **Eenmalige aanmelding**: wij hebben eenmalige aanmelding geïmplementeerd, zodat u zich voor Microsoft Flow kunt laten verifiëren bij andere Microsoft-services zoals Office 365.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/welcome-to-flow-now-more-mobile/) over deze release.

### <a name="release-2016-06-18"></a>Release 18-06-2016
* **Nieuwe e-mailservice**: u kunt e-mailberichten nu rechtstreeks vanuit Microsoft Flow verzenden, zonder dat u in Microsoft Flow een koppeling hoeft te hebben met uw zakelijke of persoonlijke e-mailaccounts.
* **Meldingen in de portal**: u ziet nu meldingen aan de bovenkant van de portal wanneer er iets met uw stromen aan de hand is.
* **Alle activiteiten in de portal**: u ziet nu activiteit bij al uw stromen door te klikken op het nieuwe tabblad Activiteit op de Flow-website.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/mail-and-all-activity/) over deze release.

### <a name="release-2016-05-27"></a>Release 27-05-2016
* **Op service door sjablonen bladeren**: er is nu een manier om alle services te zien die wij ondersteunen (zonder dat u zich hoeft aan te melden). Op deze pagina kunt u een beschrijving van elk van de services zien en de sjablonen bekijken die wij voor die service hebben.
* **Uw aangepaste connectors maken en gebruiken**: net zoals u aangepaste connectors in PowerApps kunt maken, kunt u ook rechtstreeks vanaf flow.microsoft.com verbinding met uw eigen API's maken:
* **Uw stromen testen voordat u klaar bent**: wanneer u een stroom opslaat kunt u nu live de resultaten zien van de stroomuitvoering, als u de startactie uitvoert.

[Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/may-updates-to-microsoft-flow/) over deze release.

### <a name="release-2016-05-07"></a>Release 07-05-2016
Er zijn twee nieuwe services toegevoegd: Microsoft Project Online en Mandrill van Mailchimp. [Lees meer informatie en stel vragen](https://flow.microsoft.com/blog/announcing-microsoft-flow-webinars/) over deze release.

### <a name="release-2016-04-27---public-preview"></a>Release 2016-04-27: openbare preview
Als u logische stromen gebruikt als onderdeel van [Microsoft PowerApps](https://powerapps.microsoft.com), biedt de Microsoft Flow Preview-release diverse nieuwe functies:

* U kunt nu door een galerie met tientallen sjablonen bladeren en deze sorteren op populariteit, naam of publicatiedatum.
* U kunt [uw eigen sjablonen publiceren](publish-a-template.md) in de galerie nadat u een stroom hebt aangepast.
* U kunt de geschiedenis van elke controle en uitvoering van een stroom bekijken.
* Wanneer u een stroom opslaat, kunt u deze [onmiddellijk in actie zien](see-a-flow-run.md) door de triggeractie uit te voeren.
* In onze [nieuwe community](https://go.microsoft.com/fwlink/?LinkID=787467) kunt u Flow bespreken of [uw ideeën delen](https://go.microsoft.com/fwlink/?LinkID=787474).

## <a name="next-steps"></a>Volgende stappen
Als u problemen ondervindt die niet worden besproken in deze releaseopmerkingen of in de [veelgestelde vragen](frequently-asked-questions.md), stel uw vraag dan aan [onze community](https://go.microsoft.com/fwlink/?LinkID=787467) of [neem contact op met het ondersteuningsteam](http://go.microsoft.com/fwlink/?LinkID=787479).

