---
title: 'Procedura: chiamare le operazioni in modo asincrono tramite una channel factory'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cc17dd47-b9ad-451c-a362-e36e0aac7ba0
ms.openlocfilehash: 25d88b00e0bb1105be57989ff5d090a308177329
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601270"
---
# <a name="how-to-call-operations-asynchronously-using-a-channel-factory"></a>Procedura: chiamare le operazioni in modo asincrono tramite una channel factory
In questo argomento viene illustrato in che modo un client può accedere a un'operazione del servizio in modalità asincrona quando si usa un'applicazione client basata su <xref:System.ServiceModel.ChannelFactory%601>. Quando si usa un oggetto <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> per richiamare un servizio, è possibile usare il modello di chiamata asincrono basato su eventi. Per altre informazioni, vedere [procedura: chiamare operazioni del servizio in modo asincrono](how-to-call-wcf-service-operations-asynchronously.md). Per ulteriori informazioni sul modello di chiamata asincrono basato su eventi, vedere [modello asincrono basato su eventi (EAP)](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).  
  
 Il servizio in questo argomento implementa l'interfaccia `ICalculator`. Il client può chiamare in modo asincrono le operazioni su tale interfaccia, il che significa che le operazioni come `Add` vengono suddivise in due metodi, `BeginAdd` ed `EndAdd`, il primo dei quali avvia la chiamata e il secondo recupera il risultato al termine dell'operazione. Per un esempio che illustra come implementare un'operazione in modo asincrono in un servizio, vedere [procedura: implementare un'operazione del servizio asincrona](../how-to-implement-an-asynchronous-service-operation.md). Per informazioni dettagliate sulle operazioni sincrone e asincrone, vedere [operazioni sincrone e asincrone](../synchronous-and-asynchronous-operations.md).  
  
## <a name="procedure"></a>Procedura  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a>Per chiamare operazioni del servizio WCF in modo asincrono  
  
1. Eseguire lo strumento [ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) con l' `/async` opzione, come illustrato nel comando seguente.  
  
    ```console
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a  
    ```  
  
     Questo genera una versione client asincrona del contratto di servizio per l'operazione.  
  
2. Creare una funzione di callback da chiamare al temine dell'operazione asincrona, come illustrato nel codice di esempio seguente.  
  
     [!code-csharp[C_How_To_CF_Async#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/client.cs#2)]
     [!code-vb[C_How_To_CF_Async#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/client.vb#2)]  
  
3. Per accedere in modo asincrono a un'operazione del servizio, creare il client, chiamare `Begin[Operation]` (ad esempio, `BeginAdd`) e specificare una funzione di callback, come illustrato nel codice di esempio seguente.  
  
     [!code-csharp[C_How_To_CF_Async#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/client.cs#3)]
     [!code-vb[C_How_To_CF_Async#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/client.vb#3)]  
  
     Quando la funzione di callback viene eseguita, il client chiama `End<operation>``EndAdd` (ad esempio, ) per recuperare il risultato.  
  
## <a name="example"></a>Esempio  
 Il servizio usato con il codice client della procedura precedente implementa l'interfaccia `ICalculator` come illustrato nel codice seguente. Sul lato del servizio, le `Add` `Subtract` operazioni e del contratto vengono richiamate in modo sincrono dalla fase di esecuzione del Windows Communication Foundation (WCF), anche se i passaggi client precedenti vengono richiamati in modo asincrono nel client. Le operazioni `Multiply` e `Divide` vengono usate per richiamare il servizio in modo asincrono sul lato del servizio, anche se il client le richiama in modo sincrono. In questo esempio la proprietà <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> viene impostata su `true`. Questa impostazione della proprietà, in combinazione con l'implementazione del modello di .NET Framework asincrono, indica al runtime di richiamare l'operazione in modo asincrono.  
  
 [!code-csharp[C_How_To_CF_Async#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/service.cs#4)]
 [!code-vb[C_How_To_CF_Async#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/service.vb#4)]  
