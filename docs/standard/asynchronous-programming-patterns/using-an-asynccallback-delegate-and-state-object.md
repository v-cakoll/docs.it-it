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
# <a name="using-an-asynccallback-delegate-and-state-object"></a><span data-ttu-id="d938b-102">Utilizzo di un oggetto di stato e di un delegato AsyncCallback</span><span class="sxs-lookup"><span data-stu-id="d938b-102">Using an AsyncCallback Delegate and State Object</span></span>
<span data-ttu-id="d938b-103">Quando si utilizza un <xref:System.AsyncCallback> delegato per elaborare i risultati dell'operazione asincrona in un thread separato, è possibile utilizzare un oggetto di stato per passare informazioni tra i metodi di callback e per recuperare un risultato finale.</span><span class="sxs-lookup"><span data-stu-id="d938b-103">When you use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread, you can use a state object to pass information between the callbacks and to retrieve a final result.</span></span> <span data-ttu-id="d938b-104">In questo argomento viene illustrato tale pratica espandendo l'esempio in [tramite un delegato AsyncCallback per terminare un'operazione asincrona](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="d938b-104">This topic demonstrates that practice by expanding the example in [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d938b-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="d938b-105">Example</span></span>  
 <span data-ttu-id="d938b-106">Esempio di codice seguente viene illustrato come utilizzare metodi asincroni nel <xref:System.Net.Dns> classe per recuperare le informazioni di sistema DNS (Domain Name) per i computer specificati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="d938b-106">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System (DNS) information for user-specified computers.</span></span> <span data-ttu-id="d938b-107">In questo esempio viene definito e viene utilizzata la `HostRequest` classe per archiviare le informazioni sullo stato.</span><span class="sxs-lookup"><span data-stu-id="d938b-107">This example defines and uses the `HostRequest` class to store state information.</span></span> <span data-ttu-id="d938b-108">Oggetto `HostRequest` viene creato l'oggetto per ogni nome computer immesso dall'utente.</span><span class="sxs-lookup"><span data-stu-id="d938b-108">A `HostRequest` object gets created for each computer name entered by the user.</span></span> <span data-ttu-id="d938b-109">Questo oggetto viene passato per il <xref:System.Net.Dns.BeginGetHostByName%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="d938b-109">This object is passed to the <xref:System.Net.Dns.BeginGetHostByName%2A> method.</span></span> <span data-ttu-id="d938b-110">Il `ProcessDnsInformation` metodo viene chiamato ogni volta che viene completata una richiesta.</span><span class="sxs-lookup"><span data-stu-id="d938b-110">The `ProcessDnsInformation` method is called each time a request completes.</span></span> <span data-ttu-id="d938b-111">Il `HostRequest` oggetto viene recuperato utilizzando il <xref:System.IAsyncResult.AsyncState%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="d938b-111">The `HostRequest` object is retrieved using the <xref:System.IAsyncResult.AsyncState%2A> property.</span></span> <span data-ttu-id="d938b-112">Il `ProcessDnsInformation` metodo utilizza il `HostRequest` oggetto usato per archiviare il <xref:System.Net.IPHostEntry> restituito dalla richiesta o una <xref:System.Net.Sockets.SocketException> generata dalla richiesta.</span><span class="sxs-lookup"><span data-stu-id="d938b-112">The `ProcessDnsInformation` method uses the `HostRequest` object to store the <xref:System.Net.IPHostEntry> returned by the request or a <xref:System.Net.Sockets.SocketException> thrown by the request.</span></span> <span data-ttu-id="d938b-113">Una volta completate tutte le richieste, l'applicazione scorre il `HostRequest` oggetti e visualizza le informazioni DNS o <xref:System.Net.Sockets.SocketException> messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="d938b-113">When all requests are complete, the application iterates over the `HostRequest` objects and displays the DNS information or <xref:System.Net.Sockets.SocketException> error message.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateWithStateObject.cs#5)]
 [!code-vb[AsyncDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateWithStateObject.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="d938b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d938b-114">See Also</span></span>  
 <span data-ttu-id="d938b-115">[Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi)</span><span class="sxs-lookup"><span data-stu-id="d938b-115">[Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)</span></span>  
 [<span data-ttu-id="d938b-116">Panoramica sul modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="d938b-116">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [<span data-ttu-id="d938b-117">Uso di un delegato AsyncCallback per terminare un'operazione asincrona</span><span class="sxs-lookup"><span data-stu-id="d938b-117">Using an AsyncCallback Delegate to End an Asynchronous Operation</span></span>](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)
