---
title: "Procedura: implementare un'operazione del servizio asincrona"
description: Informazioni sulla struttura di un'operazione asincrona del servizio in WFC. Un'operazione del servizio può essere implementata in modo asincrono o sincrono.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e5d2ea5-d8f8-4712-bd18-ea3c5461702c
ms.openlocfilehash: 5f890bd5124e2353cecee37d163b7f2c65b87fde
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244621"
---
# <a name="how-to-implement-an-asynchronous-service-operation"></a>Procedura: implementare un'operazione del servizio asincrona
Nelle applicazioni Windows Communication Foundation (WCF) un'operazione del servizio può essere implementata in modo asincrono o sincrono senza che venga dettata la modalità di chiamata del client. Ad esempio, le operazioni asincrone del servizio possono essere chiamate in modo sincrono e le operazioni sincrone del servizio possono essere chiamate in modo asincrono. Per un esempio in cui viene illustrato come chiamare un'operazione in modo asincrono in un'applicazione client, vedere [procedura: chiamare operazioni del servizio in modo asincrono](./feature-details/how-to-call-wcf-service-operations-asynchronously.md). Per ulteriori informazioni sulle operazioni sincrone e asincrone, vedere [progettazione di contratti di servizio](designing-service-contracts.md) e [operazioni sincrone e asincrone](synchronous-and-asynchronous-operations.md). In questo argomento viene descritta la struttura di base di un'operazione del servizio asincrona (il codice non è completo). Per un esempio completo del lato client e del servizio, vedere [asincrono](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms751505(v=vs.100)).  
  
### <a name="implement-a-service-operation-asynchronously"></a>Implementazione di un'operazione del servizio in modo asincrono  
  
1. Nel contratto di servizio, dichiarare una coppia di metodi asincroni in base alle linee guida di progettazione asincrona .NET. Il metodo `Begin` prende un parametro, un oggetto callback e un oggetto di stato e restituisce un <xref:System.IAsyncResult?displayProperty=nameWithType> e un metodo `End` corrispondente che prende un <xref:System.IAsyncResult?displayProperty=nameWithType> e restituisce il valore restituito. Per ulteriori informazioni sulle chiamate asincrone, vedere [modelli di progettazione della programmazione asincrona](../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).  
  
2. Contrassegnare il metodo `Begin` della coppia di metodi asincroni con l'attributo <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType> e impostare la proprietà <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A?displayProperty=nameWithType> su `true`. Nel codice seguente, ad esempio, vengono eseguiti i passaggi 1 e 2.  
  
     [!code-csharp[C_SyncAsyncClient#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#6)]
     [!code-vb[C_SyncAsyncClient#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#6)]  
  
3. Implementare la coppia di metodi `Begin/End` nella classe del servizio in base alle linee guida di progettazione asincrona. Nell'esempio di codice seguente viene illustrata un'implementazione nella quale una stringa viene scritta nella console sia nella parte `Begin` che nella parte `End` dell'operazione del servizio asincrona e viene restituito al client il valore restituito dell'operazione `End`. Per un esempio completo di codice, vedere la sezione degli esempi.  
  
     [!code-csharp[C_SyncAsyncClient#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#3)]
     [!code-vb[C_SyncAsyncClient#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#3)]  
  
## <a name="example"></a>Esempio  
 Negli esempi di codice seguenti viene illustrato:  
  
1. Un'interfaccia del contratto di servizio con:  
  
    1. Un'operazione `SampleMethod` sincrona.  
  
    2. Un'operazione `BeginSampleMethod` asincrona.  
  
    3. Coppia di `BeginServiceAsyncMethod` / `EndServiceAsyncMethod` operazioni asincrone.  
  
2. Un'implementazione del servizio tramite un oggetto <xref:System.IAsyncResult?displayProperty=nameWithType>.  
  
 [!code-csharp[C_SyncAsyncClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#1)]
 [!code-vb[C_SyncAsyncClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Progettazione dei contratti di servizio](designing-service-contracts.md)
- [Operazioni sincrone e asincrone](synchronous-and-asynchronous-operations.md)
