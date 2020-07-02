---
ms.openlocfilehash: 2e13268d4983af5d2fdd6d12b4d9e67d61d07f3d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622032"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a><span data-ttu-id="8a215-101">La profilatura delle app ASP.Net MVC4 può causare un errore irreversibile del motore di esecuzione</span><span class="sxs-lookup"><span data-stu-id="8a215-101">Profiling ASP.Net MVC4 apps can lead to Fatal Execution Engine Error</span></span>

#### <a name="details"></a><span data-ttu-id="8a215-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="8a215-102">Details</span></span>

<span data-ttu-id="8a215-103">I profiler che usano gli assembly NGEN /Profile potrebbero causare arresti anomali delle applicazioni ASP.NET MVC4 profilate all'avvio con una 'eccezione irreversibile del motore di esecuzione'</span><span class="sxs-lookup"><span data-stu-id="8a215-103">Profilers using NGEN /Profile assemblies may crash profiled ASP.NET MVC4 applications on startup with a 'Fatal Execution Engine Exception'</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8a215-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="8a215-104">Suggestion</span></span>

<span data-ttu-id="8a215-105">Questo problema è risolto in .NET Framework 4.5.2.</span><span class="sxs-lookup"><span data-stu-id="8a215-105">This issue is fixed in the .NET Framework 4.5.2.</span></span> <span data-ttu-id="8a215-106">In alternativa, il profiler può evitare questo problema specificando <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> nella maschera dell'evento.</span><span class="sxs-lookup"><span data-stu-id="8a215-106">Alternatively, the profiler may avoid this issue by specifying <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in its event mask.</span></span>

| <span data-ttu-id="8a215-107">Nome</span><span class="sxs-lookup"><span data-stu-id="8a215-107">Name</span></span>    | <span data-ttu-id="8a215-108">Valore</span><span class="sxs-lookup"><span data-stu-id="8a215-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8a215-109">Scope</span><span class="sxs-lookup"><span data-stu-id="8a215-109">Scope</span></span>   |<span data-ttu-id="8a215-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8a215-110">Edge</span></span>|
|<span data-ttu-id="8a215-111">Version</span><span class="sxs-lookup"><span data-stu-id="8a215-111">Version</span></span>|<span data-ttu-id="8a215-112">4.5</span><span class="sxs-lookup"><span data-stu-id="8a215-112">4.5</span></span>|
|<span data-ttu-id="8a215-113">Type</span><span class="sxs-lookup"><span data-stu-id="8a215-113">Type</span></span>|<span data-ttu-id="8a215-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="8a215-114">Runtime</span></span>|
