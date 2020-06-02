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
ms.openlocfilehash: e52ed550510253aba9401931c0f612211c7d1bf5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84276426"
---
# <a name="using-an-asynccallback-delegate-and-state-object"></a><span data-ttu-id="78903-102">Utilizzo di un oggetto di stato e di un delegato AsyncCallback</span><span class="sxs-lookup"><span data-stu-id="78903-102">Using an AsyncCallback Delegate and State Object</span></span>
<span data-ttu-id="78903-103">Quando si usa un delegato <xref:System.AsyncCallback> per elaborare i risultati dell'operazione asincrona in un thread separato, è possibile usare un oggetto di stato per passare le informazioni tra i metodi di callback e per recuperare un risultato finale.</span><span class="sxs-lookup"><span data-stu-id="78903-103">When you use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread, you can use a state object to pass information between the callbacks and to retrieve a final result.</span></span> <span data-ttu-id="78903-104">In questo argomento viene illustrata tale pratica analizzando ulteriormente l'esempio descritto in [Uso di un delegato AsyncCallback per terminare un'operazione asincrona](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="78903-104">This topic demonstrates that practice by expanding the example in [Using an AsyncCallback Delegate to End an Asynchronous Operation](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="78903-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="78903-105">Example</span></span>  
 <span data-ttu-id="78903-106">Nell'esempio di codice seguente viene illustrato come usare metodi asincroni nella classe <xref:System.Net.Dns> per recuperare le informazioni sul DNS (Domain Name System) per i computer specificati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="78903-106">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System (DNS) information for user-specified computers.</span></span> <span data-ttu-id="78903-107">Questo esempio definisce e usa la classe `HostRequest` per archiviare le informazioni sullo stato.</span><span class="sxs-lookup"><span data-stu-id="78903-107">This example defines and uses the `HostRequest` class to store state information.</span></span> <span data-ttu-id="78903-108">Viene creato l'oggetto `HostRequest` per ogni nome computer immesso dall'utente.</span><span class="sxs-lookup"><span data-stu-id="78903-108">A `HostRequest` object gets created for each computer name entered by the user.</span></span> <span data-ttu-id="78903-109">Questo oggetto viene passato al metodo <xref:System.Net.Dns.BeginGetHostByName%2A>.</span><span class="sxs-lookup"><span data-stu-id="78903-109">This object is passed to the <xref:System.Net.Dns.BeginGetHostByName%2A> method.</span></span> <span data-ttu-id="78903-110">Il metodo `ProcessDnsInformation` viene chiamato ogni volta che viene completata una richiesta.</span><span class="sxs-lookup"><span data-stu-id="78903-110">The `ProcessDnsInformation` method is called each time a request completes.</span></span> <span data-ttu-id="78903-111">L'oggetto `HostRequest` viene recuperato tramite la proprietà <xref:System.IAsyncResult.AsyncState%2A>.</span><span class="sxs-lookup"><span data-stu-id="78903-111">The `HostRequest` object is retrieved using the <xref:System.IAsyncResult.AsyncState%2A> property.</span></span> <span data-ttu-id="78903-112">Il metodo `ProcessDnsInformation` usa l'oggetto `HostRequest` per archiviare l'oggetto <xref:System.Net.IPHostEntry> restituito dalla richiesta o un'eccezione <xref:System.Net.Sockets.SocketException> generata dalla richiesta.</span><span class="sxs-lookup"><span data-stu-id="78903-112">The `ProcessDnsInformation` method uses the `HostRequest` object to store the <xref:System.Net.IPHostEntry> returned by the request or a <xref:System.Net.Sockets.SocketException> thrown by the request.</span></span> <span data-ttu-id="78903-113">Al completamento di tutte le richieste, l'applicazione scorre gli oggetti `HostRequest` e visualizza le informazioni DNS o il messaggio di errore <xref:System.Net.Sockets.SocketException>.</span><span class="sxs-lookup"><span data-stu-id="78903-113">When all requests are complete, the application iterates over the `HostRequest` objects and displays the DNS information or <xref:System.Net.Sockets.SocketException> error message.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateWithStateObject.cs#5)]
 [!code-vb[AsyncDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateWithStateObject.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="78903-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78903-114">See also</span></span>

- <span data-ttu-id="78903-115">[Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi, EAP)</span><span class="sxs-lookup"><span data-stu-id="78903-115">[Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md)</span></span>
- [<span data-ttu-id="78903-116">Cenni preliminari sul modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="78903-116">Event-based Asynchronous Pattern Overview</span></span>](event-based-asynchronous-pattern-overview.md)
- [<span data-ttu-id="78903-117">Utilizzo di un delegato AsyncCallback per terminare un'operazione asincrona</span><span class="sxs-lookup"><span data-stu-id="78903-117">Using an AsyncCallback Delegate to End an Asynchronous Operation</span></span>](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)
