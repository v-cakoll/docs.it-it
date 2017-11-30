---
title: ThrottledParallelForEach
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2855b5f-e9a7-433d-96a4-40fc31025215
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7155c4f33cb29c5778e59124dd924005e4ef52f6
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2017
---
# <a name="throttled-parallel-foreach"></a><span data-ttu-id="1b649-102">ThrottledParallelForEach</span><span class="sxs-lookup"><span data-stu-id="1b649-102">Throttled Parallel ForEach</span></span>
<span data-ttu-id="1b649-103">Il `ThrottleParallelForEach` è simile all'attività di <!--zz <xref:System.Activities.Statements.ParallelForEach>--> `System.Activities.Statements.ParallelForEach` attività con l'unica eccezione che consente l'impostazione di un fattore di concorrenza per limitare il numero di rami simultanei da eseguire.</span><span class="sxs-lookup"><span data-stu-id="1b649-103">The `ThrottleParallelForEach` activity is similar to the <!--zz <xref:System.Activities.Statements.ParallelForEach>--> `System.Activities.Statements.ParallelForEach` activity with the one exception that it allows setting a concurrency factor to restrict the number of simultaneous branches to execute.</span></span> <span data-ttu-id="1b649-104">L'attività `ThrottleParallelForEach` deriva dall'oggetto <xref:System.Activities.NativeActivity>, poiché deve pianificare altre attività (le attività figlio) ed è accessibile solo tramite la classe <xref:System.Activities.NativeActivityContext>.</span><span class="sxs-lookup"><span data-stu-id="1b649-104">The `ThrottleParallelForEach` activity derives from <xref:System.Activities.NativeActivity>, because it needs to schedule other activities (the child activities) and this is only accessible through the <xref:System.Activities.NativeActivityContext> class.</span></span>  
  
## <a name="projects"></a><span data-ttu-id="1b649-105">Progetti</span><span class="sxs-lookup"><span data-stu-id="1b649-105">Projects</span></span>  
  
|<span data-ttu-id="1b649-106">**ProjectName**</span><span class="sxs-lookup"><span data-stu-id="1b649-106">**ProjectName**</span></span>|<span data-ttu-id="1b649-107">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="1b649-107">**Description**</span></span>|<span data-ttu-id="1b649-108">**File principali**</span><span class="sxs-lookup"><span data-stu-id="1b649-108">**Main Files**</span></span>|  
|-|-|-|  
|<span data-ttu-id="1b649-109">ThrottledParallelForEach</span><span class="sxs-lookup"><span data-stu-id="1b649-109">ThrottledParallelForEach</span></span>|<span data-ttu-id="1b649-110">Contiene l'attività `ThrottledParallelForEach` e la relativa finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="1b649-110">Contains `ThrottledParallelForEach` activity and its designer.</span></span>|<span data-ttu-id="1b649-111">ThrottledParallelForEach.cs</span><span class="sxs-lookup"><span data-stu-id="1b649-111">ThrottledParallelForEach.cs</span></span><br /><br /> <span data-ttu-id="1b649-112">Definizione dell'attività `ThrottledParallelForEach`.</span><span class="sxs-lookup"><span data-stu-id="1b649-112">The `ThrottledParallelForEach` activity definition.</span></span>|  
|<span data-ttu-id="1b649-113">CodeTestClient</span><span class="sxs-lookup"><span data-stu-id="1b649-113">CodeTestClient</span></span>|<span data-ttu-id="1b649-114">Applicazione client di esempio che configura ed esegue un flusso di lavoro con un oggetto `ThrottledParallelForEach` usando il codice imperativo.</span><span class="sxs-lookup"><span data-stu-id="1b649-114">Sample client application that configures and runs a workflow with a `ThrottledParallelForEach` using imperative code.</span></span>|<span data-ttu-id="1b649-115">Program.cs</span><span class="sxs-lookup"><span data-stu-id="1b649-115">Program.cs</span></span><br /><br /> <span data-ttu-id="1b649-116">Definisce ed esegue un'istanza del flusso di lavoro di esempio.</span><span class="sxs-lookup"><span data-stu-id="1b649-116">Defines and runs an instance of the sample workflow.</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="1b649-117">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="1b649-117">To use this sample</span></span>  
  
1.  <span data-ttu-id="1b649-118">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione ThrottledParallelForEach.sln.</span><span class="sxs-lookup"><span data-stu-id="1b649-118">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ThrottledParallelForEach.sln file.</span></span>  
  
2.  <span data-ttu-id="1b649-119">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="1b649-119">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="1b649-120">Per eseguire la soluzione, premere F5.</span><span class="sxs-lookup"><span data-stu-id="1b649-120">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1b649-121">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="1b649-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1b649-122">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="1b649-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="1b649-123">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1b649-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1b649-124">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="1b649-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\ThrottledParallelForEach`