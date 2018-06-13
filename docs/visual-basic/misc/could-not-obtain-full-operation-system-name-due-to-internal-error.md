---
title: Errore interno. Impossibile ottenere il nome completo del sistema operativo
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
ms.openlocfilehash: f85ca5f7f325cb0dd2b8fc55d3f90f6abdfd4a7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33635077"
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a><span data-ttu-id="ff4c3-102">Errore interno. Impossibile ottenere il nome completo del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="ff4c3-102">Could not obtain full operation system name due to internal error</span></span>
<span data-ttu-id="ff4c3-103">Errore interno. Impossibile ottenere il nome completo del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ff4c3-103">Could not obtain full operation system name due to internal error.</span></span> <span data-ttu-id="ff4c3-104">WMI potrebbe non essere presente sul computer in uso.</span><span class="sxs-lookup"><span data-stu-id="ff4c3-104">This might be caused by WMI not existing on the current machine.</span></span>  
  
 <span data-ttu-id="ff4c3-105">Una chiamata alla proprietà `My.Computer.Info.OSFullName` non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="ff4c3-105">A call to the `My.Computer.Info.OSFullName` property failed.</span></span> <span data-ttu-id="ff4c3-106">L'errore può derivare dal fatto che Strumentazione gestione Windows (WMI) non è installato nel computer corrente.</span><span class="sxs-lookup"><span data-stu-id="ff4c3-106">A possible cause for this failure is if Windows Management Instrumentation (WMI) is not installed on the current computer.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ff4c3-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="ff4c3-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="ff4c3-108">Aggiungere un blocco `Try...Catch` nella chiamata alla proprietà `My.Computer.Info.OSFullName` .</span><span class="sxs-lookup"><span data-stu-id="ff4c3-108">Add a `Try...Catch` block around the call to the `My.Computer.Info.OSFullName` property.</span></span>  
  
2.  <span data-ttu-id="ff4c3-109">Per ulteriori informazioni su WMI e su come installarlo, passare a e cercare "Windows Management Instrumentation Core".</span><span class="sxs-lookup"><span data-stu-id="ff4c3-109">For more information about WMI and how to install it, go to  and search for "Windows Management Instrumentation Core".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff4c3-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff4c3-110">See Also</span></span>  
 [<span data-ttu-id="ff4c3-111">My.Computer.Info.OSFullName</span><span class="sxs-lookup"><span data-stu-id="ff4c3-111">My.Computer.Info.OSFullName</span></span>](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)  
 [<span data-ttu-id="ff4c3-112">Eccezioni e gestione degli errori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ff4c3-112">Exception and Error Handling in Visual Basic</span></span>](http://msdn.microsoft.com/library/3e351e73-cf23-40ab-8b60-05794160529e)  
 [<span data-ttu-id="ff4c3-113">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="ff4c3-113">Try...Catch...Finally Statement</span></span>](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
