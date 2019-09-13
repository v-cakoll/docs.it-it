---
title: 'Procedura: Chiamare le operazioni del servizio WCF in modo asincrono'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
ms.openlocfilehash: 2c0a6f1477ceec5471c22fa3e46d85f5856b298e
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895071"
---
# <a name="how-to-call-wcf-service-operations-asynchronously"></a>Procedura: Chiamare le operazioni del servizio WCF in modo asincrono
In questo argomento viene illustrato come un client può accedere a un'operazione del servizio in modo asincrono. Il servizio in questo argomento implementa l'interfaccia `ICalculator`. Il client può chiamare le operazioni in questa interfaccia in modo asincrono utilizzando il modello di chiamata asincrono basato su eventi. Per ulteriori informazioni sul modello di chiamata asincrono basato su eventi, vedere [programmazione multithreading con il modello asincrono basato su eventi](https://go.microsoft.com/fwlink/?LinkId=248184). Per un esempio in cui viene illustrato come implementare un'operazione in modo asincrono in un servizio [, vedere Procedura: Implementare un'operazione](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)del servizio asincrona. Per altre informazioni sulle operazioni sincrone e asincrone, vedere [operazioni sincrone e asincrone](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).  
  
> [!NOTE]
> Il modello di chiamata asincrono basato su eventi non è supportato quando si utilizza una classe <xref:System.ServiceModel.ChannelFactory%601>. Per informazioni sull'esecuzione di chiamate asincrone mediante <xref:System.ServiceModel.ChannelFactory%601>, vedere [procedura: Chiamare le operazioni in modo asincrono utilizzando una](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md)Channel factory.  
  
## <a name="procedure"></a>Routine  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a>Per chiamare operazioni del servizio WCF in modo asincrono  
  
1. Eseguire lo strumento [ServiceModel Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) con le `/async` opzioni e del `/tcv:Version35` comando insieme, come illustrato nel comando seguente.  
  
    ```console
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     Questo genera, oltre alle operazioni asincrone basate su delegati sincroni e standard, una classe client WCF che contiene:  
  
    - Due <`operationName` > operazionidautilizzareconl'approcciodichiamataasincrono`Async` basato su eventi. Ad esempio:  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    - Gli eventi completati dell'operazione nel`operationName` form <> `Completed` per l'uso con l'approccio di chiamata asincrono basato su eventi. Ad esempio:  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    - <xref:System.EventArgs?displayProperty=nameWithType>tipi per ogni operazione (nel formato <`operationName`>`CompletedEventArgs`) da utilizzare con l'approccio di chiamata asincrono basato su eventi. Ad esempio:  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2. Nell'applicazione chiamante creare un metodo di callback da chiamare al temine dell'operazione asincrona, come illustrato nel codice di esempio seguente.  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3. Prima di chiamare l'operazione, usare un nuovo oggetto <xref:System.EventHandler%601?displayProperty=nameWithType> generico di tipo`operationName` <`Completed` > `EventArgs` per aggiungere il metodo del gestore (creato nel passaggio precedente) all'evento`operationName` <> . Chiamare quindi il metodo`operationName` <> `Async` . Ad esempio:  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## <a name="example"></a>Esempio  
  
> [!NOTE]
> Le linee guida di progettazione per il modello asincrono basato su eventi indicano che, se vengono restituiti più valori, un valore viene restituito come proprietà `Result` e i restanti valori sono restituiti come proprietà nell’oggetto <xref:System.EventArgs>. Di conseguenza, è possibile che, se un client importa metadati utilizzando le opzioni di comando asincrone basate su eventi e l'operazione restituisce più valori, l'oggetto predefinito <xref:System.EventArgs> restituisce un valore come proprietà `Result` e i restanti valori come proprietà dell’oggetto <xref:System.EventArgs>. Se si desidera ricevere l’oggetto del messaggio come proprietà `Result` e i valori restituiti come proprietà in quell’oggetto, utilizzare l’opzione di comando `/messageContract`. Questa operazione genera una firma che restituisce il messaggio di risposta come proprietà `Result` nell’oggetto <xref:System.EventArgs>. Pertanto, tutti i valori restituiti interni sono proprietà dell’oggetto del messaggio di risposta.  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Implementare un'operazione del servizio asincrona](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)
