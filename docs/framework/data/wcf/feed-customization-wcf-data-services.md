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
ms.openlocfilehash: 1922351ffb11d5ff6541ef22dee623c20d153d6a
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43747067"
---
# <a name="feed-customization-wcf-data-services"></a>Personalizzazione di feed (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] Usa il [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] per esporre i dati come feed. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] supporta i formati Atom e JavaScript Object Notation (JSON) per i feed di dati. Quando si usa un feed Atom, [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] fornisce un metodo standard per serializzare i dati, ad esempio le entità e relazioni, in formato XML che può essere incluso nel corpo del messaggio HTTP. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] definisce un mapping di proprietà di entità predefinito tra i dati contenuti nelle entità e gli elementi Atom. Per altre informazioni, vedere [OData: formato Atom](https://go.microsoft.com/fwlink/?LinkID=185794).  
  
 È possibile che lo scenario applicativo in uso richieda che i dati delle proprietà restituiti dal servizio dati vengano serializzati in modo personalizzato piuttosto che nel formato dei feed standard. Con [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], è possibile personalizzare la serializzazione in un feed di dati in modo che le proprietà di un'entità possano essere mappate agli elementi inutilizzati e agli attributi di una voce o agli elementi personalizzati di una voce nel feed.  
  
> [!NOTE]
>  La personalizzazione di feed è supportata solo per i feed Atom. I feed personalizzati non vengono restituiti quando per il feed restituito è richiesto il formato JSON.  
  
 Con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] è possibile definire un mapping alternativo di proprietà di entità per un payload Atom applicando manualmente gli attributi ai tipi di entità nel modello di dati. La modalità di applicazione degli attributi viene determinata dal provider dell'origine dati del servizio dati.  
  
> [!IMPORTANT]
>  Quando si definiscono feed personalizzati, è necessario assicurarsi che tutte le proprietà dell'entità che dispongono di definizioni di mapping personalizzate siano incluse nella proiezione. Se una proprietà di entità mappata non è inclusa nella proiezione potrebbe verificarsi una perdita di dati. Per altre informazioni, vedere [proiezioni di Query](../../../../docs/framework/data/wcf/query-projections-wcf-data-services.md).  
  
## <a name="customizing-feeds-with-the-entity-framework-provider"></a>Personalizzazione di feed con il provider di Entity Framework  
 Il modello di dati usato con il provider di [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] è rappresentato come codice XML nel file con estensione edmx. In questo caso, gli attributi che definiscono i feed personalizzati vengono aggiunti agli elementi `EntityType` e `Property` che rappresentano tipi di entità e proprietà nel modello di dati. Questi attributi di personalizzazione di feed non sono definiti nel [ \[MC-CSDL\]: formato di File di definizione dello Schema concettuale](https://go.microsoft.com/fwlink/?LinkId=159072), ovvero nel formato che il [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] provider viene utilizzato per definire il modello di dati. È pertanto necessario dichiarare gli attributi di personalizzazione dei feed in uno spazio dei nomi dello schema specifico, definito come `m="http://schemas.microsoft.com/ado/2007/08/dataservices/metadata"`. Nel frammento XML seguente vengono illustrati gli attributi di personalizzazione dei feed applicati agli elementi `Property` del tipo di entità `Products` che definiscono le proprietà `ProductName`, `ReorderLevel` e `UnitsInStock`.  
  
 [!code-xml[Astoria Custom Feeds#EdmFeedAttributes](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria custom feeds/xml/northwind.csdl#edmfeedattributes)]  
  
 Questi attributi producono il feed di dati personalizzato seguente per il set di entità `Products`. Nel feed di dati personalizzato il valore della proprietà `ProductName` viene visualizzato sia nell'elemento `author` sia come elemento proprietà `ProductName` e la proprietà `UnitsInStock` viene visualizzata in un elemento personalizzato con il relativo spazio dei nomi univoco e con la proprietà `ReorderLevel` come attributo:  
  
 [!code-xml[Astoria Custom Feeds#EdmFeedResultProduct](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria custom feeds/xml/edmfeedresult.xml#edmfeedresultproduct)]  
  
 Per altre informazioni, vedere [procedura: personalizzare feed con il Provider Entity Framework](../../../../docs/framework/data/wcf/how-to-customize-feeds-with-ef-provider-wcf-data-services.md).  
  
> [!NOTE]
>  Poiché le estensioni al modello di dati non sono supportate da Entity Designer, è necessario modificare manualmente il file XML contenente il modello di dati. Per altre informazioni sul file con estensione edmx generato dal [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] degli strumenti, vedere [Cenni preliminari sul File edmx](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4).  
  
### <a name="custom-feed-attributes"></a>Attributi di feed personalizzati  
 Nella tabella seguente vengono elencati gli attributi XML per la personalizzazione di feed che è possibile aggiungere al file CSDL (Conceptual Schema Definition Language) che definisce il modello di dati. Questi attributi equivalgono alle proprietà dell'oggetto <xref:System.Data.Services.Common.EntityPropertyMappingAttribute> usato con il provider di reflection.  
  
|Nome attributo|Descrizione|  
|--------------------|-----------------|  
|`FC_ContentKind`|Indica il tipo di contenuto. Le parole chiave seguenti definiscono i tipi di contenuto di diffusione.<br /><br /> `text:` Il valore della proprietà viene visualizzato nel feed come testo.<br /><br /> `html:` Il valore della proprietà viene visualizzato nel feed come HTML.<br /><br /> `xhtml:` Il valore della proprietà viene visualizzato nel feed come HTML in formato XML.<br /><br /> Queste parole chiave equivalgono ai valori dell'enumerazione <xref:System.Data.Services.Common.SyndicationTextContentKind> usata con il provider di reflection.<br /><br /> Questo attributo non è supportato quando si usano gli attributi `FC_NsPrefix` e `FC_NsUri`.<br /><br /> Quando si specifica un valore `xhtml` per l'attributo `FC_ContentKind`, è necessario assicurarsi che il valore della proprietà contenga codice XML formattato correttamente. Il servizio dati restituisce il valore senza eseguire alcuna trasformazione. È inoltre necessario assicurarsi che tutti i prefissi degli elementi XML nel codice XML risultante dispongano di un URI dello spazio dei nomi e di un prefisso definito nel feed sottoposto a mapping.|  
|`FC_KeepInContent`|Indica che il valore della proprietà a cui viene fatto riferimento deve essere incluso sia nella sezione di contenuto del feed sia nel percorso sottoposto a mapping. I valori validi sono `true` e `false`. Per rendere compatibili con le versioni precedenti di feed risultante [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], specificare il valore `true` per assicurarsi che il valore è incluso nella sezione del contenuto del feed.|  
|`FC_NsPrefix`|Prefisso dello spazio dei nomi dell'elemento XML in un mapping non di diffusione. Questo attributo deve essere usato con l'attributo `FC_NsUri` e non è possibile usarlo con l'attributo `FC_ContentKind`.|  
|`FC_NsUri`|URI dello spazio dei nomi dell'elemento XML in un mapping non di diffusione. Questo attributo deve essere usato con l'attributo `FC_NsPrefix` e non è possibile usarlo con l'attributo `FC_ContentKind`.|  
|`FC_SourcePath`|Percorso della proprietà dell'entità a cui si applica la regola di mapping del feed. Questo attributo è supportato solo quando lo si usa in un elemento `EntityType`.<br /><br /> La proprietà <xref:System.Data.Services.Common.EntityPropertyMappingAttribute.SourcePath%2A> non può fare riferimento direttamente a un tipo complesso. Per i tipi complessi, è necessario usare un'espressione di percorso in cui i nomi delle proprietà sono separati da una barra rovesciata (`/`). Ad esempio, i valori seguenti sono consentiti per un tipo di entità `Person` con una proprietà integer `Age` e una proprietà complessa<br /><br /> `Address`:<br /><br /> `Age`<br /><br /> `Address/Street`<br /><br /> La proprietà <xref:System.Data.Services.Common.EntityPropertyMappingAttribute.SourcePath%2A> non può essere impostata su un valore contenente uno spazio o qualsiasi altro carattere non valido in un nome di proprietà.|  
|`FC_TargetPath`|Nome dell'elemento di destinazione del feed risultante per il mapping della proprietà. Questo elemento può corrispondere a un elemento definito dalla specifica Atom o a un elemento personalizzato.<br /><br /> Le parole chiave seguenti rappresentano valori del percorso di destinazione di diffusione predefiniti che puntano a una posizione specifica in un feed [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].<br /><br /> `SyndicationAuthorEmail:` Il `atom:email` elemento figlio dell'elemento di `atom:author` elemento.<br /><br /> `SyndicationAuthorName:` Il `atom:name` elemento figlio dell'elemento di `atom:author` elemento.<br /><br /> `SyndicationAuthorUri:` Il `atom:uri` elemento figlio dell'elemento di `atom:author` elemento.<br /><br /> `SyndicationContributorEmail:` Il `atom:email` elemento figlio dell'elemento di `atom:contributor` elemento.<br /><br /> `SyndicationContributorName:` Il `atom:name` elemento figlio dell'elemento di `atom:contributor` elemento.<br /><br /> `SyndicationContributorUri:` Il `atom:uri` elemento figlio dell'elemento di `atom:contributor` elemento.<br /><br /> `SyndicationCustomProperty:` Un elemento di proprietà personalizzato. Quando si esegue il mapping a un elemento personalizzato, la destinazione deve corrispondere a un'espressione di percorso in cui gli elementi annidati sono separati da una barra rovesciata (`/`) e gli attributi vengono specificati da una e commerciale (`@`). Nell'esempio seguente la stringa `UnitsInStock/@ReorderLevel` esegue il mapping di un valore di proprietà a un attributo denominato `ReorderLevel` in un elemento figlio denominato `UnitsInStock` dell'elemento entry radice.<br /><br /> `<Property Name="ReorderLevel" Type="Int16"               m:FC_TargetPath="UnitsInStock/@ReorderLevel"               m:FC_NsPrefix="Northwind"               m:FC_NsUri="http://schemas.examples.microsoft.com/dataservices"               m:FC_KeepInContent="false"               />`<br /><br /> Quando la destinazione corrisponde a un nome di elemento personalizzato, è inoltre necessario specificare gli attributi `FC_NsPrefix` e `FC_NsUri`.<br /><br /> `SyndicationPublished:` Il `atom:published` elemento.<br /><br /> `SyndicationRights:` Il `atom:rights` elemento.<br /><br /> `SyndicationSummary:` Il `atom:summary` elemento.<br /><br /> `SyndicationTitle:` Il `atom:title` elemento.<br /><br /> `SyndicationUpdated:` Il `atom:updated` elemento.<br /><br /> Queste parole chiave equivalgono ai valori dell'enumerazione <xref:System.Data.Services.Common.SyndicationItemProperty> usata con il provider di reflection.|  
  
> [!NOTE]
>  Per i nomi e i valori degli attributi viene effettuata la distinzione tra maiuscole e minuscole. Gli attributi possono essere applicati all'elemento `EntityType` oppure a uno o più elementi `Property`, ma non a entrambi.  
  
## <a name="customizing-feeds-with-the-reflection-provider"></a>Personalizzazione di feed con il provider di reflection  
 Per personalizzare feed per un modello di dati implementato tramite il provider di reflection, aggiungere una o più istanze dell'attributo <xref:System.Data.Services.Common.EntityPropertyMappingAttribute> alle classi che rappresentano i tipi di entità nel modello di dati. Le proprietà della classe <xref:System.Data.Services.Common.EntityPropertyMappingAttribute> corrispondono agli attributi di personalizzazione dei feed descritti nella sezione precedente. Di seguito viene illustrato un esempio di dichiarazione del tipo `Order`, con mapping del feed personalizzato definito per entrambe le proprietà.  
  
> [!NOTE]
>  Il modello di dati per questo esempio viene definito nell'argomento [procedura: creare un servizio dati utilizzando il Provider di Reflection](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md).  
  
 [!code-csharp[Astoria Custom Feeds#CustomOrderFeed](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria custom feeds/cs/orderitems.svc.cs#customorderfeed)]
 [!code-vb[Astoria Custom Feeds#CustomOrderFeed](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria custom feeds/vb/orderitems.svc.vb#customorderfeed)]  
  
 Questi attributi producono il feed di dati personalizzato seguente per il set di entità `Orders`. In questo feed personalizzato il `OrderId` valore della proprietà viene visualizzato solo nel `title` elemento del `entry` e il `Customer` valore della proprietà viene visualizzato sia nel `author` elemento e come il `Customer` property (elemento):  
  
 [!code-xml[Astoria Custom Feeds#IQueryableFeedResult](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria custom feeds/xml/iqueryablefeedresult.xml#iqueryablefeedresult)]  
  
 Per altre informazioni, vedere [procedura: personalizzare feed con il Provider di Reflection](../../../../docs/framework/data/wcf/how-to-customize-feeds-with-the-reflection-provider-wcf-data-services.md).  
  
## <a name="customizing-feeds-with-a-custom-data-service-provider"></a>Personalizzazione di feed con un provider del servizio dati personalizzato  
 La personalizzazione di feed per un modello di dati definito mediante un provider del servizio dati personalizzato viene definita per un tipo di risorsa chiamando il metodo <xref:System.Data.Services.Providers.ResourceType.AddEntityPropertyMappingAttribute%2A> sull'oggetto <xref:System.Data.Services.Providers.ResourceType> che rappresenta un tipo di entità nel modello di dati. Per altre informazioni, vedere [provider di servizi dati personalizzati](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md).  
  
## <a name="consuming-custom-feeds"></a>Uso di feed personalizzati  
 Quando l'applicazione utilizza direttamente un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] alimentare, deve essere in grado di elaborare gli elementi personalizzati e gli attributi nel feed restituito. Dopo aver implementato i feed personalizzati nel modello di dati, indipendentemente dal provider del servizio dati, l'endpoint `$metadata` restituisce le informazioni sui feed personalizzati come attributi dei feed personalizzati nel file CSDL restituito dal servizio dati. Quando si usa la **Aggiungi riferimento al servizio** finestra di dialogo o la [datasvcutil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) strumento per generare classi del servizio dati client, il feed personalizzato vengono utilizzati attributi per garantire che le richieste e risposte per il servizio dati vengano gestite correttamente.  
  
## <a name="feed-customization-considerations"></a>Considerazioni sulla personalizzazione dei feed  
 Quando si definiscono i mapping dei feed personalizzati è opportuno tenere presenti le considerazioni seguenti.  
  
-   Il [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] client vengono considerati gli elementi mappati in un feed vuoto quando contengono solo spazi vuoti. Per questo motivo, gli elementi mappati che contengono solo spazi vuoti non vengono materializzati sul client con lo stesso spazio vuoto. Per mantenere questo spazio vuoto sul client, è necessario impostare il valore di `KeepInContext` a `true` dell'attributo di mapping del feed.  
  
## <a name="versioning-requirements"></a>Requisiti di versione  
 La personalizzazione dei feed prevede i seguenti requisiti di versione del protocollo [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]:  
  
-   La personalizzazione dei feed richiede che il client e il servizio dati supportino entrambi la versione 2.0 del protocollo [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] e versioni successive.  
  
 Per altre informazioni, vedere [controllo delle versioni del servizio dati](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Provider di reflection](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)  
 [Provider di Entity Framework](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)
