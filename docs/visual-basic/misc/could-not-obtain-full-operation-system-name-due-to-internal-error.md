---
title: Errore interno. Impossibile ottenere il nome completo del sistema operativo
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
ms.openlocfilehash: 67e8fb5e906800d28bf15714463b7ff6ae585693
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402278"
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a><span data-ttu-id="fd1d0-102">Errore interno. Impossibile ottenere il nome completo del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="fd1d0-102">Could not obtain full operation system name due to internal error</span></span>
<span data-ttu-id="fd1d0-103">Errore interno. Impossibile ottenere il nome completo del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="fd1d0-103">Could not obtain full operation system name due to internal error.</span></span> <span data-ttu-id="fd1d0-104">WMI potrebbe non essere presente sul computer in uso.</span><span class="sxs-lookup"><span data-stu-id="fd1d0-104">This might be caused by WMI not existing on the current machine.</span></span>  
  
 <span data-ttu-id="fd1d0-105">Una chiamata alla proprietà `My.Computer.Info.OSFullName` non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="fd1d0-105">A call to the `My.Computer.Info.OSFullName` property failed.</span></span> <span data-ttu-id="fd1d0-106">L'errore può derivare dal fatto che Strumentazione gestione Windows (WMI) non è installato nel computer corrente.</span><span class="sxs-lookup"><span data-stu-id="fd1d0-106">A possible cause for this failure is if Windows Management Instrumentation (WMI) is not installed on the current computer.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fd1d0-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="fd1d0-107">To correct this error</span></span>  
  
1. <span data-ttu-id="fd1d0-108">Aggiungere un blocco `Try...Catch` nella chiamata alla proprietà `My.Computer.Info.OSFullName` .</span><span class="sxs-lookup"><span data-stu-id="fd1d0-108">Add a `Try...Catch` block around the call to the `My.Computer.Info.OSFullName` property.</span></span>  
  
2. <span data-ttu-id="fd1d0-109">Per ulteriori informazioni su WMI e su come installarlo, vedere e cercare "Strumentazione gestione Windows Core".</span><span class="sxs-lookup"><span data-stu-id="fd1d0-109">For more information about WMI and how to install it, go to  and search for "Windows Management Instrumentation Core".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd1d0-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd1d0-110">See also</span></span>

- [<span data-ttu-id="fd1d0-111">My. computer. info. OSFullName</span><span class="sxs-lookup"><span data-stu-id="fd1d0-111">My.Computer.Info.OSFullName</span></span>](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)
- [<span data-ttu-id="fd1d0-112">Gestione e generazione di eccezioni in .NET</span><span class="sxs-lookup"><span data-stu-id="fd1d0-112">Handling and throwing exceptions in .NET</span></span>](../../standard/exceptions/index.md)
- [<span data-ttu-id="fd1d0-113">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="fd1d0-113">Try...Catch...Finally Statement</span></span>](../language-reference/statements/try-catch-finally-statement.md)
