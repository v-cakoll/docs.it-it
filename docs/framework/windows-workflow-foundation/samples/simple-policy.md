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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0c704a9f3f27d63fb1a28db61f03cdc9b8de4370
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="simple-policy"></a><span data-ttu-id="1ae81-102">Criteri semplici</span><span class="sxs-lookup"><span data-stu-id="1ae81-102">Simple Policy</span></span>
<span data-ttu-id="1ae81-103">In questo esempio viene mostrato come usare un'attività <xref:System.Workflow.Activities.PolicyActivity> in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1ae81-103">This sample shows how to use a <xref:System.Workflow.Activities.PolicyActivity> activity in a workflow.</span></span>  
  
 <span data-ttu-id="1ae81-104">Il flusso di lavoro sequenziale in questo esempio viene creato usando un'attività <xref:System.Workflow.Activities.PolicyActivity>.</span><span class="sxs-lookup"><span data-stu-id="1ae81-104">The sequential workflow in this sample is created by using a <xref:System.Workflow.Activities.PolicyActivity> activity.</span></span> <span data-ttu-id="1ae81-105">Il flusso di lavoro definisce campi `orderValue`, `customerType` e `discount` usati per definire un flusso di lavoro di sconto del prodotto.</span><span class="sxs-lookup"><span data-stu-id="1ae81-105">The workflow defines `orderValue`, `customerType`, and `discount` fields that are used to define a product discount workflow.</span></span> <span data-ttu-id="1ae81-106">Le regole definite nel file delle regole impostano un valore di sconto basato su `orderValue` e `customerType`.</span><span class="sxs-lookup"><span data-stu-id="1ae81-106">The rules defined in the rules file set a discount value that is based on the `orderValue` and `customerType`.</span></span> <span data-ttu-id="1ae81-107">`orderValue` e `customerType` sono impostati nella definizione della classe `SimplePolicyWorkflow` e possono essere modificati per modificarne il comportamento.</span><span class="sxs-lookup"><span data-stu-id="1ae81-107">The `orderValue` and `customerType` are set in the `SimplePolicyWorkflow` class definition and can be changed to alter the behavior.</span></span> <span data-ttu-id="1ae81-108">Lo sconto risultante viene scritto nella console nel gestore eventi <xref:System.Workflow.Runtime.WorkflowRuntime.WorkflowCompleted> definito nella classe `SimplePolicyWorkflow`.</span><span class="sxs-lookup"><span data-stu-id="1ae81-108">The resulting discount is written to the console in the <xref:System.Workflow.Runtime.WorkflowRuntime.WorkflowCompleted> event handler that is defined in the `SimplePolicyWorkflow` class.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="1ae81-109">Per compilare l'esempio</span><span class="sxs-lookup"><span data-stu-id="1ae81-109">To build the sample</span></span>  
  
1.  <span data-ttu-id="1ae81-110">Aprire la soluzione in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ae81-110">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="1ae81-111">Premere CTRL+MAIUSC+B per compilare la soluzione,</span><span class="sxs-lookup"><span data-stu-id="1ae81-111">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="1ae81-112">Eseguire la soluzione senza debug premendo CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="1ae81-112">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="1ae81-113">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="1ae81-113">To run the sample</span></span>  
  
-   <span data-ttu-id="1ae81-114">Nella finestra del prompt dei comandi di SDK eseguire il file con estensione exe nella cartella SimplePolicy\bin\debug (oppure nella cartella SimplePolicy\bin per la versione Visual Basic dell'esempio), collocata sotto la cartella principale dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="1ae81-114">In the SDK Command Prompt window, run the .exe file in the SimplePolicy\bin\debug folder (or the SimplePolicy\bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1ae81-115">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="1ae81-115">The samples may already be installed on your computer.</span></span> <span data-ttu-id="1ae81-116">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="1ae81-116">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="1ae81-117">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ae81-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1ae81-118">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="1ae81-118">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\SimplePolicy`  
  
## <a name="see-also"></a><span data-ttu-id="1ae81-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ae81-119">See Also</span></span>  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [<span data-ttu-id="1ae81-120">Criteri avanzati</span><span class="sxs-lookup"><span data-stu-id="1ae81-120">Advanced Policy</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/advanced-policy.md)
