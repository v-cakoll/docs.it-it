---
title: '&#39;&lt;EventName&gt; &#39; è un evento e non può essere chiamato direttamente'
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 4d8a7d716d2b7c52d1d027a1e7959d981bb0857e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587332"
---
# <a name="39lteventnamegt39-is-an-event-and-cannot-be-called-directly"></a><span data-ttu-id="63e11-102">&#39;&lt;EventName&gt; &#39; è un evento e non può essere chiamato direttamente</span><span class="sxs-lookup"><span data-stu-id="63e11-102">&#39;&lt;eventname&gt;&#39; is an event, and cannot be called directly</span></span>
<span data-ttu-id="63e11-103">' <`eventname`>' è un evento e non può essere chiamato direttamente.</span><span class="sxs-lookup"><span data-stu-id="63e11-103">'<`eventname`>' is an event, and so cannot be called directly.</span></span> <span data-ttu-id="63e11-104">Utilizzare un `RaiseEvent` istruzione per generare un evento.</span><span class="sxs-lookup"><span data-stu-id="63e11-104">Use a `RaiseEvent` statement to raise an event.</span></span>  
  
 <span data-ttu-id="63e11-105">Una chiamata di procedura specifica un evento per il nome della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="63e11-105">A procedure call specifies an event for the procedure name.</span></span> <span data-ttu-id="63e11-106">Un gestore eventi è una procedura, ma l'evento è un dispositivo di segnalazione, che deve essere generato e gestito.</span><span class="sxs-lookup"><span data-stu-id="63e11-106">An event handler is a procedure, but the event itself is a signaling device, which must be raised and handled.</span></span>  
  
 <span data-ttu-id="63e11-107">**ID errore:** BC32022</span><span class="sxs-lookup"><span data-stu-id="63e11-107">**Error ID:** BC32022</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="63e11-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="63e11-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="63e11-109">Utilizzare un `RaiseEvent` istruzione per segnalare un evento e richiamare la routine o una routine che gestiscono.</span><span class="sxs-lookup"><span data-stu-id="63e11-109">Use a `RaiseEvent` statement to signal an event and invoke the procedure or procedures that handle it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63e11-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63e11-110">See Also</span></span>  
 [<span data-ttu-id="63e11-111">Istruzione RaiseEvent</span><span class="sxs-lookup"><span data-stu-id="63e11-111">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
