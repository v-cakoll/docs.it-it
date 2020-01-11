---
title: Utilizzo di dati binari (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, binary data
- WCF Data Services, streams
ms.assetid: aeccc45c-d5c5-4671-ad63-a492ac8043ac
ms.openlocfilehash: aa3e58d559121aaca401e7b851a4b4fd8e7753cd
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900836"
---
# <a name="working-with-binary-data-wcf-data-services"></a>Utilizzo di dati binari (WCF Data Services)

La libreria client di WCF Data Services consente di recuperare e aggiornare i dati binari da un feed di Open Data Protocol (OData) in uno dei modi seguenti:

- Come proprietà di tipo primitivo di un'entità. Si tratta del metodo consigliato per l'uso di oggetti dati binari di dimensioni ridotte che possono essere caricati facilmente in memoria. In questo caso, la proprietà binaria è una proprietà dell'entità esposta dal modello di dati e il servizio dati serializza i dati binari come codice XML binario in base 64 nel messaggio di risposta.

- Come flusso separato di risorse binarie. Si tratta del metodo consigliato per l'accesso e la modifica di dati di oggetti binari di grandi dimensioni (BLOB) che possono rappresentare una foto, un video o qualsiasi altro tipo di dati codificati binari.

WCF Data Services implementa il flusso di dati binari tramite HTTP come definito in OData. In questo meccanismo, i dati binari vengono considerati come una risorsa multimediale che è separata da ma correlata a un'entità, denominata voce di collegamento multimediale. Per ulteriori informazioni, vedere [provider di flussi](streaming-provider-wcf-data-services.md).

> [!TIP]
> Per un esempio dettagliato di come creare un'applicazione client Windows Presentation Foundation (WPF) che Scarica i file di immagine binari da un servizio OData che archivia le foto, vedere la [serie Post Data Services Streaming provider-parte 2: accesso a un flusso di risorse multimediali dal client](https://docs.microsoft.com/archive/blogs/astoriateam/data-services-streaming-provider-series-part-2-accessing-a-media-resource-stream-from-the-client). Per scaricare il codice di esempio per il servizio dati di foto di flusso in evidenza nel post di Blog, vedere l' [esempio streaming Photo Data Service](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/Streaming%20Photo%20OData%20Service%20Sample) in GitHub.

## <a name="entity-metadata"></a>Metadati dell'entità

Un'entità che dispone di un flusso di risorsa multimediale correlato viene indicata nei metadati del servizio dati dall'attributo `HasStream` applicato a un tipo di entità che è la voce di collegamento multimediale. Nell'esempio seguente, l'entità `PhotoInfo` è una voce di collegamento multimediale con una risorsa multimediale correlata, indicata dall'attributo `HasStream`.

[!code-xml[Astoria Photo Streaming Service#HasStream](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_photo_streaming_service/xml/photodata.edmx#hasstream)]

Negli esempi restanti di questo argomento viene illustrato come accedere e modificare il flusso di risorsa multimediale. Per un esempio completo su come usare un flusso di risorse multimediali in un'applicazione client di .NET Framework usando la libreria client di WCF Data Services, vedere l'articolo relativo all' [accesso a un flusso di risorse multimediali dal client](https://docs.microsoft.com/archive/blogs/astoriateam/data-services-streaming-provider-series-part-2-accessing-a-media-resource-stream-from-the-client).

## <a name="accessing-the-binary-resource-stream"></a>Accesso al flusso di risorsa binaria

La libreria client di WCF Data Services fornisce metodi per l'accesso ai flussi di risorse binarie da un servizio dati basato su OData. Quando si scarica una risorsa multimediale, è possibile usare l'URI della risorsa multimediale od ottenere un flusso binario contenente i dati della risorsa multimediale. È possibile caricare i dati della risorsa multimediale anche come un flusso binario.

> [!TIP]
> Per un esempio dettagliato di come creare un'applicazione client Windows Presentation Foundation (WPF) che Scarica i file di immagine binari da un servizio OData che archivia le foto, vedere la [serie Post Data Services Streaming provider-parte 2: accesso a un flusso di risorse multimediali dal client](https://docs.microsoft.com/archive/blogs/astoriateam/data-services-streaming-provider-series-part-2-accessing-a-media-resource-stream-from-the-client). Per scaricare il codice di esempio per il servizio dati di foto di flusso in evidenza nel post di Blog, vedere l' [esempio streaming Photo Data Service](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/Streaming%20Photo%20OData%20Service%20Sample) in GitHub.

### <a name="getting-the-uri-of-the-binary-stream"></a>Recupero dell'URI del flusso binario

Quando si recuperano determinati tipi di risorse multimediali, ad esempio immagini e altri file multimediali, è spesso più semplice usare l'URI della risorsa multimediale nell'applicazione anziché gestire il flusso di dati binari. Per ottenere l'URI di un flusso di risorsa associato a una data voce di collegamento multimediale, è necessario chiamare il metodo <xref:System.Data.Services.Client.DataServiceContext.GetReadStreamUri%2A> sull'istanza <xref:System.Data.Services.Client.DataServiceContext> che tiene traccia dell'entità. Nell'esempio seguente viene mostrato come chiamare il metodo <xref:System.Data.Services.Client.DataServiceContext.GetReadStreamUri%2A> per ottenere l'URI di un flusso di risorsa multimediale usato per creare una nuova immagine nel client:

[!code-csharp[Astoria Photo Streaming Client#GetReadStreamUri](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_photo_streaming_client/cs/photowindow.xaml.cs#getreadstreamuri)]
[!code-vb[Astoria Photo Streaming Client#GetReadStreamUri](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_photo_streaming_client/vb/photowindow.xaml.vb#getreadstreamuri)]

### <a name="downloading-the-binary-resource-stream"></a>Download del flusso di risorsa binaria

Quando si recupera un flusso di risorsa binaria, è necessario chiamare il metodo <xref:System.Data.Services.Client.DataServiceContext.GetReadStream%2A> sull'istanza di <xref:System.Data.Services.Client.DataServiceContext> che tiene traccia della voce di collegamento multimediale. Questo metodo invia una richiesta al servizio dati che restituisce un oggetto <xref:System.Data.Services.Client.DataServiceStreamResponse> che presenta un riferimento al flusso contenente la risorsa. Usare questo metodo quando l'applicazione richiede la risorsa binaria come <xref:System.IO.Stream>. Nell'esempio seguente viene mostrato come chiamare il metodo <xref:System.Data.Services.Client.DataServiceContext.GetReadStream%2A> per recuperare un flusso usato per creare una nuova immagine nel client:

[!code-csharp[Astoria Streaming Client#GetReadStreamClient](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_streaming_client/cs/customerphotowindow.xaml.cs#getreadstreamclient)]
[!code-vb[Astoria Streaming Client#GetReadStreamClient](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_streaming_client/vb/customerphotowindow.xaml.vb#getreadstreamclient)]

> [!NOTE]
> L'intestazione Content-Length nel messaggio di risposta che contiene il flusso binario non è impostata dal servizio dati. È possibile che questo valore non rifletta la lunghezza effettiva del flusso di dati binari.

### <a name="uploading-a-media-resource-as-a-stream"></a>Caricamento di una risorsa multimediale come flusso

Per inserire o aggiornare una risorsa multimediale, chiamare il metodo <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A> sull'istanza <xref:System.Data.Services.Client.DataServiceContext> che tiene traccia dell'entità. Questo metodo invia una richiesta al servizio dati che contiene la risorsa multimediale letta dal flusso fornito. Nell'esempio seguente viene indicato come chiamare il metodo <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A> per inviare un'immagine al servizio dati:

[!code-csharp[Astoria Photo Streaming Client#SetSaveStream](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_photo_streaming_client/cs/photodetailswindow.xaml.cs#setsavestream)]
[!code-vb[Astoria Photo Streaming Client#SetSaveStream](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_photo_streaming_client/vb/photodetailswindow.xaml.vb#setsavestream)]

In questo esempio il metodo <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A> viene chiamato fornendo un valore `true` per il parametro `closeStream`. Ciò garantisce che <xref:System.Data.Services.Client.DataServiceContext> chiuda il flusso dopo aver caricato i dati binari nel servizio dati.

> [!NOTE]
> Quando si chiama <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A>, il flusso non viene inviato al servizio dati fino a quando non viene chiamato il metodo <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.

## <a name="see-also"></a>Vedere anche

- [Libreria client WCF Data Services](wcf-data-services-client-library.md)
- [Associazione di dati a controlli](binding-data-to-controls-wcf-data-services.md)
