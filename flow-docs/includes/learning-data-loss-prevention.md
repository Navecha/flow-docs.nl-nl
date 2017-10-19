U kunt voor steeds meer [services](https://flow.microsoft.com/services) werkstromen bouwen met [Microsoft Flow](https://flow.microsoft.com). Het kan daarom handig zijn om gevoelige of kritieke zakelijke gegevens veilig te stellen die zijn opgeslagen in bedrijfsservices zoals SharePoint of Salesforce. Mogelijk moet uw organisatie een beleid creëren waarmee u er zeker van bent dat gevoelige zakelijke gegevens niet worden gepubliceerd in consumentenservices zoals Twitter en Facebook. Met Microsoft Flow kunt u eenvoudig beleid voor **preventie van gegevensverlies** (DLP) maken om te bepalen met welke consumentenservices uw zakelijke gegevens mogen worden gedeeld wanneer uw gebruikers stromen maken.  

## <a name="terms-you-should-get-familiar-with"></a>Termen die u moet onthouden
| Term | Beschrijving |
| --- | --- |
| **DLP** |Dit staat voor Data Loss Prevention: het voorkomen van gegevensverlies. U maakt DLP-beleid om het delen van gegevens tussen **services** te beheren. |
| **Services** |[Services](https://flow.microsoft.com/services) zijn toepassingen zoals Salesforce, SharePoint en Twitter. Onder andere deze services worden gebruikt om stromen te maken. |
| **Gegevensgroep** |Een logische groep services. U plaatst services waarvoor gegevens mogen worden gedeeld in dezelfde gegevensgroep. Er zijn twee beschikbare gegevensgroepen: **Alleen bedrijfsgegevens** en **Geen bedrijfsgegevens toegestaan**. |
| **Omgeving** |DLP-beleid wordt toegepast op een [omgeving](../environments-overview-admin.md). Een omgeving bevat gebruikers. |
| **Gebruikers** |Gebruikers maken deel uit van uw organisatie. Als ze lid zijn van een omgeving, is er DLP-beleid op hen van toepassing. |
| **Stroom** |Een stroom is een werkstroom-app waarin een combinatie van de beschikbare services wordt gebruikt. |

## <a name="all-about-how-dlp-policies-work"></a>Informatie over hoe DLP-beleid werkt
DLP-beleid bestaat uit een regel die elke service expliciet in één van de twee gegevensgroepen plaatst. Deze regel wordt vervolgens toegepast op een omgeving. Een omgeving bestaat uit een logische groep gebruikers. Gebruikers mogen geen stromen maken en mogen geen gegevens delen tussen de services die u in de verschillende gegevensgroepen plaatst. Met andere woorden: uw gebruikers kunnen alleen stromen maken waarbij gegevens worden gedeeld tussen de services in **één** gegevensgroep. Delen tussen gegevensgroepen is niet toegestaan.  

| **Naam van gegevensgroep** | **Beschrijving van gegevensgroep** |
| --- | --- |
| **Alleen zakelijke gegevens** |Tussen alle services in deze groep kunnen gegevens worden gedeeld. Er kunnen geen gegevens worden gedeeld met de gegevensgroep **Geen zakelijke gegevens toegestaan**. |
| **Geen zakelijke gegevens toegestaan** |Tussen alle services in deze groep kunnen gegevens worden gedeeld. Er kunnen geen gegevens worden gedeeld met de gegevensgroep **Alleen zakelijke gegevens**. |

**Opmerking**: Als u een service toevoegt aan een gegevensgroep, wordt deze automatisch uit de andere gegevensgroep verwijderd. Als Twitter zich bijvoorbeeld momenteel bevindt in de gegevensgroep met **alleen zakelijke gegevens**, en u niet wilt dat zakelijke gegevens met Twitter worden gedeeld, voegt u de Twitter-service toe aan de gegevensgroep waarin **geen zakelijke gegevens zijn toegestaan**. Hiermee wordt Twitter verwijderd uit de gegevensgroep **Alleen zakelijke gegevens**.

## <a name="heres-what-you-need-to-create-a-dlp"></a>Dit hebt u nodig om een DLP te maken
* Toegang tot het Microsoft Flow-[beheercentrum](https://admin.flow.microsoft.com)  
* Een account in de rol Omgevingsbeheerder  
* Een omgeving waaraan gebruikers zijn toegewezen  

## <a name="create-a-dlp-policy"></a>Een DLP-beleid maken
U maakt als volgt een DLP-beleid:  

1. Geef het beleid een naam
2. Selecteer de omgeving waar het beleid op van toepassing is
3. Voeg de services toe aan één van de twee gegevensgroepen. Alleen services in een bepaalde groep kunnen gegevens delen. Als u stromen maakt voor het delen van gegevens tussen services in twee gegevensgroepen, worden deze automatisch geblokkeerd wanneer de maker ze opslaat.  

Er is ook een meer [gedetailleerd overzicht](../prevent-data-loss.md) van DLP-beleidsregels beschikbaar.  

## <a name="examples"></a>Voorbeelden
* Als u een beleid maakt dat stromen beperkt zodat er alleen zakelijke gegevens worden gedeeld tussen SharePoint, Office 365-gebruikers, Office 365 Outlook OneDrive voor Bedrijven, Dynamics 365, SQL Server en Salesforce, ziet dat er als volgt uit:  
  ![](./media/learning-data-loss-prevention/a-few-business-centric-services.png)  
* De situatie is als volgt wanneer u een beleid maakt waarmee leden uit een bepaalde omgeving geen stroom mogen maken voor het delen van SharePoint-gegevens. SharePoint is de enige service in de gegevensgroep met **alleen zakelijke gegevens**:  
  ![Alleen zakelijke gegevens](./media/learning-data-loss-prevention/sharepoint-only-no-sharing-guided-learning.png)

