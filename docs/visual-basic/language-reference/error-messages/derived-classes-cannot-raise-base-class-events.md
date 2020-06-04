---
title: Le classi derivate non possono generare eventi di classe base
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: c59212a28ba27123a7db9163ff7437c159a3d310
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409699"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a><span data-ttu-id="c6988-102">Le classi derivate non possono generare eventi di classe base</span><span class="sxs-lookup"><span data-stu-id="c6988-102">Derived classes cannot raise base class events</span></span>
<span data-ttu-id="c6988-103">Un evento può essere generato solo dallo spazio di dichiarazione in cui è dichiarato.</span><span class="sxs-lookup"><span data-stu-id="c6988-103">An event can be raised only from the declaration space in which it is declared.</span></span> <span data-ttu-id="c6988-104">Pertanto, una classe non può generare eventi da qualsiasi altra classe, anche uno da cui è derivato.</span><span class="sxs-lookup"><span data-stu-id="c6988-104">Therefore, a class cannot raise events from any other class, even one from which it is derived.</span></span>  
  
 <span data-ttu-id="c6988-105">**ID errore:** BC30029</span><span class="sxs-lookup"><span data-stu-id="c6988-105">**Error ID:** BC30029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c6988-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="c6988-106">To correct this error</span></span>  
  
- <span data-ttu-id="c6988-107">Spostare l' `Event` istruzione o l' `RaiseEvent` istruzione in modo che si trovino nella stessa classe.</span><span class="sxs-lookup"><span data-stu-id="c6988-107">Move the `Event` statement or the `RaiseEvent` statement so they are in the same class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6988-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6988-108">See also</span></span>

- [<span data-ttu-id="c6988-109">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="c6988-109">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="c6988-110">Istruzione RaiseEvent</span><span class="sxs-lookup"><span data-stu-id="c6988-110">RaiseEvent Statement</span></span>](../statements/raiseevent-statement.md)
