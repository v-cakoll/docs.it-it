---
ms.openlocfilehash: 107b34c7bd26e1396e8a6638d6929c15de92b8e4
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67803278"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a><span data-ttu-id="d33d4-101">La profilatura delle app ASP.Net MVC4 può causare un errore irreversibile del motore di esecuzione</span><span class="sxs-lookup"><span data-stu-id="d33d4-101">Profiling ASP.Net MVC4 apps can lead to Fatal Execution Engine Error</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d33d4-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d33d4-102">Details</span></span>|<span data-ttu-id="d33d4-103">I profiler che usano gli assembly NGEN /Profile potrebbero causare arresti anomali delle applicazioni ASP.NET MVC4 profilate all'avvio con una 'eccezione irreversibile del motore di esecuzione'</span><span class="sxs-lookup"><span data-stu-id="d33d4-103">Profilers using NGEN /Profile assemblies may crash profiled ASP.NET MVC4 applications on startup with a 'Fatal Execution Engine Exception'</span></span>|
|<span data-ttu-id="d33d4-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="d33d4-104">Suggestion</span></span>|<span data-ttu-id="d33d4-105">Questo problema è risolto in .NET Framework 4.5.2.</span><span class="sxs-lookup"><span data-stu-id="d33d4-105">This issue is fixed in the .NET Framework 4.5.2.</span></span> <span data-ttu-id="d33d4-106">In alternativa, il profiler può evitare questo problema specificando <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> nella maschera dell'evento.</span><span class="sxs-lookup"><span data-stu-id="d33d4-106">Alternatively, the profiler may avoid this issue by specifying <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in its event mask.</span></span>|
|<span data-ttu-id="d33d4-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="d33d4-107">Scope</span></span>|<span data-ttu-id="d33d4-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d33d4-108">Edge</span></span>|
|<span data-ttu-id="d33d4-109">Versione</span><span class="sxs-lookup"><span data-stu-id="d33d4-109">Version</span></span>|<span data-ttu-id="d33d4-110">4.5</span><span class="sxs-lookup"><span data-stu-id="d33d4-110">4.5</span></span>|
|<span data-ttu-id="d33d4-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="d33d4-111">Type</span></span>|<span data-ttu-id="d33d4-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="d33d4-112">Runtime</span></span>|

