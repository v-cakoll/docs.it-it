---
title: OverloadGroups
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d1d547d2-f5fb-4de3-a959-ee6139a4f1ad
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2a5ab416dc484dddc0b6aa0ec25757921815c723
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="overloadgroups"></a><span data-ttu-id="ac171-102">OverloadGroups</span><span class="sxs-lookup"><span data-stu-id="ac171-102">OverloadGroups</span></span>
<span data-ttu-id="ac171-103">Questo esempio è costituito da un'attività (`CreateLocation`) che dispone di due caratteristiche interessanti:</span><span class="sxs-lookup"><span data-stu-id="ac171-103">This sample consists of an activity (`CreateLocation`), which has two interesting characteristics:</span></span>  
  
1.  <span data-ttu-id="ac171-104">Presenta alcuni argomenti obbligatori e alcuni facoltativi.</span><span class="sxs-lookup"><span data-stu-id="ac171-104">It has some required arguments and some optional ones.</span></span>  
  
2.  <span data-ttu-id="ac171-105">Consente all'utente di scegliere di fornire uno di due set diversi di argomenti.</span><span class="sxs-lookup"><span data-stu-id="ac171-105">It allows the user to choose to provide one of two different sets of arguments.</span></span>  
  
 <span data-ttu-id="ac171-106">Questi comportamenti sono portati a termine usando queste due funzionalità:</span><span class="sxs-lookup"><span data-stu-id="ac171-106">These behaviors are accomplished by using these two features:</span></span>  
  
-   <span data-ttu-id="ac171-107">`[isRequired]` convalida l'assegnazione di un'attività specifica da parte di una proprietà e, in caso contrario, genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="ac171-107">`[isRequired]` validates that a property of a specific activity is assign, and if not, it throws an exception.</span></span>  
  
-   <span data-ttu-id="ac171-108">`[OverloadGroup]` raggruppa un set di argomenti, in modo che l'utente dell'attività possa scegliere quale usare.</span><span class="sxs-lookup"><span data-stu-id="ac171-108">`[OverloadGroup]` puts together a set of arguments, so that the user of the activity can choose between using one set or another.</span></span> <span data-ttu-id="ac171-109">L'utente non può usare argomenti da gruppi di overload diversi nella stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="ac171-109">The user cannot use arguments from different Overload Groups in the same instance.</span></span>  
  
 <span data-ttu-id="ac171-110">Dopo avere configurato flussi di lavoro diversi, chiamare <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> che restituisce un <xref:System.Activities.Validation.ValidationResults> insieme di <!--zz <xref:System.Activities.Validation.ConstraintViolation>--> `System.Activities.Validation.ConstraintViolation`.</span><span class="sxs-lookup"><span data-stu-id="ac171-110">After setting up different workflows, call <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> which returns a <xref:System.Activities.Validation.ValidationResults> collection of <!--zz <xref:System.Activities.Validation.ConstraintViolation>--> `System.Activities.Validation.ConstraintViolation`.</span></span> <span data-ttu-id="ac171-111">Stampa il <!--zz <xref:System.Activities.Validation.ConstraintViolation>--> `System.Activities.Validation.ConstraintViolation` oggetti nella console.</span><span class="sxs-lookup"><span data-stu-id="ac171-111">Print the <!--zz <xref:System.Activities.Validation.ConstraintViolation>--> `System.Activities.Validation.ConstraintViolation` objects to the console.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ac171-112">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="ac171-112">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="ac171-113">Aprire il **OverloadGroups.sln** soluzione di esempio [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac171-113">Open the **OverloadGroups.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="ac171-114">Compilare ed eseguire la soluzione.</span><span class="sxs-lookup"><span data-stu-id="ac171-114">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ac171-115">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="ac171-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ac171-116">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="ac171-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ac171-117">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ac171-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ac171-118">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="ac171-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\OverloadGroups`  
  
## <a name="see-also"></a><span data-ttu-id="ac171-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac171-119">See Also</span></span>
