---
title: Utilizzo di un delegato AsyncCallback per terminare un'operazione asincrona
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ending asynchronous operations
- asynchronous programming, ending operations
- AsyncCallback delegate
- stopping asynchronous operations
ms.assetid: 9d97206c-8917-406c-8961-7d0909d84eeb
ms.openlocfilehash: c3cac2db57a24bf6a0f5640e4ad8101686e6c3e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73130928"
---
# <a name="using-an-asynccallback-delegate-to-end-an-asynchronous-operation"></a>Utilizzo di un delegato AsyncCallback per terminare un'operazione asincrona
Le applicazioni che possono eseguire altre attività durante l'attesa dei risultati di un'operazione asincrona non devono bloccare lo stato di attesa fino al completamento dell'operazione. Usare una delle opzioni seguenti per continuare a eseguire le istruzioni durante l'attesa del completamento di un'operazione asincrona:  
  
- Usare un delegato <xref:System.AsyncCallback> per elaborare i risultati dell'operazione asincrona in un thread separato. Questo metodo viene dimostrato in questo argomento.  
  
- Utilizzare <xref:System.IAsyncResult.IsCompleted%2A> la proprietà <xref:System.IAsyncResult> dell'oggetto restituito dal metodo **Begin**_NomeOperazione_ dell'operazione asincrona per determinare se l'operazione è stata completata. Per un esempio che illustri questo approccio, vedere [Esecuzione del polling dello stato di un'operazione asincrona](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene illustrato come usare metodi asincroni nella classe <xref:System.Net.Dns> per recuperare le informazioni sul DNS (Domain Name System) per i computer specificati dall'utente. Questo esempio crea un delegato <xref:System.AsyncCallback> che fa riferimento al metodo `ProcessDnsInformation`. Questo metodo viene chiamato una volta per ogni richiesta asincrona per le informazioni DNS.  
  
 Si noti che l'host specificato dall'utente viene passato al parametro <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.Object>. Per un esempio che illustri la definizione e l'uso di un oggetto di stato più complesso, vedere [Uso di un oggetto di stato e di un delegato AsyncCallback](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md).  
  
 [!code-csharp[AsyncDesignPattern#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateNoStateObject.cs#4)]
 [!code-vb[AsyncDesignPattern#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateNoState.vb#4)]  
  
## <a name="see-also"></a>Vedere anche

- [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi, EAP)
- [Cenni preliminari sul modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [Chiamata di metodi asincroni tramite IAsyncResult](../../../docs/standard/asynchronous-programming-patterns/calling-asynchronous-methods-using-iasyncresult.md)
- [Utilizzo di un oggetto di stato e di un delegato AsyncCallback](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)
