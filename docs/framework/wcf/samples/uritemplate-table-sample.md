---
title: Tabella di esempio UriTemplate
ms.date: 03/30/2017
ms.assetid: 5dd1d38f-1989-4c64-820d-821f5a02216a
ms.openlocfilehash: c0aed1a49faf74ab9fd463769aab66ad72e74038
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183260"
---
# <a name="uritemplate-table-sample"></a><span data-ttu-id="7e790-102">Tabella di esempio UriTemplate</span><span class="sxs-lookup"><span data-stu-id="7e790-102">UriTemplate Table Sample</span></span>
<span data-ttu-id="7e790-103">La classe <xref:System.UriTemplateTable> fornisce una struttura con tabella associativa simile a un dizionario per lavorare con un set di istanze `UriTemplate`.</span><span class="sxs-lookup"><span data-stu-id="7e790-103">The <xref:System.UriTemplateTable> class provides a dictionary-like associative table structure for working with a set of `UriTemplate` instances.</span></span> <span data-ttu-id="7e790-104">URI (Uniform Resource Identifier) specifici possono essere associati in modo efficace con tutti i modelli della tabella e i dati associati al modello corrispondente possono essere recuperati.</span><span class="sxs-lookup"><span data-stu-id="7e790-104">Specific Uniform Resource Identifiers (URIs) can be matched efficiently against all templates in the table, and data associated with the matched template can be retrieved.</span></span>  
  
 <span data-ttu-id="7e790-105">In questo esempio vengono illustrati i seguenti concetti principali relativi alla classe `UriTemplateTable`:</span><span class="sxs-lookup"><span data-stu-id="7e790-105">This sample demonstrates the following key concepts related to the `UriTemplateTable` class:</span></span>  
  
- <span data-ttu-id="7e790-106">Sintassi per la creazione di un'istanza `UriTemplateTable`.</span><span class="sxs-lookup"><span data-stu-id="7e790-106">Syntax for instantiating a `UriTemplateTable`.</span></span>  
  
- <span data-ttu-id="7e790-107">Popolare una `UriTemplateTable` con un set di coppie chiave/valore.</span><span class="sxs-lookup"><span data-stu-id="7e790-107">Populating a `UriTemplateTable` with a set of key/value pairs.</span></span>  
  
- <span data-ttu-id="7e790-108">Associare un candidato URI alla tabella utilizzando <xref:System.UriTemplateTable.MatchSingle%2A>.</span><span class="sxs-lookup"><span data-stu-id="7e790-108">Matching a candidate URI against the table using <xref:System.UriTemplateTable.MatchSingle%2A>.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="7e790-109">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="7e790-109">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="7e790-110">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7e790-110">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="7e790-111">Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7e790-111">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7e790-112">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="7e790-112">The samples may already be installed on your computer.</span></span> <span data-ttu-id="7e790-113">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="7e790-113">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="7e790-114">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="7e790-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7e790-115">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="7e790-115">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateTable`  
  
## <a name="see-also"></a><span data-ttu-id="7e790-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e790-116">See also</span></span>

- [<span data-ttu-id="7e790-117">Dispatcher della tabella UriTemplate</span><span class="sxs-lookup"><span data-stu-id="7e790-117">UriTemplate Table Dispatcher</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)
- [<span data-ttu-id="7e790-118">Uritemplate</span><span class="sxs-lookup"><span data-stu-id="7e790-118">UriTemplate</span></span>](../../../../docs/framework/wcf/samples/uritemplate-sample.md)
