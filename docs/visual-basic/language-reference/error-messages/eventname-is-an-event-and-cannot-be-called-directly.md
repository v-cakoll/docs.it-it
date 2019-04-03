---
title: "'<eventname>' è un evento e non può essere chiamato direttamente"
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: eb0b40a80d37788bcab32791d7ed701a77505371
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58831444"
---
# <a name="eventname-is-an-event-and-cannot-be-called-directly"></a><span data-ttu-id="968da-102">'\<NomeEvento >' è un evento e non può essere chiamato direttamente</span><span class="sxs-lookup"><span data-stu-id="968da-102">'\<eventname>' is an event, and cannot be called directly</span></span>
<span data-ttu-id="968da-103">' <`eventname`>' è un evento e non può essere chiamato direttamente.</span><span class="sxs-lookup"><span data-stu-id="968da-103">'<`eventname`>' is an event, and so cannot be called directly.</span></span> <span data-ttu-id="968da-104">Usare un `RaiseEvent` istruzione per generare un evento.</span><span class="sxs-lookup"><span data-stu-id="968da-104">Use a `RaiseEvent` statement to raise an event.</span></span>  
  
 <span data-ttu-id="968da-105">Una chiamata di routine specifica un evento per il nome della routine.</span><span class="sxs-lookup"><span data-stu-id="968da-105">A procedure call specifies an event for the procedure name.</span></span> <span data-ttu-id="968da-106">Un gestore di è una procedura, ma l'evento stesso è un dispositivo di segnalazione, che deve essere generato e gestito.</span><span class="sxs-lookup"><span data-stu-id="968da-106">An event handler is a procedure, but the event itself is a signaling device, which must be raised and handled.</span></span>  
  
 <span data-ttu-id="968da-107">**ID errore:** BC32022</span><span class="sxs-lookup"><span data-stu-id="968da-107">**Error ID:** BC32022</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="968da-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="968da-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="968da-109">Usare un `RaiseEvent` istruzione per segnalare un evento e richiamare la routine o una routine che gestiscono.</span><span class="sxs-lookup"><span data-stu-id="968da-109">Use a `RaiseEvent` statement to signal an event and invoke the procedure or procedures that handle it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="968da-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="968da-110">See also</span></span>

- [<span data-ttu-id="968da-111">Istruzione RaiseEvent</span><span class="sxs-lookup"><span data-stu-id="968da-111">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
