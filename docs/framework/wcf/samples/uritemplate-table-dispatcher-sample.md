---
title: Dispatcher di esempio nella tabella UriTemplate
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b32975d-ba90-4c5c-83bc-2fbb48f11c0c
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3574183f0900c853bd3ff541aabc8fc6b7fcd157
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="uritemplate-table-dispatcher-sample"></a><span data-ttu-id="2a238-102">Dispatcher di esempio nella tabella UriTemplate</span><span class="sxs-lookup"><span data-stu-id="2a238-102">UriTemplate Table Dispatcher Sample</span></span>
<span data-ttu-id="2a238-103">La classe <xref:System.UriTemplateTable> fornisce una struttura con tabella associativa simile a un dizionario per lavorare con un set di istanze <xref:System.UriTemplate>.</span><span class="sxs-lookup"><span data-stu-id="2a238-103">The <xref:System.UriTemplateTable> class provides a dictionary-like associative table structure for working with a set of <xref:System.UriTemplate> instances.</span></span> <span data-ttu-id="2a238-104">In questo esempio viene illustrato un motore di distribuzione di base compilato utilizzando `UriTemplateTable`, uno scenario di utilizzo comune per la classe `UriTemplateTable`.</span><span class="sxs-lookup"><span data-stu-id="2a238-104">This sample demonstrates a basic dispatching engine built using `UriTemplateTable`, a common usage scenario for the `UriTemplateTable` class.</span></span>  
  
 <span data-ttu-id="2a238-105">In questo esempio vengono illustrati i seguenti concetti principali relativi alla classe `UriTemplateTable`:</span><span class="sxs-lookup"><span data-stu-id="2a238-105">This sample demonstrates the following key concepts for the `UriTemplateTable` class:</span></span>  
  
-   <span data-ttu-id="2a238-106">Associazione di delegati a `UriTemplates` in un `UriTemplateTable`.</span><span class="sxs-lookup"><span data-stu-id="2a238-106">Associating delegates with `UriTemplates` in a `UriTemplateTable`.</span></span>  
  
-   <span data-ttu-id="2a238-107">Utilizzo di <xref:System.UriTemplateTable.MatchSingle%2A> per ottenere il delegato del gestore corretto per un particolare URI.</span><span class="sxs-lookup"><span data-stu-id="2a238-107">Using <xref:System.UriTemplateTable.MatchSingle%2A> to obtain the correct handler delegate for a particular URI.</span></span>  
  
-   <span data-ttu-id="2a238-108">Chiamata al delegato del gestore per elaborare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="2a238-108">Invoking the handler delegate to process the request.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2a238-109">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="2a238-109">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="2a238-110">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2a238-110">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="2a238-111">Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2a238-111">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2a238-112">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="2a238-112">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2a238-113">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="2a238-113">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2a238-114">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2a238-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2a238-115">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="2a238-115">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateDispatcher`  
  
## <a name="see-also"></a><span data-ttu-id="2a238-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a238-116">See Also</span></span>  
 [<span data-ttu-id="2a238-117">Tabella UriTemplate</span><span class="sxs-lookup"><span data-stu-id="2a238-117">UriTemplate Table</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)  
 [<span data-ttu-id="2a238-118">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="2a238-118">UriTemplate</span></span>](../../../../docs/framework/wcf/samples/uritemplate-sample.md)
