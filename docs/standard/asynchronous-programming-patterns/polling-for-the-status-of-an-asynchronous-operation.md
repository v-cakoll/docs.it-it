---
title: Esecuzione del polling dello stato di un'operazione asincrona
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
- asynchronous programming, status polling
- polling asynchronous operation status
- status information [.NET Framework], asynchronous operations
ms.assetid: b541af31-dacb-4e20-8847-1b1ff7c35363
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1f7f74a8b38c06f6a042d55c0def76ddfc5da77
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="polling-for-the-status-of-an-asynchronous-operation"></a><span data-ttu-id="40f0f-102">Esecuzione del polling dello stato di un'operazione asincrona</span><span class="sxs-lookup"><span data-stu-id="40f0f-102">Polling for the Status of an Asynchronous Operation</span></span>
<span data-ttu-id="40f0f-103">Le applicazioni che è possano eseguire altre attività in attesa dei risultati di un'operazione asincrona non devono bloccarsi in attesa fino al completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="40f0f-103">Applications that can do other work while waiting for the results of an asynchronous operation should not block waiting until the operation completes.</span></span> <span data-ttu-id="40f0f-104">Per continuare l'esecuzione di istruzioni durante l'attesa di completamento di un'operazione asincrona, utilizzare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="40f0f-104">Use one of the following options to continue executing instructions while waiting for an asynchronous operation to complete:</span></span>  
  
-   <span data-ttu-id="40f0f-105">Utilizzare il <xref:System.IAsyncResult.IsCompleted%2A> proprietà del <xref:System.IAsyncResult> restituito tramite l'operazione asincrona **iniziare** *OperationName* metodo per determinare se l'operazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="40f0f-105">Use the <xref:System.IAsyncResult.IsCompleted%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin** *OperationName* method to determine whether the operation has completed.</span></span> <span data-ttu-id="40f0f-106">Questo approccio è noto come polling e viene illustrato in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="40f0f-106">This approach is known as polling and is demonstrated in this topic.</span></span>  
  
-   <span data-ttu-id="40f0f-107">Utilizzare un <xref:System.AsyncCallback> delegato per elaborare i risultati dell'operazione asincrona in un thread separato.</span><span class="sxs-lookup"><span data-stu-id="40f0f-107">Use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread.</span></span> <span data-ttu-id="40f0f-108">Per un esempio che illustra questo approccio, vedere [tramite un delegato AsyncCallback per terminare un'operazione asincrona](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="40f0f-108">For an example that demonstrates this approach, see [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="40f0f-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="40f0f-109">Example</span></span>  
 <span data-ttu-id="40f0f-110">Esempio di codice seguente viene illustrato come utilizzare metodi asincroni nel <xref:System.Net.Dns> classe per recuperare le informazioni di sistema di nome di dominio per un computer specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="40f0f-110">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="40f0f-111">In questo esempio viene avviata l'operazione asincrona e vengono quindi stampati punti (".") nella console fino al completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="40f0f-111">This example starts the asynchronous operation and then prints periods (".") at the console until the operation is complete.</span></span> <span data-ttu-id="40f0f-112">Si noti che **null** (**nulla** in Visual Basic) viene passato il <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.AsyncCallback> e <xref:System.Object> parametri poiché questi argomenti non sono necessari quando si utilizza questo approccio.</span><span class="sxs-lookup"><span data-stu-id="40f0f-112">Note that **null** (**Nothing** in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.AsyncCallback> and <xref:System.Object> parameters because these arguments are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_Poll.cs#3)]
 [!code-vb[AsyncDesignPattern#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_Poll.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="40f0f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40f0f-113">See Also</span></span>  
 <span data-ttu-id="40f0f-114">[Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi)</span><span class="sxs-lookup"><span data-stu-id="40f0f-114">[Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)</span></span>  
 [<span data-ttu-id="40f0f-115">Panoramica sul modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="40f0f-115">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
