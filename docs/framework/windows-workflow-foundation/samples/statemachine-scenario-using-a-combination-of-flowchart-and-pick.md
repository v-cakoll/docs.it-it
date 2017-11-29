---
title: "Scenario StateMachine utilizzando una combinazione attività FlowChart e Pick"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88d81395-f7a3-41d8-8439-20a425c538a6
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0fb0364310c8780dd41c5369e6b1851dee668d15
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="statemachine-scenario-using-a-combination-of-flowchart-and-pick"></a><span data-ttu-id="e0167-102">Scenario StateMachine utilizzando una combinazione attività FlowChart e Pick</span><span class="sxs-lookup"><span data-stu-id="e0167-102">StateMachine Scenario Using a Combination of FlowChart and Pick</span></span>
<span data-ttu-id="e0167-103">In questo esempio, viene illustrato come implementare uno scenario StopWatch semplice usando una combinazione di attività <xref:System.Activities.Statements.Flowchart> e <xref:System.Activities.Statements.Pick>.</span><span class="sxs-lookup"><span data-stu-id="e0167-103">This sample demonstrates how to implement a simple stopwatch scenario using a combination of the <xref:System.Activities.Statements.Flowchart> and <xref:System.Activities.Statements.Pick> activities.</span></span> <span data-ttu-id="e0167-104">Vengono usate attività Receive e Send all'interno dell'attività Pick per rimanere in ascolto di eventi Stopwatch.</span><span class="sxs-lookup"><span data-stu-id="e0167-104">It uses Receive and Send within the Pick activity to listen for stopwatch events.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e0167-105">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="e0167-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e0167-106">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="e0167-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e0167-107">Se questa directory non esiste, visitare la pagina di download per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e0167-107">If this directory does not exist, go to (download page) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e0167-108">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="e0167-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\StateMachineWithPick`  
  
## <a name="sample-details"></a><span data-ttu-id="e0167-109">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="e0167-109">Sample Details</span></span>  
 <span data-ttu-id="e0167-110">Nella tabella seguente vengono elencati i progetti contenuti in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="e0167-110">The following table lists the projects in this sample.</span></span>  
  
|<span data-ttu-id="e0167-111">Nome progetto</span><span class="sxs-lookup"><span data-stu-id="e0167-111">Project Name</span></span>|<span data-ttu-id="e0167-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e0167-112">Description</span></span>|  
|-|-|  
|<span data-ttu-id="e0167-113">StopWatchService</span><span class="sxs-lookup"><span data-stu-id="e0167-113">StopWatchService</span></span>|<span data-ttu-id="e0167-114">Questo progetto contiene l'implementazione di una macchina a stati per l'esempio del cronometro usando una combinazione di attività <xref:System.Activities.Statements.Flowchart> e <xref:System.Activities.Statements.Pick>.</span><span class="sxs-lookup"><span data-stu-id="e0167-114">This project contains the implementation of a state machine for the stopwatch sample using a combination of the <xref:System.Activities.Statements.Flowchart> and <xref:System.Activities.Statements.Pick> activities.</span></span><br /><br /> <span data-ttu-id="e0167-115">L'attività <xref:System.Activities.Statements.Pick> dispone di 3 istruzioni <xref:System.Activities.Statements.PickBranch> all'interno della proprietà <xref:System.Activities.Statements.Pick.Branches%2A> che rimane in ascolto di eventi `GetStart`, `GetStop` e `GetOff`.</span><span class="sxs-lookup"><span data-stu-id="e0167-115">The <xref:System.Activities.Statements.Pick> activity has 3 <xref:System.Activities.Statements.PickBranch> statements within the <xref:System.Activities.Statements.Pick.Branches%2A> property that listen for `GetStart`, `GetStop` and `GetOff` events.</span></span> <span data-ttu-id="e0167-116">In base all'evento in ingresso, si attivano i trigger per uno dei rami e viene attivato l'oggetto <xref:System.Activities.Statements.PickBranch.Action%2A> corrispondente.</span><span class="sxs-lookup"><span data-stu-id="e0167-116">Based on the incoming event, the triggers for one of the branches activate and the corresponding <xref:System.Activities.Statements.PickBranch.Action%2A> is triggered.</span></span> <span data-ttu-id="e0167-117">Nella proprietà <xref:System.Activities.Statements.PickBranch.Action%2A> è presente un'istruzione <xref:System.Activities.Statements.Switch%601> che valuta se la transizione è valida e, tal caso, la proprietà `currentState` viene aggiornata allo stato di transizione e inviata al client.</span><span class="sxs-lookup"><span data-stu-id="e0167-117">In the <xref:System.Activities.Statements.PickBranch.Action%2A> property, there is a <xref:System.Activities.Statements.Switch%601> statement that evaluates whether the transition is a legitimate transition and if it is, the `currentState` property is updated to the transitioning state and sent to the client.</span></span><br /><br /> <span data-ttu-id="e0167-118">L'attività <xref:System.Activities.Statements.FlowDecision> alla fine di <xref:System.Activities.Statements.Flowchart> valuta la proprietà `currentState` per determinare se lo stato è finale.</span><span class="sxs-lookup"><span data-stu-id="e0167-118">The <xref:System.Activities.Statements.FlowDecision> activity at the end of the <xref:System.Activities.Statements.Flowchart> evaluates the `currentState` property to determine whether the state is terminal.</span></span> <span data-ttu-id="e0167-119">In caso affermativo, il flusso di lavoro viene terminato. In caso contrario il controllo esegue il loopback all'inizio dell'attività <xref:System.Activities.Statements.Pick> dove il flusso di lavoro attende più eventi Stopwatch.</span><span class="sxs-lookup"><span data-stu-id="e0167-119">If it is, the workflow ends; otherwise control loops back to the start of the <xref:System.Activities.Statements.Pick> activity where the workflow waits for more stopwatch events.</span></span>|  
|<span data-ttu-id="e0167-120">StopWatchClient</span><span class="sxs-lookup"><span data-stu-id="e0167-120">StopWatchClient</span></span>|<span data-ttu-id="e0167-121">Si tratta di una semplice applicazione console del flusso di lavoro sequenziale che invia vari eventi Stopwatch con semplici combinazioni di attività Send o Receive.</span><span class="sxs-lookup"><span data-stu-id="e0167-121">This is a simple sequential workflow console application that sends various stopwatch events with simple Send or Receive activity combinations.</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="e0167-122">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="e0167-122">To use this sample</span></span>  
  
1.  <span data-ttu-id="e0167-123">Tramite [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione StateMachineWithPick.sln.</span><span class="sxs-lookup"><span data-stu-id="e0167-123">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open StateMachineWithPick.sln solution file.</span></span>  
  
2.  <span data-ttu-id="e0167-124">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="e0167-124">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="e0167-125">Avviare StopWatchService.exe da [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] come amministratore facendo clic il file .exe e selezionando **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="e0167-125">Start the StopWatchService.exe from [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] as an administrator by right clicking the .exe file and selecting **Run as administrator**.</span></span>  
  
    1.  <span data-ttu-id="e0167-126">Passare alla cartella StateMachineWithPick\CS\StopWatchService\bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="e0167-126">Navigate to the StateMachineWithPick\CS\StopWatchService\bin\Debug folder.</span></span>  
  
    2.  <span data-ttu-id="e0167-127">Fare clic sul file StopWatchService.exe e selezionare **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="e0167-127">Right-click the StopWatchService.exe file and select **Run as administrator**.</span></span>  
  
4.  <span data-ttu-id="e0167-128">Avviare l'applicazione client StopWatchClient dall'interno di [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e0167-128">Start the StopWatchClient client application from within [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
    1.  <span data-ttu-id="e0167-129">In **Esplora**, selezionare il **StopWatchClient** del progetto e fare doppio clic su **imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="e0167-129">In **Solution Explorer**, select the **StopWatchClient** project and right-click **Set as StartUp Project**.</span></span>  
  
    2.  <span data-ttu-id="e0167-130">Per eseguire la soluzione, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="e0167-130">To run the solution, press CTRL+F5.</span></span>  
  
5.  <span data-ttu-id="e0167-131">Tornare alla finestra della console di StopWatchService.exe per visualizzare le transizioni di stato.</span><span class="sxs-lookup"><span data-stu-id="e0167-131">Switch back to the console window for the StopWatchService.exe to view the state transitions.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e0167-132">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="e0167-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e0167-133">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="e0167-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e0167-134">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e0167-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e0167-135">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="e0167-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\StateMachineWithPick`  
  
## <a name="see-also"></a><span data-ttu-id="e0167-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0167-136">See Also</span></span>
