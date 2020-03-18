---
title: Utilizzo di un oggetto di stato e di un delegato AsyncCallback
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- asynchronous programming, delegates
- AsyncCallback delegate, samples
- asynchronous programming, state objects
- IAsyncResult interface, samples
ms.assetid: e3e5475d-c5e9-43f0-928e-d18df8ca1f1d
ms.openlocfilehash: c7bd0a7606b5f93289cf39d33794457265e7e453
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73094599"
---
# <a name="using-an-asynccallback-delegate-and-state-object"></a>Utilizzo di un oggetto di stato e di un delegato AsyncCallback
Quando si usa un delegato <xref:System.AsyncCallback> per elaborare i risultati dell'operazione asincrona in un thread separato, è possibile usare un oggetto di stato per passare le informazioni tra i metodi di callback e per recuperare un risultato finale. In questo argomento viene illustrata tale pratica analizzando ulteriormente l'esempio descritto in [Uso di un delegato AsyncCallback per terminare un'operazione asincrona](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene illustrato come usare metodi asincroni nella classe <xref:System.Net.Dns> per recuperare le informazioni sul DNS (Domain Name System) per i computer specificati dall'utente. Questo esempio definisce e usa la classe `HostRequest` per archiviare le informazioni sullo stato. Viene creato l'oggetto `HostRequest` per ogni nome computer immesso dall'utente. Questo oggetto viene passato al metodo <xref:System.Net.Dns.BeginGetHostByName%2A>. Il metodo `ProcessDnsInformation` viene chiamato ogni volta che viene completata una richiesta. L'oggetto `HostRequest` viene recuperato tramite la proprietà <xref:System.IAsyncResult.AsyncState%2A>. Il metodo `ProcessDnsInformation` usa l'oggetto `HostRequest` per archiviare l'oggetto <xref:System.Net.IPHostEntry> restituito dalla richiesta o un'eccezione <xref:System.Net.Sockets.SocketException> generata dalla richiesta. Al completamento di tutte le richieste, l'applicazione scorre gli oggetti `HostRequest` e visualizza le informazioni DNS o il messaggio di errore <xref:System.Net.Sockets.SocketException>.  
  
 [!code-csharp[AsyncDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateWithStateObject.cs#5)]
 [!code-vb[AsyncDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateWithStateObject.vb#5)]  
  
## <a name="see-also"></a>Vedere anche

- [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi, EAP)
- [Cenni preliminari sul modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [Utilizzo di un delegato AsyncCallback per terminare un'operazione asincrona](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)
