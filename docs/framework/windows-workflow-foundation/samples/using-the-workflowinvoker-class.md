---
title: Utilizzo della classe WorkflowInvoker
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a966164-3990-4e78-8aa2-c6797ebbee94
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f5310b2adefa24d2d16733965395a34cc5cb69d5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="using-the-workflowinvoker-class"></a><span data-ttu-id="d40bd-102">Utilizzo della classe WorkflowInvoker</span><span class="sxs-lookup"><span data-stu-id="d40bd-102">Using the WorkflowInvoker Class</span></span>
<span data-ttu-id="d40bd-103">In questo esempio viene illustrato come usare la classe <xref:System.Activities.WorkflowInvoker> per richiamare un'attività come se fosse un metodo.</span><span class="sxs-lookup"><span data-stu-id="d40bd-103">This sample demonstrates how to use the <xref:System.Activities.WorkflowInvoker> class to invoke an activity as if it were a method.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="d40bd-104">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="d40bd-104">Sample Details</span></span>  
 <span data-ttu-id="d40bd-105">L'uso della classe <xref:System.Activities.WorkflowInvoker> è il modo più semplice per eseguire un'attività.</span><span class="sxs-lookup"><span data-stu-id="d40bd-105">Using the <xref:System.Activities.WorkflowInvoker> class is the simplest way to execute an activity.</span></span> <span data-ttu-id="d40bd-106">È progettata per eseguire direttamente un'attività come una chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="d40bd-106">It is designed for directly running an activity as if it were a method call.</span></span> <span data-ttu-id="d40bd-107">Questa API ad alte prestazioni, leggera e semplice da usare in scenari in cui l'esecuzione di un'attività non richiede l'infrastruttura di controllo fornita da altre varianti di hosting.</span><span class="sxs-lookup"><span data-stu-id="d40bd-107">It is a lightweight, high-performing, easy to use API for use in scenarios where an activity’s execution does not require the control infrastructure provided by other hosting variations.</span></span>  
  
 <span data-ttu-id="d40bd-108">L'esempio utilizza un'attività personalizzata che deriva da <xref:System.Activities.CodeActivity%601>< Int32\> denominato `Add` che aggiunge due <xref:System.Activities.InArgument%601>, `X` e `Y`e restituisce un `Result` <xref:System.Activities.OutArgument%601>.</span><span class="sxs-lookup"><span data-stu-id="d40bd-108">The sample uses a custom activity that derives from <xref:System.Activities.CodeActivity%601><Int32\> named `Add` that adds two <xref:System.Activities.InArgument%601>, `X` and `Y`, and returns a `Result`<xref:System.Activities.OutArgument%601>.</span></span> <span data-ttu-id="d40bd-109">(<xref:System.Activities.CodeActivity%601>\<T > deriva da <xref:System.Activities.Activity%601>< T\>, che presenta un <xref:System.Activities.OutArgument%601> \<T > denominato `Result`.) Oggetto `Dictionary` \<stringa, oggetto > viene utilizzato per passare argomenti a un'attività richiamata tramite <xref:System.Activities.WorkflowInvoker>.</span><span class="sxs-lookup"><span data-stu-id="d40bd-109">(<xref:System.Activities.CodeActivity%601>\<T> derives from <xref:System.Activities.Activity%601><T\>, which has an <xref:System.Activities.OutArgument%601>\<T> named `Result`.) A `Dictionary`\<string, object> is used to pass arguments into an activity being invoked through <xref:System.Activities.WorkflowInvoker>.</span></span> <span data-ttu-id="d40bd-110">La chiave del dizionario corrisponde al nome di un argomento nell'attività richiamata.</span><span class="sxs-lookup"><span data-stu-id="d40bd-110">The key of the dictionary corresponds to the name of an argument on the invoked activity.</span></span> <span data-ttu-id="d40bd-111">Il valore associato a una particolare chiave viene associato all'argomento identificato dalla chiave.</span><span class="sxs-lookup"><span data-stu-id="d40bd-111">The value associated with a particular key is bound to the argument identified by the key.</span></span>  
  
 <span data-ttu-id="d40bd-112">Nell'esempio viene chiamato <xref:System.Activities.WorkflowInvoker.Invoke%2A> e viene passato un dizionario che contiene valori per `X` e `Y`.</span><span class="sxs-lookup"><span data-stu-id="d40bd-112">The sample calls <xref:System.Activities.WorkflowInvoker.Invoke%2A> and passes a dictionary that contains values for `X` and `Y`.</span></span> <span data-ttu-id="d40bd-113">La classe <xref:System.Activities.WorkflowInvoker> associa questi valori agli argomenti dell'attività `Add`, esegue l'attività e restituisce il risultato.</span><span class="sxs-lookup"><span data-stu-id="d40bd-113">The <xref:System.Activities.WorkflowInvoker> class binds these values to the `Add` activity’s arguments, executes the activity, and returns the result.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="d40bd-114">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="d40bd-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="d40bd-115">Tramite [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione Invoker.sln.</span><span class="sxs-lookup"><span data-stu-id="d40bd-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the Invoker.sln solution file.</span></span>  
  
2.  <span data-ttu-id="d40bd-116">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="d40bd-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="d40bd-117">Per eseguire la soluzione, premere F5.</span><span class="sxs-lookup"><span data-stu-id="d40bd-117">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d40bd-118">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="d40bd-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d40bd-119">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="d40bd-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d40bd-120">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d40bd-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d40bd-121">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="d40bd-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\WorkflowInvoker`  
  
## <a name="see-also"></a><span data-ttu-id="d40bd-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d40bd-122">See Also</span></span>
