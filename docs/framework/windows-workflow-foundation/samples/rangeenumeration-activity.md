---
title: "Attività RangeEnumeration"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ca5b78f4-94fa-4aa7-830d-26039ac422c8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7dc793d57718dbc68f304d3eb5031a9fa96b00cb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="rangeenumeration-activity"></a><span data-ttu-id="471b8-102">Attività RangeEnumeration</span><span class="sxs-lookup"><span data-stu-id="471b8-102">RangeEnumeration Activity</span></span>
<span data-ttu-id="471b8-103">In questo esempio viene illustrato come creare un'attività personalizzata che scorre una raccolta di numeri. Nella tabella seguente sono indicati in dettaglio i file principali inclusi nell'esempio.</span><span class="sxs-lookup"><span data-stu-id="471b8-103">This sample demonstrates how to create a custom activity that iterates over a collection of numbers.The following table details the main files included in the sample.</span></span>  
  
|<span data-ttu-id="471b8-104">Nome file</span><span class="sxs-lookup"><span data-stu-id="471b8-104">File name</span></span>|<span data-ttu-id="471b8-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="471b8-105">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="471b8-106">RangeEnumeration.cs</span><span class="sxs-lookup"><span data-stu-id="471b8-106">RangeEnumeration.cs</span></span>|<span data-ttu-id="471b8-107">Definisce un'attività personalizzata denominata `RangeEnumeration` che esegue l'override della classe <xref:System.Activities.NativeActivity> e riproduce un ciclo continuo di una serie di numeri.</span><span class="sxs-lookup"><span data-stu-id="471b8-107">Defines a custom activity named `RangeEnumeration` that overrides the <xref:System.Activities.NativeActivity> class and loops through a series of numbers.</span></span>|  
|<span data-ttu-id="471b8-108">RangeEnumerationSample.cs</span><span class="sxs-lookup"><span data-stu-id="471b8-108">RangeEnumerationSample.cs</span></span>|<span data-ttu-id="471b8-109">Applicazione client che usa l'attività `RangeEnumeration` per scorrere una raccolta di numeri.</span><span class="sxs-lookup"><span data-stu-id="471b8-109">A client application that uses the `RangeEnumeration` activity to iterate over a collection of numbers.</span></span>|  
  
 <span data-ttu-id="471b8-110">Nella tabella seguente sono indicate in dettaglio le proprietà dell'attività `RangeEnumeration`.</span><span class="sxs-lookup"><span data-stu-id="471b8-110">The following table details the properties of the `RangeEnumeration` activity.</span></span>  
  
|<span data-ttu-id="471b8-111">Proprietà</span><span class="sxs-lookup"><span data-stu-id="471b8-111">Property</span></span>|<span data-ttu-id="471b8-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="471b8-112">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="471b8-113">Start</span><span class="sxs-lookup"><span data-stu-id="471b8-113">Start</span></span>|<span data-ttu-id="471b8-114">Integer da cui iniziare il ciclo.</span><span class="sxs-lookup"><span data-stu-id="471b8-114">The integer to start the loop from.</span></span>|  
|<span data-ttu-id="471b8-115">Interrompi</span><span class="sxs-lookup"><span data-stu-id="471b8-115">Stop</span></span>|<span data-ttu-id="471b8-116">Integer in corrispondenza del quale arrestare il ciclo.</span><span class="sxs-lookup"><span data-stu-id="471b8-116">The integer to stop the loop at.</span></span>|  
|<span data-ttu-id="471b8-117">Passaggio</span><span class="sxs-lookup"><span data-stu-id="471b8-117">Step</span></span>|<span data-ttu-id="471b8-118">Specifica la durata di ogni iterazione.</span><span class="sxs-lookup"><span data-stu-id="471b8-118">Specifies how much to iterate each time.</span></span>|  
|<span data-ttu-id="471b8-119">Corpo</span><span class="sxs-lookup"><span data-stu-id="471b8-119">Body</span></span>|<span data-ttu-id="471b8-120">Specifica il codice da eseguire durante ogni iterazione.</span><span class="sxs-lookup"><span data-stu-id="471b8-120">Specifies the code to execute during each iteration.</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="471b8-121">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="471b8-121">To use this sample</span></span>  
  
1.  <span data-ttu-id="471b8-122">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione RangeEnumeration.sln.</span><span class="sxs-lookup"><span data-stu-id="471b8-122">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the RangeEnumeration.sln solution file.</span></span>  
  
2.  <span data-ttu-id="471b8-123">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="471b8-123">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="471b8-124">Per eseguire la soluzione, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="471b8-124">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="471b8-125">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="471b8-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="471b8-126">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="471b8-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="471b8-127">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="471b8-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="471b8-128">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="471b8-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\RangeEnumeration`