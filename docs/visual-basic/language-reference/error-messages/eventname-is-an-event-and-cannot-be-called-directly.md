---
title: "'<eventname>' è un evento e non può essere chiamato direttamente"
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 4e27d9ce788ae7b9741c0cb80da776959748b8b9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55272719"
---
# <a name="eventname-is-an-event-and-cannot-be-called-directly"></a><span data-ttu-id="e78eb-102">'\<NomeEvento >' è un evento e non può essere chiamato direttamente</span><span class="sxs-lookup"><span data-stu-id="e78eb-102">'\<eventname>' is an event, and cannot be called directly</span></span>
<span data-ttu-id="e78eb-103">' <`eventname`>' è un evento e non può essere chiamato direttamente.</span><span class="sxs-lookup"><span data-stu-id="e78eb-103">'<`eventname`>' is an event, and so cannot be called directly.</span></span> <span data-ttu-id="e78eb-104">Usare un `RaiseEvent` istruzione per generare un evento.</span><span class="sxs-lookup"><span data-stu-id="e78eb-104">Use a `RaiseEvent` statement to raise an event.</span></span>  
  
 <span data-ttu-id="e78eb-105">Una chiamata di routine specifica un evento per il nome della routine.</span><span class="sxs-lookup"><span data-stu-id="e78eb-105">A procedure call specifies an event for the procedure name.</span></span> <span data-ttu-id="e78eb-106">Un gestore di è una procedura, ma l'evento stesso è un dispositivo di segnalazione, che deve essere generato e gestito.</span><span class="sxs-lookup"><span data-stu-id="e78eb-106">An event handler is a procedure, but the event itself is a signaling device, which must be raised and handled.</span></span>  
  
 <span data-ttu-id="e78eb-107">**ID errore:** BC32022</span><span class="sxs-lookup"><span data-stu-id="e78eb-107">**Error ID:** BC32022</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e78eb-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="e78eb-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="e78eb-109">Usare un `RaiseEvent` istruzione per segnalare un evento e richiamare la routine o una routine che gestiscono.</span><span class="sxs-lookup"><span data-stu-id="e78eb-109">Use a `RaiseEvent` statement to signal an event and invoke the procedure or procedures that handle it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e78eb-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e78eb-110">See also</span></span>
- [<span data-ttu-id="e78eb-111">Istruzione RaiseEvent</span><span class="sxs-lookup"><span data-stu-id="e78eb-111">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
