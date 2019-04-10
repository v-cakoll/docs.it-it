---
title: Tabella di esempio UriTemplate
ms.date: 03/30/2017
ms.assetid: 5dd1d38f-1989-4c64-820d-821f5a02216a
ms.openlocfilehash: 4543d4676344d10c3e380c3522a7ca5a6a8d6294
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59293957"
---
# <a name="uritemplate-table-sample"></a><span data-ttu-id="0c177-102">Tabella di esempio UriTemplate</span><span class="sxs-lookup"><span data-stu-id="0c177-102">UriTemplate Table Sample</span></span>
<span data-ttu-id="0c177-103">La classe <xref:System.UriTemplateTable> fornisce una struttura con tabella associativa simile a un dizionario per lavorare con un set di istanze `UriTemplate`.</span><span class="sxs-lookup"><span data-stu-id="0c177-103">The <xref:System.UriTemplateTable> class provides a dictionary-like associative table structure for working with a set of `UriTemplate` instances.</span></span> <span data-ttu-id="0c177-104">URI (Uniform Resource Identifier) specifici possono essere associati in modo efficace con tutti i modelli della tabella e i dati associati al modello corrispondente possono essere recuperati.</span><span class="sxs-lookup"><span data-stu-id="0c177-104">Specific Uniform Resource Identifiers (URIs) can be matched efficiently against all templates in the table, and data associated with the matched template can be retrieved.</span></span>  
  
 <span data-ttu-id="0c177-105">In questo esempio vengono illustrati i seguenti concetti principali relativi alla classe `UriTemplateTable`:</span><span class="sxs-lookup"><span data-stu-id="0c177-105">This sample demonstrates the following key concepts related to the `UriTemplateTable` class:</span></span>  
  
-   <span data-ttu-id="0c177-106">Sintassi per la creazione di un'istanza `UriTemplateTable`.</span><span class="sxs-lookup"><span data-stu-id="0c177-106">Syntax for instantiating a `UriTemplateTable`.</span></span>  
  
-   <span data-ttu-id="0c177-107">Popolare una `UriTemplateTable` con un set di coppie chiave/valore.</span><span class="sxs-lookup"><span data-stu-id="0c177-107">Populating a `UriTemplateTable` with a set of key/value pairs.</span></span>  
  
-   <span data-ttu-id="0c177-108">Associare un candidato URI alla tabella utilizzando <xref:System.UriTemplateTable.MatchSingle%2A>.</span><span class="sxs-lookup"><span data-stu-id="0c177-108">Matching a candidate URI against the table using <xref:System.UriTemplateTable.MatchSingle%2A>.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0c177-109">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="0c177-109">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="0c177-110">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0c177-110">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="0c177-111">Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0c177-111">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0c177-112">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="0c177-112">The samples may already be installed on your computer.</span></span> <span data-ttu-id="0c177-113">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="0c177-113">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0c177-114">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="0c177-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0c177-115">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="0c177-115">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateTable`  
  
## <a name="see-also"></a><span data-ttu-id="0c177-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c177-116">See also</span></span>

- [<span data-ttu-id="0c177-117">Dispatcher della tabella UriTemplate</span><span class="sxs-lookup"><span data-stu-id="0c177-117">UriTemplate Table Dispatcher</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)
- [<span data-ttu-id="0c177-118">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="0c177-118">UriTemplate</span></span>](../../../../docs/framework/wcf/samples/uritemplate-sample.md)
