---
title: Utilizzo dell'attività Pick
ms.date: 03/30/2017
ms.assetid: b89be812-a247-4025-b0e3-ffb20db027a6
ms.openlocfilehash: 193b60bff7b08c0de9a0957668483eb73be97274
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43784673"
---
# <a name="using-the-pick-activity"></a><span data-ttu-id="4aae0-102">Utilizzo dell'attività Pick</span><span class="sxs-lookup"><span data-stu-id="4aae0-102">Using the Pick Activity</span></span>
<span data-ttu-id="4aae0-103">In questo esempio viene illustrato come usare l'attività <xref:System.Activities.Statements.Pick>.</span><span class="sxs-lookup"><span data-stu-id="4aae0-103">This sample demonstrates how to use the <xref:System.Activities.Statements.Pick> activity.</span></span>  
  
 <span data-ttu-id="4aae0-104">L'attività <xref:System.Activities.Statements.Pick> fornisce il modello di controllo basato sugli eventi</span><span class="sxs-lookup"><span data-stu-id="4aae0-104">The <xref:System.Activities.Statements.Pick> activity provides event-based control modeling.</span></span> <span data-ttu-id="4aae0-105">il cui comportamento è analogo a quello dell'istruzione C# `switch`, che esegue solo uno dei rami nell'istruzione `switch`.</span><span class="sxs-lookup"><span data-stu-id="4aae0-105">It behaves similar to the C# `switch` statement, which executes only one of the branches in the `switch` statement.</span></span> <span data-ttu-id="4aae0-106">A differenza dell'istruzione `switch` in cui l'esecuzione di un ramo viene effettuata in base a un valore, l'attività <xref:System.Activities.Statements.Pick> esegue un ramo in base alla modalità di completamento di un'attività.</span><span class="sxs-lookup"><span data-stu-id="4aae0-106">Unlike the `switch` statement in which a branch is executed based upon on a value, the <xref:System.Activities.Statements.Pick> activity executes a branch based upon how an activity completes.</span></span>  
  
 <span data-ttu-id="4aae0-107">In questo esempio un utente deve digitare il nome nella console entro un periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="4aae0-107">This sample prompts a user to type in their name on the console within a given time period.</span></span> <span data-ttu-id="4aae0-108">L'attività <xref:System.Activities.Statements.Pick> nell'esempio dispone di due rami eseguiti in base al fatto che l'utente abbia o meno digitato il nome entro 5 secondi.</span><span class="sxs-lookup"><span data-stu-id="4aae0-108">The <xref:System.Activities.Statements.Pick> activity in the sample has two branches that are executed based upon whether the user types in their name within 5 seconds or not.</span></span> <span data-ttu-id="4aae0-109">Se l'utente digita il nome nei 5 secondi, viene eseguito il primo ramo che contiene un'attività `ReadLine` personalizzata; in caso contrario, viene eseguito l'altro ramo che contiene un'attività <xref:System.Activities.Statements.Delay>.</span><span class="sxs-lookup"><span data-stu-id="4aae0-109">If the user types in their name within 5 seconds, the first branch is executed, which contains a custom `ReadLine` activity; otherwise the other branch is executed, which contains a <xref:System.Activities.Statements.Delay> activity.</span></span> <span data-ttu-id="4aae0-110">Una volta digitato nella console, il nome dell'utente viene stampato nella console.</span><span class="sxs-lookup"><span data-stu-id="4aae0-110">Once a user’s name is typed in on the console, the user’s name is printed on the console.</span></span> <span data-ttu-id="4aae0-111">Se un input non viene immesso entro 5 secondi, l'operazione è scaduta.</span><span class="sxs-lookup"><span data-stu-id="4aae0-111">If an input is not entered within 5 seconds, the operation is timed out.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="4aae0-112">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="4aae0-112">Demonstrates</span></span>  
 <span data-ttu-id="4aae0-113">Attività <xref:System.Activities.Statements.Pick></span><span class="sxs-lookup"><span data-stu-id="4aae0-113"><xref:System.Activities.Statements.Pick> activity.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="4aae0-114">Discussione</span><span class="sxs-lookup"><span data-stu-id="4aae0-114">Discussion</span></span>  
 <span data-ttu-id="4aae0-115">Nell'esempio è incluso un flusso di lavoro della finestra di progettazione e un flusso di lavoro codificato.</span><span class="sxs-lookup"><span data-stu-id="4aae0-115">The sample includes a Designer workflow and coded workflow.</span></span>  
  
 <span data-ttu-id="4aae0-116">Flusso di lavoro della finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="4aae0-116">Designer Workflow</span></span>  
 <span data-ttu-id="4aae0-117">Nella versione della finestra di progettazione dell'esempio viene illustrato come creare un flusso di lavoro nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="4aae0-117">The Designer version of the sample demonstrates how to create a workflow in the designer.</span></span> <span data-ttu-id="4aae0-118">Sono inclusi i file seguenti:</span><span class="sxs-lookup"><span data-stu-id="4aae0-118">The following files are included:</span></span>  
  
-   <span data-ttu-id="4aae0-119">Program.cs: include la funzione `Main` che esegue il flusso di lavoro di esempio.</span><span class="sxs-lookup"><span data-stu-id="4aae0-119">Program.cs : Includes the `Main` function that executes the sample workflow.</span></span>  
  
-   <span data-ttu-id="4aae0-120">ReadString.cs: attività personalizzata che legge alcuni input dalla console.</span><span class="sxs-lookup"><span data-stu-id="4aae0-120">ReadString.cs: A custom activity that reads some input from the console.</span></span>  
  
-   <span data-ttu-id="4aae0-121">Sequence1.xaml: flusso di lavoro creato tramite la finestra di progettazione usata da Pick.</span><span class="sxs-lookup"><span data-stu-id="4aae0-121">Sequence1.xaml: A workflow created using the designer that uses Pick.</span></span>  
  
 <span data-ttu-id="4aae0-122">Flusso di lavoro codificato</span><span class="sxs-lookup"><span data-stu-id="4aae0-122">Coded Workflow</span></span>  
 <span data-ttu-id="4aae0-123">Nella versione codificata dell'esempio viene illustrato come creare un flusso di lavoro nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="4aae0-123">The coded version of the sample demonstrates how to create a workflow in the designer.</span></span> <span data-ttu-id="4aae0-124">Sono inclusi i file seguenti:</span><span class="sxs-lookup"><span data-stu-id="4aae0-124">The following files are included:</span></span>  
  
-   <span data-ttu-id="4aae0-125">Program.cs: include la funzione `Main` che esegue il flusso di lavoro di esempio.</span><span class="sxs-lookup"><span data-stu-id="4aae0-125">Program.cs : Includes the `Main` function that executes the sample workflow.</span></span>  
  
-   <span data-ttu-id="4aae0-126">ReadString.cs: attività personalizzata che legge alcuni input dalla console.</span><span class="sxs-lookup"><span data-stu-id="4aae0-126">ReadString.cs: A custom activity that reads some input from the console.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="4aae0-127">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="4aae0-127">To use this sample</span></span>  
  
1.  <span data-ttu-id="4aae0-128">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione Pick.sln.</span><span class="sxs-lookup"><span data-stu-id="4aae0-128">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the Pick.sln solution file.</span></span>  
  
2.  <span data-ttu-id="4aae0-129">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="4aae0-129">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="4aae0-130">Per eseguire la soluzione, premere F5.</span><span class="sxs-lookup"><span data-stu-id="4aae0-130">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4aae0-131">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="4aae0-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4aae0-132">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="4aae0-132">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4aae0-133">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="4aae0-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4aae0-134">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="4aae0-134">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Pick`