---
title: Errore interno. Impossibile ottenere il nome completo del sistema operativo
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
ms.openlocfilehash: 192033348a779591a54860505d5d707a802c415a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43560899"
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a><span data-ttu-id="5f9e4-102">Errore interno. Impossibile ottenere il nome completo del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="5f9e4-102">Could not obtain full operation system name due to internal error</span></span>
<span data-ttu-id="5f9e4-103">Errore interno. Impossibile ottenere il nome completo del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5f9e4-103">Could not obtain full operation system name due to internal error.</span></span> <span data-ttu-id="5f9e4-104">WMI potrebbe non essere presente sul computer in uso.</span><span class="sxs-lookup"><span data-stu-id="5f9e4-104">This might be caused by WMI not existing on the current machine.</span></span>  
  
 <span data-ttu-id="5f9e4-105">Una chiamata alla proprietà `My.Computer.Info.OSFullName` non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="5f9e4-105">A call to the `My.Computer.Info.OSFullName` property failed.</span></span> <span data-ttu-id="5f9e4-106">L'errore può derivare dal fatto che Strumentazione gestione Windows (WMI) non è installato nel computer corrente.</span><span class="sxs-lookup"><span data-stu-id="5f9e4-106">A possible cause for this failure is if Windows Management Instrumentation (WMI) is not installed on the current computer.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5f9e4-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="5f9e4-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="5f9e4-108">Aggiungere un blocco `Try...Catch` nella chiamata alla proprietà `My.Computer.Info.OSFullName` .</span><span class="sxs-lookup"><span data-stu-id="5f9e4-108">Add a `Try...Catch` block around the call to the `My.Computer.Info.OSFullName` property.</span></span>  
  
2.  <span data-ttu-id="5f9e4-109">Per altre informazioni su WMI e come installarla, passare a e cercare "Windows Management Instrumentation Core".</span><span class="sxs-lookup"><span data-stu-id="5f9e4-109">For more information about WMI and how to install it, go to  and search for "Windows Management Instrumentation Core".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f9e4-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f9e4-110">See Also</span></span>  
 [<span data-ttu-id="5f9e4-111">My.Computer.Info.OSFullName</span><span class="sxs-lookup"><span data-stu-id="5f9e4-111">My.Computer.Info.OSFullName</span></span>](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)  
 [<span data-ttu-id="5f9e4-112">Eccezioni e gestione degli errori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5f9e4-112">Exception and Error Handling in Visual Basic</span></span>](https://msdn.microsoft.com/library/3e351e73-cf23-40ab-8b60-05794160529e)  
 [<span data-ttu-id="5f9e4-113">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="5f9e4-113">Try...Catch...Finally Statement</span></span>](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
