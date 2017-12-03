---
title: "Utilizzo dell'attività InvokeMethod"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b6643550-d043-4ac7-8069-9c55ebbb4233
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ba0c2333c14eaebdb6409323bb6b92aa2b29d2ec
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="using-the-invokemethod-activity"></a><span data-ttu-id="c902c-102">Utilizzo dell'attività InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="c902c-102">Using the InvokeMethod Activity</span></span>
<span data-ttu-id="c902c-103">In questo esempio viene illustrato come utilizzare il <!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) attività per richiamare metodi pubblici nelle classi pubbliche.</span><span class="sxs-lookup"><span data-stu-id="c902c-103">This sample demonstrates how to use the <!--zz <xref:System.Activities.Statements.InvokeMethod%601> -->[<code>System.Activities.Statements.InvokeMethod\\`1</code>](https://msdn.microsoft.com/library/dd647677.aspx) activity to invoke public methods in public classes.</span></span> <span data-ttu-id="c902c-104">Il <!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) attività consente a un flusso di lavoro chiamare metodi negli oggetti, passare parametri, ottenere il valore restituito, specificare tipi per i metodi generici e indicare se il metodo è sincrono o asincrona.</span><span class="sxs-lookup"><span data-stu-id="c902c-104">The <!--zz <xref:System.Activities.Statements.InvokeMethod%601> -->[<code>System.Activities.Statements.InvokeMethod\\`1</code>](https://msdn.microsoft.com/library/dd647677.aspx) activity allows a workflow to call methods against objects, pass in parameters, get the return value, specify types for generic methods, and specify whether the method is synchronous or asynchronous.</span></span> 
  
<span data-ttu-id="c902c-105">È disponibile una versione non generica del <xref:System.Activities.Statements.InvokeMethod> attività in cui il valore restituito è impostato per il <xref:System.Activities.Statements.InvokeMethod.Result%2A> proprietà e una versione generica del <!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) attività in cui viene restituito il valore restituito tramite il <!--zz <xref:System.Activities.Statements.InvokeMethod.Result%601.Result%2A> --> [ <code>System.Activities.Statements.InvokeMethod\`1.Result</code> ](https://msdn.microsoft.com/library/dd987724.aspx) proprietà di tipo `TResult`.</span><span class="sxs-lookup"><span data-stu-id="c902c-105">There is a non-generic version of the <xref:System.Activities.Statements.InvokeMethod> activity where the return value is set to the <xref:System.Activities.Statements.InvokeMethod.Result%2A> property and a generic version of the <!--zz <xref:System.Activities.Statements.InvokeMethod%601> -->[<code>System.Activities.Statements.InvokeMethod\`1</code>](https://msdn.microsoft.com/library/dd647677.aspx) activity where the return value is returned through the <!--zz <xref:System.Activities.Statements.InvokeMethod.Result%601.Result%2A> -->[<code>System.Activities.Statements.InvokeMethod\`1.Result</code>](https://msdn.microsoft.com/library/dd987724.aspx) property of type `TResult`.</span></span> 
  
 <span data-ttu-id="c902c-106">In questo esempio viene illustrato come chiamare diversi tipi di metodo.</span><span class="sxs-lookup"><span data-stu-id="c902c-106">This sample demonstrates how to call various method types.</span></span> <span data-ttu-id="c902c-107">Nell'elenco seguente sono indicati in dettaglio i tipi di metodo illustrati nell'esempio:</span><span class="sxs-lookup"><span data-stu-id="c902c-107">The following list details the method types demonstrated in this sample:</span></span>  
  
-   <span data-ttu-id="c902c-108">Richiamare un metodo di istanza senza parametri.</span><span class="sxs-lookup"><span data-stu-id="c902c-108">Invoke an instance method without parameters.</span></span>  
  
-   <span data-ttu-id="c902c-109">Richiamare un metodo di istanza con due parametri (System.String e System.Int32).</span><span class="sxs-lookup"><span data-stu-id="c902c-109">Invoke an instance method with two parameters (System.String and System.Int32).</span></span>  
  
-   <span data-ttu-id="c902c-110">Richiamare un metodo di istanza con due parametri (System.String e System.Int32) e una matrice di parametri di tipo System.String[].</span><span class="sxs-lookup"><span data-stu-id="c902c-110">Invoke an instance method with two parameters (System.String and System.Int32) and a parameter array of type System.String[].</span></span>  
  
-   <span data-ttu-id="c902c-111">Richiamare un metodo di istanza con due parametri (due numeri System.Int32) e un risultato di tipo System.Int32.</span><span class="sxs-lookup"><span data-stu-id="c902c-111">Invoke an instance method with two parameters (two System.Int32 numbers) and a result of type System.Int32.</span></span>  
  
     <span data-ttu-id="c902c-112">Il valore restituito viene associato a una variabile e stampato nella console tramite l'attività <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="c902c-112">The return value is bound to a variable and printed to the console using the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
-   <span data-ttu-id="c902c-113">Richiamare un metodo statico con due parametri (System.String e System.Int32).</span><span class="sxs-lookup"><span data-stu-id="c902c-113">Invoke a static method with two parameters (System.String and System.Int32).</span></span>  
  
-   <span data-ttu-id="c902c-114">Richiamare un metodo di istanza con un parametro generico (System.String).</span><span class="sxs-lookup"><span data-stu-id="c902c-114">Invoke an instance method with one generic parameter (System.String).</span></span>  
  
-   <span data-ttu-id="c902c-115">Richiamare un metodo statico con due parametri generici (System.String e System.Int32).</span><span class="sxs-lookup"><span data-stu-id="c902c-115">Invoke a static method with two generic parameters (System.String and System.Int32).</span></span>  
  
-   <span data-ttu-id="c902c-116">Richiamare un metodo di istanza che dispone di un parametro passato dal riferimento (System.String).</span><span class="sxs-lookup"><span data-stu-id="c902c-116">Invoke an instance method that has one parameter passed by reference (System.String).</span></span>  
  
     <span data-ttu-id="c902c-117">Il parametro a cui si fa riferimento viene associato a una variabile e stampato nella console tramite l'attività <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="c902c-117">The referenced parameter is bound to a variable and printed to the console using the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
-   <span data-ttu-id="c902c-118">Richiamare un metodo di istanza asincrono.</span><span class="sxs-lookup"><span data-stu-id="c902c-118">Invoke an asynchronous instance method.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="c902c-119">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="c902c-119">To use this sample</span></span>  
  
1.  <span data-ttu-id="c902c-120">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione InvokeMethodUsage.sln.</span><span class="sxs-lookup"><span data-stu-id="c902c-120">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the InvokeMethodUsage.sln solution file.</span></span>  
  
2.  <span data-ttu-id="c902c-121">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="c902c-121">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="c902c-122">Per eseguire la soluzione, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="c902c-122">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c902c-123">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="c902c-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c902c-124">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="c902c-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c902c-125">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c902c-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c902c-126">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="c902c-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InvokeMethod`