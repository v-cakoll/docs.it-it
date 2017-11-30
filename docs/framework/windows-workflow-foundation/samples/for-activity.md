---
title: "Attività For"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ea751b4-36f0-48aa-a115-70a2ab89f6d8
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c8567eb848fbb7b5f6c68f52f1be78750a002411
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="for-activity"></a><span data-ttu-id="477f8-102">Attività For</span><span class="sxs-lookup"><span data-stu-id="477f8-102">For Activity</span></span>
<span data-ttu-id="477f8-103">Nell'esempio For viene illustrato come compilare un'attività personalizzata che eredita da <xref:System.Activities.NativeActivity> e usarla in un flusso di lavoro per eseguire un esempio reale.</span><span class="sxs-lookup"><span data-stu-id="477f8-103">The For sample demonstrates how to build a custom activity that inherits from <xref:System.Activities.NativeActivity>, and use it in a workflow to execute a real world example.</span></span> <span data-ttu-id="477f8-104">L'attività personalizzata inclusa in questo esempio funziona come l'istruzione `for` di C#.</span><span class="sxs-lookup"><span data-stu-id="477f8-104">The custom activity included in this sample functions like the C# `for` statement.</span></span> <span data-ttu-id="477f8-105">T</span><span class="sxs-lookup"><span data-stu-id="477f8-105">T</span></span>  
  
 <span data-ttu-id="477f8-106">L'attività personalizzata `For` dispone di proprietà denominate `InitAction`, `IterationAction`, `Condition` e `Body` che corrispondono rispettivamente all'istruzione dell'inizializzazione, all'istruzione iterativa, alla condizione di continuazione e all'istruzione del corpo disponibili nell'istruzione standard `For` di C#.</span><span class="sxs-lookup"><span data-stu-id="477f8-106">The `For` custom activity has properties named `InitAction`, `IterationAction`, `Condition`, and `Body` that correspond to the initialization statement, iterative statement, continuation condition, and body statement respectively found in the standard C# `For` statement.</span></span>  
  
 <span data-ttu-id="477f8-107">Nella tabella seguente vengono descritti i file principali dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="477f8-107">The following table describes the key files in the sample.</span></span>  
  
|<span data-ttu-id="477f8-108">File</span><span class="sxs-lookup"><span data-stu-id="477f8-108">File</span></span>|<span data-ttu-id="477f8-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="477f8-109">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="477f8-110">For.cs</span><span class="sxs-lookup"><span data-stu-id="477f8-110">For.cs</span></span>|<span data-ttu-id="477f8-111">Definizione di classe per l'attività personalizzata `For` che estende la classe <xref:System.Activities.NativeActivity> per fornire la funzionalità dell'istruzione `For` di C#.</span><span class="sxs-lookup"><span data-stu-id="477f8-111">Class definition for the `For` custom activity, which extends the <xref:System.Activities.NativeActivity> class to provide the functionality of the C# `For` statement.</span></span>|  
|<span data-ttu-id="477f8-112">Program.cs</span><span class="sxs-lookup"><span data-stu-id="477f8-112">Program.cs</span></span>|<span data-ttu-id="477f8-113">Applicazione client che esegue lavoro iterativo di base in una raccolta usando l'attività `For` personalizzata.</span><span class="sxs-lookup"><span data-stu-id="477f8-113">A client application that performs basic iterative work on a collection using the custom `For` activity.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="477f8-114">Quando si usa l'attività personalizzata `For`, assicurarsi che venga impostata la proprietà `Condition`. Diversamente si potrebbe verificare un ciclo infinito.</span><span class="sxs-lookup"><span data-stu-id="477f8-114">When using the `For` custom activity, ensure that the `Condition` property is set; otherwise an infinite loop could occur.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="477f8-115">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="477f8-115">Demonstrates</span></span>  
 <span data-ttu-id="477f8-116">Creare un'attività personalizzata che eredita da <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="477f8-116">Create a custom activity that inherits from <xref:System.Activities.NativeActivity>.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="477f8-117">Discussione</span><span class="sxs-lookup"><span data-stu-id="477f8-117">Discussion</span></span>  
 <span data-ttu-id="477f8-118">Nella tabella seguente sono descritte le proprietà dell'attività inclusa in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="477f8-118">The following table describes the properties of the activity included in this sample.</span></span>  
  
 <span data-ttu-id="477f8-119">InitAction</span><span class="sxs-lookup"><span data-stu-id="477f8-119">InitAction</span></span>  
 <span data-ttu-id="477f8-120">Istruzione di inizializzazione</span><span class="sxs-lookup"><span data-stu-id="477f8-120">Initialization statement</span></span>  
  
 <span data-ttu-id="477f8-121">IterationAction</span><span class="sxs-lookup"><span data-stu-id="477f8-121">IterationAction</span></span>  
 <span data-ttu-id="477f8-122">Istruzione iterativa</span><span class="sxs-lookup"><span data-stu-id="477f8-122">Iterative statement</span></span>  
  
 <span data-ttu-id="477f8-123">Condizione</span><span class="sxs-lookup"><span data-stu-id="477f8-123">Condition</span></span>  
 <span data-ttu-id="477f8-124">Istruzione di continuazione</span><span class="sxs-lookup"><span data-stu-id="477f8-124">Continuation statement</span></span>  
  
 <span data-ttu-id="477f8-125">Corpo</span><span class="sxs-lookup"><span data-stu-id="477f8-125">Body</span></span>  
 <span data-ttu-id="477f8-126">Istruzione del corpo</span><span class="sxs-lookup"><span data-stu-id="477f8-126">Body statement</span></span>  
  
 <span data-ttu-id="477f8-127">L'attività eredita da <xref:System.Activities.NativeActivity> per ottenere l'accesso alle funzionalità di runtime, quale la pianificazione di attività aggiuntive da eseguire, usando uno dei metodi `ScheduleActivity` di <xref:System.Activities.NativeActivityContext>.</span><span class="sxs-lookup"><span data-stu-id="477f8-127">The activity inherits from <xref:System.Activities.NativeActivity> to gain access to runtime features such as scheduling additional activities to run, using one of the `ScheduleActivity` methods of <xref:System.Activities.NativeActivityContext>.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="477f8-128">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="477f8-128">To use this sample</span></span>  
  
1.  <span data-ttu-id="477f8-129">Tramite [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione For.sln.</span><span class="sxs-lookup"><span data-stu-id="477f8-129">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the For.sln solution file.</span></span>  
  
2.  <span data-ttu-id="477f8-130">Premere CTRL+MAIUSC+B per compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="477f8-130">Build the solution, by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="477f8-131">Eseguire la soluzione premendo F5.</span><span class="sxs-lookup"><span data-stu-id="477f8-131">Run the solution, by pressing F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="477f8-132">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="477f8-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="477f8-133">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="477f8-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="477f8-134">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="477f8-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="477f8-135">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="477f8-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\For`  
  
## <a name="see-also"></a><span data-ttu-id="477f8-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="477f8-136">See Also</span></span>
