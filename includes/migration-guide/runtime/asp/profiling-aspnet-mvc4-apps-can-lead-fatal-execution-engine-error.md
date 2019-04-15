---
ms.openlocfilehash: 439a4976482639cd2e4e17315ec1a53ca54aa477
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235525"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a><span data-ttu-id="3adc0-101">La profilatura delle app ASP.Net MVC4 può causare un errore irreversibile del motore di esecuzione</span><span class="sxs-lookup"><span data-stu-id="3adc0-101">Profiling ASP.Net MVC4 apps can lead to Fatal Execution Engine Error</span></span>

|   |   |
|---|---|
|<span data-ttu-id="3adc0-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="3adc0-102">Details</span></span>|<span data-ttu-id="3adc0-103">I profiler che usano gli assembly NGEN /Profile potrebbero causare arresti anomali delle applicazioni ASP.NET MVC4 profilate all'avvio con una 'eccezione irreversibile del motore di esecuzione'</span><span class="sxs-lookup"><span data-stu-id="3adc0-103">Profilers using NGEN /Profile assemblies may crash profiled ASP.NET MVC4 applications on startup with a 'Fatal Execution Engine Exception'</span></span>|
|<span data-ttu-id="3adc0-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="3adc0-104">Suggestion</span></span>|<span data-ttu-id="3adc0-105">Questo problema è risolto in .NET Framework 4.5.2.</span><span class="sxs-lookup"><span data-stu-id="3adc0-105">This issue is fixed in the .NET Framework 4.5.2.</span></span> <span data-ttu-id="3adc0-106">In alternativa, il profiler può evitare questo problema specificando <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> nella maschera dell'evento.</span><span class="sxs-lookup"><span data-stu-id="3adc0-106">Alternatively, the profiler may avoid this issue by specifying <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in its event mask.</span></span>|
|<span data-ttu-id="3adc0-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="3adc0-107">Scope</span></span>|<span data-ttu-id="3adc0-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3adc0-108">Edge</span></span>|
|<span data-ttu-id="3adc0-109">Versione</span><span class="sxs-lookup"><span data-stu-id="3adc0-109">Version</span></span>|<span data-ttu-id="3adc0-110">4.5</span><span class="sxs-lookup"><span data-stu-id="3adc0-110">4.5</span></span>|
|<span data-ttu-id="3adc0-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="3adc0-111">Type</span></span>|<span data-ttu-id="3adc0-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="3adc0-112">Runtime</span></span>|
