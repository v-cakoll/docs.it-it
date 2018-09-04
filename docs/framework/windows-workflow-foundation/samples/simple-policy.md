---
title: Criteri semplici
ms.date: 03/30/2017
ms.assetid: 6a94c834-2e32-4bed-9f47-ae5845eef6ff
ms.openlocfilehash: 7f189e4d1811cb0b7dd9138b944bfd0552481690
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43561264"
---
# <a name="simple-policy"></a><span data-ttu-id="e9ad4-102">Criteri semplici</span><span class="sxs-lookup"><span data-stu-id="e9ad4-102">Simple Policy</span></span>
<span data-ttu-id="e9ad4-103">In questo esempio viene mostrato come usare un'attività <xref:System.Workflow.Activities.PolicyActivity> in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e9ad4-103">This sample shows how to use a <xref:System.Workflow.Activities.PolicyActivity> activity in a workflow.</span></span>  
  
 <span data-ttu-id="e9ad4-104">Il flusso di lavoro sequenziale in questo esempio viene creato usando un'attività <xref:System.Workflow.Activities.PolicyActivity>.</span><span class="sxs-lookup"><span data-stu-id="e9ad4-104">The sequential workflow in this sample is created by using a <xref:System.Workflow.Activities.PolicyActivity> activity.</span></span> <span data-ttu-id="e9ad4-105">Il flusso di lavoro definisce campi `orderValue`, `customerType` e `discount` usati per definire un flusso di lavoro di sconto del prodotto.</span><span class="sxs-lookup"><span data-stu-id="e9ad4-105">The workflow defines `orderValue`, `customerType`, and `discount` fields that are used to define a product discount workflow.</span></span> <span data-ttu-id="e9ad4-106">Le regole definite nel file delle regole impostano un valore di sconto basato su `orderValue` e `customerType`.</span><span class="sxs-lookup"><span data-stu-id="e9ad4-106">The rules defined in the rules file set a discount value that is based on the `orderValue` and `customerType`.</span></span> <span data-ttu-id="e9ad4-107">`orderValue` e `customerType` sono impostati nella definizione della classe `SimplePolicyWorkflow` e possono essere modificati per modificarne il comportamento.</span><span class="sxs-lookup"><span data-stu-id="e9ad4-107">The `orderValue` and `customerType` are set in the `SimplePolicyWorkflow` class definition and can be changed to alter the behavior.</span></span> <span data-ttu-id="e9ad4-108">Lo sconto risultante viene scritto nella console nel gestore eventi <xref:System.Workflow.Runtime.WorkflowRuntime.WorkflowCompleted> definito nella classe `SimplePolicyWorkflow`.</span><span class="sxs-lookup"><span data-stu-id="e9ad4-108">The resulting discount is written to the console in the <xref:System.Workflow.Runtime.WorkflowRuntime.WorkflowCompleted> event handler that is defined in the `SimplePolicyWorkflow` class.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="e9ad4-109">Per compilare l'esempio</span><span class="sxs-lookup"><span data-stu-id="e9ad4-109">To build the sample</span></span>  
  
1.  <span data-ttu-id="e9ad4-110">Aprire la soluzione in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9ad4-110">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="e9ad4-111">Premere CTRL+MAIUSC+B per compilare la soluzione,</span><span class="sxs-lookup"><span data-stu-id="e9ad4-111">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="e9ad4-112">Eseguire la soluzione senza debug premendo CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="e9ad4-112">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="e9ad4-113">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="e9ad4-113">To run the sample</span></span>  
  
-   <span data-ttu-id="e9ad4-114">Nella finestra del prompt dei comandi di SDK eseguire il file con estensione exe nella cartella SimplePolicy\bin\debug (oppure nella cartella SimplePolicy\bin per la versione Visual Basic dell'esempio), collocata sotto la cartella principale dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="e9ad4-114">In the SDK Command Prompt window, run the .exe file in the SimplePolicy\bin\debug folder (or the SimplePolicy\bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e9ad4-115">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="e9ad4-115">The samples may already be installed on your computer.</span></span> <span data-ttu-id="e9ad4-116">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="e9ad4-116">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e9ad4-117">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="e9ad4-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e9ad4-118">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="e9ad4-118">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\SimplePolicy`  
  
## <a name="see-also"></a><span data-ttu-id="e9ad4-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9ad4-119">See Also</span></span>  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [<span data-ttu-id="e9ad4-120">Criteri avanzati</span><span class="sxs-lookup"><span data-stu-id="e9ad4-120">Advanced Policy</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/advanced-policy.md)
