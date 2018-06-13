---
title: Le classi derivate non possono generare eventi di classe base
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 365ce6ece1d964d3fac2a44f7ed4c1e16f44c95d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586399"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a><span data-ttu-id="04d12-102">Le classi derivate non possono generare eventi di classe base</span><span class="sxs-lookup"><span data-stu-id="04d12-102">Derived classes cannot raise base class events</span></span>
<span data-ttu-id="04d12-103">Un evento può essere generato solo dallo spazio di dichiarazione in cui viene dichiarato.</span><span class="sxs-lookup"><span data-stu-id="04d12-103">An event can be raised only from the declaration space in which it is declared.</span></span> <span data-ttu-id="04d12-104">Pertanto, una classe non può generare eventi da qualsiasi altra classe, uno da cui deriva.</span><span class="sxs-lookup"><span data-stu-id="04d12-104">Therefore, a class cannot raise events from any other class, even one from which it is derived.</span></span>  
  
 <span data-ttu-id="04d12-105">**ID errore:** BC30029</span><span class="sxs-lookup"><span data-stu-id="04d12-105">**Error ID:** BC30029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="04d12-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="04d12-106">To correct this error</span></span>  
  
-   <span data-ttu-id="04d12-107">Spostare il `Event` istruzione o `RaiseEvent` istruzione in modo che siano della stessa classe.</span><span class="sxs-lookup"><span data-stu-id="04d12-107">Move the `Event` statement or the `RaiseEvent` statement so they are in the same class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04d12-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04d12-108">See Also</span></span>  
 [<span data-ttu-id="04d12-109">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="04d12-109">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="04d12-110">Istruzione RaiseEvent</span><span class="sxs-lookup"><span data-stu-id="04d12-110">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
