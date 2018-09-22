---
title: '&lt;services&gt; di &lt;workflowRuntime&gt;'
ms.date: 03/30/2017
ms.assetid: 219a05b1-f573-45c9-849b-e86bc373b62f
ms.openlocfilehash: 44da735ab1aa2391fe882dfba6e1afc47be746ff
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2018
ms.locfileid: "46576691"
---
# <a name="ltservicesgt-of-ltworkflowruntimegt"></a><span data-ttu-id="24085-102">&lt;services&gt; di &lt;workflowRuntime&gt;</span><span class="sxs-lookup"><span data-stu-id="24085-102">&lt;services&gt; of &lt;workflowRuntime&gt;</span></span>
<span data-ttu-id="24085-103">Rappresenta una raccolta di servizi da aggiungere al motore di <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="24085-103">Represents a collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="24085-104">Gli elementi sono di tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="24085-104">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="24085-105">I servizi specificati nella raccolta verranno inizializzati dal motore di runtime del flusso di lavoro e verranno aggiunti ai relativi servizi quando verrà chiamato il costruttore <xref:System.Workflow.Runtime.WorkflowRuntime> appropriato.</span><span class="sxs-lookup"><span data-stu-id="24085-105">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="24085-106">Pertanto, i servizi specificati nella raccolta devono seguire regole precise riguardanti le firme dei relativi costruttori.</span><span class="sxs-lookup"><span data-stu-id="24085-106">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="24085-107">Per altre informazioni, vedere <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="24085-107">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24085-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24085-108">See Also</span></span>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <span data-ttu-id="24085-109">[File di configurazione del flusso di lavoro](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="24085-109">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
