---
title: Convalida di base
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba1343cc-aaab-4ade-b0c0-1dd5063bf4ad
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d388b3d6acad28e4ff952f72aa64a607d745f307
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="basic-validation"></a><span data-ttu-id="dae8d-102">Convalida di base</span><span class="sxs-lookup"><span data-stu-id="dae8d-102">Basic Validation</span></span>
<span data-ttu-id="dae8d-103">Questo esempio è costituito da un'attività `CreateProduct` che verifica che l'argomento `Cost` sia minore o uguale al relativo argomento `Price`.</span><span class="sxs-lookup"><span data-stu-id="dae8d-103">This sample consists of an activity, `CreateProduct`, which validates that its `Cost` argument is smaller than or equal to its `Price` argument.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="dae8d-104">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="dae8d-104">Sample Details</span></span>  
 <span data-ttu-id="dae8d-105">Esistono due autori che usano la convalida, l'autore di attività (crea la logica di convalida per l'attività) e l'autore del flusso di lavoro che chiama i servizi di convalida in un flusso di lavoro specifico.</span><span class="sxs-lookup"><span data-stu-id="dae8d-105">There are two authors that use validation, the activity author (creates the validation logic for the activity) and the workflow author that calls validation services on a specific workflow.</span></span> <span data-ttu-id="dae8d-106">In questo scenario, l'autore di attività desidera che ogni istanza dell'attività abbia un costo minore o uguale a un determinato prezzo.</span><span class="sxs-lookup"><span data-stu-id="dae8d-106">In this scenario, the activity author wants to enforce that every instance of his activity must have a smaller or equal cost than that of the price.</span></span>  
  
 <span data-ttu-id="dae8d-107">L'autore di attività (nell'attività) deve:</span><span class="sxs-lookup"><span data-stu-id="dae8d-107">The activity author (inside the activity) must:</span></span>  
  
-   <span data-ttu-id="dae8d-108">Creare un vincolo (`PriceGreaterThanCost`),</span><span class="sxs-lookup"><span data-stu-id="dae8d-108">Create a constraint (`PriceGreaterThanCost`).</span></span> <span data-ttu-id="dae8d-109">ovvero il punto in cui far risiedere l'intera logica di convalida.</span><span class="sxs-lookup"><span data-stu-id="dae8d-109">This is where all the validation logic resides.</span></span>  
  
-   <span data-ttu-id="dae8d-110">Eseguire l'override del metodo `System.Activities.CodeActivity.OnGetConstraints()` e aggiungere il vincolo (`PriceGreaterThanCost`) ai vincoli <xref:System.Collections.IList>.</span><span class="sxs-lookup"><span data-stu-id="dae8d-110">Override `System.Activities.CodeActivity.OnGetConstraints()` and add the constraint (`PriceGreaterThanCost`) to the constraints <xref:System.Collections.IList>.</span></span>  
  
 <span data-ttu-id="dae8d-111">L'autore del flusso di lavoro (programma principale) deve:</span><span class="sxs-lookup"><span data-stu-id="dae8d-111">The workflow author (main program) must:</span></span>  
  
-   <span data-ttu-id="dae8d-112">Creare un flusso di lavoro con un'istanza dell'attività da convalidare (`CreateProduct`).</span><span class="sxs-lookup"><span data-stu-id="dae8d-112">Create a workflow with an instance of the activity to validate (`CreateProduct`).</span></span>  
  
-   <span data-ttu-id="dae8d-113">Chiamare il metodo <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, che restituisce una raccolta <xref:System.Activities.Validation.ValidationResults> di oggetti <xref:System.Activities.Validation.ValidationError>.</span><span class="sxs-lookup"><span data-stu-id="dae8d-113">Call <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, which returns a <xref:System.Activities.Validation.ValidationResults> collection of <xref:System.Activities.Validation.ValidationError>.</span></span>  
  
-   <span data-ttu-id="dae8d-114">(Facoltativo) Stampare gli oggetti <xref:System.Activities.Validation.ValidationError>.</span><span class="sxs-lookup"><span data-stu-id="dae8d-114">(Optional) Print the <xref:System.Activities.Validation.ValidationError> objects.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="dae8d-115">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="dae8d-115">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="dae8d-116">Aprire la soluzione di esempio BasicValidation.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dae8d-116">Open the BasicValidation.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="dae8d-117">Compilare ed eseguire la soluzione.</span><span class="sxs-lookup"><span data-stu-id="dae8d-117">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dae8d-118">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="dae8d-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="dae8d-119">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="dae8d-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="dae8d-120">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dae8d-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dae8d-121">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="dae8d-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\BasicValidation`  
  
## <a name="see-also"></a><span data-ttu-id="dae8d-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dae8d-122">See Also</span></span>
