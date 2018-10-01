---
title: Chiamata di metodi asincroni tramite IAsyncResult
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- ending asynchronous operations
- waiting for asynchronous operations
- asynchronous method calling
- calling asynchronous methods
- asynchronous programming, calling asynchronous methods
- IAsyncResult interface, calling asynchronous methods
- stopping asynchronous operations
ms.assetid: 07fba116-045b-473c-a0b7-acdbeb49861f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 23fa927dcdb91fb3905f1cbe845450751de91157
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2018
ms.locfileid: "47234848"
---
# <a name="calling-asynchronous-methods-using-iasyncresult"></a><span data-ttu-id="6d2f0-102">Chiamata di metodi asincroni tramite IAsyncResult</span><span class="sxs-lookup"><span data-stu-id="6d2f0-102">Calling Asynchronous Methods Using IAsyncResult</span></span>
<span data-ttu-id="6d2f0-103">I tipi nelle librerie di classi di .NET Framework e di terze parti possono fornire metodi che consentono di continuare a eseguire un'applicazione durante l'esecuzione di operazioni asincrone in thread diversi dal thread dell'applicazione principale.</span><span class="sxs-lookup"><span data-stu-id="6d2f0-103">Types in the .NET Framework and third-party class libraries can provide methods that allow an application to continue executing while performing asynchronous operations in threads other than the main application thread.</span></span> <span data-ttu-id="6d2f0-104">Le sezioni seguenti descrivono e forniscono esempi di codice che illustrano i diversi modi in cui è possibile chiamare metodi asincroni che usano lo schema progettuale <xref:System.IAsyncResult>.</span><span class="sxs-lookup"><span data-stu-id="6d2f0-104">The following sections describe and provide code examples that demonstrate the different ways you can call asynchronous methods that use the <xref:System.IAsyncResult> design pattern.</span></span>  
  
-   <span data-ttu-id="6d2f0-105">[Blocco dell'esecuzione dell'applicazione terminando un'operazione asincrona](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).</span><span class="sxs-lookup"><span data-stu-id="6d2f0-105">[Blocking Application Execution by Ending an Async Operation](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).</span></span>  
  
-   <span data-ttu-id="6d2f0-106">[Blocco dell'esecuzione dell'applicazione tramite AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span><span class="sxs-lookup"><span data-stu-id="6d2f0-106">[Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span></span>  
  
-   <span data-ttu-id="6d2f0-107">[Esecuzione del polling dello stato di un'operazione asincrona](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="6d2f0-107">[Polling for the Status of an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).</span></span>  
  
-   <span data-ttu-id="6d2f0-108">[Uso di un delegato AsyncCallback per terminare un'operazione asincrona](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="6d2f0-108">[Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d2f0-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d2f0-109">See also</span></span>

- <span data-ttu-id="6d2f0-110">[Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi, EAP)</span><span class="sxs-lookup"><span data-stu-id="6d2f0-110">[Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)</span></span>  
- [<span data-ttu-id="6d2f0-111">Panoramica sul modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="6d2f0-111">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
