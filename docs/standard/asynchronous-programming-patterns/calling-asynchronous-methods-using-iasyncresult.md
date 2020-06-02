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
ms.openlocfilehash: 88ca1b5bfbb8bfbdfef01dea8af07c5d56784c5c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289915"
---
# <a name="calling-asynchronous-methods-using-iasyncresult"></a><span data-ttu-id="fe374-102">Chiamata di metodi asincroni tramite IAsyncResult</span><span class="sxs-lookup"><span data-stu-id="fe374-102">Calling Asynchronous Methods Using IAsyncResult</span></span>
<span data-ttu-id="fe374-103">I tipi nelle librerie di classi di .NET Framework e di terze parti possono fornire metodi che consentono di continuare a eseguire un'applicazione durante l'esecuzione di operazioni asincrone in thread diversi dal thread dell'applicazione principale.</span><span class="sxs-lookup"><span data-stu-id="fe374-103">Types in the .NET Framework and third-party class libraries can provide methods that allow an application to continue executing while performing asynchronous operations in threads other than the main application thread.</span></span> <span data-ttu-id="fe374-104">Le sezioni seguenti descrivono e forniscono esempi di codice che illustrano i diversi modi in cui è possibile chiamare metodi asincroni che usano lo schema progettuale <xref:System.IAsyncResult>.</span><span class="sxs-lookup"><span data-stu-id="fe374-104">The following sections describe and provide code examples that demonstrate the different ways you can call asynchronous methods that use the <xref:System.IAsyncResult> design pattern.</span></span>  
  
- <span data-ttu-id="fe374-105">[Blocco dell'esecuzione dell'applicazione terminando un'operazione asincrona](blocking-application-execution-by-ending-an-async-operation.md).</span><span class="sxs-lookup"><span data-stu-id="fe374-105">[Blocking Application Execution by Ending an Async Operation](blocking-application-execution-by-ending-an-async-operation.md).</span></span>  
  
- <span data-ttu-id="fe374-106">[Blocco dell'esecuzione dell'applicazione tramite AsyncWaitHandle](blocking-application-execution-using-an-asyncwaithandle.md).</span><span class="sxs-lookup"><span data-stu-id="fe374-106">[Blocking Application Execution Using an AsyncWaitHandle](blocking-application-execution-using-an-asyncwaithandle.md).</span></span>  
  
- <span data-ttu-id="fe374-107">[Polling dello stato di un'operazione asincrona](polling-for-the-status-of-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="fe374-107">[Polling for the Status of an Asynchronous Operation](polling-for-the-status-of-an-asynchronous-operation.md).</span></span>  
  
- <span data-ttu-id="fe374-108">[Uso di un delegato AsyncCallback per terminare un'operazione asincrona](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="fe374-108">[Using an AsyncCallback Delegate to End an Asynchronous Operation](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe374-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe374-109">See also</span></span>

- <span data-ttu-id="fe374-110">[Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi, EAP)</span><span class="sxs-lookup"><span data-stu-id="fe374-110">[Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md)</span></span>
- [<span data-ttu-id="fe374-111">Cenni preliminari sul modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="fe374-111">Event-based Asynchronous Pattern Overview</span></span>](event-based-asynchronous-pattern-overview.md)
