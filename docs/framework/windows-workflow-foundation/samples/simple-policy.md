---
title: Criteri semplici
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a94c834-2e32-4bed-9f47-ae5845eef6ff
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6a2798c753e1fc526b2f95801d49108a2aba9e8a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="simple-policy"></a><span data-ttu-id="9ef33-102">Criteri semplici</span><span class="sxs-lookup"><span data-stu-id="9ef33-102">Simple Policy</span></span>
<span data-ttu-id="9ef33-103">In questo esempio viene mostrato come usare un'attività <xref:System.Workflow.Activities.PolicyActivity> in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9ef33-103">This sample shows how to use a <xref:System.Workflow.Activities.PolicyActivity> activity in a workflow.</span></span>  
  
 <span data-ttu-id="9ef33-104">Il flusso di lavoro sequenziale in questo esempio viene creato usando un'attività <xref:System.Workflow.Activities.PolicyActivity>.</span><span class="sxs-lookup"><span data-stu-id="9ef33-104">The sequential workflow in this sample is created by using a <xref:System.Workflow.Activities.PolicyActivity> activity.</span></span> <span data-ttu-id="9ef33-105">Il flusso di lavoro definisce campi `orderValue`, `customerType` e `discount` usati per definire un flusso di lavoro di sconto del prodotto.</span><span class="sxs-lookup"><span data-stu-id="9ef33-105">The workflow defines `orderValue`, `customerType`, and `discount` fields that are used to define a product discount workflow.</span></span> <span data-ttu-id="9ef33-106">Le regole definite nel file delle regole impostano un valore di sconto basato su `orderValue` e `customerType`.</span><span class="sxs-lookup"><span data-stu-id="9ef33-106">The rules defined in the rules file set a discount value that is based on the `orderValue` and `customerType`.</span></span> <span data-ttu-id="9ef33-107">`orderValue` e `customerType` sono impostati nella definizione della classe `SimplePolicyWorkflow` e possono essere modificati per modificarne il comportamento.</span><span class="sxs-lookup"><span data-stu-id="9ef33-107">The `orderValue` and `customerType` are set in the `SimplePolicyWorkflow` class definition and can be changed to alter the behavior.</span></span> <span data-ttu-id="9ef33-108">Lo sconto risultante viene scritto nella console nel gestore eventi <xref:System.Workflow.Runtime.WorkflowRuntime.WorkflowCompleted> definito nella classe `SimplePolicyWorkflow`.</span><span class="sxs-lookup"><span data-stu-id="9ef33-108">The resulting discount is written to the console in the <xref:System.Workflow.Runtime.WorkflowRuntime.WorkflowCompleted> event handler that is defined in the `SimplePolicyWorkflow` class.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="9ef33-109">Per compilare l'esempio</span><span class="sxs-lookup"><span data-stu-id="9ef33-109">To build the sample</span></span>  
  
1.  <span data-ttu-id="9ef33-110">Aprire la soluzione in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ef33-110">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="9ef33-111">Premere CTRL+MAIUSC+B per compilare la soluzione,</span><span class="sxs-lookup"><span data-stu-id="9ef33-111">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="9ef33-112">Eseguire la soluzione senza debug premendo CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="9ef33-112">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="9ef33-113">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="9ef33-113">To run the sample</span></span>  
  
-   <span data-ttu-id="9ef33-114">Nella finestra del prompt dei comandi di SDK eseguire il file con estensione exe nella cartella SimplePolicy\bin\debug (oppure nella cartella SimplePolicy\bin per la versione Visual Basic dell'esempio), collocata sotto la cartella principale dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="9ef33-114">In the SDK Command Prompt window, run the .exe file in the SimplePolicy\bin\debug folder (or the SimplePolicy\bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9ef33-115">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="9ef33-115">The samples may already be installed on your computer.</span></span> <span data-ttu-id="9ef33-116">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="9ef33-116">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9ef33-117">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9ef33-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9ef33-118">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="9ef33-118">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\SimplePolicy`  
  
## <a name="see-also"></a><span data-ttu-id="9ef33-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ef33-119">See Also</span></span>  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [<span data-ttu-id="9ef33-120">Criteri avanzati</span><span class="sxs-lookup"><span data-stu-id="9ef33-120">Advanced Policy</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/advanced-policy.md)
