---
title: Personalizzazione di feed (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, feeds
- WCF Data Services, Atom protocol
- Atom Publishing Protocol [WCF Data Services]
- WCF Data Services, customizing feeds
ms.assetid: 0d1a39bc-6462-4683-bd7d-e74e0fd28a85
ms.openlocfilehash: f34ee198ba49a168ed8b56785bea68beee2eb214
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348117"
---
# <a name="feed-customization-wcf-data-services"></a>Personalizzazione di feed (WCF Data Services)
WCF Data Services USA il Open Data Protocol (OData) per esporre i dati come feed. OData supporta sia i formati Atom che JavaScript Object Notation (JSON) per i feed di dati. Quando si utilizza un feed Atom, OData fornisce un metodo standard per serializzare i dati, ad esempio entità e relazioni, in un formato XML che può essere incluso nel corpo del messaggio HTTP. OData definisce un mapping di proprietà di entità predefinito tra i dati contenuti nelle entità e gli elementi Atom. Per ulteriori informazioni, vedere [OData: formato Atom](https://www.odata.org/documentation/odata-version-2-0/atom-format/).  
  
 È possibile che lo scenario applicativo in uso richieda che i dati delle proprietà restituiti dal servizio dati vengano serializzati in modo personalizzato piuttosto che nel formato dei feed standard. Con OData è possibile personalizzare la serializzazione in un feed di dati in modo che sia possibile eseguire il mapping delle proprietà di un'entità agli elementi e agli attributi inutilizzati di una voce o agli elementi personalizzati di una voce nel feed.  
  
> [!NOTE]
> La personalizzazione di feed è supportata solo per i feed Atom. I feed personalizzati non vengono restituiti quando per il feed restituito è richiesto il formato JSON.  
  
 Con WCF Data Services è possibile definire un mapping di proprietà di entità alternativo per un payload Atom applicando manualmente attributi ai tipi di entità nel modello di dati. La modalità di applicazione degli attributi viene determinata dal provider dell'origine dati del servizio dati.  
  
> [!IMPORTANT]
> Quando si definiscono feed personalizzati, è necessario assicurarsi che tutte le proprietà dell'entità che dispongono di definizioni di mapping personalizzate siano incluse nella proiezione. Se una proprietà di entità mappata non è inclusa nella proiezione potrebbe verificarsi una perdita di dati. Per altre informazioni, vedere [proiezioni di query](query-projections-wcf-data-services.md).  
  
## <a name="customizing-feeds-with-the-entity-framework-provider"></a>Personalizzazione di feed con il provider di Entity Framework  
 Il modello di dati utilizzato con il provider di Entity Framework viene rappresentato come XML nel file con estensione edmx. In questo caso, gli attributi che definiscono i feed personalizzati vengono aggiunti agli elementi `EntityType` e `Property` che rappresentano tipi di entità e proprietà nel modello di dati. Questi attributi di personalizzazione del feed non sono definiti in [\[MC-CSDL\]: formato del file di definizione dello schema concettuale](https://docs.microsoft.com/openspecs/windows_protocols/mc-csdl/c03ad8c3-e8b7-4306-af96-a9e52bb3df12), ovvero il formato utilizzato dal provider di Entity Framework per definire il modello di dati. È pertanto necessario dichiarare gli attributi di personalizzazione dei feed in uno spazio dei nomi dello schema specifico, definito come `m="http://schemas.microsoft.com/ado/2007/08/dataservices/metadata"`. Nel frammento XML seguente vengono illustrati gli attributi di personalizzazione dei feed applicati agli elementi `Property` del tipo di entità `Products` che definiscono le proprietà `ProductName`, `ReorderLevel` e `UnitsInStock`.  
  
 [!code-xml[Astoria Custom Feeds#EdmFeedAttributes](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/northwind.csdl#edmfeedattributes)]  
  
 Questi attributi producono il feed di dati personalizzato seguente per il set di entità `Products`. Nel feed di dati personalizzato il valore della proprietà `ProductName` viene visualizzato sia nell'elemento `author` sia come elemento proprietà `ProductName` e la proprietà `UnitsInStock` viene visualizzata in un elemento personalizzato con il relativo spazio dei nomi univoco e con la proprietà `ReorderLevel` come attributo:  
  
 [!code-xml[Astoria Custom Feeds#EdmFeedResultProduct](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/edmfeedresult.xml#edmfeedresultproduct)]  
  
 Per altre informazioni, vedere [procedura: personalizzare i feed con il provider di Entity Framework](how-to-customize-feeds-with-ef-provider-wcf-data-services.md).  
  
> [!NOTE]
> Poiché le estensioni al modello di dati non sono supportate da Entity Designer, è necessario modificare manualmente il file XML contenente il modello di dati. Per ulteriori informazioni sul file con estensione edmx generato dagli strumenti di Entity Data Model, vedere [Cenni preliminari sui file con estensione edmx (Entity Framework)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)).  
  
### <a name="custom-feed-attributes"></a>Attributi di feed personalizzati  
 Nella tabella seguente vengono elencati gli attributi XML per la personalizzazione di feed che è possibile aggiungere al file CSDL (Conceptual Schema Definition Language) che definisce il modello di dati. Questi attributi equivalgono alle proprietà dell'oggetto <xref:System.Data.Services.Common.EntityPropertyMappingAttribute> usato con il provider di reflection.  
  
|Nome attributo|Descrizione|  
|--------------------|-----------------|  
|`FC_ContentKind`|Indica il tipo di contenuto. Le parole chiave seguenti definiscono i tipi di contenuto di diffusione.<br /><br /> `text:` il valore della proprietà viene visualizzato nel feed come testo.<br /><br /> `html:` il valore della proprietà viene visualizzato nel feed come HTML.<br /><br /> `xhtml:` il valore della proprietà viene visualizzato nel feed come HTML in formato XML.<br /><br /> Queste parole chiave equivalgono ai valori dell'enumerazione <xref:System.Data.Services.Common.SyndicationTextContentKind> usata con il provider di reflection.<br /><br /> Questo attributo non è supportato quando si usano gli attributi `FC_NsPrefix` e `FC_NsUri`.<br /><br /> Quando si specifica un valore `xhtml` per l'attributo `FC_ContentKind`, è necessario assicurarsi che il valore della proprietà contenga codice XML formattato correttamente. Il servizio dati restituisce il valore senza eseguire alcuna trasformazione. È inoltre necessario assicurarsi che tutti i prefissi degli elementi XML nel codice XML risultante dispongano di un URI dello spazio dei nomi e di un prefisso definito nel feed sottoposto a mapping.|  
|`FC_KeepInContent`|Indica che il valore della proprietà a cui viene fatto riferimento deve essere incluso sia nella sezione di contenuto del feed sia nel percorso sottoposto a mapping. I valori validi sono `true` e `false`. Per rendere il feed risultante compatibile con le versioni precedenti di WCF Data Services, specificare il valore `true` per assicurarsi che il valore sia incluso nella sezione contenuto del feed.|  
|`FC_NsPrefix`|Prefisso dello spazio dei nomi dell'elemento XML in un mapping non di diffusione. Questo attributo deve essere usato con l'attributo `FC_NsUri` e non è possibile usarlo con l'attributo `FC_ContentKind`.|  
|`FC_NsUri`|URI dello spazio dei nomi dell'elemento XML in un mapping non di diffusione. Questo attributo deve essere usato con l'attributo `FC_NsPrefix` e non è possibile usarlo con l'attributo `FC_ContentKind`.|  
|`FC_SourcePath`|Percorso della proprietà dell'entità a cui si applica la regola di mapping del feed. Questo attributo è supportato solo quando lo si usa in un elemento `EntityType`.<br /><br /> La proprietà <xref:System.Data.Services.Common.EntityPropertyMappingAttribute.SourcePath%2A> non può fare riferimento direttamente a un tipo complesso. Per i tipi complessi, è necessario usare un'espressione di percorso in cui i nomi delle proprietà sono separati da una barra rovesciata (`/`). Ad esempio, i valori seguenti sono consentiti per un tipo di entità `Person` con una proprietà Integer `Age` e una proprietà complessa<br /><br /> `Address`:<br /><br /> `Age`<br /><br /> `Address/Street`<br /><br /> La proprietà <xref:System.Data.Services.Common.EntityPropertyMappingAttribute.SourcePath%2A> non può essere impostata su un valore contenente uno spazio o qualsiasi altro carattere non valido in un nome di proprietà.|  
|`FC_TargetPath`|Nome dell'elemento di destinazione del feed risultante per il mapping della proprietà. Questo elemento può corrispondere a un elemento definito dalla specifica Atom o a un elemento personalizzato.<br /><br /> Le parole chiave seguenti sono valori di percorso di destinazione di diffusione predefiniti che puntano a una posizione specifica in un feed OData.<br /><br /> `SyndicationAuthorEmail:` l'elemento figlio `atom:email` dell'elemento `atom:author`.<br /><br /> `SyndicationAuthorName:` l'elemento figlio `atom:name` dell'elemento `atom:author`.<br /><br /> `SyndicationAuthorUri:` l'elemento figlio `atom:uri` dell'elemento `atom:author`.<br /><br /> `SyndicationContributorEmail:` l'elemento figlio `atom:email` dell'elemento `atom:contributor`.<br /><br /> `SyndicationContributorName:` l'elemento figlio `atom:name` dell'elemento `atom:contributor`.<br /><br /> `SyndicationContributorUri:` l'elemento figlio `atom:uri` dell'elemento `atom:contributor`.<br /><br /> `SyndicationCustomProperty:` un elemento proprietà personalizzato. Quando si esegue il mapping a un elemento personalizzato, la destinazione deve corrispondere a un'espressione di percorso in cui gli elementi annidati sono separati da una barra rovesciata (`/`) e gli attributi vengono specificati da una e commerciale (`@`). Nell'esempio seguente la stringa `UnitsInStock/@ReorderLevel` esegue il mapping di un valore di proprietà a un attributo denominato `ReorderLevel` in un elemento figlio denominato `UnitsInStock` dell'elemento entry radice.<br /><br /> `<Property Name="ReorderLevel" Type="Int16"               m:FC_TargetPath="UnitsInStock/@ReorderLevel"               m:FC_NsPrefix="Northwind"               m:FC_NsUri="http://schemas.examples.microsoft.com/dataservices"               m:FC_KeepInContent="false"               />`<br /><br /> Quando la destinazione corrisponde a un nome di elemento personalizzato, è inoltre necessario specificare gli attributi `FC_NsPrefix` e `FC_NsUri`.<br /><br /> `SyndicationPublished:` elemento `atom:published`.<br /><br /> `SyndicationRights:` elemento `atom:rights`.<br /><br /> `SyndicationSummary:` elemento `atom:summary`.<br /><br /> `SyndicationTitle:` elemento `atom:title`.<br /><br /> `SyndicationUpdated:` elemento `atom:updated`.<br /><br /> Queste parole chiave equivalgono ai valori dell'enumerazione <xref:System.Data.Services.Common.SyndicationItemProperty> usata con il provider di reflection.|  
  
> [!NOTE]
> Per i nomi e i valori degli attributi viene effettuata la distinzione tra maiuscole e minuscole. Gli attributi possono essere applicati all'elemento `EntityType` oppure a uno o più elementi `Property`, ma non a entrambi.  
  
## <a name="customizing-feeds-with-the-reflection-provider"></a>Personalizzazione di feed con il provider di reflection  
 Per personalizzare feed per un modello di dati implementato tramite il provider di reflection, aggiungere una o più istanze dell'attributo <xref:System.Data.Services.Common.EntityPropertyMappingAttribute> alle classi che rappresentano i tipi di entità nel modello di dati. Le proprietà della classe <xref:System.Data.Services.Common.EntityPropertyMappingAttribute> corrispondono agli attributi di personalizzazione dei feed descritti nella sezione precedente. Di seguito viene illustrato un esempio di dichiarazione del tipo `Order`, con mapping del feed personalizzato definito per entrambe le proprietà.  
  
> [!NOTE]
> Il modello di dati per questo esempio è definito nell'argomento [procedura: creare un servizio dati tramite il provider di Reflection](create-a-data-service-using-rp-wcf-data-services.md).  
  
 [!code-csharp[Astoria Custom Feeds#CustomOrderFeed](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_custom_feeds/cs/orderitems.svc.cs#customorderfeed)]
 [!code-vb[Astoria Custom Feeds#CustomOrderFeed](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_custom_feeds/vb/orderitems.svc.vb#customorderfeed)]  
  
 Questi attributi producono il feed di dati personalizzato seguente per il set di entità `Orders`. In questo feed personalizzato il valore della proprietà `OrderId` viene visualizzato solo nell'elemento `title` del `entry` e il valore della proprietà `Customer` viene visualizzato sia nell'elemento `author` che nell'elemento proprietà `Customer`:  
  
 [!code-xml[Astoria Custom Feeds#IQueryableFeedResult](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/iqueryablefeedresult.xml#iqueryablefeedresult)]  
  
 Per altre informazioni, vedere [procedura: personalizzare i feed con il provider di Reflection](how-to-customize-feeds-with-the-reflection-provider-wcf-data-services.md).  
  
## <a name="customizing-feeds-with-a-custom-data-service-provider"></a>Personalizzazione di feed con un provider del servizio dati personalizzato  
 La personalizzazione di feed per un modello di dati definito mediante un provider del servizio dati personalizzato viene definita per un tipo di risorsa chiamando il metodo <xref:System.Data.Services.Providers.ResourceType.AddEntityPropertyMappingAttribute%2A> sull'oggetto <xref:System.Data.Services.Providers.ResourceType> che rappresenta un tipo di entità nel modello di dati. Per ulteriori informazioni, vedere [provider di servizi dati personalizzati](custom-data-service-providers-wcf-data-services.md).  
  
## <a name="consuming-custom-feeds"></a>Uso di feed personalizzati  
 Quando l'applicazione utilizza direttamente un feed OData, deve essere in grado di elaborare gli elementi e gli attributi personalizzati nel feed restituito. Dopo aver implementato i feed personalizzati nel modello di dati, indipendentemente dal provider del servizio dati, l'endpoint `$metadata` restituisce le informazioni sui feed personalizzati come attributi dei feed personalizzati nel file CSDL restituito dal servizio dati. Quando si utilizza la finestra di dialogo **Aggiungi riferimento al servizio** o lo strumento [DataSvcUtil. exe](wcf-data-service-client-utility-datasvcutil-exe.md) per generare classi del servizio dati client, gli attributi dei feed personalizzati vengono utilizzati per garantire che le richieste e le risposte al servizio dati vengano gestite correttamente.  
  
## <a name="feed-customization-considerations"></a>Considerazioni sulla personalizzazione dei feed  
 Quando si definiscono i mapping dei feed personalizzati è opportuno tenere presenti le considerazioni seguenti.  
  
- Il client WCF Data Services considera gli elementi mappati in un feed come vuoti quando contengono solo spazi vuoti. Per questo motivo, gli elementi mappati che contengono solo spazi vuoti non vengono materializzati sul client con lo stesso spazio vuoto. Per mantenere lo spazio vuoto nel client, è necessario impostare il valore di `KeepInContext` su `true` nell'attributo mapping del feed.  
  
## <a name="versioning-requirements"></a>Requisiti di versione  
 La personalizzazione dei feed presenta i requisiti di controllo delle versioni del protocollo OData seguenti:  
  
- Per la personalizzazione dei feed è necessario che sia il client che il servizio dati supportino la versione 2,0 del protocollo OData e versioni successive.  
  
 Per ulteriori informazioni, vedere [controllo delle versioni del servizio dati](data-service-versioning-wcf-data-services.md).  
  
## <a name="see-also"></a>Vedere anche

- [Provider di reflection](reflection-provider-wcf-data-services.md)
- [Provider di Entity Framework](entity-framework-provider-wcf-data-services.md)
