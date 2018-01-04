---
title: Criteri avanzati
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75a22c88-5e54-4ae8-84cb-fbb22a612f0a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c83f4167ce1947b10f97e0cab5b5ddd2f8e00c76
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="advanced-policy"></a><span data-ttu-id="ef592-102">Criteri avanzati</span><span class="sxs-lookup"><span data-stu-id="ef592-102">Advanced Policy</span></span>
<span data-ttu-id="ef592-103">Questo esempio estende l'esempio di criterio semplice.</span><span class="sxs-lookup"><span data-stu-id="ef592-103">This sample extends the Simple Policy sample.</span></span> <span data-ttu-id="ef592-104">Oltre alle regole di sconto residenziale e sconto aziendale dell'esempio di criterio semplice, sono state aggiunte molte nuove regole.</span><span class="sxs-lookup"><span data-stu-id="ef592-104">In addition to the residential discount and business discount rules from the Simple Policy example, several new rules have been added.</span></span>  
  
 <span data-ttu-id="ef592-105">Viene aggiunta una regola per valori elevati, che consente uno sconto maggiore per gli ordini di alto valore.</span><span class="sxs-lookup"><span data-stu-id="ef592-105">A high-value rule is added, which provides a bigger discount for high-value orders.</span></span> <span data-ttu-id="ef592-106">Viene fornito un valore di priorità minore rispetto alle due regole precedenti che sovrascriverà il campo dello sconto e avrà la precedenza rispetto a entrambe le regole di sconto residenziale e aziendale.</span><span class="sxs-lookup"><span data-stu-id="ef592-106">It is given a priority value less than the previous two rules so that it will overwrite the discount field and take precedence over both the residential and business discount rules.</span></span>  
  
 <span data-ttu-id="ef592-107">Viene aggiunta una regola di calcolo del totale, che calcola il totale in base al livello di sconto.</span><span class="sxs-lookup"><span data-stu-id="ef592-107">A calculate total rule is also added, which computes the total based on the discount level.</span></span> <span data-ttu-id="ef592-108">Viene mostrato come fare riferimento a un metodo definito sull'attività del flusso di lavoro e come usare le azioni else.</span><span class="sxs-lookup"><span data-stu-id="ef592-108">It shows how to reference a method defined on the workflow activity, as well as how to use else actions.</span></span> <span data-ttu-id="ef592-109">Questa regola dimostra anche il comportamento mutevole, dal momento che verrà valutata a ogni modifica del campo di sconto.</span><span class="sxs-lookup"><span data-stu-id="ef592-109">This rule also demonstrates chaining behavior since it will be evaluated anytime the discount field changes.</span></span> <span data-ttu-id="ef592-110">Inoltre, viene mostrata l'attribuzione del metodo con RuleWriteAttribute sul metodo CalculateTotal.</span><span class="sxs-lookup"><span data-stu-id="ef592-110">Furthermore, method attributing is shown with the RuleWriteAttribute on the CalculateTotal method.</span></span> <span data-ttu-id="ef592-111">Ciò fa in modo che regole con impatto (ErrorTotalRule) vengano rivalutate ogni qualvolta il metodo viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="ef592-111">This causes impacted rules (ErrorTotalRule) to be re-evaluated whenever the method gets executed.</span></span>  
  
 <span data-ttu-id="ef592-112">L'ultima regola aggiunta rileva gli errori (in questo caso il Totale inferiore a 0).</span><span class="sxs-lookup"><span data-stu-id="ef592-112">The last rule added is one that detects errors (in this case, Total less than 0).</span></span> <span data-ttu-id="ef592-113">Se si verifica tale condizione, l'esecuzione del criterio verrà interrotta.</span><span class="sxs-lookup"><span data-stu-id="ef592-113">If this occurs, the policy execution is halted.</span></span>  
  
 <span data-ttu-id="ef592-114">Infine, vengono aggiunte le chiamate a `Console.Writeline` come azioni a ogni regola in modo da fornire più visibilità all'esecuzione della regola, dimostrando allo stesso tempo che è possibile accedere a metodi statici sui tipi a cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="ef592-114">Finally, `Console.Writeline` calls are added as actions to each rule to provide more visibility into rule execution, while also showing that it is possible to access static methods on referenced types.</span></span> <span data-ttu-id="ef592-115">È anche possibile usare il rilevamento per ottenere visibilità nelle regole eseguite.</span><span class="sxs-lookup"><span data-stu-id="ef592-115">You could also use tracking to get visibility into the rules that are executed.</span></span>  
  
 <span data-ttu-id="ef592-116">Le regole usate in questo esempio sono:</span><span class="sxs-lookup"><span data-stu-id="ef592-116">The rules used in this sample are:</span></span>  
  
 <span data-ttu-id="ef592-117">**ResidentialDiscountRule:**</span><span class="sxs-lookup"><span data-stu-id="ef592-117">**ResidentialDiscountRule:**</span></span>  
  
 <span data-ttu-id="ef592-118">IF OrderValue > 500 AND CustomerType = Residential</span><span class="sxs-lookup"><span data-stu-id="ef592-118">IF OrderValue > 500 AND CustomerType = Residential</span></span>  
  
 <span data-ttu-id="ef592-119">THEN Discount = 5%</span><span class="sxs-lookup"><span data-stu-id="ef592-119">THEN Discount = 5%</span></span>  
  
 <span data-ttu-id="ef592-120">**BusinessDiscountRule:**</span><span class="sxs-lookup"><span data-stu-id="ef592-120">**BusinessDiscountRule:**</span></span>  
  
 <span data-ttu-id="ef592-121">IF OrderValue > 10000 AND CustomerType = Business</span><span class="sxs-lookup"><span data-stu-id="ef592-121">IF OrderValue > 10000 AND CustomerType = Business</span></span>  
  
 <span data-ttu-id="ef592-122">THEN Discount = 10%</span><span class="sxs-lookup"><span data-stu-id="ef592-122">THEN Discount = 10%</span></span>  
  
 <span data-ttu-id="ef592-123">**HighValueDiscountRule:**</span><span class="sxs-lookup"><span data-stu-id="ef592-123">**HighValueDiscountRule:**</span></span>  
  
 <span data-ttu-id="ef592-124">IF OrderValue > 20000</span><span class="sxs-lookup"><span data-stu-id="ef592-124">IF OrderValue > 20000</span></span>  
  
 <span data-ttu-id="ef592-125">THEN Discount = 15%</span><span class="sxs-lookup"><span data-stu-id="ef592-125">THEN Discount = 15%</span></span>  
  
 <span data-ttu-id="ef592-126">**TotalRule:**</span><span class="sxs-lookup"><span data-stu-id="ef592-126">**TotalRule:**</span></span>  
  
 <span data-ttu-id="ef592-127">IF Discount > 0</span><span class="sxs-lookup"><span data-stu-id="ef592-127">IF Discount > 0</span></span>  
  
 <span data-ttu-id="ef592-128">THEN CalculateTotal(OrderValue, Discount)</span><span class="sxs-lookup"><span data-stu-id="ef592-128">THEN CalculateTotal(OrderValue, Discount)</span></span>  
  
 <span data-ttu-id="ef592-129">ELSE Total = OrderValue</span><span class="sxs-lookup"><span data-stu-id="ef592-129">ELSE Total = OrderValue</span></span>  
  
 <span data-ttu-id="ef592-130">**ErrorTotalRule:**</span><span class="sxs-lookup"><span data-stu-id="ef592-130">**ErrorTotalRule:**</span></span>  
  
 <span data-ttu-id="ef592-131">Se totale \< 0</span><span class="sxs-lookup"><span data-stu-id="ef592-131">IF Total \< 0</span></span>  
  
 <span data-ttu-id="ef592-132">THEN Error = "Fired ErrorTotalRule"; Halt</span><span class="sxs-lookup"><span data-stu-id="ef592-132">THEN Error = "Fired ErrorTotalRule"; Halt</span></span>  
  
 <span data-ttu-id="ef592-133">La valutazione e l'esecuzione delle regole può essere inoltre visualizzata tramite traccia e rilevamento.</span><span class="sxs-lookup"><span data-stu-id="ef592-133">Rule evaluation and execution can also be seen through tracing and tracking.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="ef592-134">Per compilare l'esempio</span><span class="sxs-lookup"><span data-stu-id="ef592-134">To build the sample</span></span>  
  
1.  <span data-ttu-id="ef592-135">Aprire la soluzione in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef592-135">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="ef592-136">Premere CTRL+MAIUSC+B per compilare la soluzione,</span><span class="sxs-lookup"><span data-stu-id="ef592-136">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="ef592-137">Eseguire la soluzione senza debug premendo CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="ef592-137">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="ef592-138">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="ef592-138">To run the sample</span></span>  
  
-   <span data-ttu-id="ef592-139">Nella finestra del prompt dei comandi di SDK eseguire il file con estensione exe nella cartella AdvancedPolicy\bin\debug (oppure nella cartella AdvancedPolicy\bin per la versione Visual Basic dell'esempio), collocata sotto la cartella principale dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="ef592-139">In the SDK Command Prompt window, run the .exe file in the AdvancedPolicy\bin\debug folder (or the AdvancedPolicy \bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ef592-140">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="ef592-140">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ef592-141">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="ef592-141">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ef592-142">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ef592-142">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ef592-143">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="ef592-143">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\AdvancedPolicy`  
  
## <a name="see-also"></a><span data-ttu-id="ef592-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef592-144">See Also</span></span>  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [<span data-ttu-id="ef592-145">Criteri semplici</span><span class="sxs-lookup"><span data-stu-id="ef592-145">Simple Policy</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/simple-policy.md)
