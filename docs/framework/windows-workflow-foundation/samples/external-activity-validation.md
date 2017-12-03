---
title: "Convalida di attività esterna"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49619f59-9819-484a-bcd8-5596308e8551
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6ebc79fa582a32ccc252e6c22b9b223870da7e44
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="external-activity-validation"></a><span data-ttu-id="d660e-102">Convalida di attività esterna</span><span class="sxs-lookup"><span data-stu-id="d660e-102">External Activity Validation</span></span>
<span data-ttu-id="d660e-103">In questo esempio viene illustrato come aggiungere la logica di convalida a un'attività incorporata di cui l'utente non è l'autore.</span><span class="sxs-lookup"><span data-stu-id="d660e-103">This sample shows how to add validation logic to a built-in activity that you are not the author of.</span></span> <span data-ttu-id="d660e-104">La logica di convalida consiste nell'imporre che tutte le attività <xref:System.Activities.Statements.If> presenti nel flusso di lavoro dispongano d un proprio set di proprietà <xref:System.Activities.Statements.If.Then%2A> o <xref:System.Activities.Statements.If.Else%2A>.</span><span class="sxs-lookup"><span data-stu-id="d660e-104">The validation logic consists of enforcing that all <xref:System.Activities.Statements.If> activities present in the workflow either have their <xref:System.Activities.Statements.If.Then%2A> property set or their <xref:System.Activities.Statements.If.Else%2A> property set.</span></span> <span data-ttu-id="d660e-105">La logica di convalida include inoltre la verifica che tutte le attività <xref:System.Activities.Statements.Pick> presenti nel flusso di lavoro dispongano di più di un ramo e, in caso contrario, che venga generato un avviso.</span><span class="sxs-lookup"><span data-stu-id="d660e-105">Also, the validation logic includes checking that all <xref:System.Activities.Statements.Pick> activities present in the workflow have more than one branch, and if that is not the case, a warning is generated.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="d660e-106">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="d660e-106">Sample details</span></span>  
 <span data-ttu-id="d660e-107">Questo esempio crea un flusso di lavoro con un'istanza di ogni attività da convalidare: l'attività <xref:System.Activities.Statements.If> e l'attività <xref:System.Activities.Statements.Pick>.</span><span class="sxs-lookup"><span data-stu-id="d660e-107">This sample creates a workflow with an instance of each activity to validate: the <xref:System.Activities.Statements.If> activity and the <xref:System.Activities.Statements.Pick> activity.</span></span> <span data-ttu-id="d660e-108">Per ogni comportamento di convalida viene creato <xref:System.Activities.Validation.Constraint>.</span><span class="sxs-lookup"><span data-stu-id="d660e-108">A <xref:System.Activities.Validation.Constraint> is created for each validation behavior.</span></span> <span data-ttu-id="d660e-109">I vincoli creati in questo esempio sono `ConstraintError_IfShouldHaveThenOrElse` e `ConstraintWarning_PickHasOneBranch`.</span><span class="sxs-lookup"><span data-stu-id="d660e-109">The constraints created in this sample are `ConstraintError_IfShouldHaveThenOrElse` and `ConstraintWarning_PickHasOneBranch`.</span></span> <span data-ttu-id="d660e-110">Questi vincoli vengono quindi aggiunti alla raccolta `AdditionalConstraints` di un'istanza di <xref:System.Activities.Validation.ValidationSettings>.</span><span class="sxs-lookup"><span data-stu-id="d660e-110">Next, these constraints are added to the `AdditionalConstraints` collection of a <xref:System.Activities.Validation.ValidationSettings> instance.</span></span> <span data-ttu-id="d660e-111">Infine, viene chiamato il metodo `static`<xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> di <xref:System.Activities.Validation.ActivityValidationServices> per convalidare le attività nel flusso di lavoro e i risultati della convalida vengono stampati nella console.</span><span class="sxs-lookup"><span data-stu-id="d660e-111">Finally, the `static`<xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> method of <xref:System.Activities.Validation.ActivityValidationServices> is called to validate the activities in the workflow and the validation results are printed out to the console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d660e-112">È possibile aggiungere vincoli di criteri a qualsiasi attività.</span><span class="sxs-lookup"><span data-stu-id="d660e-112">You can add policy constraints to any activity.</span></span> <span data-ttu-id="d660e-113">Ad esempio, è possibile aggiungere un vincolo di criteri a un'attività <xref:System.Activities.Statements.Sequence> o <xref:System.Activities.Statements.Parallel>.</span><span class="sxs-lookup"><span data-stu-id="d660e-113">For example, you can add a policy constraint to a <xref:System.Activities.Statements.Sequence> or <xref:System.Activities.Statements.Parallel> activity.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="d660e-114">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="d660e-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="d660e-115">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione ExternalActivityValidation.sln.</span><span class="sxs-lookup"><span data-stu-id="d660e-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ExternalActivityValidation.sln file.</span></span>  
  
2.  <span data-ttu-id="d660e-116">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="d660e-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="d660e-117">Per eseguire la soluzione, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="d660e-117">To run the solution, press Ctrl+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d660e-118">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="d660e-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d660e-119">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="d660e-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d660e-120">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d660e-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d660e-121">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="d660e-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\ExternalActivityValidation`