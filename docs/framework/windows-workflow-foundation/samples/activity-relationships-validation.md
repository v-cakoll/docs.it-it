---
title: Convalida di relazioni tra attività
ms.date: 03/30/2017
ms.assetid: 6f11a34e-ed67-4bce-88ce-7e96bbb4d052
ms.openlocfilehash: 50f08118fb5ad4d9b8fe809e7ab3cc5d57f28149
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44193666"
---
# <a name="activity-relationships-validation"></a><span data-ttu-id="dfee2-102">Convalida di relazioni tra attività</span><span class="sxs-lookup"><span data-stu-id="dfee2-102">Activity Relationships Validation</span></span>
<span data-ttu-id="dfee2-103">Il presente esempio è costituito da tre attività, `CreateCity`, `CreateState` e `CreateCountry`.</span><span class="sxs-lookup"><span data-stu-id="dfee2-103">This sample consists of three activities, `CreateCity`, `CreateState`, and `CreateCountry`.</span></span> <span data-ttu-id="dfee2-104">`CreateCity` deve trovarsi all'interno di un'attività `CreateState` e `CreateState` deve trovarsi all'interno di un'attività `CreateCountry`.</span><span class="sxs-lookup"><span data-stu-id="dfee2-104">`CreateCity` must be inside a `CreateState` activity, and `CreateState` must be inside a `CreateCountry` activity.</span></span> <span data-ttu-id="dfee2-105">Ai fini di questo esempio, la logica di convalida è nel codice per l'attività `CreateState` e in XAML per l'attività `CreateCity`.</span><span class="sxs-lookup"><span data-stu-id="dfee2-105">For the purpose of this sample, the validation logic is in code for the `CreateState` activity, and in XAML for the `CreateCity` activity.</span></span> <span data-ttu-id="dfee2-106">Entrambi i vincoli presentano lo stesso comportamento.</span><span class="sxs-lookup"><span data-stu-id="dfee2-106">Both constraints have the same behavior.</span></span>  
  
 <span data-ttu-id="dfee2-107">[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] fornisce le tre attività di supporto seguenti che consentono allo sviluppatore di convalidare relazioni tra attività.</span><span class="sxs-lookup"><span data-stu-id="dfee2-107">The [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] provides the following three helper activities that allow the developer to validate relationships between activities:</span></span>  
  
 <xref:System.Activities.Validation.GetParentChain>  
 <span data-ttu-id="dfee2-108">Viene fornita la raccolta di tutte le attività che appartengono all'elemento padre del nodo corrente.</span><span class="sxs-lookup"><span data-stu-id="dfee2-108">Provides the collection of all activities that belong to the parent of the current node</span></span>  
  
 <xref:System.Activities.Validation.GetChildSubtree>  
 <span data-ttu-id="dfee2-109">Viene fornita la raccolta di tutte le attività che appartengono al sottoalbero, escluso il nodo corrente.</span><span class="sxs-lookup"><span data-stu-id="dfee2-109">Provides the collection of all activities that belong to the sub-tree of the current node, excluding the current node</span></span>  
  
 <xref:System.Activities.Validation.GetWorkflowTree>  
 <span data-ttu-id="dfee2-110">Viene fornita la raccolta di tutte le attività nello stesso albero del nodo corrente.</span><span class="sxs-lookup"><span data-stu-id="dfee2-110">Provides the collection of all activities in the same tree as the current node</span></span>  
  
 <span data-ttu-id="dfee2-111">Nell'esempio, un'attività <xref:System.Activities.Statements.ForEach%601> viene usata per esaminare la raccolta restituita da <xref:System.Activities.Validation.GetParentChain>.</span><span class="sxs-lookup"><span data-stu-id="dfee2-111">In the sample, a <xref:System.Activities.Statements.ForEach%601> activity is used to walk through the collection returned by <xref:System.Activities.Validation.GetParentChain>.</span></span> <span data-ttu-id="dfee2-112">Per ogni elemento nella raccolta, il tipo viene confrontato con `CreateCountry` (o `CreateState` se è in corso la convalida di `CreateCity`) e quando viene trovata una corrispondenza il flag del risultato viene impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="dfee2-112">For every element in the collection, its type is compared to `CreateCountry` (or `CreateState` if `CreateCity` is being validated), and when a match is found the result flag is set to `true`.</span></span> <span data-ttu-id="dfee2-113">Infine, viene usato <xref:System.Activities.Validation.AssertValidation> per generare un errore di convalida se il flag del risultato viene impostato su `false`.</span><span class="sxs-lookup"><span data-stu-id="dfee2-113">Finally, an <xref:System.Activities.Validation.AssertValidation> is used to generate a validation error if the result flag is set to `false`.</span></span>  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="dfee2-114">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="dfee2-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="dfee2-115">Aprire la soluzione di esempio ContainmentValidation.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dfee2-115">Open the ContainmentValidation.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="dfee2-116">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="dfee2-116">Build the solution.</span></span>  
  
3.  <span data-ttu-id="dfee2-117">Premere CTRL+F5 per avviare il programma.</span><span class="sxs-lookup"><span data-stu-id="dfee2-117">Press CTRL + F5 to launch the program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dfee2-118">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="dfee2-118">The samples may already be installed on your computer.</span></span> <span data-ttu-id="dfee2-119">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="dfee2-119">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="dfee2-120">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="dfee2-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dfee2-121">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="dfee2-121">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\ActivityRelationships`
