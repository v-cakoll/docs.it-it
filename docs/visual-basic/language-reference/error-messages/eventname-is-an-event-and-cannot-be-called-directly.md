---
title: "'<eventname>' è un evento e non può essere chiamato direttamente"
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 510fff5370e63a31ee271421c0ab6f154518899f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409595"
---
# <a name="eventname-is-an-event-and-cannot-be-called-directly"></a><span data-ttu-id="6b85b-102">'\<eventname>' è un evento e non può essere chiamato direttamente</span><span class="sxs-lookup"><span data-stu-id="6b85b-102">'\<eventname>' is an event, and cannot be called directly</span></span>
<span data-ttu-id="6b85b-103">' <`eventname`>' è un evento e non può essere chiamato direttamente.</span><span class="sxs-lookup"><span data-stu-id="6b85b-103">'<`eventname`>' is an event, and so cannot be called directly.</span></span> <span data-ttu-id="6b85b-104">Utilizzare un' `RaiseEvent` istruzione per generare un evento.</span><span class="sxs-lookup"><span data-stu-id="6b85b-104">Use a `RaiseEvent` statement to raise an event.</span></span>  
  
 <span data-ttu-id="6b85b-105">Una chiamata di routine specifica un evento per il nome della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="6b85b-105">A procedure call specifies an event for the procedure name.</span></span> <span data-ttu-id="6b85b-106">Un gestore eventi è una routine, ma l'evento stesso è un dispositivo di segnalazione, che deve essere generato e gestito.</span><span class="sxs-lookup"><span data-stu-id="6b85b-106">An event handler is a procedure, but the event itself is a signaling device, which must be raised and handled.</span></span>  
  
 <span data-ttu-id="6b85b-107">**ID errore:** BC32022</span><span class="sxs-lookup"><span data-stu-id="6b85b-107">**Error ID:** BC32022</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6b85b-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="6b85b-108">To correct this error</span></span>  
  
1. <span data-ttu-id="6b85b-109">Utilizzare un' `RaiseEvent` istruzione per segnalare un evento e richiamare la procedura o le procedure che la gestiscono.</span><span class="sxs-lookup"><span data-stu-id="6b85b-109">Use a `RaiseEvent` statement to signal an event and invoke the procedure or procedures that handle it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b85b-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b85b-110">See also</span></span>

- [<span data-ttu-id="6b85b-111">Istruzione RaiseEvent</span><span class="sxs-lookup"><span data-stu-id="6b85b-111">RaiseEvent Statement</span></span>](../statements/raiseevent-statement.md)
