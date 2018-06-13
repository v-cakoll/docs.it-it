---
title: 'Procedura: dichiarare eventi personalizzati per evitare il blocco (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
ms.openlocfilehash: 3cb66aed71195d2fd2335fbd59cc499b3dbf808e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33646926"
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a><span data-ttu-id="281dc-102">Procedura: dichiarare eventi personalizzati per evitare il blocco (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="281dc-102">How to: Declare Custom Events To Avoid Blocking (Visual Basic)</span></span>
<span data-ttu-id="281dc-103">Quando è importante che un gestore eventi non bloccano i gestori eventi successivi, esistono diverse circostanze.</span><span class="sxs-lookup"><span data-stu-id="281dc-103">There are several circumstances when it is important that one event handler not block subsequent event handlers.</span></span> <span data-ttu-id="281dc-104">Eventi personalizzati consentono di chiamare i relativi gestori eventi in modo asincrono l'evento.</span><span class="sxs-lookup"><span data-stu-id="281dc-104">Custom events allow the event to call its event handlers asynchronously.</span></span>  
  
 <span data-ttu-id="281dc-105">Per impostazione predefinita, il campo di archivio di backup per una dichiarazione di evento è un delegato multicast che combina in modo seriale tutti i gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="281dc-105">By default, the backing-store field for an event declaration is a multicast delegate that serially combines all the event handlers.</span></span> <span data-ttu-id="281dc-106">Ciò significa che se un gestore richiede molto tempo, si blocca altri gestori fino al completamento.</span><span class="sxs-lookup"><span data-stu-id="281dc-106">This means that if one handler takes a long time to complete, it blocks the other handlers until it completes.</span></span> <span data-ttu-id="281dc-107">(Gestori eventi ben progettati non devono mai eseguire operazioni di lunga durate o di blocco.)</span><span class="sxs-lookup"><span data-stu-id="281dc-107">(Well-behaved event handlers should never perform lengthy or potentially blocking operations.)</span></span>  
  
 <span data-ttu-id="281dc-108">Anziché utilizzare l'implementazione predefinita di eventi disponibili in Visual Basic, è possibile utilizzare un evento personalizzato per eseguire i gestori eventi in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="281dc-108">Instead of using the default implementation of events that Visual Basic provides, you can use a custom event to execute the event handlers asynchronously.</span></span>  
  
## <a name="example"></a><span data-ttu-id="281dc-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="281dc-109">Example</span></span>  
 <span data-ttu-id="281dc-110">In questo esempio, il `AddHandler` accessor aggiunge il delegato per ogni gestore del `Click` evento da un <xref:System.Collections.ArrayList> archiviati nel `EventHandlerList` campo.</span><span class="sxs-lookup"><span data-stu-id="281dc-110">In this example, the `AddHandler` accessor adds the delegate for each handler of the `Click` event to an <xref:System.Collections.ArrayList> stored in the `EventHandlerList` field.</span></span>  
  
 <span data-ttu-id="281dc-111">Quando il codice genera il `Click` evento, il `RaiseEvent` della funzione di accesso richiama tutti i delegati del gestore eventi in modo asincrono utilizzando il <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="281dc-111">When code raises the `Click` event, the `RaiseEvent` accessor invokes all the event handler delegates asynchronously using the <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> method.</span></span> <span data-ttu-id="281dc-112">Tale metodo richiama ciascun gestore su un thread di lavoro e restituisce immediatamente, pertanto non è possibile bloccare gestori tra loro.</span><span class="sxs-lookup"><span data-stu-id="281dc-112">That method invokes each handler on a worker thread and returns immediately, so handlers cannot block one another.</span></span>  
  
 [!code-vb[VbVbalrEvents#27](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-avoid-blocking_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="281dc-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="281dc-113">See Also</span></span>  
 <xref:System.Collections.ArrayList>  
 <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>  
 [<span data-ttu-id="281dc-114">Eventi</span><span class="sxs-lookup"><span data-stu-id="281dc-114">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [<span data-ttu-id="281dc-115">Procedura: Dichiarare eventi personalizzati per proteggere la memoria</span><span class="sxs-lookup"><span data-stu-id="281dc-115">How to: Declare Custom Events To Conserve Memory</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
