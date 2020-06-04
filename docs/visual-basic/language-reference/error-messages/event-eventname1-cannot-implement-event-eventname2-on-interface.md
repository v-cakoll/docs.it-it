---
title: L'evento '<eventname1>' non può implementare l'evento '<eventname2>' nell'interfaccia '<interface>' poiché i tipi delegati '<delegate1>' e '<delegate2>' non corrispondono
ms.date: 07/20/2015
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
ms.openlocfilehash: 32d6733580de8798a66c30d486b8439befd2af19
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409608"
---
# <a name="event-eventname1-cannot-implement-event-eventname2-on-interface-interface-because-their-delegate-types-delegate1-and-delegate2-do-not-match"></a><span data-ttu-id="ed421-102">L'evento '\<eventname1>' non può implementare l'evento '\<eventname2>' nell'interfaccia '\<interface>' poiché i tipi delegati '\<delegate1>' e '\<delegate2>' non corrispondono</span><span class="sxs-lookup"><span data-stu-id="ed421-102">Event '\<eventname1>' cannot implement event '\<eventname2>' on interface '\<interface>' because their delegate types '\<delegate1>' and '\<delegate2>' do not match</span></span>
<span data-ttu-id="ed421-103">Visual Basic non è in grado di implementare un evento perché il tipo delegato dell'evento non corrisponde al tipo delegato dell'evento nell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="ed421-103">Visual Basic cannot implement an event because the delegate type of the event does not match the delegate type of the event in the interface.</span></span> <span data-ttu-id="ed421-104">Questo errore può insorgere quando si definiscono più eventi in un'interfaccia e si prova a implementarli assieme con lo stesso evento.</span><span class="sxs-lookup"><span data-stu-id="ed421-104">This error can occur when you define multiple events in an interface and then attempt to implement them together with the same event.</span></span> <span data-ttu-id="ed421-105">Un evento può implementare due o più eventi solo se tutti gli eventi implementati vengono dichiarati usando la sintassi `As` e se tutti specificano lo stesso tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="ed421-105">An event can implement two or more events only if all implemented events are declared using the `As` syntax and specify the same delegate type.</span></span>  
  
 <span data-ttu-id="ed421-106">**ID errore:** BC31423</span><span class="sxs-lookup"><span data-stu-id="ed421-106">**Error ID:** BC31423</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ed421-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="ed421-107">To correct this error</span></span>  
  
- <span data-ttu-id="ed421-108">Implementare gli eventi separatamente.</span><span class="sxs-lookup"><span data-stu-id="ed421-108">Implement the events separately.</span></span>  
  
     <span data-ttu-id="ed421-109">-oppure-</span><span class="sxs-lookup"><span data-stu-id="ed421-109">—or—</span></span>  
  
- <span data-ttu-id="ed421-110">Definire gli eventi nell'interfaccia usando la `As` sintassi e specificare lo stesso tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="ed421-110">Define the events in the interface using the `As` syntax and specify the same delegate type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed421-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed421-111">See also</span></span>

- [<span data-ttu-id="ed421-112">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="ed421-112">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="ed421-113">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="ed421-113">Delegate Statement</span></span>](../statements/delegate-statement.md)
- [<span data-ttu-id="ed421-114">Events</span><span class="sxs-lookup"><span data-stu-id="ed421-114">Events</span></span>](../../programming-guide/language-features/events/index.md)
