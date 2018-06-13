---
title: Esempio di UriTemplate
ms.date: 03/30/2017
ms.assetid: 0aaf91d0-ce18-468d-8006-bc9bc2e48231
ms.openlocfilehash: 53ce296eadf03d7f9f46d36cb0130c9b502f4893
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33502374"
---
# <a name="uritemplate-sample"></a><span data-ttu-id="8eae4-102">Esempio di UriTemplate</span><span class="sxs-lookup"><span data-stu-id="8eae4-102">UriTemplate Sample</span></span>
<span data-ttu-id="8eae4-103">La classe <xref:System.UriTemplate> fornisce metodi per l'utilizzo di set di URI che condividono una struttura comune.</span><span class="sxs-lookup"><span data-stu-id="8eae4-103">The <xref:System.UriTemplate> class provides methods for working with sets of URIs that share a common structure.</span></span> <span data-ttu-id="8eae4-104">In questo esempio vengono illustrati i seguenti concetti principali relativi a `UriTemplate`:</span><span class="sxs-lookup"><span data-stu-id="8eae4-104">This sample demonstrates the following key concepts relating to `UriTemplate`:</span></span>  
  
-   <span data-ttu-id="8eae4-105">Sintassi per la creazione di modelli.</span><span class="sxs-lookup"><span data-stu-id="8eae4-105">Syntax for creating templates.</span></span>  
  
-   <span data-ttu-id="8eae4-106">Creazione di istanze degli URI da un `UriTemplate` utilizzando <xref:System.UriTemplate.BindByName%2A> e <xref:System.UriTemplate.BindByPosition%2A>.</span><span class="sxs-lookup"><span data-stu-id="8eae4-106">Instantiating URIs from a `UriTemplate` using <xref:System.UriTemplate.BindByName%2A> and <xref:System.UriTemplate.BindByPosition%2A>.</span></span>  
  
-   <span data-ttu-id="8eae4-107"><xref:System.UriTemplateTable.Match%2A>, che corrisponde all'operazione inversa di `BindByName` e `BindByPosition`.</span><span class="sxs-lookup"><span data-stu-id="8eae4-107"><xref:System.UriTemplateTable.Match%2A>, which is the inverse operation of `BindByName` and `BindByPosition`.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8eae4-108">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="8eae4-108">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="8eae4-109">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8eae4-109">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="8eae4-110">Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8eae4-110">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8eae4-111">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="8eae4-111">The samples may already be installed on your computer.</span></span> <span data-ttu-id="8eae4-112">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="8eae4-112">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8eae4-113">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="8eae4-113">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8eae4-114">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="8eae4-114">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplate`  
  
## <a name="see-also"></a><span data-ttu-id="8eae4-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8eae4-115">See Also</span></span>  
 [<span data-ttu-id="8eae4-116">UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="8eae4-116">UriTemplate Table</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)  
 [<span data-ttu-id="8eae4-117">Dispatcher della tabella UriTemplate</span><span class="sxs-lookup"><span data-stu-id="8eae4-117">UriTemplate Table Dispatcher</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)
