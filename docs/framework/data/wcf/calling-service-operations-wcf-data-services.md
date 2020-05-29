---
title: Operazioni del servizio di chiamata (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1767f3a7-29d2-4834-a763-7d169693fa8b
ms.openlocfilehash: f1ff707c90e884dc66ab10563dc41ea7789f5cda
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202015"
---
# <a name="calling-service-operations-wcf-data-services"></a>Operazioni del servizio di chiamata (WCF Data Services)
Il Open Data Protocol (OData) definisce le operazioni del servizio per un servizio dati. WCF Data Services consente di definire tali operazioni come metodi nel servizio dati. Allo stesso modo di altre risorse del servizio dati, queste operazioni del servizio vengono indirizzate mediante URI. Un'operazione del servizio può restituire raccolte di tipi di entità, singole istanze del tipo di entità e tipi primitivi, ad esempio Integer e stringa. Un'operazione del servizio può restituire anche `null` (`Nothing` in Visual Basic). La libreria client di WCF Data Services può essere usata per accedere alle operazioni del servizio che supportano richieste HTTP GET. Questi tipi di operazioni del servizio sono definiti come metodi a cui vengono applicati oggetti <xref:System.ServiceModel.Web.WebGetAttribute>. Per altre informazioni, vedere [operazioni del servizio](service-operations-wcf-data-services.md).  
  
 Le operazioni del servizio sono esposte nei metadati restituiti da un servizio dati che implementa OData. Nei metadati le operazioni del servizio vengono rappresentate come elementi `FunctionImport`. Quando si genera la fortemente tipizzata <xref:System.Data.Services.Client.DataServiceContext> , gli strumenti Aggiungi riferimento al servizio e DataSvcUtil. exe ignorano questo elemento. Per questo motivo, nel contesto non sarà disponibile alcun metodo che consenta di chiamare direttamente un'operazione di servizio. Tuttavia, è comunque possibile usare il client WCF Data Services per chiamare le operazioni del servizio in uno dei due modi seguenti:  
  
- Chiamare il metodo <xref:System.Data.Services.Client.DataServiceContext.Execute%2A> su <xref:System.Data.Services.Client.DataServiceContext>, fornendo l'URI dell'operazione del servizio ed eventuali parametri. Questo metodo è usato per chiamare qualsiasi operazione del servizio GET.  
  
- Usare il metodo <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> su <xref:System.Data.Services.Client.DataServiceContext> per creare un oggetto <xref:System.Data.Services.Client.DataServiceQuery%601>. Quando si chiama <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A>, il nome dell'operazione di servizio viene fornito al parametro `entitySetName`. Questo metodo restituisce un oggetto <xref:System.Data.Services.Client.DataServiceQuery%601> che chiama l'operazione di servizio in caso di enumerazione o quando viene chiamato il metodo <xref:System.Data.Services.Client.DataServiceQuery%601.Execute%2A>. Questo metodo viene usato per chiamare operazioni di servizio GET che restituiscono una raccolta. Tramite il metodo <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> è possibile fornire un singolo parametro. L'oggetto <xref:System.Data.Services.Client.DataServiceQuery%601> restituito da questo metodo può essere ulteriormente composto come qualsiasi oggetto query. Per ulteriori informazioni, vedere [esecuzione di query sul servizio dati](querying-the-data-service-wcf-data-services.md).  
  
## <a name="considerations-for-calling-service-operations"></a>Considerazioni per la chiamata di operazioni del servizio  
 Quando si utilizza il client WCF Data Services per chiamare le operazioni del servizio, è necessario tenere presenti le considerazioni seguenti.  
  
- Quando si accede al servizio dati in modo asincrono, è necessario utilizzare i metodi asincroni equivalenti <xref:System.Data.Services.Client.DataServiceContext.BeginExecute%2A> / <xref:System.Data.Services.Client.DataServiceContext.EndExecute%2A> su <xref:System.Data.Services.Client.DataServiceContext> o sui <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> / <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> metodi in <xref:System.Data.Services.Client.DataServiceQuery%601> .  
  
- La libreria client di WCF Data Services non è in grado di materializzare i risultati di un'operazione del servizio che restituisce una raccolta di tipi primitivi.  
  
- La libreria client di WCF Data Services non supporta la chiamata di operazioni del servizio POST. Operazioni del servizio chiamate da HTTP POST sono definite tramite <xref:System.ServiceModel.Web.WebInvokeAttribute> con il parametro `Method="POST"`. Per chiamare un'operazione del servizio tramite una richiesta HTTP POST, è necessario usare un oggetto <xref:System.Net.HttpWebRequest>.  
  
- Non è possibile usare <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> per chiamare un'operazione del servizio GET che restituisca un solo risultato, sia di tipo entità che primitivo, o che richieda più di un parametro di input. È necessario chiamare invece il metodo <xref:System.Data.Services.Client.DataServiceContext.Execute%2A>.  
  
- Provare a creare un metodo di estensione sulla classe parziale fortemente tipizzata <xref:System.Data.Services.Client.DataServiceContext> , generata dagli strumenti, che usa il <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> <xref:System.Data.Services.Client.DataServiceContext.Execute%2A> metodo o per chiamare un'operazione del servizio. In questo modo è possibile chiamare operazioni di servizio direttamente dal contesto. Per ulteriori informazioni, vedere le operazioni del servizio post di Blog [e il Client WCF Data Services](https://docs.microsoft.com/archive/blogs/astoriateam/service-operations-and-the-wcf-data-services-client).  
  
- Quando si usa <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> per chiamare un'operazione del servizio, la libreria client esegue automaticamente l'escape dei caratteri forniti al <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> eseguendo la codifica percentuale di caratteri riservati, ad esempio la e commerciale (&), e l'escape delle virgolette singole nelle stringhe. Tuttavia, quando si chiama uno dei metodi *Execute* per chiamare un'operazione del servizio, è necessario ricordare di eseguire l'escape di qualsiasi valore stringa fornito dall'utente. Per le virgolette singole negli URI vengono usati come caratteri di escape coppie di virgolette singole.  
  
## <a name="examples-of-calling-service-operations"></a>Esempi di chiamata di operazioni di servizio  
 Questa sezione contiene gli esempi seguenti di come chiamare le operazioni del servizio usando la libreria client di WCF Data Services:  
  
- [Chiamata di Execute &lt; T &gt; per restituire una raccolta di entità](calling-service-operations-wcf-data-services.md#ExecuteIQueryable)  
  
- [Utilizzo di CreateQuery &lt; T &gt; per restituire una raccolta di entità](calling-service-operations-wcf-data-services.md#CreateQueryIQueryable)  
  
- [Chiamata &lt; di Execute T &gt; per restituire una singola entità](calling-service-operations-wcf-data-services.md#ExecuteSingleEntity)  
  
- [Chiamata di Execute &lt; T &gt; per restituire una raccolta di valori primitivi](calling-service-operations-wcf-data-services.md#ExecutePrimitiveCollection)  
  
- [Chiamata &lt; di Execute T &gt; per restituire un singolo valore primitivo](calling-service-operations-wcf-data-services.md#ExecutePrimitiveValue)  
  
- [Chiamata di un'operazione di servizio che non restituisce dati](calling-service-operations-wcf-data-services.md#ExecuteVoid)  
  
- [Chiamata di un'operazione di servizio in modo asincrono](calling-service-operations-wcf-data-services.md#ExecuteAsync)  
  
<a name="ExecuteIQueryable"></a>
### <a name="calling-executet-to-return-a-collection-of-entities"></a>Chiamata di Execute \<T> per restituire una raccolta di entità  
 Nell'esempio seguente viene chiamata un'operazione di servizio denominata GetOrdersByCity che accetta un parametro stringa `city` e restituisce un oggetto <xref:System.Linq.IQueryable%601>:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationIQueryable](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationiqueryable)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationIQueryable](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationiqueryable)]  
  
 In questo esempio l'operazione di servizio restituisce una raccolta di oggetti `Order` con oggetti `Order_Detail` correlati.  
  
<a name="CreateQueryIQueryable"></a>
### <a name="using-createqueryt-to-return-a-collection-of-entities"></a>Utilizzo \<T> di CreateQuery per restituire una raccolta di entità  
 Nell'esempio seguente viene usato <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> per restituire un oggetto <xref:System.Data.Services.Client.DataServiceQuery%601> usato per chiamare la stessa operazione di servizio GetOrdersByCity:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationCreateQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationcreatequery)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationCreateQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationcreatequery)]  
  
 In questo esempio il metodo <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> viene usato per aggiungere il parametro alla query, mentre il metodo <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> viene usato per includere oggetti Order_Details correlati nei risultati.  
  
<a name="ExecuteSingleEntity"></a>
### <a name="calling-executet-to-return-a-single-entity"></a>Chiamata \<T> di Execute per restituire una singola entità  
 Nell'esempio seguente viene chiamata un'operazione di servizio denominata GetNewestOrder che restituisce solo un'entità Order singola:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationSingleEntity](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationsingleentity)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationSingleEntity](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationsingleentity)]  
  
 In questo esempio il metodo <xref:System.Linq.Enumerable.FirstOrDefault%2A> viene usato per richiedere solo un'entità Order singola durante l'esecuzione.  
  
<a name="ExecutePrimitiveCollection"></a>
### <a name="calling-executet-to-return-a-collection-of-primitive-values"></a>Chiamata \<T> di Execute per restituire una raccolta di valori primitivi  
 Nell'esempio seguente viene chiamata un'operazione di servizio che restituisce una raccolta di valori stringa:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationEnumString](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationenumstring)]  
  
<a name="ExecutePrimitiveValue"></a>
### <a name="calling-executet-to-return-a-single-primitive-value"></a>Chiamata \<T> di Execute per restituire un singolo valore primitivo  
 Nell'esempio seguente viene chiamata un'operazione di servizio che restituisce un valore stringa singolo:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationSingleInt](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationsingleint)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationSingleInt](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationsingleint)]  
  
 In questo esempio il metodo <xref:System.Linq.Enumerable.FirstOrDefault%2A> viene usato per richiedere solo un valore Integer singolo durante l'esecuzione.  
  
<a name="ExecuteVoid"></a>
### <a name="calling-a-service-operation-that-returns-no-data"></a>Chiamata di un'operazione di servizio che non restituisce dati  
 Nell'esempio seguente viene chiamata un'operazione di servizio che non restituisce dati:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationVoid](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationvoid)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationVoid](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationvoid)]  
  
 Poiché non vengono restituiti dati, il valore dell'esecuzione non viene assegnato. L'unica indicazione relativa all'esito positivo della richiesta è la mancata generazione di un'eccezione <xref:System.Data.Services.Client.DataServiceQueryException>.  
  
<a name="ExecuteAsync"></a>
### <a name="calling-a-service-operation-asynchronously"></a>Chiamata di un'operazione di servizio in modo asincrono  
 Nell'esempio seguente viene chiamata un'operazione di servizio in modo asincrono tramite <xref:System.Data.Services.Client.DataServiceContext.BeginExecute%2A> e <xref:System.Data.Services.Client.DataServiceContext.EndExecute%2A>:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationasync)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationasync)]  
  
 [!code-csharp[Astoria Northwind Client#OnAsyncExecutionComplete](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#onasyncexecutioncomplete)]
 [!code-vb[Astoria Northwind Client#OnAsyncExecutionComplete](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#onasyncexecutioncomplete)]  
  
 Poiché non vengono restituiti dati, il valore restituito dell'esecuzione non viene assegnato. L'unica indicazione relativa all'esito positivo della richiesta è la mancata generazione di un'eccezione <xref:System.Data.Services.Client.DataServiceQueryException>.  
  
 Nell'esempio seguente viene chiamata la stessa operazione di servizio in modo asincrono tramite <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A>:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationQueryAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationqueryasync)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationQueryAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationqueryasync)]  
  
 [!code-csharp[Astoria Northwind Client#OnAsyncQueryExecutionComplete](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#onasyncqueryexecutioncomplete)]
 [!code-vb[Astoria Northwind Client#OnAsyncQueryExecutionComplete](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#onasyncqueryexecutioncomplete)]  
  
## <a name="see-also"></a>Vedere anche

- [Libreria client WCF Data Services](wcf-data-services-client-library.md)
