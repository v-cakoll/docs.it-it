---
title: ConditionedActivityGroup
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f76ef924-34ce-48ae-8c8d-48faf9697754
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e0df4ddc6f2cc5404c8153b30df66cda41487691
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="conditioned-activity-group"></a><span data-ttu-id="de8db-102">ConditionedActivityGroup</span><span class="sxs-lookup"><span data-stu-id="de8db-102">Conditioned Activity Group</span></span>
<span data-ttu-id="de8db-103">Nell'esempio viene illustrata un'applicazione di prenotazione di viaggio.</span><span class="sxs-lookup"><span data-stu-id="de8db-103">The sample demonstrates a travel booking application.</span></span> <span data-ttu-id="de8db-104"><xref:System.Workflow.Activities.ConditionedActivityGroup> (CAG) ha due attività di codice: un'attività Car e una attività Airline.</span><span class="sxs-lookup"><span data-stu-id="de8db-104">The <xref:System.Workflow.Activities.ConditionedActivityGroup> (CAG) has two code activities: a Car activity and an Airline activity.</span></span> <span data-ttu-id="de8db-105">Nel costruttore `SimpleCAGWorkflow`, un oggetto ArrayList "travelNeedType" viene popolato con i tipi di prenotazioni di viaggio richiesti.</span><span class="sxs-lookup"><span data-stu-id="de8db-105">In the `SimpleCAGWorkflow` constructor, a "travelNeedType" ArrayList object is populated with the types of travel bookings that are required.</span></span> <span data-ttu-id="de8db-106">Tramite l'aggiunta di commenti a una o entrambe le istruzioni `travelNeeds.Add`, il comportamento di CAG viene modificato di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="de8db-106">By commenting out one or both of the `travelNeeds.Add` statements, you modify the CAG behavior accordingly.</span></span> <span data-ttu-id="de8db-107">Entrambi le attività Car e Airline dispongono della condizione <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty> popolata con una <xref:System.Workflow.Activities.CodeCondition>.</span><span class="sxs-lookup"><span data-stu-id="de8db-107">Both the Car and Airline activities have their <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty> condition populated with a <xref:System.Workflow.Activities.CodeCondition>.</span></span> <span data-ttu-id="de8db-108">L'attività Car viene eseguita solo se la raccolta `travelNeeds` dispone di una voce `TravelNeeds.Car` e l'attività Airline viene eseguita solo se la raccolta `travelNeeds` dispone di una voce `TravelNeeds.Airline`.</span><span class="sxs-lookup"><span data-stu-id="de8db-108">The Car activity executes only if the `travelNeeds` collection has a `TravelNeeds.Car` entry, and the Airline activity executes only if the `travelNeeds` collection has a `TravelNeeds.Airline` entry.</span></span>  
  
 <span data-ttu-id="de8db-109">L'esecuzione di ciascuna attività rimuove la voce corrispondente dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="de8db-109">The execution of each activity removes the corresponding entry from the collection.</span></span> <span data-ttu-id="de8db-110">La condizione <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A> predefinita specifica che CAG debba essere chiuso se non sono presenti esecuzione da parte dei figli o se i figli sono pronti per l'esecuzione (in base alle condizioni <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty>).</span><span class="sxs-lookup"><span data-stu-id="de8db-110">The default <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A> condition specifies that the CAG should exit when no children are executing or are ready for execution (based on their <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty> conditions).</span></span> <span data-ttu-id="de8db-111">In questo esempio, ciò vuole dire che CAG viene chiuso quando la raccolta `travelNeeds` è vuota.</span><span class="sxs-lookup"><span data-stu-id="de8db-111">In this sample, this means that the CAG exits when the `travelNeeds` collection is empty.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="de8db-112">Per compilare l'esempio</span><span class="sxs-lookup"><span data-stu-id="de8db-112">To build the sample</span></span>  
  
1.  <span data-ttu-id="de8db-113">Aprire la soluzione in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de8db-113">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="de8db-114">Premere CTRL+MAIUSC+B per compilare la soluzione,</span><span class="sxs-lookup"><span data-stu-id="de8db-114">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="de8db-115">Eseguire la soluzione senza debug premendo CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="de8db-115">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="de8db-116">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="de8db-116">To run the sample</span></span>  
  
-   <span data-ttu-id="de8db-117">Nella finestra del prompt dei comandi di SDK eseguire il file con estensione exe nella cartella SimpleCAG\bin\debug (oppure nella cartella SimpleCAG\bin per la versione Visual Basic dell'esempio), collocata sotto la cartella principale dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="de8db-117">In the SDK Command Prompt window, run the .exe file in the SimpleCAG\bin\debug folder (or the SimpleCAG\bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="de8db-118">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="de8db-118">The samples may already be installed on your computer.</span></span> <span data-ttu-id="de8db-119">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="de8db-119">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="de8db-120">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="de8db-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="de8db-121">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="de8db-121">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\SimpleCAG`  
  
## <a name="see-also"></a><span data-ttu-id="de8db-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de8db-122">See Also</span></span>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty>  
 <xref:System.Workflow.Activities.CodeCondition>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A>
