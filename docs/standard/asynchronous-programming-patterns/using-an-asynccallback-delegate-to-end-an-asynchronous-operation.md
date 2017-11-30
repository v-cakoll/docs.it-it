---
title: Utilizzo di un delegato AsyncCallback per terminare un'operazione asincrona
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
- ending asynchronous operations
- asynchronous programming, ending operations
- AsyncCallback delegate
- stopping asynchronous operations
ms.assetid: 9d97206c-8917-406c-8961-7d0909d84eeb
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bbe170588776daa97fec4c736d4b1bdd871de518
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="using-an-asynccallback-delegate-to-end-an-asynchronous-operation"></a><span data-ttu-id="2c742-102">Utilizzo di un delegato AsyncCallback per terminare un'operazione asincrona</span><span class="sxs-lookup"><span data-stu-id="2c742-102">Using an AsyncCallback Delegate to End an Asynchronous Operation</span></span>
<span data-ttu-id="2c742-103">Le applicazioni che è possano eseguire altre attività in attesa dei risultati di un'operazione asincrona non devono bloccarsi in attesa fino al completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="2c742-103">Applications that can do other work while waiting for the results of an asynchronous operation should not block waiting until the operation completes.</span></span> <span data-ttu-id="2c742-104">Per continuare l'esecuzione di istruzioni durante l'attesa di completamento di un'operazione asincrona, utilizzare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c742-104">Use one of the following options to continue executing instructions while waiting for an asynchronous operation to complete:</span></span>  
  
-   <span data-ttu-id="2c742-105">Utilizzare un <xref:System.AsyncCallback> delegato per elaborare i risultati dell'operazione asincrona in un thread separato.</span><span class="sxs-lookup"><span data-stu-id="2c742-105">Use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread.</span></span> <span data-ttu-id="2c742-106">Questo approccio viene illustrato in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="2c742-106">This approach is demonstrated in this topic.</span></span>  
  
-   <span data-ttu-id="2c742-107">Utilizzare il <xref:System.IAsyncResult.IsCompleted%2A> proprietà del <xref:System.IAsyncResult> restituito tramite l'operazione asincrona **iniziare** *OperationName* metodo per determinare se l'operazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="2c742-107">Use the <xref:System.IAsyncResult.IsCompleted%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin** *OperationName* method to determine whether the operation has completed.</span></span> <span data-ttu-id="2c742-108">Per un esempio che illustra questo approccio, vedere [il Polling dello stato dell'operazione asincrona](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="2c742-108">For an example that demonstrates this approach, see [Polling for the Status of an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c742-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="2c742-109">Example</span></span>  
 <span data-ttu-id="2c742-110">Esempio di codice seguente viene illustrato come utilizzare metodi asincroni nel <xref:System.Net.Dns> classe per recuperare le informazioni di sistema DNS (Domain Name) per i computer specificati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="2c742-110">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System (DNS) information for user-specified computers.</span></span> <span data-ttu-id="2c742-111">Questo esempio viene creato un <xref:System.AsyncCallback> delegato che fa riferimento il `ProcessDnsInformation` metodo.</span><span class="sxs-lookup"><span data-stu-id="2c742-111">This example creates an <xref:System.AsyncCallback> delegate that references the `ProcessDnsInformation` method.</span></span> <span data-ttu-id="2c742-112">Questo metodo viene chiamato una volta per ogni richiesta asincrona per le informazioni DNS.</span><span class="sxs-lookup"><span data-stu-id="2c742-112">This method is called once for each asynchronous request for DNS information.</span></span>  
  
 <span data-ttu-id="2c742-113">Si noti che l'host specificato dall'utente viene passato per il <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.Object> parametro.</span><span class="sxs-lookup"><span data-stu-id="2c742-113">Note that the user-specified host is passed to the <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.Object> parameter.</span></span> <span data-ttu-id="2c742-114">Per un esempio che illustra la definizione e utilizzo di un oggetto di stato più complesso, vedere [tramite un delegato AsyncCallback e un oggetto di stato](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md).</span><span class="sxs-lookup"><span data-stu-id="2c742-114">For an example that demonstrates defining and using a more complex state object, see [Using an AsyncCallback Delegate and State Object](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md).</span></span>  
  
 [!code-csharp[AsyncDesignPattern#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateNoStateObject.cs#4)]
 [!code-vb[AsyncDesignPattern#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateNoState.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="2c742-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c742-115">See Also</span></span>  
 <span data-ttu-id="2c742-116">[Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi)</span><span class="sxs-lookup"><span data-stu-id="2c742-116">[Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)</span></span>  
 [<span data-ttu-id="2c742-117">Panoramica sul modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="2c742-117">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [<span data-ttu-id="2c742-118">Chiamata di metodi asincroni tramite IAsyncResult</span><span class="sxs-lookup"><span data-stu-id="2c742-118">Calling Asynchronous Methods Using IAsyncResult</span></span>](../../../docs/standard/asynchronous-programming-patterns/calling-asynchronous-methods-using-iasyncresult.md)  
 [<span data-ttu-id="2c742-119">Uso di un oggetto di stato e di un delegato AsyncCallback</span><span class="sxs-lookup"><span data-stu-id="2c742-119">Using an AsyncCallback Delegate and State Object</span></span>](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)
