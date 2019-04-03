---
title: L'evento '<eventname1>' non può implementare l'evento '<eventname2>' nell'interfaccia '<interface>' poiché i tipi delegati '<delegate1>' e '<delegate2>' non corrispondono
ms.date: 07/20/2015
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
ms.openlocfilehash: 9581168fa86f8f0715e004b60c2eb2a813cd38ab
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58840523"
---
# <a name="event-eventname1-cannot-implement-event-eventname2-on-interface-interface-because-their-delegate-types-delegate1-and-delegate2-do-not-match"></a><span data-ttu-id="e848e-102">Evento '\<eventname1 >' non può implementare l'evento '\<eventname2 >' nell'interfaccia '\<interfaccia >' perché i relativi tipi delegato\<delegate1 >' e '\<delegate2 >' non corrispondono</span><span class="sxs-lookup"><span data-stu-id="e848e-102">Event '\<eventname1>' cannot implement event '\<eventname2>' on interface '\<interface>' because their delegate types '\<delegate1>' and '\<delegate2>' do not match</span></span>
<span data-ttu-id="e848e-103">Visual Basic non può implementare un evento perché il tipo di delegato dell'evento non corrisponde al tipo delegato dell'evento nell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e848e-103">Visual Basic cannot implement an event because the delegate type of the event does not match the delegate type of the event in the interface.</span></span> <span data-ttu-id="e848e-104">Questo errore può insorgere quando si definiscono più eventi in un'interfaccia e si prova a implementarli assieme con lo stesso evento.</span><span class="sxs-lookup"><span data-stu-id="e848e-104">This error can occur when you define multiple events in an interface and then attempt to implement them together with the same event.</span></span> <span data-ttu-id="e848e-105">Un evento può implementare due o più eventi solo se tutti gli eventi implementati vengono dichiarati usando la sintassi `As` e se tutti specificano lo stesso tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="e848e-105">An event can implement two or more events only if all implemented events are declared using the `As` syntax and specify the same delegate type.</span></span>  
  
 <span data-ttu-id="e848e-106">**ID errore:** BC31423</span><span class="sxs-lookup"><span data-stu-id="e848e-106">**Error ID:** BC31423</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e848e-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="e848e-107">To correct this error</span></span>  
  
-   <span data-ttu-id="e848e-108">Implementare gli eventi separatamente.</span><span class="sxs-lookup"><span data-stu-id="e848e-108">Implement the events separately.</span></span>  
  
     <span data-ttu-id="e848e-109">-oppure-</span><span class="sxs-lookup"><span data-stu-id="e848e-109">—or—</span></span>  
  
-   <span data-ttu-id="e848e-110">Definire gli eventi nell'interfaccia utilizzando il `As` sintassi e specificare lo stesso tipo di delegato.</span><span class="sxs-lookup"><span data-stu-id="e848e-110">Define the events in the interface using the `As` syntax and specify the same delegate type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e848e-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e848e-111">See also</span></span>

- [<span data-ttu-id="e848e-112">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="e848e-112">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="e848e-113">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="e848e-113">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="e848e-114">Eventi</span><span class="sxs-lookup"><span data-stu-id="e848e-114">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
