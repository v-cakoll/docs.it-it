---
title: Provider di flusso (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, binary data
- streaming data provider [WCF Data Services]
- WCF Data Services, streams
ms.assetid: f0978fe4-5f9f-42aa-a5c2-df395d7c9495
ms.openlocfilehash: 1eb1267ae0b08d558d5afc41d03270917473a669
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900917"
---
# <a name="streaming-provider-wcf-data-services"></a>Provider di flusso (WCF Data Services)

Un servizio dati può esporre dati Large Object Binary. Tali dati binari possono rappresentare flussi audio e video, immagini, file documento o altri tipi di elementi multimediali binari. Quando un'entità del modello di dati include una o più proprietà binarie, il servizio dati restituisce tali dati binari codificati in base 64 all'interno dell'elemento entry presente nel feed di risposta. Poiché questo tipo di caricamento e serializzazione di dati binari di grandi dimensioni può influire sulle prestazioni, il Open Data Protocol (OData) definisce un meccanismo per il recupero di dati binari indipendentemente dall'entità a cui appartiene. Questa operazione viene eseguita separando i dati binari dall'entità in uno o più flussi di dati.

- Risorsa multimediale: dati binari che appartengono a un'entità, quali una risorsa video, audio, immagine o altri tipi di flusso di risorse multimediali.

- Elemento entry di collegamento multimediale: entità che presenta un riferimento a un flusso di risorse multimediali correlato.

Con WCF Data Services, si definisce un flusso di risorse binario implementando un provider di dati di flusso. L'implementazione del provider di flusso fornisce al servizio dati il flusso di risorse multimediali associato a un'entità specifica come oggetto <xref:System.IO.Stream>. Questa implementazione consente al servizio dati di accettare e restituire risorse multimediali tramite HTTP sotto forma di flussi di dati binari di un tipo MIME specificato.

La configurazione di un servizio dati per supportare il flusso di dati binari richiede l'esecuzione dei passaggi seguenti:

1. Assegnare una o più entità del modello di dati come entry di collegamento multimediale. Queste entità non devono includere dati binari da trasmettere. Qualsiasi proprietà binaria di un'entità viene sempre restituita nell'elemento entry sotto forma di dati binari codificati in base 64.

2. Implementare l'interfaccia T:System.Data.Services.Providers.IDataServiceStreamProvider.

3. Definire un servizio dati che implementi l'interfaccia <xref:System.IServiceProvider>. Il servizio dati usa l'implementazione <xref:System.IServiceProvider.GetService%2A> per accedere all'implementazione del provider di dati di flusso. Questo metodo restituisce l'implementazione del provider di flusso appropriata.

4. Abilitare flussi di messaggi di grandi dimensioni nella configurazione dell'applicazione Web.

5. Abilitare accesso alle risorse binarie sul server o in un'origine dati.

Gli esempi in questo argomento sono basati su un servizio di foto di streaming di esempio, illustrato in dettaglio nella [serie di provider di streaming Post Data Services: implementazione di un provider di flusso (parte 1)](https://docs.microsoft.com/archive/blogs/astoriateam/data-services-streaming-provider-series-implementing-a-streaming-provider-part-1). Il codice sorgente per l'esempio streaming Photo Data Service è disponibile su [GitHub](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/Streaming%20Photo%20OData%20Service%20Sample).

## <a name="defining-a-media-link-entry-in-the-data-model"></a>Definizione di un elemento entry di collegamento multimediale nel modello di dati

Il provider dell'origine dati determina la modalità di definizione di un'entità come entry di collegamento multimediale nel modello di dati.

**Provider di Entity Framework**

Per indicare che un'entità è un elemento entry di collegamento multimediale, aggiungere l'attributo `HasStream` alla definizione del tipo di entità nel modello concettuale, come nell'esempio seguente:

[!code-xml[Astoria Photo Streaming Service#HasStream](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_photo_streaming_service/xml/photodata.edmx#hasstream)]

È inoltre necessario aggiungere lo spazio dei nomi `xmlns:m=http://schemas.microsoft.com/ado/2007/08/dataservices/metadata` all'entità o alla radice del file con estensione edmx o csdl che definisce il modello di dati.

Per un esempio di un servizio dati che usa il provider di Entity Framework ed espone una risorsa multimediale, vedere la [serie di provider di flusso post Data Services: implementazione di un provider di flusso (parte 1)](https://docs.microsoft.com/archive/blogs/astoriateam/data-services-streaming-provider-series-implementing-a-streaming-provider-part-1).

**Provider di reflection**

Per indicare che un'entità è un elemento entry di collegamento multimediale, aggiungere <xref:System.Data.Services.Common.HasStreamAttribute> alla classe che definisce il tipo di entità nel provider di reflection.

**Provider del servizio dati personalizzato**

Quando si usano provider di servizi personalizzati, si implementa l'interfaccia <xref:System.Data.Services.Providers.IDataServiceMetadataProvider> per definire i metadati per il servizio dati. Per ulteriori informazioni, vedere [provider di servizi dati personalizzati](custom-data-service-providers-wcf-data-services.md). Si indica che un flusso di risorse binarie appartiene a un oggetto <xref:System.Data.Services.Providers.ResourceType> impostando la proprietà <xref:System.Data.Services.Providers.ResourceType.IsMediaLinkEntry%2A> su `true` nell'oggetto <xref:System.Data.Services.Providers.ResourceType> che rappresenta il tipo di entità, un elemento entry di collegamento multimediale.

## <a name="implementing-the-idataservicestreamprovider-interface"></a>Implementazione dell'interfaccia IDataServiceStreamProvider

Per creare un servizio dati che supporta i flussi di dati binari, è necessario implementare l'interfaccia <xref:System.Data.Services.Providers.IDataServiceStreamProvider>. Questa implementazione consente al servizio dati di restituire al client i dati binari sotto forma di flusso e di usarli come flusso inviato dal client. Il servizio dati crea un'istanza di questa interfaccia ogni volta che deve accedere ai dati binari sotto forma di flusso. L'interfaccia <xref:System.Data.Services.Providers.IDataServiceStreamProvider> specifica i membri seguenti:

|Nome membro|Descrizione|
|-----------------|-----------------|
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.DeleteStream%2A>|Questo metodo viene richiamato dal servizio dati per eliminare la risorsa multimediale corrispondente quando viene eliminato l'elemento entry di collegamento multimediale. Quando si implementa <xref:System.Data.Services.Providers.IDataServiceStreamProvider>, questo metodo contiene il codice che elimina la risorsa multimediale associata all'elemento entry di collegamento multimediale fornito.|
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetReadStream%2A>|Questo metodo viene richiamato dal servizio dati per restituire una risorsa multimediale come flusso. Quando si implementa <xref:System.Data.Services.Providers.IDataServiceStreamProvider>, questo metodo contiene il codice che fornisce un flusso usato dal servizio dati per restituire la risorsa multimediale associata all'elemento entry di collegamento multimediale specifico.|
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetReadStreamUri%2A>|Questo metodo viene richiamato dal servizio dati per restituire l'URI usato per richiedere la risorsa multimediale relativa all'elemento entry di collegamento multimediale. Questo valore consente di creare l'attributo `src` nell'elemento di contenuto dell'entry di collegamento multimediale che viene usato per richiedere il flusso di dati. Quando questo metodo restituisce `null`, il servizio dati determina automaticamente l'URI. Usare questo metodo quando è necessario fornire ai client accesso diretto ai dati binari senza usare il provider di flusso.|
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetStreamContentType%2A>|Questo metodo viene richiamato dal servizio dati per restituire il valore Content-Type della risorsa multimediale associata all'elemento entry di collegamento multimediale specificato.|
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetStreamETag%2A>|Questo metodo viene richiamato dal servizio dati per restituire il valore eTag del flusso di dati associato all'entità specificata e viene usato per gestire la concorrenza dei dati binari. Quando questo metodo restituisce Null, il servizio dati non rileva la concorrenza.|
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A>|Questo metodo viene richiamato dal servizio dati per ottenere il flusso usato per la ricezione del flusso inviato dal client. Quando si implementa <xref:System.Data.Services.Providers.IDataServiceStreamProvider>, è necessario restituire un flusso scrivibile nel quale il servizio dati possa scrivere i dati del flusso ricevuti.|
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.ResolveType%2A>|Restituisce un nome di tipo completo con lo spazio dei nomi che rappresenta il tipo che il runtime del servizio dati deve creare per l'elemento entry di collegamento multimediale associato al flusso di dati della risorsa multimediale inserita.|

## <a name="creating-the-streaming-data-service"></a>Creazione del servizio dati di flusso

Per consentire all'WCF Data Services Runtime di accedere all'implementazione <xref:System.Data.Services.Providers.IDataServiceStreamProvider>, il servizio dati creato deve implementare anche l'interfaccia <xref:System.IServiceProvider>. Nell'esempio seguente viene illustrato come implementare il metodo <xref:System.IServiceProvider.GetService%2A> per restituire un'istanza della classe `PhotoServiceStreamProvider` che implementa <xref:System.Data.Services.Providers.IDataServiceStreamProvider>.

[!code-csharp[Astoria Photo Streaming Service#PhotoServiceStreamingProvider](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_photo_streaming_service/cs/photodata.svc.cs#photoservicestreamingprovider)]
[!code-vb[Astoria Photo Streaming Service#PhotoServiceStreamingProvider](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_photo_streaming_service/vb/photodata.svc.vb#photoservicestreamingprovider)]

Per informazioni generali su come creare un servizio dati, vedere [configurazione del servizio dati](configuring-the-data-service-wcf-data-services.md).

## <a name="enabling-large-binary-streams-in-the-hosting-environment"></a>Abilitazione dei flussi binari di grandi dimensioni nell'ambiente di hosting

Quando si crea un servizio dati in un'applicazione Web ASP.NET, viene utilizzato Windows Communication Foundation (WCF) per fornire l'implementazione del protocollo HTTP. Per impostazione predefinita, WCF limita la dimensione dei messaggi HTTP a soli 65.000 byte. Per consentire il flusso dei dati binari di grandi dimensioni verso e dal servizio dati, è inoltre necessario configurare l'applicazione Web per l'abilitazione di file binari di grandi dimensioni e l'uso di flussi per il trasferimento. A tal fine, aggiungere quanto segue all'elemento `<configuration />` del file Web.config dell'applicazione:

> [!NOTE]
> È necessario utilizzare una modalità di trasferimento <xref:System.ServiceModel.TransferMode.Streamed?displayProperty=nameWithType> per assicurarsi che i dati binari in entrambi i messaggi di richiesta e risposta vengano trasmessi e non memorizzati nel buffer da WCF.

Per ulteriori informazioni, vedere [trasmissione di flussi di messaggi](../../wcf/feature-details/streaming-message-transfer.md) e [quote di trasporto](../../wcf/feature-details/transport-quotas.md).

Per impostazione predefinita, Internet Information Services (IIS) consente anche di limitare la dimensione delle richieste a 4 MB. Per consentire al servizio dati di ricevere flussi di dimensioni superiori a 4 MB durante l'esecuzione in IIS, è necessario impostare anche l'attributo `maxRequestLength` dell' [elemento httpRuntime (schema delle impostazioni ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e1f13641(v=vs.100)) nella sezione `<system.web />` configurazione, come illustrato nell'esempio seguente:

## <a name="using-data-streams-in-a-client-application"></a>Utilizzo dei flussi di dati in un'applicazione client

La libreria client di WCF Data Services consente di recuperare e aggiornare queste risorse esposte come flussi binari nel client. Per ulteriori informazioni, vedere [utilizzo di dati binari](working-with-binary-data-wcf-data-services.md).

## <a name="considerations-for-working-with-a-streaming-provider"></a>Considerazioni sull'utilizzo di un provider di flusso

Quando si implementa un provider di flusso e si accede alle risorse multimediali da un servizio dati, è necessario tenere presente le considerazioni seguenti.

- Le richieste MERGE non sono supportate per le risorse multimediali. Usare una richiesta PUT per modificare la risorsa multimediale di un'entità esistente.

- Non è possibile usare una richiesta POST per creare un nuovo elemento entry di collegamento multimediale. È invece necessario inviare una richiesta POST per creare una nuova risorsa multimediale. Il servizio dati crea un nuovo elemento entry di collegamento multimediale con i valori predefiniti. Questa nuova entità può essere aggiornata da una richiesta MERGE o PUT successiva. È anche possibile memorizzare l'entità nella cache ed eseguire nell'elemento di eliminazione aggiornamenti, quale l'impostazione del valore della proprietà sul valore dell'intestazione Slug nella richiesta POST.

- Quando viene ricevuta una richiesta POST, il servizio dati chiama <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A> per creare la risorsa multimediale prima di chiamare <xref:System.Data.Services.IUpdatable.SaveChanges%2A> per creare l'elemento entry di collegamento multimediale.

- Un'implementazione di <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A> non deve restituire un oggetto <xref:System.IO.MemoryStream>. Quando si usa questo tipo di flusso, si verificano problemi nelle risorse di memoria alla ricezione di flussi di dati di dimensioni molto elevate da parte del servizio.

- Quando si archiviano le risorse multimediali in un database, occorre tenere presente le seguenti considerazioni.

  - Nel modello di dati non devono essere incluse le proprietà binarie che sono risorse multimediali. Tutte le proprietà esposte in un modello di dati vengono restituite nell'elemento entry di un feed di risposta.

  - Per migliorare le prestazioni con flussi binari di grandi dimensioni, è consigliabile creare una classe del flusso personalizzata per archiviare i dati binari nel database. Questa classe viene restituita dall'implementazione di <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A> e invia i dati binari al database in blocchi. Per un database di SQL Server, è consigliabile utilizzare un FILESTREAM per trasmettere i dati nel database quando i dati binari sono più grandi di 1 MB.

  - Assicurarsi che il database sia stato progettato per archiviare flussi binari di grandi dimensioni che devono essere ricevuti dal servizio dati.

  - Quando un client invia una richiesta POST per inserire un elemento entry di collegamento multimediale e una risorsa multimediale in una sola richiesta, viene chiamato <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A> per ottenere il flusso prima che il servizio dati inserisca la nuova entità nel database. Un'implementazione del provider di flusso deve essere in grado di gestire questo comportamento del servizio dati. Usare una tabella di dati separata per archiviare i dati binari o archiviare il flusso di dati in un file fino al completo inserimento dell'entità nel database.

- Quando si implementa il metodo <xref:System.Data.Services.Providers.IDataServiceStreamProvider.DeleteStream%2A>, <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetReadStream%2A> o <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A>, è necessario usare i valori eTag e Content-Type forniti come parametri dei metodi. Non impostare le intestazioni eTag o Content-Type nell'implementazione del provider <xref:System.Data.Services.Providers.IDataServiceStreamProvider>.

- Per impostazione predefinita, il client invia i flussi binari di grandi dimensioni tramite codifica di trasferimento HTTP Chunked. Poiché il Server di sviluppo ASP.NET non supporta questo tipo di codifica, non è possibile usare questo server Web per ospitare un servizio dati di flusso che deve accettare flussi binari di grandi dimensioni. Per altre informazioni su Server di sviluppo ASP.NET, vedere [server Web in Visual Studio per progetti web ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/58wxa9w5(v=vs.120)).

<a name="versioning"></a>

## <a name="versioning-requirements"></a>Requisiti di versione

Il provider di flusso presenta i requisiti di controllo delle versioni del protocollo OData seguenti:

- Il provider di flusso richiede che il servizio dati supporti la versione 2,0 del protocollo OData e versioni successive.

Per ulteriori informazioni, vedere [controllo delle versioni del servizio dati](data-service-versioning-wcf-data-services.md).

## <a name="see-also"></a>Vedere anche

- [Provider di servizi dati](data-services-providers-wcf-data-services.md)
- [Provider di servizi dati personalizzati](custom-data-service-providers-wcf-data-services.md)
- [Utilizzo di dati binari](working-with-binary-data-wcf-data-services.md)
