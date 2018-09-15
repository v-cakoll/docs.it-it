---
title: Dispatcher di esempio nella tabella UriTemplate
ms.date: 03/30/2017
ms.assetid: 3b32975d-ba90-4c5c-83bc-2fbb48f11c0c
ms.openlocfilehash: 4a4f725e88e014da241e1042c27bfee270e13268
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2018
ms.locfileid: "45648512"
---
# <a name="uritemplate-table-dispatcher-sample"></a><span data-ttu-id="b0450-102">Dispatcher di esempio nella tabella UriTemplate</span><span class="sxs-lookup"><span data-stu-id="b0450-102">UriTemplate Table Dispatcher Sample</span></span>
<span data-ttu-id="b0450-103">La classe <xref:System.UriTemplateTable> fornisce una struttura con tabella associativa simile a un dizionario per lavorare con un set di istanze <xref:System.UriTemplate>.</span><span class="sxs-lookup"><span data-stu-id="b0450-103">The <xref:System.UriTemplateTable> class provides a dictionary-like associative table structure for working with a set of <xref:System.UriTemplate> instances.</span></span> <span data-ttu-id="b0450-104">In questo esempio viene illustrato un motore di distribuzione di base compilato utilizzando `UriTemplateTable`, uno scenario di utilizzo comune per la classe `UriTemplateTable`.</span><span class="sxs-lookup"><span data-stu-id="b0450-104">This sample demonstrates a basic dispatching engine built using `UriTemplateTable`, a common usage scenario for the `UriTemplateTable` class.</span></span>  
  
 <span data-ttu-id="b0450-105">In questo esempio vengono illustrati i seguenti concetti principali relativi alla classe `UriTemplateTable`:</span><span class="sxs-lookup"><span data-stu-id="b0450-105">This sample demonstrates the following key concepts for the `UriTemplateTable` class:</span></span>  
  
-   <span data-ttu-id="b0450-106">Associazione di delegati a `UriTemplates` in un `UriTemplateTable`.</span><span class="sxs-lookup"><span data-stu-id="b0450-106">Associating delegates with `UriTemplates` in a `UriTemplateTable`.</span></span>  
  
-   <span data-ttu-id="b0450-107">Utilizzo di <xref:System.UriTemplateTable.MatchSingle%2A> per ottenere il delegato del gestore corretto per un particolare URI.</span><span class="sxs-lookup"><span data-stu-id="b0450-107">Using <xref:System.UriTemplateTable.MatchSingle%2A> to obtain the correct handler delegate for a particular URI.</span></span>  
  
-   <span data-ttu-id="b0450-108">Chiamata al delegato del gestore per elaborare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="b0450-108">Invoking the handler delegate to process the request.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b0450-109">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="b0450-109">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="b0450-110">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b0450-110">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="b0450-111">Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b0450-111">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b0450-112">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="b0450-112">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b0450-113">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="b0450-113">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b0450-114">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="b0450-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b0450-115">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="b0450-115">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateDispatcher`  
  
## <a name="see-also"></a><span data-ttu-id="b0450-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0450-116">See Also</span></span>  
 [<span data-ttu-id="b0450-117">UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="b0450-117">UriTemplate Table</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)  
 [<span data-ttu-id="b0450-118">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="b0450-118">UriTemplate</span></span>](../../../../docs/framework/wcf/samples/uritemplate-sample.md)
