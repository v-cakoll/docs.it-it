---
title: Attività RangeEnumeration
ms.date: 03/30/2017
ms.assetid: ca5b78f4-94fa-4aa7-830d-26039ac422c8
ms.openlocfilehash: 9aa04c80f20e2d410fb49e2d07d836c8c5ab1b4d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33516578"
---
# <a name="rangeenumeration-activity"></a><span data-ttu-id="07874-102">Attività RangeEnumeration</span><span class="sxs-lookup"><span data-stu-id="07874-102">RangeEnumeration Activity</span></span>
<span data-ttu-id="07874-103">In questo esempio viene illustrato come creare un'attività personalizzata che scorre una raccolta di numeri. Nella tabella seguente sono indicati in dettaglio i file principali inclusi nell'esempio.</span><span class="sxs-lookup"><span data-stu-id="07874-103">This sample demonstrates how to create a custom activity that iterates over a collection of numbers.The following table details the main files included in the sample.</span></span>  
  
|<span data-ttu-id="07874-104">Nome file</span><span class="sxs-lookup"><span data-stu-id="07874-104">File name</span></span>|<span data-ttu-id="07874-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07874-105">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="07874-106">RangeEnumeration.cs</span><span class="sxs-lookup"><span data-stu-id="07874-106">RangeEnumeration.cs</span></span>|<span data-ttu-id="07874-107">Definisce un'attività personalizzata denominata `RangeEnumeration` che esegue l'override della classe <xref:System.Activities.NativeActivity> e riproduce un ciclo continuo di una serie di numeri.</span><span class="sxs-lookup"><span data-stu-id="07874-107">Defines a custom activity named `RangeEnumeration` that overrides the <xref:System.Activities.NativeActivity> class and loops through a series of numbers.</span></span>|  
|<span data-ttu-id="07874-108">RangeEnumerationSample.cs</span><span class="sxs-lookup"><span data-stu-id="07874-108">RangeEnumerationSample.cs</span></span>|<span data-ttu-id="07874-109">Applicazione client che usa l'attività `RangeEnumeration` per scorrere una raccolta di numeri.</span><span class="sxs-lookup"><span data-stu-id="07874-109">A client application that uses the `RangeEnumeration` activity to iterate over a collection of numbers.</span></span>|  
  
 <span data-ttu-id="07874-110">Nella tabella seguente sono indicate in dettaglio le proprietà dell'attività `RangeEnumeration`.</span><span class="sxs-lookup"><span data-stu-id="07874-110">The following table details the properties of the `RangeEnumeration` activity.</span></span>  
  
|<span data-ttu-id="07874-111">Proprietà</span><span class="sxs-lookup"><span data-stu-id="07874-111">Property</span></span>|<span data-ttu-id="07874-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07874-112">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="07874-113">Start</span><span class="sxs-lookup"><span data-stu-id="07874-113">Start</span></span>|<span data-ttu-id="07874-114">Integer da cui iniziare il ciclo.</span><span class="sxs-lookup"><span data-stu-id="07874-114">The integer to start the loop from.</span></span>|  
|<span data-ttu-id="07874-115">Interrompi</span><span class="sxs-lookup"><span data-stu-id="07874-115">Stop</span></span>|<span data-ttu-id="07874-116">Integer in corrispondenza del quale arrestare il ciclo.</span><span class="sxs-lookup"><span data-stu-id="07874-116">The integer to stop the loop at.</span></span>|  
|<span data-ttu-id="07874-117">Passaggio</span><span class="sxs-lookup"><span data-stu-id="07874-117">Step</span></span>|<span data-ttu-id="07874-118">Specifica la durata di ogni iterazione.</span><span class="sxs-lookup"><span data-stu-id="07874-118">Specifies how much to iterate each time.</span></span>|  
|<span data-ttu-id="07874-119">Corpo</span><span class="sxs-lookup"><span data-stu-id="07874-119">Body</span></span>|<span data-ttu-id="07874-120">Specifica il codice da eseguire durante ogni iterazione.</span><span class="sxs-lookup"><span data-stu-id="07874-120">Specifies the code to execute during each iteration.</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="07874-121">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="07874-121">To use this sample</span></span>  
  
1.  <span data-ttu-id="07874-122">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione RangeEnumeration.sln.</span><span class="sxs-lookup"><span data-stu-id="07874-122">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the RangeEnumeration.sln solution file.</span></span>  
  
2.  <span data-ttu-id="07874-123">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="07874-123">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="07874-124">Per eseguire la soluzione, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="07874-124">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="07874-125">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="07874-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="07874-126">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="07874-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="07874-127">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="07874-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="07874-128">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="07874-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\RangeEnumeration`