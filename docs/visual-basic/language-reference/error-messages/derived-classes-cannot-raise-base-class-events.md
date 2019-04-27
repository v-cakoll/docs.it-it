---
title: Le classi derivate non possono generare eventi di classe base
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 0e9acf4b3e71295655c15ae9b1c80852c9aca8df
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803571"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a><span data-ttu-id="48c0b-102">Le classi derivate non possono generare eventi di classe base</span><span class="sxs-lookup"><span data-stu-id="48c0b-102">Derived classes cannot raise base class events</span></span>
<span data-ttu-id="48c0b-103">Un evento può essere generato solo dallo spazio di dichiarazione in cui è dichiarata.</span><span class="sxs-lookup"><span data-stu-id="48c0b-103">An event can be raised only from the declaration space in which it is declared.</span></span> <span data-ttu-id="48c0b-104">Di conseguenza, una classe non può generare eventi da qualsiasi altra classe, anche uno solo da cui è derivato.</span><span class="sxs-lookup"><span data-stu-id="48c0b-104">Therefore, a class cannot raise events from any other class, even one from which it is derived.</span></span>  
  
 <span data-ttu-id="48c0b-105">**ID errore:** BC30029</span><span class="sxs-lookup"><span data-stu-id="48c0b-105">**Error ID:** BC30029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="48c0b-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="48c0b-106">To correct this error</span></span>  
  
-   <span data-ttu-id="48c0b-107">Spostare il `Event` istruzione o il `RaiseEvent` istruzione in modo che siano nella stessa classe.</span><span class="sxs-lookup"><span data-stu-id="48c0b-107">Move the `Event` statement or the `RaiseEvent` statement so they are in the same class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48c0b-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48c0b-108">See also</span></span>

- [<span data-ttu-id="48c0b-109">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="48c0b-109">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="48c0b-110">Istruzione RaiseEvent</span><span class="sxs-lookup"><span data-stu-id="48c0b-110">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
