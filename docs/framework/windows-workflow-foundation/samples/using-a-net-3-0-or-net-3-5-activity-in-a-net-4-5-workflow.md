---
title: Utilizzo di un'attività di .NET Framework 3.0 o .NET Framework 3.5 in un flusso di lavoro di .NET Framework 4.5
ms.date: 03/30/2017
ms.assetid: 6c53fd4c-5dd0-4fb4-ab6b-111302629548
ms.openlocfilehash: ab2e93918617bd1ca21fb32878d446db0dd2ef16
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33514899"
---
# <a name="using-a-net-framework-30-or-net-framework-35-activity-in-a-net-framework-45-workflow"></a><span data-ttu-id="998be-102">Utilizzo di un'attività di .NET Framework 3.0 o .NET Framework 3.5 in un flusso di lavoro di .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="998be-102">Using a .NET Framework 3.0 or .NET Framework 3.5 Activity in a .NET Framework 4.5 Workflow</span></span>
<span data-ttu-id="998be-103">Il <xref:System.Activities.Statements.Interop> attività consente di eseguire un'attività di .NET Framework 3.0 Windows Workflow Foundation (WF) all'interno di un [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="998be-103">The <xref:System.Activities.Statements.Interop> activity allows you to run a .NET Framework 3.0 Windows Workflow Foundation (WF) activity within a [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] workflow.</span></span> <span data-ttu-id="998be-104">In questo esempio viene illustrato come usare l'attività <xref:System.Activities.Statements.Interop> per passare una stringa come argomento a un'attività [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] personalizzata.</span><span class="sxs-lookup"><span data-stu-id="998be-104">This sample demonstrates how to use the <xref:System.Activities.Statements.Interop> activity to pass a string as an argument to a custom [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] activity.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="998be-105">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="998be-105">To use this sample</span></span>  
  
1.  <span data-ttu-id="998be-106">In [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] aprire il file della soluzione SimpleInterop.sln.</span><span class="sxs-lookup"><span data-stu-id="998be-106">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the SimpleInterop.sln solution file.</span></span>  
  
2.  <span data-ttu-id="998be-107">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="998be-107">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="998be-108">Per eseguire la soluzione, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="998be-108">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="998be-109">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="998be-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="998be-110">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="998be-110">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="998be-111">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="998be-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="998be-112">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="998be-112">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\SimpleInterop`  
  
## <a name="see-also"></a><span data-ttu-id="998be-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="998be-113">See Also</span></span>
