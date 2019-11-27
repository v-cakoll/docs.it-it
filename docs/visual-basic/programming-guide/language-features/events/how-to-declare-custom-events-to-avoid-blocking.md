---
title: 'Procedura: dichiarare eventi personalizzati per evitare il blocco'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
ms.openlocfilehash: 8d73d9c4590afb33e7176f647069cafcb3a9d7d8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345144"
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a><span data-ttu-id="fe706-102">Procedura: dichiarare eventi personalizzati per evitare il blocco (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe706-102">How to: Declare Custom Events To Avoid Blocking (Visual Basic)</span></span>
<span data-ttu-id="fe706-103">In alcuni casi è importante che un gestore eventi non blocchi i gestori eventi successivi.</span><span class="sxs-lookup"><span data-stu-id="fe706-103">There are several circumstances when it is important that one event handler not block subsequent event handlers.</span></span> <span data-ttu-id="fe706-104">Gli eventi personalizzati consentono all'evento di chiamare i relativi gestori eventi in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="fe706-104">Custom events allow the event to call its event handlers asynchronously.</span></span>  
  
 <span data-ttu-id="fe706-105">Per impostazione predefinita, il campo di archivio di backup per una dichiarazione di evento è un delegato multicast che combina in modo seriale tutti i gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="fe706-105">By default, the backing-store field for an event declaration is a multicast delegate that serially combines all the event handlers.</span></span> <span data-ttu-id="fe706-106">Ciò significa che se un gestore impiega molto tempo per il completamento, blocca gli altri gestori fino a quando non viene completato.</span><span class="sxs-lookup"><span data-stu-id="fe706-106">This means that if one handler takes a long time to complete, it blocks the other handlers until it completes.</span></span> <span data-ttu-id="fe706-107">I gestori di eventi ben funzionanti non devono mai eseguire operazioni lunghe o potenzialmente bloccanti.</span><span class="sxs-lookup"><span data-stu-id="fe706-107">(Well-behaved event handlers should never perform lengthy or potentially blocking operations.)</span></span>  
  
 <span data-ttu-id="fe706-108">Anziché utilizzare l'implementazione predefinita di eventi forniti da Visual Basic, è possibile utilizzare un evento personalizzato per eseguire i gestori eventi in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="fe706-108">Instead of using the default implementation of events that Visual Basic provides, you can use a custom event to execute the event handlers asynchronously.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe706-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="fe706-109">Example</span></span>  
 <span data-ttu-id="fe706-110">In questo esempio, la funzione di accesso `AddHandler` aggiunge il delegato per ogni gestore dell'evento `Click` a un <xref:System.Collections.ArrayList> archiviato nel campo `EventHandlerList`.</span><span class="sxs-lookup"><span data-stu-id="fe706-110">In this example, the `AddHandler` accessor adds the delegate for each handler of the `Click` event to an <xref:System.Collections.ArrayList> stored in the `EventHandlerList` field.</span></span>  
  
 <span data-ttu-id="fe706-111">Quando il codice genera l'evento `Click`, la funzione di accesso `RaiseEvent` richiama tutti i delegati del gestore eventi in modo asincrono usando il metodo <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>.</span><span class="sxs-lookup"><span data-stu-id="fe706-111">When code raises the `Click` event, the `RaiseEvent` accessor invokes all the event handler delegates asynchronously using the <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> method.</span></span> <span data-ttu-id="fe706-112">Il metodo richiama ogni gestore in un thread di lavoro e restituisce immediatamente il controllo, in modo che i gestori non possano bloccarsi l'uno all'altro.</span><span class="sxs-lookup"><span data-stu-id="fe706-112">That method invokes each handler on a worker thread and returns immediately, so handlers cannot block one another.</span></span>  
  
 [!code-vb[VbVbalrEvents#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#27)]  
  
## <a name="see-also"></a><span data-ttu-id="fe706-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe706-113">See also</span></span>

- <xref:System.Collections.ArrayList>
- <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>
- [<span data-ttu-id="fe706-114">Eventi</span><span class="sxs-lookup"><span data-stu-id="fe706-114">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [<span data-ttu-id="fe706-115">Procedura: Dichiarare eventi personalizzati per proteggere la memoria</span><span class="sxs-lookup"><span data-stu-id="fe706-115">How to: Declare Custom Events To Conserve Memory</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
