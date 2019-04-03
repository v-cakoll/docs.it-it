---
title: 'Procedura: Dichiarare eventi personalizzati per evitare il blocco (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
ms.openlocfilehash: 6eea47ea2c8aee697eb34ca904dad22ca88e6ce4
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58821257"
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a><span data-ttu-id="f6ac0-102">Procedura: Dichiarare eventi personalizzati per evitare il blocco (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6ac0-102">How to: Declare Custom Events To Avoid Blocking (Visual Basic)</span></span>
<span data-ttu-id="f6ac0-103">Esistono diversi casi quando è importante che un gestore eventi non bloccano i gestori eventi successivi.</span><span class="sxs-lookup"><span data-stu-id="f6ac0-103">There are several circumstances when it is important that one event handler not block subsequent event handlers.</span></span> <span data-ttu-id="f6ac0-104">Eventi personalizzati consentono di chiamare i relativi gestori eventi in modo asincrono l'evento.</span><span class="sxs-lookup"><span data-stu-id="f6ac0-104">Custom events allow the event to call its event handlers asynchronously.</span></span>  
  
 <span data-ttu-id="f6ac0-105">Per impostazione predefinita, il campo di archivio di backup per una dichiarazione di evento è un delegato multicast che combina in modo seriale tutti i gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="f6ac0-105">By default, the backing-store field for an event declaration is a multicast delegate that serially combines all the event handlers.</span></span> <span data-ttu-id="f6ac0-106">Ciò significa che se un singolo gestore richiede molto tempo per il completamento, si blocca altri gestori fino al completamento.</span><span class="sxs-lookup"><span data-stu-id="f6ac0-106">This means that if one handler takes a long time to complete, it blocks the other handlers until it completes.</span></span> <span data-ttu-id="f6ac0-107">(I gestori eventi ben progettate devono evitare di eseguire operazioni di lunga durate o potenzialmente di blocco.)</span><span class="sxs-lookup"><span data-stu-id="f6ac0-107">(Well-behaved event handlers should never perform lengthy or potentially blocking operations.)</span></span>  
  
 <span data-ttu-id="f6ac0-108">Invece di usare l'implementazione predefinita di eventi disponibili in Visual Basic, è possibile usare un evento personalizzato da eseguire in modo asincrono i gestori di eventi.</span><span class="sxs-lookup"><span data-stu-id="f6ac0-108">Instead of using the default implementation of events that Visual Basic provides, you can use a custom event to execute the event handlers asynchronously.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6ac0-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="f6ac0-109">Example</span></span>  
 <span data-ttu-id="f6ac0-110">In questo esempio, il `AddHandler` della funzione di accesso aggiunge il delegato per ogni gestore del `Click` evento a un <xref:System.Collections.ArrayList> archiviati nel `EventHandlerList` campo.</span><span class="sxs-lookup"><span data-stu-id="f6ac0-110">In this example, the `AddHandler` accessor adds the delegate for each handler of the `Click` event to an <xref:System.Collections.ArrayList> stored in the `EventHandlerList` field.</span></span>  
  
 <span data-ttu-id="f6ac0-111">Quando il codice genera il `Click` evento, il `RaiseEvent` funzione di accesso richiama tutti i delegati del gestore eventi in modo asincrono utilizzando il <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="f6ac0-111">When code raises the `Click` event, the `RaiseEvent` accessor invokes all the event handler delegates asynchronously using the <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> method.</span></span> <span data-ttu-id="f6ac0-112">Tale metodo richiama ciascun gestore su un thread di lavoro e restituisce immediatamente, in modo che i gestori non blocchino reciprocamente.</span><span class="sxs-lookup"><span data-stu-id="f6ac0-112">That method invokes each handler on a worker thread and returns immediately, so handlers cannot block one another.</span></span>  
  
 [!code-vb[VbVbalrEvents#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#27)]  
  
## <a name="see-also"></a><span data-ttu-id="f6ac0-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6ac0-113">See also</span></span>

- <xref:System.Collections.ArrayList>
- <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>
- [<span data-ttu-id="f6ac0-114">Eventi</span><span class="sxs-lookup"><span data-stu-id="f6ac0-114">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [<span data-ttu-id="f6ac0-115">Procedura: Dichiarare eventi personalizzati per proteggere la memoria</span><span class="sxs-lookup"><span data-stu-id="f6ac0-115">How to: Declare Custom Events To Conserve Memory</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
