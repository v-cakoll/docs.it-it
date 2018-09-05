---
title: Proprietà di esecuzione
ms.date: 03/30/2017
ms.assetid: 31c009db-397c-4653-87e2-32dc77fa4b13
ms.openlocfilehash: 4906c2ad11c8b5822764435d2b39a5b51f2673ba
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43748194"
---
# <a name="execution-properties"></a><span data-ttu-id="0aa37-102">Proprietà di esecuzione</span><span class="sxs-lookup"><span data-stu-id="0aa37-102">Execution Properties</span></span>
<span data-ttu-id="0aa37-103">In questo esempio viene illustrato come definire e usare una proprietà di esecuzione in un'attività personalizzata.</span><span class="sxs-lookup"><span data-stu-id="0aa37-103">This sample shows how to define and use an execution property in a custom activity.</span></span> <span data-ttu-id="0aa37-104">In questo esempio la proprietà di esecuzione determina il colore di primo piano della console.</span><span class="sxs-lookup"><span data-stu-id="0aa37-104">In this example, the execution property determines the console's foreground color.</span></span> <span data-ttu-id="0aa37-105">Un flusso di lavoro di esempio illustra come i diversi percorsi logici di esecuzione (rami di un'attività <xref:System.Activities.Statements.Parallel> ) possono gestire diversi colori della console nonostante esecuzione interleave delle attività (attraverso i rami dell'attività <xref:System.Activities.Statements.Parallel> ).</span><span class="sxs-lookup"><span data-stu-id="0aa37-105">An example workflow shows how different logical paths of execution (branches of a <xref:System.Activities.Statements.Parallel> activity) can maintain different console colors despite interleaved execution of activities (across the branches of the <xref:System.Activities.Statements.Parallel> activity).</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0aa37-106">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="0aa37-106">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="0aa37-107">Aprire la soluzione di esempio ExecutionProperties.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0aa37-107">Open the ExecutionProperties.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0aa37-108">Se si visualizza ThreeColors.xaml prima di compilare la soluzione viene visualizzato un errore, perché le attività personalizzate usate devono essere compilate contemporaneamente alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="0aa37-108">Viewing ThreeColors.xaml before building the solution displays an error, because the custom activities used must be built at the same time as the solution.</span></span>  
  
2.  <span data-ttu-id="0aa37-109">Compilare ed eseguire la soluzione.</span><span class="sxs-lookup"><span data-stu-id="0aa37-109">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0aa37-110">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="0aa37-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0aa37-111">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="0aa37-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0aa37-112">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="0aa37-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0aa37-113">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="0aa37-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ExecutionProperties`