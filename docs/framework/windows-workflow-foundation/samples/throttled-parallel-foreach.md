---
title: ThrottledParallelForEach
ms.date: 03/30/2017
ms.assetid: f2855b5f-e9a7-433d-96a4-40fc31025215
ms.openlocfilehash: 8691edb8a5a61204b187be8def553f2f06be0f0d
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "48581862"
---
# <a name="throttled-parallel-foreach"></a><span data-ttu-id="c835b-102">ThrottledParallelForEach</span><span class="sxs-lookup"><span data-stu-id="c835b-102">Throttled Parallel ForEach</span></span>
<span data-ttu-id="c835b-103">Il `ThrottleParallelForEach` è simile all'attività la <!--zz <xref:System.Activities.Statements.ParallelForEach>--> `System.Activities.Statements.ParallelForEach` attività con l'unica eccezione che consente l'impostazione di un fattore di concorrenza per limitare il numero di rami simultanei da eseguire.</span><span class="sxs-lookup"><span data-stu-id="c835b-103">The `ThrottleParallelForEach` activity is similar to the <!--zz <xref:System.Activities.Statements.ParallelForEach>--> `System.Activities.Statements.ParallelForEach` activity with the one exception that it allows setting a concurrency factor to restrict the number of simultaneous branches to execute.</span></span> <span data-ttu-id="c835b-104">L'attività `ThrottleParallelForEach` deriva dall'oggetto <xref:System.Activities.NativeActivity>, poiché deve pianificare altre attività (le attività figlio) ed è accessibile solo tramite la classe <xref:System.Activities.NativeActivityContext>.</span><span class="sxs-lookup"><span data-stu-id="c835b-104">The `ThrottleParallelForEach` activity derives from <xref:System.Activities.NativeActivity>, because it needs to schedule other activities (the child activities) and this is only accessible through the <xref:System.Activities.NativeActivityContext> class.</span></span>

## <a name="projects"></a><span data-ttu-id="c835b-105">Progetti</span><span class="sxs-lookup"><span data-stu-id="c835b-105">Projects</span></span>

|<span data-ttu-id="c835b-106">**ProjectName**</span><span class="sxs-lookup"><span data-stu-id="c835b-106">**ProjectName**</span></span>|<span data-ttu-id="c835b-107">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="c835b-107">**Description**</span></span>|<span data-ttu-id="c835b-108">**File principali.**</span><span class="sxs-lookup"><span data-stu-id="c835b-108">**Main Files**</span></span>|
|-|-|-|
|<span data-ttu-id="c835b-109">ThrottledParallelForEach</span><span class="sxs-lookup"><span data-stu-id="c835b-109">ThrottledParallelForEach</span></span>|<span data-ttu-id="c835b-110">Contiene l'attività `ThrottledParallelForEach` e la relativa finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="c835b-110">Contains `ThrottledParallelForEach` activity and its designer.</span></span>|<span data-ttu-id="c835b-111">ThrottledParallelForEach.cs</span><span class="sxs-lookup"><span data-stu-id="c835b-111">ThrottledParallelForEach.cs</span></span><br /><br /> <span data-ttu-id="c835b-112">Definizione dell'attività `ThrottledParallelForEach`.</span><span class="sxs-lookup"><span data-stu-id="c835b-112">The `ThrottledParallelForEach` activity definition.</span></span>|
|<span data-ttu-id="c835b-113">CodeTestClient</span><span class="sxs-lookup"><span data-stu-id="c835b-113">CodeTestClient</span></span>|<span data-ttu-id="c835b-114">Applicazione client di esempio che configura ed esegue un flusso di lavoro con un oggetto `ThrottledParallelForEach` usando il codice imperativo.</span><span class="sxs-lookup"><span data-stu-id="c835b-114">Sample client application that configures and runs a workflow with a `ThrottledParallelForEach` using imperative code.</span></span>|<span data-ttu-id="c835b-115">Program.cs</span><span class="sxs-lookup"><span data-stu-id="c835b-115">Program.cs</span></span><br /><br /> <span data-ttu-id="c835b-116">Definisce ed esegue un'istanza del flusso di lavoro di esempio.</span><span class="sxs-lookup"><span data-stu-id="c835b-116">Defines and runs an instance of the sample workflow.</span></span>|

#### <a name="to-use-this-sample"></a><span data-ttu-id="c835b-117">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="c835b-117">To use this sample</span></span>

1.  <span data-ttu-id="c835b-118">Con Visual Studio 2010, aprire il file Throttledparallelforeach.</span><span class="sxs-lookup"><span data-stu-id="c835b-118">Using Visual Studio 2010, open the ThrottledParallelForEach.sln file.</span></span>

2.  <span data-ttu-id="c835b-119">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="c835b-119">To build the solution, press CTRL+SHIFT+B.</span></span>

3.  <span data-ttu-id="c835b-120">Per eseguire la soluzione, premere F5.</span><span class="sxs-lookup"><span data-stu-id="c835b-120">To run the solution, press F5.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="c835b-121">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="c835b-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c835b-122">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="c835b-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c835b-123">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="c835b-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c835b-124">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="c835b-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\ThrottledParallelForEach`