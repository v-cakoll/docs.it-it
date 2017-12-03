---
title: "Utilizzo di AsyncOperationContext in un esempio di attività"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0888a0bd-d227-4c00-ad6a-b654a01740e8
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d5fce0160f98b5af5476b5e647763d79e94fb4e3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="using-asyncoperationcontext-in-an-activity-sample"></a><span data-ttu-id="a55a6-102">Utilizzo di AsyncOperationContext in un esempio di attività</span><span class="sxs-lookup"><span data-stu-id="a55a6-102">Using AsyncOperationContext in an Activity Sample</span></span>
<span data-ttu-id="a55a6-103">In questo esempio viene dimostrato come sviluppare un oggetto <xref:System.Activities.CodeActivity> personalizzato che usa <xref:System.Activities.AsyncCodeActivityContext> per eseguire operazioni asincrone al di fuori del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a55a6-103">This sample demonstrates how to develop a custom <xref:System.Activities.CodeActivity> that uses <xref:System.Activities.AsyncCodeActivityContext> to perform work asynchronously outside of the workflow.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="a55a6-104">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="a55a6-104">Sample Details</span></span>  
 <span data-ttu-id="a55a6-105">L'attività di esempio usa i metodi <xref:System.IO.FileStream.BeginWrite%2A> e <xref:System.IO.FileStream.EndWrite%2A> nella classe <xref:System.IO.FileStream> per scrivere in modo asincrono dati in un file.</span><span class="sxs-lookup"><span data-stu-id="a55a6-105">The sample activity uses the <xref:System.IO.FileStream.BeginWrite%2A> and <xref:System.IO.FileStream.EndWrite%2A> methods on the <xref:System.IO.FileStream> class to asynchronously write data to a file.</span></span> <span data-ttu-id="a55a6-106">Il modello introdotto qui può essere adattato per l'uso con gli altri metodi asincroni.</span><span class="sxs-lookup"><span data-stu-id="a55a6-106">The pattern introduced here can be adapted for use with other asynchronous methods.</span></span> <span data-ttu-id="a55a6-107">Mentre l'operazione asincrona è in esecuzione, possono essere eseguite le altre attività nel flusso di lavoro, ma il flusso di lavoro non può essere salvato in modo permanente.</span><span class="sxs-lookup"><span data-stu-id="a55a6-107">While the asynchronous operation is executing, other activities in the workflow can execute, but the workflow cannot be persisted.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a55a6-108">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="a55a6-108">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="a55a6-109">Aprire la soluzione di esempio Async.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a55a6-109">Open the Async.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="a55a6-110">Compilare ed eseguire la soluzione.</span><span class="sxs-lookup"><span data-stu-id="a55a6-110">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a55a6-111">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="a55a6-111">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a55a6-112">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="a55a6-112">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a55a6-113">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a55a6-113">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a55a6-114">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="a55a6-114">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\Async`