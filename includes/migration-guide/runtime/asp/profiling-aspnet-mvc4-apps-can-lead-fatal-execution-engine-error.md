---
ms.openlocfilehash: 439a4976482639cd2e4e17315ec1a53ca54aa477
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803278"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a><span data-ttu-id="223ef-101">La profilatura delle app ASP.Net MVC4 può causare un errore irreversibile del motore di esecuzione</span><span class="sxs-lookup"><span data-stu-id="223ef-101">Profiling ASP.Net MVC4 apps can lead to Fatal Execution Engine Error</span></span>

|   |   |
|---|---|
|<span data-ttu-id="223ef-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="223ef-102">Details</span></span>|<span data-ttu-id="223ef-103">I profiler che usano gli assembly NGEN /Profile potrebbero causare arresti anomali delle applicazioni ASP.NET MVC4 profilate all'avvio con una 'eccezione irreversibile del motore di esecuzione'</span><span class="sxs-lookup"><span data-stu-id="223ef-103">Profilers using NGEN /Profile assemblies may crash profiled ASP.NET MVC4 applications on startup with a 'Fatal Execution Engine Exception'</span></span>|
|<span data-ttu-id="223ef-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="223ef-104">Suggestion</span></span>|<span data-ttu-id="223ef-105">Questo problema è risolto in .NET Framework 4.5.2.</span><span class="sxs-lookup"><span data-stu-id="223ef-105">This issue is fixed in the .NET Framework 4.5.2.</span></span> <span data-ttu-id="223ef-106">In alternativa, il profiler può evitare questo problema specificando <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> nella maschera dell'evento.</span><span class="sxs-lookup"><span data-stu-id="223ef-106">Alternatively, the profiler may avoid this issue by specifying <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in its event mask.</span></span>|
|<span data-ttu-id="223ef-107">Scope</span><span class="sxs-lookup"><span data-stu-id="223ef-107">Scope</span></span>|<span data-ttu-id="223ef-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="223ef-108">Edge</span></span>|
|<span data-ttu-id="223ef-109">Versione</span><span class="sxs-lookup"><span data-stu-id="223ef-109">Version</span></span>|<span data-ttu-id="223ef-110">4.5</span><span class="sxs-lookup"><span data-stu-id="223ef-110">4.5</span></span>|
|<span data-ttu-id="223ef-111">Type</span><span class="sxs-lookup"><span data-stu-id="223ef-111">Type</span></span>|<span data-ttu-id="223ef-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="223ef-112">Runtime</span></span>|
