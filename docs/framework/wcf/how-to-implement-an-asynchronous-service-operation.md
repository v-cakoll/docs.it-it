---
title: 'Procedura: implementare un''operazione del servizio asincrona'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 4e5d2ea5-d8f8-4712-bd18-ea3c5461702c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 276dd3cc84c15c66adeab30f86583e6d9eec4144
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-an-asynchronous-service-operation"></a>Procedura: implementare un'operazione del servizio asincrona
Nelle applicazioni [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], un'operazione del servizio può essere implementata in modo sincrono o asincrono senza imporre al client la modalità di chiamata. È possibile, ad esempio, che operazioni del servizio asincrone vengano chiamate in modo sincrono e che operazioni del servizio sincrone vengano chiamate in modo asincrono. Per un esempio che illustra come chiamare un'operazione in modo asincrono in un'applicazione client, vedere [procedura: chiamare servizio operazioni in modo asincrono](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md). [!INCLUDE[crabout](../../../includes/crabout-md.md)]operazioni sincrone e asincrone, vedere [progettazione contratti di servizio](../../../docs/framework/wcf/designing-service-contracts.md) e [sincrono e alle operazioni asincrone](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md). In questo argomento viene descritta la struttura di base di un'operazione del servizio asincrona (il codice non è completo). Per un esempio completo di lati client e servizio vedere [asincrono](http://msdn.microsoft.com/en-us/833db946-f511-4f64-a26f-2759a11217c7).  
  
### <a name="implement-a-service-operation-asynchronously"></a>Implementazione di un'operazione del servizio in modo asincrono  
  
1.  Nel contratto di servizio, dichiarare una coppia di metodi asincroni in base alle linee guida di progettazione asincrona .NET. Il metodo `Begin` prende un parametro, un oggetto callback e un oggetto di stato e restituisce un <xref:System.IAsyncResult?displayProperty=nameWithType> e un metodo `End` corrispondente che prende un <xref:System.IAsyncResult?displayProperty=nameWithType> e restituisce il valore restituito. Per ulteriori informazioni sulle chiamate asincrone, vedere [Asynchronous Programming Design Patterns](http://go.microsoft.com/fwlink/?LinkId=248221).  
  
2.  Contrassegnare il metodo `Begin` della coppia di metodi asincroni con l'attributo <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType> e impostare la proprietà <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A?displayProperty=nameWithType> su `true`. Nel codice seguente, ad esempio, vengono eseguiti i passaggi 1 e 2.  
  
     [!code-csharp[C_SyncAsyncClient#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#6)]
     [!code-vb[C_SyncAsyncClient#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#6)]  
  
3.  Implementare la coppia di metodi `Begin/End` nella classe del servizio in base alle linee guida di progettazione asincrona. Nell'esempio di codice seguente viene illustrata un'implementazione nella quale una stringa viene scritta nella console sia nella parte `Begin` che nella parte `End` dell'operazione del servizio asincrona e viene restituito al client il valore restituito dell'operazione `End`. Per un esempio completo di codice, vedere la sezione degli esempi.  
  
     [!code-csharp[C_SyncAsyncClient#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#3)]
     [!code-vb[C_SyncAsyncClient#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#3)]  
  
## <a name="example"></a>Esempio  
 Negli esempi di codice seguenti viene illustrato:  
  
1.  Un'interfaccia del contratto di servizio con:  
  
    1.  Un'operazione `SampleMethod` sincrona.  
  
    2.  Un'operazione `BeginSampleMethod` asincrona.  
  
    3.  Asincrono `BeginServiceAsyncMethod` / `EndServiceAsyncMethod` coppia di operazioni.  
  
2.  Un'implementazione del servizio tramite un oggetto <xref:System.IAsyncResult?displayProperty=nameWithType>.  
  
 [!code-csharp[C_SyncAsyncClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#1)]
 [!code-vb[C_SyncAsyncClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 [Progettazione dei contratti di servizio](../../../docs/framework/wcf/designing-service-contracts.md)  
 [Operazioni sincrone e asincrone](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md)
