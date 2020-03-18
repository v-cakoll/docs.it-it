---
title: Programmazione asincrona tramite delegati
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- BeginInvoke method
- asynchronous programming, delegates
- asynchronous delegates
- calling synchronous methods in asynchronous manner
- EndInvoke method
- calling asynchronous methods
- delegates [.NET Framework], asynchronous
- synchronous calling in asynchronous manner
ms.assetid: 38a345ca-6963-4436-9608-5c9defef9c64
ms.openlocfilehash: 4e17e6a96a12b705cf455d70add7e12a30f5fa90
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73121737"
---
# <a name="asynchronous-programming-using-delegates"></a><span data-ttu-id="2730a-102">Programmazione asincrona tramite delegati</span><span class="sxs-lookup"><span data-stu-id="2730a-102">Asynchronous Programming Using Delegates</span></span>
<span data-ttu-id="2730a-103">I delegati consentono di chiamare un metodo sincrono in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="2730a-103">Delegates enable you to call a synchronous method in an asynchronous manner.</span></span> <span data-ttu-id="2730a-104">Quando si chiama un delegato in modo sincrono, il metodo `Invoke` chiama il metodo di destinazione direttamente sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="2730a-104">When you call a delegate synchronously, the `Invoke` method calls the target method directly on the current thread.</span></span> <span data-ttu-id="2730a-105">Se viene chiamato il metodo `BeginInvoke`, Common Language Runtime (CLR) accoda la richiesta e restituisce immediatamente il controllo al chiamante.</span><span class="sxs-lookup"><span data-stu-id="2730a-105">If the `BeginInvoke` method is called, the common language runtime (CLR) queues the request and returns immediately to the caller.</span></span> <span data-ttu-id="2730a-106">Il metodo di destinazione viene chiamato in modo asincrono in un thread del pool di thread.</span><span class="sxs-lookup"><span data-stu-id="2730a-106">The target method is called asynchronously on a thread from the thread pool.</span></span> <span data-ttu-id="2730a-107">Il thread originale, che ha inviato la richiesta, può di continuare l'esecuzione in parallelo con il metodo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2730a-107">The original thread, which submitted the request, is free to continue executing in parallel with the target method.</span></span> <span data-ttu-id="2730a-108">Se nella chiamata al metodo `BeginInvoke`, è stato specificato un metodo di callback, quest'ultimo verrà chiamato al termine del metodo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2730a-108">If a callback method has been specified in the call to the `BeginInvoke` method, the callback method is called when the target method ends.</span></span> <span data-ttu-id="2730a-109">Nel metodo di callback il metodo `EndInvoke` ottiene il valore restituito e tutti i parametri di input/output o solo di output.</span><span class="sxs-lookup"><span data-stu-id="2730a-109">In the callback method, the `EndInvoke` method obtains the return value and any input/output or output-only parameters.</span></span> <span data-ttu-id="2730a-110">Se nella chiamata a `BeginInvoke` non viene specificato alcun metodo di callback, `EndInvoke` può essere chiamato dal thread che ha effettuato la chiamata a `BeginInvoke`.</span><span class="sxs-lookup"><span data-stu-id="2730a-110">If no callback method is specified when calling `BeginInvoke`, `EndInvoke` can be called from the thread that called `BeginInvoke`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2730a-111">I compilatori devono creare classi delegate con metodi `Invoke`, `BeginInvoke`e `EndInvoke` usando la firma del delegato specificata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="2730a-111">Compilers should emit delegate classes with `Invoke`, `BeginInvoke`, and `EndInvoke` methods using the delegate signature specified by the user.</span></span> <span data-ttu-id="2730a-112">I metodi `BeginInvoke` e `EndInvoke` devono essere contrassegnati come nativi.</span><span class="sxs-lookup"><span data-stu-id="2730a-112">The `BeginInvoke` and `EndInvoke` methods should be decorated as native.</span></span> <span data-ttu-id="2730a-113">Poiché tali metodi sono contrassegnati come nativi, Common Language Runtime ne specifica automaticamente l'implementazione in fase di caricamento della classe.</span><span class="sxs-lookup"><span data-stu-id="2730a-113">Because these methods are marked as native, the CLR automatically provides the implementation at class load time.</span></span> <span data-ttu-id="2730a-114">Il caricatore garantisce anche che non ne venga eseguito l'override.</span><span class="sxs-lookup"><span data-stu-id="2730a-114">The loader ensures that they are not overridden.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2730a-115">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="2730a-115">In This Section</span></span>  
 [<span data-ttu-id="2730a-116">Chiamata di metodi sincroni in modalità asincrona</span><span class="sxs-lookup"><span data-stu-id="2730a-116">Calling Synchronous Methods Asynchronously</span></span>](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 <span data-ttu-id="2730a-117">Descrive l'uso di delegati per eseguire chiamate asincrone a metodi comuni e contiene semplici esempi di codice in cui si illustrano i quattro modi disponibili per attendere la risposta di una chiamata asincrona.</span><span class="sxs-lookup"><span data-stu-id="2730a-117">Discusses the use of delegates to make asynchronous calls to ordinary methods, and provides simple code examples that show the four ways to wait for an asynchronous call to return.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2730a-118">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="2730a-118">Related Sections</span></span>  
 <span data-ttu-id="2730a-119">[Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi, EAP)</span><span class="sxs-lookup"><span data-stu-id="2730a-119">[Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)</span></span>  
 <span data-ttu-id="2730a-120">Descrive la programmazione asincrona con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2730a-120">Describes asynchronous programming with the .NET Framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2730a-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2730a-121">See also</span></span>

- <xref:System.Delegate>
