---
title: Utilizzo di variabili con un set di regole di .NET Framework 3.5
ms.date: 03/30/2017
ms.assetid: 27b56249-22fe-4252-840f-74c0d6c7a6b3
ms.openlocfilehash: 64d47564076e19e152e30b6ab0cb3900ce53cfa1
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43512854"
---
# <a name="using-variables-with-a-net-framework-35-ruleset"></a><span data-ttu-id="a2de3-102">Utilizzo di variabili con un set di regole di .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="a2de3-102">Using Variables with a .NET Framework 3.5 Ruleset</span></span>
<span data-ttu-id="a2de3-103">In questo esempio viene illustrato come creare un flusso di lavoro che usa l'attività <xref:System.Activities.Statements.Interop> per integrare un'attività personalizzata scritta in [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] che usa criteri e regole.</span><span class="sxs-lookup"><span data-stu-id="a2de3-103">This sample demonstrates how to create a workflow that uses the <xref:System.Activities.Statements.Interop> activity to integrate a custom activity written in [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] that uses policy and rules.</span></span> <span data-ttu-id="a2de3-104">I dati vengono passati dal flusso di lavoro all'attività personalizzata associando variabili alle proprietà di dipendenza esposte dall'attività personalizzata.</span><span class="sxs-lookup"><span data-stu-id="a2de3-104">The workflow passes data to the custom activity by binding variables to the dependency properties exposed by the custom activity.</span></span>  
  
## <a name="sample-walkthrough"></a><span data-ttu-id="a2de3-105">Scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="a2de3-105">Sample walkthrough</span></span>  
  
#### <a name="to-examine-travelrulelibrary"></a><span data-ttu-id="a2de3-106">Per esaminare TravelRuleLibrary</span><span class="sxs-lookup"><span data-stu-id="a2de3-106">To examine TravelRuleLibrary</span></span>  
  
1.  <span data-ttu-id="a2de3-107">Usa Visual Studio, aprire la soluzione interopwith35ruleset.sln.</span><span class="sxs-lookup"><span data-stu-id="a2de3-107">Using Visual Studio, open the InteropWith35RuleSet.sln solution file.</span></span>  
  
2.  <span data-ttu-id="a2de3-108">Aprire TravelRuleSet.cs nella finestra di progettazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a2de3-108">Open the TravelRuleSet.cs in the workflow designer.</span></span>  
  
     <span data-ttu-id="a2de3-109">Viene visualizzata un'attività sequenziale personalizzata che contiene <xref:System.Workflow.Activities.PolicyActivity>.</span><span class="sxs-lookup"><span data-stu-id="a2de3-109">A custom sequential activity that contains a <xref:System.Workflow.Activities.PolicyActivity> is displayed.</span></span>  
  
3.  <span data-ttu-id="a2de3-110">Fare doppio clic sull'attività dei criteri DiscountPolicy per esaminare le regole</span><span class="sxs-lookup"><span data-stu-id="a2de3-110">Double-click the DiscountPolicy policy activity to examine the rules.</span></span>  
  
     <span data-ttu-id="a2de3-111">che possono essere visualizzate nel relativo editor.</span><span class="sxs-lookup"><span data-stu-id="a2de3-111">The Rules editor pops up to show the rules.</span></span>  
  
4.  <span data-ttu-id="a2de3-112">Fare clic il `DiscountPolicy` e selezionare il **Visualizza codice** possibilità di esaminare il code-beside codice c# per l'attività.</span><span class="sxs-lookup"><span data-stu-id="a2de3-112">Right click the `DiscountPolicy` and select the **View Code** option to examine the code beside C# code for the activity.</span></span>  
  
     <span data-ttu-id="a2de3-113">Osservare l'impostazione della proprietà di dipendenza per l'oggetto `DiscountLevel`.</span><span class="sxs-lookup"><span data-stu-id="a2de3-113">Observe the dependency property setting for `DiscountLevel`.</span></span> <span data-ttu-id="a2de3-114">È equivalente agli argomenti in [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a2de3-114">This is equivalent to arguments in [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].</span></span> <span data-ttu-id="a2de3-115">Per altre informazioni sugli argomenti, vedere [variabili e argomenti](../../../../docs/framework/windows-workflow-foundation/variables-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="a2de3-115">For more information about arguments, see [Variables and Arguments](../../../../docs/framework/windows-workflow-foundation/variables-and-arguments.md).</span></span>  
  
## <a name="interopwith35ruleset"></a><span data-ttu-id="a2de3-116">InteropWith35RuleSet</span><span class="sxs-lookup"><span data-stu-id="a2de3-116">InteropWith35RuleSet</span></span>  
 <span data-ttu-id="a2de3-117">Si tratta di un progetto di flusso di lavoro sequenziale che usa l'attività <xref:System.Activities.Statements.Interop> per eseguire l'integrazione con il set di regole personalizzato creato nel progetto `TravelRuleLibrary`.</span><span class="sxs-lookup"><span data-stu-id="a2de3-117">This is a sequential workflow project that uses the <xref:System.Activities.Statements.Interop> activity to integrate with the custom Rule set created in the `TravelRuleLibrary` project.</span></span> <span data-ttu-id="a2de3-118">Le variabili vengono create nell'attività <xref:System.Activities.Statements.Sequence> di primo livello.</span><span class="sxs-lookup"><span data-stu-id="a2de3-118">Variables are created on the top level <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="a2de3-119">L'attività <xref:System.Activities.Statements.Interop> viene usata per eseguire l'integrazione con l'attività `TravelRuleSet`.</span><span class="sxs-lookup"><span data-stu-id="a2de3-119">The <xref:System.Activities.Statements.Interop> activity is used to integrate with the `TravelRuleSet` activity.</span></span> <span data-ttu-id="a2de3-120">Le variabili dichiarate nell'oggetto <xref:System.Activities.Statements.Sequence> vengono usate per eseguire l'associazione alle proprietà di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="a2de3-120">The variables that are declared on the <xref:System.Activities.Statements.Sequence> are used to bind to the dependency properties.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="a2de3-121">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="a2de3-121">To use this sample</span></span>  
  
1.  <span data-ttu-id="a2de3-122">Tramite [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione InteropWith35RuleSet.sln.</span><span class="sxs-lookup"><span data-stu-id="a2de3-122">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the InteropWith35RuleSet.sln solution file.</span></span>  
  
2.  <span data-ttu-id="a2de3-123">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="a2de3-123">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="a2de3-124">Per eseguire la soluzione, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="a2de3-124">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a2de3-125">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="a2de3-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a2de3-126">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="a2de3-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a2de3-127">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="a2de3-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a2de3-128">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="a2de3-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InteropWith35RuleSet`