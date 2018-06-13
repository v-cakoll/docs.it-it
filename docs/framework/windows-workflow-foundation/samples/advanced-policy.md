---
title: Criteri avanzati
ms.date: 03/30/2017
ms.assetid: 75a22c88-5e54-4ae8-84cb-fbb22a612f0a
ms.openlocfilehash: 81cf2fb428833d4ca8cccf197011b69f2ccf3108
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515555"
---
# <a name="advanced-policy"></a><span data-ttu-id="1da1f-102">Criteri avanzati</span><span class="sxs-lookup"><span data-stu-id="1da1f-102">Advanced Policy</span></span>
<span data-ttu-id="1da1f-103">Questo esempio estende l'esempio di criterio semplice.</span><span class="sxs-lookup"><span data-stu-id="1da1f-103">This sample extends the Simple Policy sample.</span></span> <span data-ttu-id="1da1f-104">Oltre alle regole di sconto residenziale e sconto aziendale dell'esempio di criterio semplice, sono state aggiunte molte nuove regole.</span><span class="sxs-lookup"><span data-stu-id="1da1f-104">In addition to the residential discount and business discount rules from the Simple Policy example, several new rules have been added.</span></span>  
  
 <span data-ttu-id="1da1f-105">Viene aggiunta una regola per valori elevati, che consente uno sconto maggiore per gli ordini di alto valore.</span><span class="sxs-lookup"><span data-stu-id="1da1f-105">A high-value rule is added, which provides a bigger discount for high-value orders.</span></span> <span data-ttu-id="1da1f-106">Viene fornito un valore di priorità minore rispetto alle due regole precedenti che sovrascriverà il campo dello sconto e avrà la precedenza rispetto a entrambe le regole di sconto residenziale e aziendale.</span><span class="sxs-lookup"><span data-stu-id="1da1f-106">It is given a priority value less than the previous two rules so that it will overwrite the discount field and take precedence over both the residential and business discount rules.</span></span>  
  
 <span data-ttu-id="1da1f-107">Viene aggiunta una regola di calcolo del totale, che calcola il totale in base al livello di sconto.</span><span class="sxs-lookup"><span data-stu-id="1da1f-107">A calculate total rule is also added, which computes the total based on the discount level.</span></span> <span data-ttu-id="1da1f-108">Viene mostrato come fare riferimento a un metodo definito sull'attività del flusso di lavoro e come usare le azioni else.</span><span class="sxs-lookup"><span data-stu-id="1da1f-108">It shows how to reference a method defined on the workflow activity, as well as how to use else actions.</span></span> <span data-ttu-id="1da1f-109">Questa regola dimostra anche il comportamento mutevole, dal momento che verrà valutata a ogni modifica del campo di sconto.</span><span class="sxs-lookup"><span data-stu-id="1da1f-109">This rule also demonstrates chaining behavior since it will be evaluated anytime the discount field changes.</span></span> <span data-ttu-id="1da1f-110">Inoltre, viene mostrata l'attribuzione del metodo con RuleWriteAttribute sul metodo CalculateTotal.</span><span class="sxs-lookup"><span data-stu-id="1da1f-110">Furthermore, method attributing is shown with the RuleWriteAttribute on the CalculateTotal method.</span></span> <span data-ttu-id="1da1f-111">Ciò fa in modo che regole con impatto (ErrorTotalRule) vengano rivalutate ogni qualvolta il metodo viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="1da1f-111">This causes impacted rules (ErrorTotalRule) to be re-evaluated whenever the method gets executed.</span></span>  
  
 <span data-ttu-id="1da1f-112">L'ultima regola aggiunta rileva gli errori (in questo caso il Totale inferiore a 0).</span><span class="sxs-lookup"><span data-stu-id="1da1f-112">The last rule added is one that detects errors (in this case, Total less than 0).</span></span> <span data-ttu-id="1da1f-113">Se si verifica tale condizione, l'esecuzione del criterio verrà interrotta.</span><span class="sxs-lookup"><span data-stu-id="1da1f-113">If this occurs, the policy execution is halted.</span></span>  
  
 <span data-ttu-id="1da1f-114">Infine, vengono aggiunte le chiamate a `Console.Writeline` come azioni a ogni regola in modo da fornire più visibilità all'esecuzione della regola, dimostrando allo stesso tempo che è possibile accedere a metodi statici sui tipi a cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="1da1f-114">Finally, `Console.Writeline` calls are added as actions to each rule to provide more visibility into rule execution, while also showing that it is possible to access static methods on referenced types.</span></span> <span data-ttu-id="1da1f-115">È anche possibile usare il rilevamento per ottenere visibilità nelle regole eseguite.</span><span class="sxs-lookup"><span data-stu-id="1da1f-115">You could also use tracking to get visibility into the rules that are executed.</span></span>  
  
 <span data-ttu-id="1da1f-116">Le regole usate in questo esempio sono:</span><span class="sxs-lookup"><span data-stu-id="1da1f-116">The rules used in this sample are:</span></span>  
  
 <span data-ttu-id="1da1f-117">**ResidentialDiscountRule:**</span><span class="sxs-lookup"><span data-stu-id="1da1f-117">**ResidentialDiscountRule:**</span></span>  
  
 <span data-ttu-id="1da1f-118">IF OrderValue > 500 AND CustomerType = Residential</span><span class="sxs-lookup"><span data-stu-id="1da1f-118">IF OrderValue > 500 AND CustomerType = Residential</span></span>  
  
 <span data-ttu-id="1da1f-119">THEN Discount = 5%</span><span class="sxs-lookup"><span data-stu-id="1da1f-119">THEN Discount = 5%</span></span>  
  
 <span data-ttu-id="1da1f-120">**BusinessDiscountRule:**</span><span class="sxs-lookup"><span data-stu-id="1da1f-120">**BusinessDiscountRule:**</span></span>  
  
 <span data-ttu-id="1da1f-121">IF OrderValue > 10000 AND CustomerType = Business</span><span class="sxs-lookup"><span data-stu-id="1da1f-121">IF OrderValue > 10000 AND CustomerType = Business</span></span>  
  
 <span data-ttu-id="1da1f-122">THEN Discount = 10%</span><span class="sxs-lookup"><span data-stu-id="1da1f-122">THEN Discount = 10%</span></span>  
  
 <span data-ttu-id="1da1f-123">**HighValueDiscountRule:**</span><span class="sxs-lookup"><span data-stu-id="1da1f-123">**HighValueDiscountRule:**</span></span>  
  
 <span data-ttu-id="1da1f-124">IF OrderValue > 20000</span><span class="sxs-lookup"><span data-stu-id="1da1f-124">IF OrderValue > 20000</span></span>  
  
 <span data-ttu-id="1da1f-125">THEN Discount = 15%</span><span class="sxs-lookup"><span data-stu-id="1da1f-125">THEN Discount = 15%</span></span>  
  
 <span data-ttu-id="1da1f-126">**TotalRule:**</span><span class="sxs-lookup"><span data-stu-id="1da1f-126">**TotalRule:**</span></span>  
  
 <span data-ttu-id="1da1f-127">IF Discount > 0</span><span class="sxs-lookup"><span data-stu-id="1da1f-127">IF Discount > 0</span></span>  
  
 <span data-ttu-id="1da1f-128">THEN CalculateTotal(OrderValue, Discount)</span><span class="sxs-lookup"><span data-stu-id="1da1f-128">THEN CalculateTotal(OrderValue, Discount)</span></span>  
  
 <span data-ttu-id="1da1f-129">ELSE Total = OrderValue</span><span class="sxs-lookup"><span data-stu-id="1da1f-129">ELSE Total = OrderValue</span></span>  
  
 <span data-ttu-id="1da1f-130">**ErrorTotalRule:**</span><span class="sxs-lookup"><span data-stu-id="1da1f-130">**ErrorTotalRule:**</span></span>  
  
 <span data-ttu-id="1da1f-131">Se totale \< 0</span><span class="sxs-lookup"><span data-stu-id="1da1f-131">IF Total \< 0</span></span>  
  
 <span data-ttu-id="1da1f-132">THEN Error = "Fired ErrorTotalRule"; Halt</span><span class="sxs-lookup"><span data-stu-id="1da1f-132">THEN Error = "Fired ErrorTotalRule"; Halt</span></span>  
  
 <span data-ttu-id="1da1f-133">La valutazione e l'esecuzione delle regole può essere inoltre visualizzata tramite traccia e rilevamento.</span><span class="sxs-lookup"><span data-stu-id="1da1f-133">Rule evaluation and execution can also be seen through tracing and tracking.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="1da1f-134">Per compilare l'esempio</span><span class="sxs-lookup"><span data-stu-id="1da1f-134">To build the sample</span></span>  
  
1.  <span data-ttu-id="1da1f-135">Aprire la soluzione in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1da1f-135">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="1da1f-136">Premere CTRL+MAIUSC+B per compilare la soluzione,</span><span class="sxs-lookup"><span data-stu-id="1da1f-136">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="1da1f-137">Eseguire la soluzione senza debug premendo CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="1da1f-137">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="1da1f-138">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="1da1f-138">To run the sample</span></span>  
  
-   <span data-ttu-id="1da1f-139">Nella finestra del prompt dei comandi di SDK eseguire il file con estensione exe nella cartella AdvancedPolicy\bin\debug (oppure nella cartella AdvancedPolicy\bin per la versione Visual Basic dell'esempio), collocata sotto la cartella principale dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="1da1f-139">In the SDK Command Prompt window, run the .exe file in the AdvancedPolicy\bin\debug folder (or the AdvancedPolicy \bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1da1f-140">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="1da1f-140">The samples may already be installed on your computer.</span></span> <span data-ttu-id="1da1f-141">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="1da1f-141">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="1da1f-142">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="1da1f-142">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1da1f-143">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="1da1f-143">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\AdvancedPolicy`  
  
## <a name="see-also"></a><span data-ttu-id="1da1f-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1da1f-144">See Also</span></span>  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [<span data-ttu-id="1da1f-145">Criteri semplici</span><span class="sxs-lookup"><span data-stu-id="1da1f-145">Simple Policy</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/simple-policy.md)
