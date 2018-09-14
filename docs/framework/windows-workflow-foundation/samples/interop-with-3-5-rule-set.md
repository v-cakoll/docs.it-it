---
title: Interoperabilità con il set di regole 3.5
ms.date: 03/30/2017
ms.assetid: 969f3295-d874-428c-a9c6-623e3d578e51
ms.openlocfilehash: 5ea5454ef80bfd83611ed20392782d99cd8c0c25
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45510146"
---
# <a name="interop-with-35-rule-set"></a><span data-ttu-id="47a3a-102">Interoperabilità con il set di regole 3.5</span><span class="sxs-lookup"><span data-stu-id="47a3a-102">Interop with 3.5 Rule Set</span></span>
<span data-ttu-id="47a3a-103">Questo esempio viene illustrato l'utilizzo dei <xref:System.Activities.Statements.Interop> attività per l'integrazione con un'attività personalizzata in [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] usando <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` e regole.</span><span class="sxs-lookup"><span data-stu-id="47a3a-103">This sample demonstrates the use of the <xref:System.Activities.Statements.Interop> activity to integrate with a custom activity in [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] using <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` and rules.</span></span> <span data-ttu-id="47a3a-104">Passa i dati all'attività personalizzata associando le variabili di [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] alle proprietà di dipendenza esposte dall'attività personalizzata.</span><span class="sxs-lookup"><span data-stu-id="47a3a-104">It passes data to the custom activity by binding [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] variables to the dependency properties exposed by the custom activity.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47a3a-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="47a3a-105">Requirements</span></span>  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]  
  
2.  [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]  
  
3.  [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)]  
  
## <a name="demonstrates"></a><span data-ttu-id="47a3a-106">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="47a3a-106">Demonstrates</span></span>  
 <span data-ttu-id="47a3a-107"><xref:System.Activities.Statements.Interop> attività, <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` attività [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] con le proprietà di dipendenza</span><span class="sxs-lookup"><span data-stu-id="47a3a-107"><xref:System.Activities.Statements.Interop> activity, <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` activity in [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] with dependency properties</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="47a3a-108">Discussione</span><span class="sxs-lookup"><span data-stu-id="47a3a-108">Discussion</span></span>  
 <span data-ttu-id="47a3a-109">Nell'esempio viene illustrato uno degli scenari di integrazione con un'attività [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="47a3a-109">The sample demonstrates one of the integration scenarios for integrating with a [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] activity.</span></span> <span data-ttu-id="47a3a-110">In questo esempio include un' [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] attività personalizzata che richiama un <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` attività.</span><span class="sxs-lookup"><span data-stu-id="47a3a-110">This sample includes a [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] custom activity that invokes a <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` activity.</span></span>  
  
## <a name="travelrulelibrary"></a><span data-ttu-id="47a3a-111">TravelRuleLibrary</span><span class="sxs-lookup"><span data-stu-id="47a3a-111">TravelRuleLibrary</span></span>  
 <span data-ttu-id="47a3a-112">L'apertura di TravelRuleSet.cs nella finestra di progettazione mostra un'attività sequenziale personalizzata contenente un'attività Policy come riportato di seguito</span><span class="sxs-lookup"><span data-stu-id="47a3a-112">Opening TravelRuleSet.cs in the designer shows a custom sequential activity that contains a Policy activity as follows</span></span>  
  
 <span data-ttu-id="47a3a-113">![Attività di interoperabilità](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulespolicy.jpg "InteropRulesPolicy")</span><span class="sxs-lookup"><span data-stu-id="47a3a-113">![Interop Activity](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulespolicy.jpg "InteropRulesPolicy")</span></span>  
  
 <span data-ttu-id="47a3a-114">Fare doppio clic il **DiscountPolicy** attività relativa ai criteri per esaminare le regole.</span><span class="sxs-lookup"><span data-stu-id="47a3a-114">Double-click the **DiscountPolicy** policy activity to examine the rules.</span></span> <span data-ttu-id="47a3a-115">che possono essere visualizzate nel relativo editor.</span><span class="sxs-lookup"><span data-stu-id="47a3a-115">The Rules editor appears to show the rules.</span></span>  
  
 <span data-ttu-id="47a3a-116">![Editor Set di regole](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesruleseteditor.jpg "InteropRulesRuleSetEditor")</span><span class="sxs-lookup"><span data-stu-id="47a3a-116">![Rule Set Editor](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesruleseteditor.jpg "InteropRulesRuleSetEditor")</span></span>  
  
 <span data-ttu-id="47a3a-117">Fare doppio clic il **DiscountPolicy** attività e selezionare il **Visualizza codice** possibilità di esaminare il code-beside codice c# da associare a questa attività.</span><span class="sxs-lookup"><span data-stu-id="47a3a-117">Right-click the **DiscountPolicy** activity and select the **View Code** option to examine the code-beside C# code that goes with this activity.</span></span> <span data-ttu-id="47a3a-118">Osservare l'impostazione della proprietà di dipendenza per l'oggetto `DiscountLevel`.</span><span class="sxs-lookup"><span data-stu-id="47a3a-118">Observe the dependency property setting for `DiscountLevel`.</span></span> <span data-ttu-id="47a3a-119">È uguale a un oggetto <xref:System.Activities.Argument> in [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="47a3a-119">This is equivalent to an <xref:System.Activities.Argument> in [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].</span></span>  
  
```  
public static DependencyProperty DiscountLevelProperty = DependencyProperty.Register("DiscountLevel", typeof(int), typeof(TravelRuleSet));  
  
[DescriptionAttribute("DiscountLevel")]  
[CategoryAttribute("DiscountLevel Category")]  
[BrowsableAttribute(true)]  
[DesignerSerializationVisibilityAttribute(DesignerSerializationVisibility.Visible)]  
public int DiscountLevel  
{  
   get  
   {  
return ((int)base.GetValue(TravelRuleSet.DiscountLevelProperty)));  
   }  
   set  
   {  
base.SetValue(TravelRuleSet.DiscountLevelProperty, value);  
   }  
}  
```  
  
## <a name="interopwith35ruleset"></a><span data-ttu-id="47a3a-120">InteropWith35RuleSet</span><span class="sxs-lookup"><span data-stu-id="47a3a-120">InteropWith35RuleSet</span></span>  
 <span data-ttu-id="47a3a-121">Si tratta di un flusso di lavoro sequenziale di [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] che usa l'attività <xref:System.Activities.Statements.Interop> per eseguire l'integrazione con l'oggetto RuleSet personalizzato creato nel progetto TravelRuleLibrary.</span><span class="sxs-lookup"><span data-stu-id="47a3a-121">This is a [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] sequential workflow project that uses the <xref:System.Activities.Statements.Interop> activity to integrate with the custom rule set created in the TravelRuleLibrary project.</span></span> <span data-ttu-id="47a3a-122">Le variabili vengono create nell'oggetto <xref:System.Activities.Statements.Sequence> di primo livello come riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="47a3a-122">Variables are created on the top-level <xref:System.Activities.Statements.Sequence> as follows.</span></span>  
  
 <span data-ttu-id="47a3a-123">![Le variabili](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesvariables.jpg "InteropRulesVariables")</span><span class="sxs-lookup"><span data-stu-id="47a3a-123">![Variables](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesvariables.jpg "InteropRulesVariables")</span></span>  
  
 <span data-ttu-id="47a3a-124">![Esplora soluzioni](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulessolutionexplorer.jpg "InteropRulesSolutionExplorer")</span><span class="sxs-lookup"><span data-stu-id="47a3a-124">![Solution Explorer](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulessolutionexplorer.jpg "InteropRulesSolutionExplorer")</span></span>  
  
 <span data-ttu-id="47a3a-125">Infine, l'attività <xref:System.Activities.Statements.Interop> viene usata per eseguire l'integrazione con TravelRuleSet.</span><span class="sxs-lookup"><span data-stu-id="47a3a-125">Lastly, the <xref:System.Activities.Statements.Interop> activity is used to integrate with the TravelRuleSet.</span></span> <span data-ttu-id="47a3a-126">Le variabili dichiarate precedentemente nell'oggetto <xref:System.Activities.Statements.Sequence> vengono usate per eseguire l'associazione alle proprietà di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="47a3a-126">The variables that were declared earlier on the <xref:System.Activities.Statements.Sequence> are used to bind to the dependency properties.</span></span>  
  
 <span data-ttu-id="47a3a-127">![Tipo di attività](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprules.jpg "InteropRules")</span><span class="sxs-lookup"><span data-stu-id="47a3a-127">![Activity Type](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprules.jpg "InteropRules")</span></span>  
  
 <span data-ttu-id="47a3a-128">![Freccia](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesarrow.jpg "InteropRulesArrow")</span><span class="sxs-lookup"><span data-stu-id="47a3a-128">![Arrow](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesarrow.jpg "InteropRulesArrow")</span></span>  
  
 <span data-ttu-id="47a3a-129">![Le proprietà](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesproperties.jpg "InteropRulesProperties")</span><span class="sxs-lookup"><span data-stu-id="47a3a-129">![Properties](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesproperties.jpg "InteropRulesProperties")</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="47a3a-130">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="47a3a-130">The samples may already be installed on your machine.</span></span> <span data-ttu-id="47a3a-131">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="47a3a-131">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="47a3a-132">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="47a3a-132">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="47a3a-133">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="47a3a-133">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InteropWith35RuleSet`
