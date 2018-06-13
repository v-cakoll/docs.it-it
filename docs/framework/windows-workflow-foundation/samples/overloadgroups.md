---
title: OverloadGroups
ms.date: 03/30/2017
ms.assetid: d1d547d2-f5fb-4de3-a959-ee6139a4f1ad
ms.openlocfilehash: 489d27e05c96d3b3893052254a879d1c9d75788c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515623"
---
# <a name="overloadgroups"></a><span data-ttu-id="37f73-102">OverloadGroups</span><span class="sxs-lookup"><span data-stu-id="37f73-102">OverloadGroups</span></span>
<span data-ttu-id="37f73-103">Questo esempio è costituito da un'attività (`CreateLocation`) che dispone di due caratteristiche interessanti:</span><span class="sxs-lookup"><span data-stu-id="37f73-103">This sample consists of an activity (`CreateLocation`), which has two interesting characteristics:</span></span>  
  
1.  <span data-ttu-id="37f73-104">Presenta alcuni argomenti obbligatori e alcuni facoltativi.</span><span class="sxs-lookup"><span data-stu-id="37f73-104">It has some required arguments and some optional ones.</span></span>  
  
2.  <span data-ttu-id="37f73-105">Consente all'utente di scegliere di fornire uno di due set diversi di argomenti.</span><span class="sxs-lookup"><span data-stu-id="37f73-105">It allows the user to choose to provide one of two different sets of arguments.</span></span>  
  
 <span data-ttu-id="37f73-106">Questi comportamenti sono portati a termine usando queste due funzionalità:</span><span class="sxs-lookup"><span data-stu-id="37f73-106">These behaviors are accomplished by using these two features:</span></span>  
  
-   <span data-ttu-id="37f73-107">`[isRequired]` convalida l'assegnazione di un'attività specifica da parte di una proprietà e, in caso contrario, genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="37f73-107">`[isRequired]` validates that a property of a specific activity is assign, and if not, it throws an exception.</span></span>  
  
-   <span data-ttu-id="37f73-108">`[OverloadGroup]` raggruppa un set di argomenti, in modo che l'utente dell'attività possa scegliere quale usare.</span><span class="sxs-lookup"><span data-stu-id="37f73-108">`[OverloadGroup]` puts together a set of arguments, so that the user of the activity can choose between using one set or another.</span></span> <span data-ttu-id="37f73-109">L'utente non può usare argomenti da gruppi di overload diversi nella stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="37f73-109">The user cannot use arguments from different Overload Groups in the same instance.</span></span>  
  
 <span data-ttu-id="37f73-110">Dopo avere configurato flussi di lavoro diversi, chiamare il metodo <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> che restituisce una raccolta <xref:System.Activities.Validation.ValidationResults> di oggetti <xref:System.Activities.Validation.Constraint>.</span><span class="sxs-lookup"><span data-stu-id="37f73-110">After setting up different workflows, call <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> which returns a <xref:System.Activities.Validation.ValidationResults> collection of <xref:System.Activities.Validation.Constraint>.</span></span> <span data-ttu-id="37f73-111">Stampare gli oggetti <xref:System.Activities.Validation.Constraint> nella console.</span><span class="sxs-lookup"><span data-stu-id="37f73-111">Print the <xref:System.Activities.Validation.Constraint> objects to the console.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="37f73-112">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="37f73-112">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="37f73-113">Aprire il **OverloadGroups.sln** soluzione di esempio [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37f73-113">Open the **OverloadGroups.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="37f73-114">Compilare ed eseguire la soluzione.</span><span class="sxs-lookup"><span data-stu-id="37f73-114">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="37f73-115">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="37f73-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="37f73-116">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="37f73-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="37f73-117">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="37f73-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="37f73-118">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="37f73-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\OverloadGroups`
