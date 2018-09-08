---
title: Convalida di base
ms.date: 03/30/2017
ms.assetid: ba1343cc-aaab-4ade-b0c0-1dd5063bf4ad
ms.openlocfilehash: 74d99e2d426e9ea5701fad80418fdf019112cc9e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44208621"
---
# <a name="basic-validation"></a><span data-ttu-id="566db-102">Convalida di base</span><span class="sxs-lookup"><span data-stu-id="566db-102">Basic Validation</span></span>
<span data-ttu-id="566db-103">Questo esempio è costituito da un'attività `CreateProduct` che verifica che l'argomento `Cost` sia minore o uguale al relativo argomento `Price`.</span><span class="sxs-lookup"><span data-stu-id="566db-103">This sample consists of an activity, `CreateProduct`, which validates that its `Cost` argument is smaller than or equal to its `Price` argument.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="566db-104">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="566db-104">Sample Details</span></span>  
 <span data-ttu-id="566db-105">Esistono due autori che usano la convalida, l'autore di attività (crea la logica di convalida per l'attività) e l'autore del flusso di lavoro che chiama i servizi di convalida in un flusso di lavoro specifico.</span><span class="sxs-lookup"><span data-stu-id="566db-105">There are two authors that use validation, the activity author (creates the validation logic for the activity) and the workflow author that calls validation services on a specific workflow.</span></span> <span data-ttu-id="566db-106">In questo scenario, l'autore di attività desidera che ogni istanza dell'attività abbia un costo minore o uguale a un determinato prezzo.</span><span class="sxs-lookup"><span data-stu-id="566db-106">In this scenario, the activity author wants to enforce that every instance of his activity must have a smaller or equal cost than that of the price.</span></span>  
  
 <span data-ttu-id="566db-107">L'autore di attività (nell'attività) deve:</span><span class="sxs-lookup"><span data-stu-id="566db-107">The activity author (inside the activity) must:</span></span>  
  
-   <span data-ttu-id="566db-108">Creare un vincolo (`PriceGreaterThanCost`),</span><span class="sxs-lookup"><span data-stu-id="566db-108">Create a constraint (`PriceGreaterThanCost`).</span></span> <span data-ttu-id="566db-109">ovvero il punto in cui far risiedere l'intera logica di convalida.</span><span class="sxs-lookup"><span data-stu-id="566db-109">This is where all the validation logic resides.</span></span>  
  
-   <span data-ttu-id="566db-110">Eseguire l'override del metodo `System.Activities.CodeActivity.OnGetConstraints()` e aggiungere il vincolo (`PriceGreaterThanCost`) ai vincoli <xref:System.Collections.IList>.</span><span class="sxs-lookup"><span data-stu-id="566db-110">Override `System.Activities.CodeActivity.OnGetConstraints()` and add the constraint (`PriceGreaterThanCost`) to the constraints <xref:System.Collections.IList>.</span></span>  
  
 <span data-ttu-id="566db-111">L'autore del flusso di lavoro (programma principale) deve:</span><span class="sxs-lookup"><span data-stu-id="566db-111">The workflow author (main program) must:</span></span>  
  
-   <span data-ttu-id="566db-112">Creare un flusso di lavoro con un'istanza dell'attività da convalidare (`CreateProduct`).</span><span class="sxs-lookup"><span data-stu-id="566db-112">Create a workflow with an instance of the activity to validate (`CreateProduct`).</span></span>  
  
-   <span data-ttu-id="566db-113">Chiamare il metodo <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, che restituisce una raccolta <xref:System.Activities.Validation.ValidationResults> di oggetti <xref:System.Activities.Validation.ValidationError>.</span><span class="sxs-lookup"><span data-stu-id="566db-113">Call <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, which returns a <xref:System.Activities.Validation.ValidationResults> collection of <xref:System.Activities.Validation.ValidationError>.</span></span>  
  
-   <span data-ttu-id="566db-114">(Facoltativo) Stampare gli oggetti <xref:System.Activities.Validation.ValidationError>.</span><span class="sxs-lookup"><span data-stu-id="566db-114">(Optional) Print the <xref:System.Activities.Validation.ValidationError> objects.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="566db-115">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="566db-115">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="566db-116">Aprire la soluzione di esempio BasicValidation.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="566db-116">Open the BasicValidation.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="566db-117">Compilare ed eseguire la soluzione.</span><span class="sxs-lookup"><span data-stu-id="566db-117">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="566db-118">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="566db-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="566db-119">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="566db-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="566db-120">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="566db-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="566db-121">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="566db-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\BasicValidation`