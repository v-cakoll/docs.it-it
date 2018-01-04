---
title: Determinazione della durata di esecuzione del flusso di lavoro tramite traccia
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f04ad0fd-edc7-4cbc-8979-356f2a1131c4
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f2687d045db28974e99b2f2b6a3222924a520720
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="determining-workflow-execution-duration-using-tracing"></a><span data-ttu-id="88c2a-102">Determinazione della durata di esecuzione del flusso di lavoro tramite traccia</span><span class="sxs-lookup"><span data-stu-id="88c2a-102">Determining Workflow Execution Duration Using Tracing</span></span>
<span data-ttu-id="88c2a-103">In questo argomento viene illustrato come determinare il tempo necessario per l'esecuzione corretta di un flusso di lavoro indipendente tramite la traccia del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="88c2a-103">This topic demonstrates how to determine the time it takes for a successfully completed, self-hosted workflow to execute by using workflow tracing.</span></span>  
  
### <a name="to-determine-workflow-application-execution-duration-by-using-workflow-tracing"></a><span data-ttu-id="88c2a-104">Per determinare la durata di esecuzione di un'applicazione flusso di lavoro tramite la traccia del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="88c2a-104">To determine workflow application execution duration by using workflow tracing</span></span>  
  
1.  <span data-ttu-id="88c2a-105">Aprire [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88c2a-105">Open [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  <span data-ttu-id="88c2a-106">Selezionare **File**, **nuova**, **progetto**.</span><span class="sxs-lookup"><span data-stu-id="88c2a-106">Select **File**, **New**, **Project**.</span></span>  <span data-ttu-id="88c2a-107">In **c#**, selezionare il **flusso di lavoro** nodo.</span><span class="sxs-lookup"><span data-stu-id="88c2a-107">Under **C#**, select the **Workflow** node.</span></span>  <span data-ttu-id="88c2a-108">Selezionare **applicazione Console flusso di lavoro** dall'elenco dei modelli.</span><span class="sxs-lookup"><span data-stu-id="88c2a-108">Select **Workflow Console Application** from the list of templates.</span></span>  <span data-ttu-id="88c2a-109">Denominare il nuovo progetto `WorkflowDurationTracing` e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="88c2a-109">Name the new project `WorkflowDurationTracing` and click **OK**.</span></span>  
  
2.  <span data-ttu-id="88c2a-110">Aprire Workflow1.xaml.</span><span class="sxs-lookup"><span data-stu-id="88c2a-110">Open Workflow1.xaml.</span></span>  <span data-ttu-id="88c2a-111">Trascinare un'attività <xref:System.Activities.Statements.Delay> nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="88c2a-111">Drag a <xref:System.Activities.Statements.Delay> activity onto the designer surface.</span></span> <span data-ttu-id="88c2a-112">Assegnare il valore 00.00.10 (dieci secondi) alla proprietà Duration dell'attività.</span><span class="sxs-lookup"><span data-stu-id="88c2a-112">Assign the value 00:00:10 (ten seconds) to the Duration property of the activity.</span></span>  
  
3.  <span data-ttu-id="88c2a-113">Aprire il Visualizzatore eventi fare clic su **avviare**, **eseguire**e l'immissione di `eventvwr.exe`.</span><span class="sxs-lookup"><span data-stu-id="88c2a-113">Open Event Viewer by clicking **Start**, **Run**, and entering `eventvwr.exe`.</span></span>  
  
4.  <span data-ttu-id="88c2a-114">Se è stata abilitata la traccia del flusso di lavoro, espandere **registri applicazioni e servizi**, **Microsoft**, **Windows**, **Server applicazioni-applicazioni** .</span><span class="sxs-lookup"><span data-stu-id="88c2a-114">If you haven’t enabled workflow tracing, expand **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="88c2a-115">Selezionare **vista**, **Mostra analitica e registri di Debug**.</span><span class="sxs-lookup"><span data-stu-id="88c2a-115">Select **View**, **Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="88c2a-116">Fare doppio clic su **Debug** e selezionare **Attiva registro**.</span><span class="sxs-lookup"><span data-stu-id="88c2a-116">Right-click **Debug** and select **Enable Log**.</span></span> <span data-ttu-id="88c2a-117">Lasciare aperto il Visualizzatore eventi in modo che sia possibile visualizzare le tracce dopo l'esecuzione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="88c2a-117">Leave Event Viewer open so that traces can be viewed after the workflow is run.</span></span>  
  
5.  <span data-ttu-id="88c2a-118">Premere CTRL+SHIFT+B per eseguire l'applicazione flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="88c2a-118">Execute the workflow application by pressing CTRL+SHIFT+B.</span></span>  
  
6.  <span data-ttu-id="88c2a-119">Nel Visualizzatore eventi trovare un recente evento con ID 1009 e un messaggio analogo al seguente.</span><span class="sxs-lookup"><span data-stu-id="88c2a-119">In Event Viewer, find a recent event with ID 1009 and a message similar to the following.</span></span> <span data-ttu-id="88c2a-120">Annotare l'ora in cui il messaggio è stato registrato.</span><span class="sxs-lookup"><span data-stu-id="88c2a-120">Make a note of the time that the message was logged.</span></span>  
  
 <span data-ttu-id="88c2a-121">**Attività padre ', DisplayName: ', InstanceId: ' figlio pianificato l'attività 'WorkflowDurationTracking.Workflow1', DisplayName: 'Flussodilavoro1', InstanceId: '1'.**</span><span class="sxs-lookup"><span data-stu-id="88c2a-121">**Parent Activity '', DisplayName: '', InstanceId: '' scheduled child Activity 'WorkflowDurationTracking.Workflow1', DisplayName: 'Workflow1', InstanceId: '1'.**</span></span>  
  
7.  <span data-ttu-id="88c2a-122">Trovare un altro evento recente con ID 1001 e un messaggio analogo al seguente.</span><span class="sxs-lookup"><span data-stu-id="88c2a-122">Find another recent event with ID 1001 and a message similar to the following.</span></span>  <span data-ttu-id="88c2a-123">Sottrarre l'ora del messaggio precedente dal valore registrato per questo messaggio per determinare la durata di esecuzione del flusso di lavoro che deve essere di circa 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="88c2a-123">Subtract the previous message time from this message’s Logged value to determine workflow execution duration, which should be around 10 seconds.</span></span>  
  
 <span data-ttu-id="88c2a-124">**WorkflowInstance con Id: '1bbac57b-3322-498e-9e27-8833fda3a5bf' completata nello stato Closed.**</span><span class="sxs-lookup"><span data-stu-id="88c2a-124">**WorkflowInstance Id: '1bbac57b-3322-498e-9e27-8833fda3a5bf' has completed in the Closed state.**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88c2a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88c2a-125">See Also</span></span>  
 [<span data-ttu-id="88c2a-126">Analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="88c2a-126">Workflow Tracing</span></span>](../../../docs/framework/windows-workflow-foundation/workflow-tracing.md)  
 [<span data-ttu-id="88c2a-127">Monitoraggio dell'infrastruttura di App di Windows Server</span><span class="sxs-lookup"><span data-stu-id="88c2a-127">Windows Server App Fabric Monitoring</span></span>](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [<span data-ttu-id="88c2a-128">Monitoraggio delle applicazioni con App Fabric</span><span class="sxs-lookup"><span data-stu-id="88c2a-128">Monitoring Applications with App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkId=201275)
