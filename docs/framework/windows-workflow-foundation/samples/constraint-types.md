---
title: Tipi di vincoli
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b6b246e6-1130-4698-9625-c5c42abcbfed
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cd73776aebb571fad732f554d6a96c1611506e8c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="constraint-types"></a><span data-ttu-id="9132a-102">Tipi di vincoli</span><span class="sxs-lookup"><span data-stu-id="9132a-102">Constraint Types</span></span>
<span data-ttu-id="9132a-103">In questo esempio vengono illustrate due modalità diverse per applicare vincoli a un flusso di lavoro: uno dall'interno dell'attività (compilazione) e un altro dall'esterno (criteri).</span><span class="sxs-lookup"><span data-stu-id="9132a-103">This sample shows two different ways to apply constraints to a workflow, one is from inside the activity (build) and one is from outside of it (policy).</span></span> <span data-ttu-id="9132a-104">In questo scenario, un autore di attività (di una società di software di terze parti) desidera convalidare la relazione tra due argomenti.</span><span class="sxs-lookup"><span data-stu-id="9132a-104">In this scenario, an activity author (from a 3rth-party software company) wants to validate the relationship between two arguments.</span></span> <span data-ttu-id="9132a-105">In questo caso, il costo deve essere minore o uguale al prezzo.</span><span class="sxs-lookup"><span data-stu-id="9132a-105">In this case, the cost should be smaller than or equal to the price.</span></span> <span data-ttu-id="9132a-106">Si tratta di un vincolo di compilazione di convalida generale.</span><span class="sxs-lookup"><span data-stu-id="9132a-106">This is a general validation build constraint.</span></span>  
  
 <span data-ttu-id="9132a-107">Il proprietario di un negozio desidera aggiungere alcune convalide a questa attività generica.</span><span class="sxs-lookup"><span data-stu-id="9132a-107">Then a shop owner wants to add some validation to this generic activity.</span></span> <span data-ttu-id="9132a-108">In tal caso, desidera che la maggior parte dei prodotti abbia un prezzo pari ad almeno $9.99.</span><span class="sxs-lookup"><span data-stu-id="9132a-108">In his case, he wants the majority of its products to be $9.99 or less.</span></span> <span data-ttu-id="9132a-109">Pertanto, usa un vincolo di criteri che si trova nella parte superiore dell'attività `CreateProduct`.</span><span class="sxs-lookup"><span data-stu-id="9132a-109">So, he uses a policy constraint that is on top of the `CreateProduct` activity.</span></span>  
  
 <span data-ttu-id="9132a-110">Nell'esempio:</span><span class="sxs-lookup"><span data-stu-id="9132a-110">In the sample:</span></span>  
  
 <span data-ttu-id="9132a-111">L'autore di attività (compilazione) deve:</span><span class="sxs-lookup"><span data-stu-id="9132a-111">The activity author (build) must:</span></span>  
  
-   <span data-ttu-id="9132a-112">Creare un vincolo (`PriceGreaterThanCost`),</span><span class="sxs-lookup"><span data-stu-id="9132a-112">Create a constraint (`PriceGreaterThanCost`).</span></span> <span data-ttu-id="9132a-113">ovvero il punto in cui far risiedere l'intera logica di convalida.</span><span class="sxs-lookup"><span data-stu-id="9132a-113">This is where all the validation logic resides.</span></span>  
  
-   <span data-ttu-id="9132a-114">Eseguire l'override del metodo `System.Activities.CodeActivity.OnGetConstraints()` e aggiungere il vincolo (`PriceGreaterThanCost`) ai vincoli <xref:System.Collections.IList>.</span><span class="sxs-lookup"><span data-stu-id="9132a-114">Override `System.Activities.CodeActivity.OnGetConstraints()` and add the constraint (`PriceGreaterThanCost`) to the constraints <xref:System.Collections.IList>.</span></span>  
  
 <span data-ttu-id="9132a-115">L'autore del flusso di lavoro (criteri) deve:</span><span class="sxs-lookup"><span data-stu-id="9132a-115">The workflow author (policy) must:</span></span>  
  
-   <span data-ttu-id="9132a-116">Creare un flusso di lavoro con un'istanza dell'attività da convalidare (`CreateProduct`).</span><span class="sxs-lookup"><span data-stu-id="9132a-116">Create a workflow with an instance of the activity to validate (`CreateProduct`).</span></span>  
  
-   <span data-ttu-id="9132a-117">Creare un vincolo (`MaxPrice`),</span><span class="sxs-lookup"><span data-stu-id="9132a-117">Create a constraint (`MaxPrice`).</span></span>  
  
-   <span data-ttu-id="9132a-118">Creare un'istanza <xref:System.Activities.Validation.ValidationSettings> (`validationSettings`) e aggiungere il vincolo (`MaxPrice`) alla raccolta `AdditionalConstraints`.</span><span class="sxs-lookup"><span data-stu-id="9132a-118">Create a <xref:System.Activities.Validation.ValidationSettings> instance (`validationSettings`) and add the constraint (`MaxPrice`) to the collection `AdditionalConstraints`.</span></span> <span data-ttu-id="9132a-119">A questo punto l'autore del flusso di lavoro può aggiungere vincoli di criteri a qualsiasi attività, ad esempio Sequence o Parallel.</span><span class="sxs-lookup"><span data-stu-id="9132a-119">Here the workflow author can add policy constraints to any activity, such as a sequence or parallel.</span></span>  
  
-   <span data-ttu-id="9132a-120">Chiamare il metodo <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, che restituisce una raccolta <xref:System.Activities.Validation.ValidationResults> di oggetti <xref:System.Activities.Validation.ValidationError>.</span><span class="sxs-lookup"><span data-stu-id="9132a-120">Call <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, which returns a <xref:System.Activities.Validation.ValidationResults> collection of <xref:System.Activities.Validation.ValidationError> objects.</span></span>  
  
-   <span data-ttu-id="9132a-121">(Facoltativo) Stampare gli oggetti <xref:System.Activities.Validation.ValidationError>.</span><span class="sxs-lookup"><span data-stu-id="9132a-121">(Optional) Print the <xref:System.Activities.Validation.ValidationError> objects.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="9132a-122">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="9132a-122">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="9132a-123">Aprire la soluzione di esempio ConstraintTypes.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9132a-123">Open the ConstraintTypes.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="9132a-124">Compilare ed eseguire la soluzione.</span><span class="sxs-lookup"><span data-stu-id="9132a-124">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9132a-125">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="9132a-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9132a-126">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="9132a-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9132a-127">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9132a-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9132a-128">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="9132a-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Validation\ConstraintLibrary`