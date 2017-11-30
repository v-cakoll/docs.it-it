---
title: Utilizzo di un oggetto di stato e di un delegato AsyncCallback
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- asynchronous programming, delegates
- AsyncCallback delegate, samples
- asynchronous programming, state objects
- IAsyncResult interface, samples
ms.assetid: e3e5475d-c5e9-43f0-928e-d18df8ca1f1d
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e8793a78289e9b58407038f41cc9d403ff9f9940
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="using-an-asynccallback-delegate-and-state-object"></a>Utilizzo di un oggetto di stato e di un delegato AsyncCallback
Quando si utilizza un <xref:System.AsyncCallback> delegato per elaborare i risultati dell'operazione asincrona in un thread separato, è possibile utilizzare un oggetto di stato per passare informazioni tra i metodi di callback e per recuperare un risultato finale. In questo argomento viene illustrato tale pratica espandendo l'esempio in [tramite un delegato AsyncCallback per terminare un'operazione asincrona](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente viene illustrato come utilizzare metodi asincroni nel <xref:System.Net.Dns> classe per recuperare le informazioni di sistema DNS (Domain Name) per i computer specificati dall'utente. In questo esempio viene definito e viene utilizzata la `HostRequest` classe per archiviare le informazioni sullo stato. Oggetto `HostRequest` viene creato l'oggetto per ogni nome computer immesso dall'utente. Questo oggetto viene passato per il <xref:System.Net.Dns.BeginGetHostByName%2A> metodo. Il `ProcessDnsInformation` metodo viene chiamato ogni volta che viene completata una richiesta. Il `HostRequest` oggetto viene recuperato utilizzando il <xref:System.IAsyncResult.AsyncState%2A> proprietà. Il `ProcessDnsInformation` metodo utilizza il `HostRequest` oggetto usato per archiviare il <xref:System.Net.IPHostEntry> restituito dalla richiesta o una <xref:System.Net.Sockets.SocketException> generata dalla richiesta. Una volta completate tutte le richieste, l'applicazione scorre il `HostRequest` oggetti e visualizza le informazioni DNS o <xref:System.Net.Sockets.SocketException> messaggio di errore.  
  
 [!code-csharp[AsyncDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateWithStateObject.cs#5)]
 [!code-vb[AsyncDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateWithStateObject.vb#5)]  
  
## <a name="see-also"></a>Vedere anche  
 [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi)  
 [Panoramica sul modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [Uso di un delegato AsyncCallback per terminare un'operazione asincrona](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)
