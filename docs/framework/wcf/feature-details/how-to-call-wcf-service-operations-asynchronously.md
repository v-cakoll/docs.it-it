---
title: 'Procedura: Chiamare operazioni del servizio WCF in modo asincrono'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
ms.openlocfilehash: 2815757bf9b00375f763673f18180bfbf51a165a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59317447"
---
# <a name="how-to-call-wcf-service-operations-asynchronously"></a>Procedura: Chiamare operazioni del servizio WCF in modo asincrono
In questo argomento viene illustrato come un client può accedere a un'operazione del servizio in modo asincrono. Il servizio in questo argomento implementa l'interfaccia `ICalculator`. Il client può chiamare le operazioni in questa interfaccia in modo asincrono utilizzando il modello di chiamata asincrono basato su eventi. (Per altre informazioni sul modello di chiamata asincrono basato su eventi, vedere [programmazione multithreading con il modello asincrono basato su eventi](https://go.microsoft.com/fwlink/?LinkId=248184)). Per un esempio che illustra come implementare un'operazione in modo asincrono in un servizio, vedere [come: Implementare un'operazione del servizio asincrona](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md). Per altre informazioni sulle operazioni sincrone e asincrone, vedere [sincrono e alle operazioni asincrone](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).  
  
> [!NOTE]
>  Il modello di chiamata asincrono basato su eventi non è supportato quando si utilizza una classe <xref:System.ServiceModel.ChannelFactory%601>. Per informazioni sulle chiamate asincrone utilizzando il <xref:System.ServiceModel.ChannelFactory%601>, vedere [come: Chiamare le operazioni in modo asincrono usando una Channel Factory](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).  
  
## <a name="procedure"></a>Routine  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a>Per chiamare operazioni del servizio WCF in modo asincrono  
  
1. Eseguire la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) strumento sia con i `/async` e il `/tcv:Version35` opzioni di comando come illustrato nel comando seguente.  
  
    ```  
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     Questa operazione genera, oltre alle operazioni sincrone e standard basate su delegati asincroni, una classe client WCF che contiene:  
  
    -   Due <`operationName` > `Async` operazioni per l'uso con l'approccio di chiamata asincrono basato su eventi. Ad esempio:  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    -   Eventi completati dall'operazione del form <`operationName` > `Completed` per l'uso con l'approccio di chiamata asincrono basato su eventi. Ad esempio:  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    -   <xref:System.EventArgs?displayProperty=nameWithType> i tipi per ogni operazione (nel formato <`operationName`>`CompletedEventArgs`) per l'uso con l'approccio di chiamata asincrono basato su eventi. Ad esempio:  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2. Nell'applicazione chiamante creare un metodo di callback da chiamare al temine dell'operazione asincrona, come illustrato nel codice di esempio seguente.  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3. Prima di chiamare l'operazione, usare un nuovo oggetto generico <xref:System.EventHandler%601?displayProperty=nameWithType> di tipo <`operationName` > `EventArgs` per aggiungere il metodo del gestore (creato nel passaggio precedente) per la <`operationName` > `Completed` evento. Chiamare quindi il <`operationName` > `Async` (metodo). Ad esempio:  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## <a name="example"></a>Esempio  
  
> [!NOTE]
>  Le linee guida di progettazione per il modello asincrono basato su eventi indicano che, se vengono restituiti più valori, un valore viene restituito come proprietà `Result` e i restanti valori sono restituiti come proprietà nell’oggetto <xref:System.EventArgs>. Di conseguenza, è possibile che, se un client importa metadati utilizzando le opzioni di comando asincrone basate su eventi e l'operazione restituisce più valori, l'oggetto predefinito <xref:System.EventArgs> restituisce un valore come proprietà `Result` e i restanti valori come proprietà dell’oggetto <xref:System.EventArgs>. Se si desidera ricevere l’oggetto del messaggio come proprietà `Result` e i valori restituiti come proprietà in quell’oggetto, utilizzare l’opzione di comando `/messageContract`. Questa operazione genera una firma che restituisce il messaggio di risposta come proprietà `Result` nell’oggetto <xref:System.EventArgs>. Pertanto, tutti i valori restituiti interni sono proprietà dell’oggetto del messaggio di risposta.  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Implementare un'operazione del servizio asincrona](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)
