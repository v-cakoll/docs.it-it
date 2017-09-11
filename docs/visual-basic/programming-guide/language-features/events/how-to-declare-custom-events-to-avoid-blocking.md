---
title: 'Procedura: dichiarare eventi personalizzati per evitare il blocco (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declaring events, custom
- events [Visual Basic], custom
- custom events
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 52181d1c307e4e312f4511719e540fd6d5bfcfa8
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a><span data-ttu-id="0a4e6-102">Procedura: dichiarare eventi personalizzati per evitare il blocco (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0a4e6-102">How to: Declare Custom Events To Avoid Blocking (Visual Basic)</span></span>
<span data-ttu-id="0a4e6-103">Esistono diverse circostanze quando è importante che un gestore eventi non blocchi i gestori eventi successivi.</span><span class="sxs-lookup"><span data-stu-id="0a4e6-103">There are several circumstances when it is important that one event handler not block subsequent event handlers.</span></span> <span data-ttu-id="0a4e6-104">Eventi personalizzati consentono di chiamare gestori eventi in modo asincrono l'evento.</span><span class="sxs-lookup"><span data-stu-id="0a4e6-104">Custom events allow the event to call its event handlers asynchronously.</span></span>  
  
 <span data-ttu-id="0a4e6-105">Per impostazione predefinita, il campo archivio di backup per una dichiarazione di evento è un delegato multicast che combina in modo seriale tutti i gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="0a4e6-105">By default, the backing-store field for an event declaration is a multicast delegate that serially combines all the event handlers.</span></span> <span data-ttu-id="0a4e6-106">Ciò significa che se un gestore richiede molto tempo, si blocca altri gestori fino al completamento.</span><span class="sxs-lookup"><span data-stu-id="0a4e6-106">This means that if one handler takes a long time to complete, it blocks the other handlers until it completes.</span></span> <span data-ttu-id="0a4e6-107">(I gestori eventi che devono evitare di eseguire operazioni di lunga durate o di blocco.)</span><span class="sxs-lookup"><span data-stu-id="0a4e6-107">(Well-behaved event handlers should never perform lengthy or potentially blocking operations.)</span></span>  
  
 <span data-ttu-id="0a4e6-108">Invece di utilizzare l'implementazione predefinita di eventi disponibili in Visual Basic, è possibile utilizzare un evento personalizzato per eseguire i gestori eventi in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="0a4e6-108">Instead of using the default implementation of events that Visual Basic provides, you can use a custom event to execute the event handlers asynchronously.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a4e6-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="0a4e6-109">Example</span></span>  
 <span data-ttu-id="0a4e6-110">In questo esempio, il `AddHandler` funzione di accesso aggiunge il delegato per ogni gestore del `Click` evento per un <xref:System.Collections.ArrayList>archiviati nel `EventHandlerList` campo.</xref:System.Collections.ArrayList></span><span class="sxs-lookup"><span data-stu-id="0a4e6-110">In this example, the `AddHandler` accessor adds the delegate for each handler of the `Click` event to an <xref:System.Collections.ArrayList> stored in the `EventHandlerList` field.</span></span>  
  
 <span data-ttu-id="0a4e6-111">Quando il codice genera il `Click` evento, il `RaiseEvent` funzione di accesso richiama tutti i delegati del gestore eventi in modo asincrono utilizzando il <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>(metodo).</xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A></span><span class="sxs-lookup"><span data-stu-id="0a4e6-111">When code raises the `Click` event, the `RaiseEvent` accessor invokes all the event handler delegates asynchronously using the <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> method.</span></span> <span data-ttu-id="0a4e6-112">Questo metodo richiama ogni gestore su un thread di lavoro e restituisce immediatamente, in modo che i gestori non blocchino reciprocamente.</span><span class="sxs-lookup"><span data-stu-id="0a4e6-112">That method invokes each handler on a worker thread and returns immediately, so handlers cannot block one another.</span></span>  
  
 <span data-ttu-id="0a4e6-113">[!code-vb[VbVbalrEvents&#27;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-avoid-blocking_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="0a4e6-113">[!code-vb[VbVbalrEvents#27](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-avoid-blocking_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a4e6-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a4e6-114">See Also</span></span>  
 <span data-ttu-id="0a4e6-115"><xref:System.Collections.ArrayList></xref:System.Collections.ArrayList></span><span class="sxs-lookup"><span data-stu-id="0a4e6-115"><xref:System.Collections.ArrayList></span></span>   
 <span data-ttu-id="0a4e6-116"><xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A></xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A></span><span class="sxs-lookup"><span data-stu-id="0a4e6-116"><xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A></span></span>   
<span data-ttu-id="0a4e6-117"> [Eventi](../../../../visual-basic/programming-guide/language-features/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="0a4e6-117"> [Events](../../../../visual-basic/programming-guide/language-features/events/index.md) </span></span>  
<span data-ttu-id="0a4e6-118"> [Procedura: Dichiarare eventi personalizzati per proteggere la memoria](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)</span><span class="sxs-lookup"><span data-stu-id="0a4e6-118"> [How to: Declare Custom Events To Conserve Memory](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)</span></span>
