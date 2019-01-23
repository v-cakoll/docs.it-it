---
title: Evento &#39; &lt;eventname1&gt; &#39; non è possibile implementare l'evento &#39; &lt;eventname2&gt; &#39; sull'interfaccia &#39; &lt;interfaccia&gt; &#39; perché i tipi delegati &#39; &lt;delegate1&gt; &#39; e &#39; &lt;delegate2&gt; &#39; non corrispondono
ms.date: 07/20/2015
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
ms.openlocfilehash: 024e260f12d3497d64f26e59521f016ad439ebb6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54638211"
---
# <a name="event-39lteventname1gt39-cannot-implement-event-39lteventname2gt39-on-interface-39ltinterfacegt39-because-their-delegate-types-39ltdelegate1gt39-and-39ltdelegate2gt39-do-not-match"></a><span data-ttu-id="d8d60-102">Evento &#39; &lt;eventname1&gt; &#39; non è possibile implementare l'evento &#39; &lt;eventname2&gt; &#39; sull'interfaccia &#39; &lt;interfaccia&gt; &#39; perché i tipi delegati &#39; &lt;delegate1&gt; &#39; e &#39; &lt;delegate2&gt; &#39; non corrispondono</span><span class="sxs-lookup"><span data-stu-id="d8d60-102">Event &#39;&lt;eventname1&gt;&#39; cannot implement event &#39;&lt;eventname2&gt;&#39; on interface &#39;&lt;interface&gt;&#39; because their delegate types &#39;&lt;delegate1&gt;&#39; and &#39;&lt;delegate2&gt;&#39; do not match</span></span>
<span data-ttu-id="d8d60-103">Visual Basic non può implementare un evento perché il tipo di delegato dell'evento non corrisponde al tipo delegato dell'evento nell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d8d60-103">Visual Basic cannot implement an event because the delegate type of the event does not match the delegate type of the event in the interface.</span></span> <span data-ttu-id="d8d60-104">Questo errore può insorgere quando si definiscono più eventi in un'interfaccia e si prova a implementarli assieme con lo stesso evento.</span><span class="sxs-lookup"><span data-stu-id="d8d60-104">This error can occur when you define multiple events in an interface and then attempt to implement them together with the same event.</span></span> <span data-ttu-id="d8d60-105">Un evento può implementare due o più eventi solo se tutti gli eventi implementati vengono dichiarati usando la sintassi `As` e se tutti specificano lo stesso tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="d8d60-105">An event can implement two or more events only if all implemented events are declared using the `As` syntax and specify the same delegate type.</span></span>  
  
 <span data-ttu-id="d8d60-106">**ID errore:** BC31423</span><span class="sxs-lookup"><span data-stu-id="d8d60-106">**Error ID:** BC31423</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d8d60-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="d8d60-107">To correct this error</span></span>  
  
-   <span data-ttu-id="d8d60-108">Implementare gli eventi separatamente.</span><span class="sxs-lookup"><span data-stu-id="d8d60-108">Implement the events separately.</span></span>  
  
     <span data-ttu-id="d8d60-109">-oppure-</span><span class="sxs-lookup"><span data-stu-id="d8d60-109">—or—</span></span>  
  
-   <span data-ttu-id="d8d60-110">Definire gli eventi nell'interfaccia utilizzando il `As` sintassi e specificare lo stesso tipo di delegato.</span><span class="sxs-lookup"><span data-stu-id="d8d60-110">Define the events in the interface using the `As` syntax and specify the same delegate type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8d60-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8d60-111">See also</span></span>
- [<span data-ttu-id="d8d60-112">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="d8d60-112">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="d8d60-113">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="d8d60-113">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="d8d60-114">Eventi</span><span class="sxs-lookup"><span data-stu-id="d8d60-114">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
