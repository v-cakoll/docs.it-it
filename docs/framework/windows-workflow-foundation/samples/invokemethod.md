---
title: InvokeMethod
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04988eb3-65f8-456d-b1bd-509f5d05a57c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c275943d37a3602335ecd898aed3feb6c9059edf
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="invokemethod"></a><span data-ttu-id="5d9df-102">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="5d9df-102">InvokeMethod</span></span>
<span data-ttu-id="5d9df-103">In questo esempio vengono illustrate le diverse modalità di utilizzo dell'attività <xref:System.Activities.Statements.InvokeMethod> per richiamare metodi di una classe.</span><span class="sxs-lookup"><span data-stu-id="5d9df-103">This sample shows the different ways of using the <xref:System.Activities.Statements.InvokeMethod> activity to invoke methods of a class.</span></span>  
  
 <span data-ttu-id="5d9df-104">Un metodo appartiene a una classe e rappresenta un set di operazioni autonomo.</span><span class="sxs-lookup"><span data-stu-id="5d9df-104">A method belongs to a class and represents a contained set of operations.</span></span> <span data-ttu-id="5d9df-105">L'attività <xref:System.Activities.Statements.InvokeMethod> consente di chiamare metodi in base a oggetti o tipi, passare parametri e ottenere il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="5d9df-105">The <xref:System.Activities.Statements.InvokeMethod> activity gives you the ability to call methods against objects or types, pass in parameters, and get the return value.</span></span> <span data-ttu-id="5d9df-106">È possibile richiamare i metodi in modo sincrono o asincrono.</span><span class="sxs-lookup"><span data-stu-id="5d9df-106">Methods can be invoked synchronously or asynchronously.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="5d9df-107">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="5d9df-107">Sample Details</span></span>  
 <span data-ttu-id="5d9df-108">In questo esempio viene usata l'attività <xref:System.Activities.Statements.InvokeMethod> per eseguire gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="5d9df-108">This sample uses the <xref:System.Activities.Statements.InvokeMethod> activity to perform the following scenarios:</span></span>  
  
1.  <span data-ttu-id="5d9df-109">Richiamare un metodo di istanza senza parametri.</span><span class="sxs-lookup"><span data-stu-id="5d9df-109">Invoke an instance method without parameters.</span></span>  
  
2.  <span data-ttu-id="5d9df-110">Richiamare un metodo di istanza con due parametri (<xref:System.String> e <xref:System.Int32>).</span><span class="sxs-lookup"><span data-stu-id="5d9df-110">Invoke an instance method with two parameters (<xref:System.String> and <xref:System.Int32>).</span></span>  
  
3.  <span data-ttu-id="5d9df-111">Richiamare un metodo di istanza con due parametri (<xref:System.String> e <xref:System.Int32>) e una matrice di parametri di tipo <xref:System.String>[].</span><span class="sxs-lookup"><span data-stu-id="5d9df-111">Invoke an instance method with two parameters (<xref:System.String> and <xref:System.Int32>) and a parameter array of type <xref:System.String>[].</span></span>  
  
4.  <span data-ttu-id="5d9df-112">Richiamare un metodo di istanza con due parametri di tipo <xref:System.Int32> e un risultato di tipo <xref:System.Int32>.</span><span class="sxs-lookup"><span data-stu-id="5d9df-112">Invoke an instance method with two parameters of type <xref:System.Int32> and a result of type <xref:System.Int32>.</span></span> <span data-ttu-id="5d9df-113">In questo scenario il valore restituito viene associato a una variabile e usato in un'altra attività.</span><span class="sxs-lookup"><span data-stu-id="5d9df-113">In this scenario, the result value is bound to a variable and used in another activity.</span></span> <span data-ttu-id="5d9df-114">Viene visualizzato nella console usando l'attività <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="5d9df-114">It is displayed in the console using the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
5.  <span data-ttu-id="5d9df-115">Richiamare un metodo statico con due parametri di tipo <xref:System.String> e <xref:System.Int32>.</span><span class="sxs-lookup"><span data-stu-id="5d9df-115">Invoke a static method with two parameters of type <xref:System.String> and <xref:System.Int32>.</span></span>  
  
6.  <span data-ttu-id="5d9df-116">Richiamare un metodo di istanza con un parametro generico di tipo <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5d9df-116">Invoke an instance method with one generic parameter of type <xref:System.String>.</span></span>  
  
7.  <span data-ttu-id="5d9df-117">Richiamare un metodo statico con due parametri generici di tipo <xref:System.String> e <xref:System.Int32>.</span><span class="sxs-lookup"><span data-stu-id="5d9df-117">Invoke a static method with two generic parameters of type <xref:System.String> and <xref:System.Int32>.</span></span>  
  
8.  <span data-ttu-id="5d9df-118">Richiamare un metodo di istanza che dispone di un parametro passato da un riferimento di tipo <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5d9df-118">Invoke an instance method that has one parameter passed by reference of type <xref:System.String>.</span></span> <span data-ttu-id="5d9df-119">In questo scenario il parametro di riferimento viene associato a una variabile (`outParam`) e usato in un'altra attività.</span><span class="sxs-lookup"><span data-stu-id="5d9df-119">In this scenario, the reference parameter is bound to a variable (`outParam`) and used in another activity.</span></span> <span data-ttu-id="5d9df-120">Viene visualizzato nella console usando l'attività <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="5d9df-120">It is displayed on the console using the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
9. <span data-ttu-id="5d9df-121">Richiamare un metodo di istanza asincrono.</span><span class="sxs-lookup"><span data-stu-id="5d9df-121">Invoke an asynchronous instance method.</span></span>  
  
10. <span data-ttu-id="5d9df-122">Richiamare due metodi diversi nella stessa istanza di un oggetto usando due attività <xref:System.Activities.Statements.InvokeMethod>.</span><span class="sxs-lookup"><span data-stu-id="5d9df-122">Invoke two different methods on the same instance of an object using two <xref:System.Activities.Statements.InvokeMethod> activities.</span></span>  
  
11. <span data-ttu-id="5d9df-123">Archiviare un valore in un'istanza di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="5d9df-123">Store a value in an instance of an object.</span></span>  
  
12. <span data-ttu-id="5d9df-124">Recuperare un valore da un'istanza di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="5d9df-124">Retrieve a value from an instance of an object.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="5d9df-125">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="5d9df-125">To use this sample</span></span>  
 <span data-ttu-id="5d9df-126">Questo esempio è fornito in due versioni.</span><span class="sxs-lookup"><span data-stu-id="5d9df-126">This sample is provided in two versions.</span></span> <span data-ttu-id="5d9df-127">La prima versione di questo esempio, che si trova nella cartella CodedWorkflow\CS, illustra l'uso di <xref:System.Activities.Statements.InvokeMethod> tramite codice C# usando il modello di programmazione [!INCLUDE[wf](../../../../includes/wf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d9df-127">The first version of this sample demonstrates the usage of <xref:System.Activities.Statements.InvokeMethod> through C# code using the [!INCLUDE[wf](../../../../includes/wf-md.md)] programming model and can be found under the CodedWorkflow\CS folder.</span></span> <span data-ttu-id="5d9df-128">La seconda versione, che si trova nella cartella DesignerWorkflow\CS, illustra l'uso di <xref:System.Activities.Statements.InvokeMethod> tramite XAML.</span><span class="sxs-lookup"><span data-stu-id="5d9df-128">The second version demonstrates the usage of <xref:System.Activities.Statements.InvokeMethod> using XAML and can be found under the DesignerWorkflow\CS folder.</span></span>  
  
#### <a name="to-run-the-coded-workflow-sample"></a><span data-ttu-id="5d9df-129">Per eseguire l'esempio di flusso di lavoro codificato</span><span class="sxs-lookup"><span data-stu-id="5d9df-129">To run the coded workflow sample</span></span>  
  
1.  <span data-ttu-id="5d9df-130">Tramite [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione InvokeMethodUsage.sln nella cartella CodedWorkflow\CS.</span><span class="sxs-lookup"><span data-stu-id="5d9df-130">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the InvokeMethodUsage.sln solution file in the CodedWorkflow\CS folder.</span></span>  
  
2.  <span data-ttu-id="5d9df-131">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="5d9df-131">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="5d9df-132">Per eseguire la soluzione, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="5d9df-132">To run the solution, press CTRL+F5.</span></span>  
  
#### <a name="to-run-the-designer-workflow-sample"></a><span data-ttu-id="5d9df-133">Per eseguire l'esempio di flusso di lavoro di progettazione</span><span class="sxs-lookup"><span data-stu-id="5d9df-133">To run the designer workflow sample</span></span>  
  
1.  <span data-ttu-id="5d9df-134">Tramite [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione InvokeMethodUsage.sln nella cartella DesignerWorkflow\CS.</span><span class="sxs-lookup"><span data-stu-id="5d9df-134">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the InvokeMethodUsage.sln solution file in the DesignerWorkflow\CS folder.</span></span>  
  
2.  <span data-ttu-id="5d9df-135">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="5d9df-135">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="5d9df-136">Per eseguire la soluzione, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="5d9df-136">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5d9df-137">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="5d9df-137">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5d9df-138">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="5d9df-138">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5d9df-139">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5d9df-139">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5d9df-140">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="5d9df-140">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InvokeMethod`