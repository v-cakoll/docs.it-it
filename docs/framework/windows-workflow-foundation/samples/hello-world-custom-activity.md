---
title: Attività personalizzata Hello World
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72b1dd0a-9aad-47d5-95a9-a1024ee1d0a1
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fa441a3019b0ef6df31dc0a46be7ea7e8e00a4b8
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="hello-world-custom-activity"></a><span data-ttu-id="341f5-102">Attività personalizzata Hello World</span><span class="sxs-lookup"><span data-stu-id="341f5-102">Hello World Custom Activity</span></span>
<span data-ttu-id="341f5-103">In questo esempio vengono illustrate diverse funzionalità chiave di Windows Workflow Foundation (WF), incluso come creare una semplice attività personalizzata.</span><span class="sxs-lookup"><span data-stu-id="341f5-103">This sample demonstrates several key features of Windows Workflow Foundation (WF), including how to create a simple custom activity.</span></span> <span data-ttu-id="341f5-104">Alcune delle funzionalità illustrate in questo esempio creano un'attività personalizzata in C# e usano argomenti `in` e `out` (<xref:System.Activities.InArgument> e <xref:System.Activities.OutArgument>).</span><span class="sxs-lookup"><span data-stu-id="341f5-104">Some of the features demonstrated in this sample are creating a custom activity in C# and using `in` and `out` arguments (<xref:System.Activities.InArgument> and <xref:System.Activities.OutArgument>).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="341f5-105">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="341f5-105">The samples may already be installed on your computer.</span></span> <span data-ttu-id="341f5-106">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="341f5-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="341f5-107">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="341f5-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="341f5-108">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="341f5-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\HelloWorld`  
  
## <a name="creating-a-workflow-in-code"></a><span data-ttu-id="341f5-109">Creazione di un flusso di lavoro nel codice</span><span class="sxs-lookup"><span data-stu-id="341f5-109">Creating a Workflow in Code</span></span>  
 <span data-ttu-id="341f5-110">In questo esempio vengono create due attività personalizzate usando codice C#.</span><span class="sxs-lookup"><span data-stu-id="341f5-110">In this sample, two custom activities are created using C# code.</span></span> <span data-ttu-id="341f5-111">Entrambe le attività personalizzate ereditano direttamente o indirettamente da <xref:System.Activities.Activity%601> per restituire un solo valore.</span><span class="sxs-lookup"><span data-stu-id="341f5-111">Both custom activities inherit directly or indirectly from <xref:System.Activities.Activity%601> to return a single value.</span></span> <span data-ttu-id="341f5-112">Il vantaggio dell'utilizzo del valore restituito generico, anziché ereditare dalla classe non generica <xref:System.Activities.Activity> è che alcune attività (ad esempio <xref:System.Activities.Statements.Assign>) sono in grado di accedere al valore restituito quando è usato come parte di un'attività composta.</span><span class="sxs-lookup"><span data-stu-id="341f5-112">The advantage of using the generic return value, instead of inheriting from the non-generic <xref:System.Activities.Activity> class, is that some activities (such as <xref:System.Activities.Statements.Assign>) are able to access the return value when used as part of a composed activity.</span></span>  
  
 <span data-ttu-id="341f5-113">AppendString</span><span class="sxs-lookup"><span data-stu-id="341f5-113">AppendString</span></span>  
 <span data-ttu-id="341f5-114">Questa attività eredita da <xref:System.Activities.Activity%601>e usa un'attività <xref:System.Activities.Statements.Assign> che concatena due stringhe.</span><span class="sxs-lookup"><span data-stu-id="341f5-114">This activity inherits from <xref:System.Activities.Activity%601>, and uses an <xref:System.Activities.Statements.Assign> activity that concatenates two strings together.</span></span>  
  
 <span data-ttu-id="341f5-115">Prepend String</span><span class="sxs-lookup"><span data-stu-id="341f5-115">Prepend String</span></span>  
 <span data-ttu-id="341f5-116">Questa attività eredita direttamente da <xref:System.Activities.CodeActivity%601>e crea la funzionalità simile all'attività `AppendString` che usa la logica implementata nel codice piuttosto che composta da un'attività preesistente.</span><span class="sxs-lookup"><span data-stu-id="341f5-116">This activity inherits directly from <xref:System.Activities.CodeActivity%601>, and creates similar functionality to the `AppendString` activity, which uses logic implemented in code rather than being composed of a pre-existing activity.</span></span>  
  
 <span data-ttu-id="341f5-117">In questo progetto sono inclusi i file seguenti:</span><span class="sxs-lookup"><span data-stu-id="341f5-117">The following files are included in this project.</span></span>  
  
 <span data-ttu-id="341f5-118">AppendString.cs</span><span class="sxs-lookup"><span data-stu-id="341f5-118">AppendString.cs</span></span>  
 <span data-ttu-id="341f5-119">Attività personalizzata che unisce stringhe.</span><span class="sxs-lookup"><span data-stu-id="341f5-119">The custom activity that appends strings together.</span></span> <span data-ttu-id="341f5-120">Accetta una stringa e li combina con una stringa letterale "says hello world" per formare un messaggio completo come output.</span><span class="sxs-lookup"><span data-stu-id="341f5-120">It takes in a string and combines it with a literal text string " says hello world" to form a complete message as output.</span></span>  
  
 <span data-ttu-id="341f5-121">PrependString.cs</span><span class="sxs-lookup"><span data-stu-id="341f5-121">PrependString.cs</span></span>  
 <span data-ttu-id="341f5-122">Questa attività premette una stringa predefinita a una stringa di input.</span><span class="sxs-lookup"><span data-stu-id="341f5-122">This activity prefixes a predefined string to an input string.</span></span>  
  
 <span data-ttu-id="341f5-123">Sequence1.xaml</span><span class="sxs-lookup"><span data-stu-id="341f5-123">Sequence1.xaml</span></span>  
 <span data-ttu-id="341f5-124">Flusso di lavoro che usa le attività personalizzate `AppendString` e `PrependString`.</span><span class="sxs-lookup"><span data-stu-id="341f5-124">A workflow that uses the `AppendString` and `PrependString` custom activities.</span></span>  
  
 <span data-ttu-id="341f5-125">Program.cs</span><span class="sxs-lookup"><span data-stu-id="341f5-125">Program.cs</span></span>  
 <span data-ttu-id="341f5-126">Programma che esegue il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="341f5-126">A program that runs the workflow.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="341f5-127">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="341f5-127">To use this sample</span></span>  
  
1.  <span data-ttu-id="341f5-128">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione HelloWorld.sln.</span><span class="sxs-lookup"><span data-stu-id="341f5-128">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the HelloWorld.sln solution file.</span></span>  
  
2.  <span data-ttu-id="341f5-129">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="341f5-129">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="341f5-130">Per eseguire la soluzione, premere F5.</span><span class="sxs-lookup"><span data-stu-id="341f5-130">To run the solution, press F5.</span></span>