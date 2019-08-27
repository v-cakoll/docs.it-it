---
title: Utilizzo dell'attività Pick
ms.date: 03/30/2017
ms.assetid: b89be812-a247-4025-b0e3-ffb20db027a6
ms.openlocfilehash: 03b9ff7f552ad0cdcfbe9c46121a2f46f35de52a
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70037873"
---
# <a name="using-the-pick-activity"></a><span data-ttu-id="4c7b1-102">Utilizzo dell'attività Pick</span><span class="sxs-lookup"><span data-stu-id="4c7b1-102">Using the Pick Activity</span></span>
<span data-ttu-id="4c7b1-103">In questo esempio viene illustrato come usare l'attività <xref:System.Activities.Statements.Pick>.</span><span class="sxs-lookup"><span data-stu-id="4c7b1-103">This sample demonstrates how to use the <xref:System.Activities.Statements.Pick> activity.</span></span>

 <span data-ttu-id="4c7b1-104">L'attività <xref:System.Activities.Statements.Pick> fornisce il modello di controllo basato sugli eventi</span><span class="sxs-lookup"><span data-stu-id="4c7b1-104">The <xref:System.Activities.Statements.Pick> activity provides event-based control modeling.</span></span> <span data-ttu-id="4c7b1-105">il cui comportamento è analogo a quello dell'istruzione C# `switch`, che esegue solo uno dei rami nell'istruzione `switch`.</span><span class="sxs-lookup"><span data-stu-id="4c7b1-105">It behaves similar to the C# `switch` statement, which executes only one of the branches in the `switch` statement.</span></span> <span data-ttu-id="4c7b1-106">A differenza dell'istruzione `switch` in cui l'esecuzione di un ramo viene effettuata in base a un valore, l'attività <xref:System.Activities.Statements.Pick> esegue un ramo in base alla modalità di completamento di un'attività.</span><span class="sxs-lookup"><span data-stu-id="4c7b1-106">Unlike the `switch` statement in which a branch is executed based upon on a value, the <xref:System.Activities.Statements.Pick> activity executes a branch based upon how an activity completes.</span></span>

 <span data-ttu-id="4c7b1-107">In questo esempio un utente deve digitare il nome nella console entro un periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="4c7b1-107">This sample prompts a user to type in their name on the console within a given time period.</span></span> <span data-ttu-id="4c7b1-108">L'attività <xref:System.Activities.Statements.Pick> nell'esempio dispone di due rami eseguiti in base al fatto che l'utente abbia o meno digitato il nome entro 5 secondi.</span><span class="sxs-lookup"><span data-stu-id="4c7b1-108">The <xref:System.Activities.Statements.Pick> activity in the sample has two branches that are executed based upon whether the user types in their name within 5 seconds or not.</span></span> <span data-ttu-id="4c7b1-109">Se l'utente digita il nome nei 5 secondi, viene eseguito il primo ramo che contiene un'attività `ReadLine` personalizzata; in caso contrario, viene eseguito l'altro ramo che contiene un'attività <xref:System.Activities.Statements.Delay>.</span><span class="sxs-lookup"><span data-stu-id="4c7b1-109">If the user types in their name within 5 seconds, the first branch is executed, which contains a custom `ReadLine` activity; otherwise the other branch is executed, which contains a <xref:System.Activities.Statements.Delay> activity.</span></span> <span data-ttu-id="4c7b1-110">Una volta digitato nella console, il nome dell'utente viene stampato nella console.</span><span class="sxs-lookup"><span data-stu-id="4c7b1-110">Once a user’s name is typed in on the console, the user’s name is printed on the console.</span></span> <span data-ttu-id="4c7b1-111">Se un input non viene immesso entro 5 secondi, l'operazione è scaduta.</span><span class="sxs-lookup"><span data-stu-id="4c7b1-111">If an input is not entered within 5 seconds, the operation is timed out.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="4c7b1-112">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="4c7b1-112">Demonstrates</span></span>
 <span data-ttu-id="4c7b1-113">Attività <xref:System.Activities.Statements.Pick></span><span class="sxs-lookup"><span data-stu-id="4c7b1-113"><xref:System.Activities.Statements.Pick> activity.</span></span>

## <a name="discussion"></a><span data-ttu-id="4c7b1-114">Discussione</span><span class="sxs-lookup"><span data-stu-id="4c7b1-114">Discussion</span></span>
 <span data-ttu-id="4c7b1-115">Nell'esempio è incluso un flusso di lavoro della finestra di progettazione e un flusso di lavoro codificato.</span><span class="sxs-lookup"><span data-stu-id="4c7b1-115">The sample includes a Designer workflow and coded workflow.</span></span>

 <span data-ttu-id="4c7b1-116">Workflow Designer la versione della finestra di progettazione dell'esempio illustra come creare un flusso di lavoro nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="4c7b1-116">Designer Workflow The Designer version of the sample demonstrates how to create a workflow in the designer.</span></span> <span data-ttu-id="4c7b1-117">Sono inclusi i file seguenti:</span><span class="sxs-lookup"><span data-stu-id="4c7b1-117">The following files are included:</span></span>

- <span data-ttu-id="4c7b1-118">Program.cs: Include la `Main` funzione che esegue il flusso di lavoro di esempio.</span><span class="sxs-lookup"><span data-stu-id="4c7b1-118">Program.cs : Includes the `Main` function that executes the sample workflow.</span></span>

- <span data-ttu-id="4c7b1-119">ReadString.cs: Attività personalizzata che legge un input dalla console.</span><span class="sxs-lookup"><span data-stu-id="4c7b1-119">ReadString.cs: A custom activity that reads some input from the console.</span></span>

- <span data-ttu-id="4c7b1-120">Sequence1. XAML: Flusso di lavoro creato utilizzando la finestra di progettazione che utilizza pick.</span><span class="sxs-lookup"><span data-stu-id="4c7b1-120">Sequence1.xaml: A workflow created using the designer that uses Pick.</span></span>

 <span data-ttu-id="4c7b1-121">Flusso di lavoro codificato la versione codificata dell'esempio illustra come creare un flusso di lavoro nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="4c7b1-121">Coded Workflow The coded version of the sample demonstrates how to create a workflow in the designer.</span></span> <span data-ttu-id="4c7b1-122">Sono inclusi i file seguenti:</span><span class="sxs-lookup"><span data-stu-id="4c7b1-122">The following files are included:</span></span>

- <span data-ttu-id="4c7b1-123">Program.cs: Include la `Main` funzione che esegue il flusso di lavoro di esempio.</span><span class="sxs-lookup"><span data-stu-id="4c7b1-123">Program.cs : Includes the `Main` function that executes the sample workflow.</span></span>

- <span data-ttu-id="4c7b1-124">ReadString.cs: Attività personalizzata che legge un input dalla console.</span><span class="sxs-lookup"><span data-stu-id="4c7b1-124">ReadString.cs: A custom activity that reads some input from the console.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="4c7b1-125">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="4c7b1-125">To use this sample</span></span>

1. <span data-ttu-id="4c7b1-126">Con Visual Studio 2010 aprire il file della soluzione pick. sln.</span><span class="sxs-lookup"><span data-stu-id="4c7b1-126">Using Visual Studio 2010, open the Pick.sln solution file.</span></span>

2. <span data-ttu-id="4c7b1-127">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="4c7b1-127">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="4c7b1-128">Per eseguire la soluzione, premere F5.</span><span class="sxs-lookup"><span data-stu-id="4c7b1-128">To run the solution, press F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c7b1-129">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="4c7b1-129">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4c7b1-130">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="4c7b1-130">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="4c7b1-131">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ed esempi.</span><span class="sxs-lookup"><span data-stu-id="4c7b1-131">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4c7b1-132">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="4c7b1-132">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Pick`
