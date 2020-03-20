---
ms.openlocfilehash: 8433899058c6f569e380999800557dbe8ed0a169
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858570"
---
### <a name="cor_prf_gc_root_handles-are-not-being-enumerated-by-profilers"></a><span data-ttu-id="0a1fe-101">Gli COR_PRF_GC_ROOT_HANDLE non vengono enumerati dai profiler</span><span class="sxs-lookup"><span data-stu-id="0a1fe-101">COR_PRF_GC_ROOT_HANDLEs are not being enumerated by profilers</span></span>

|   |   |
|---|---|
|<span data-ttu-id="0a1fe-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0a1fe-102">Details</span></span>|<span data-ttu-id="0a1fe-103">In .NET Framework 4.5.1, l'API di profilatura <code>RootReferences2()</code> non restituisce mai <code>COR_PRF_GC_ROOT_HANDLE</code> erroneamente (vengono invece restituiti come <code>COR_PRF_GC_ROOT_OTHER</code>).</span><span class="sxs-lookup"><span data-stu-id="0a1fe-103">In the .NET Framework v4.5.1, the profiling API <code>RootReferences2()</code> is incorrectly never returning <code>COR_PRF_GC_ROOT_HANDLE</code> (they are returned as <code>COR_PRF_GC_ROOT_OTHER</code> instead).</span></span> <span data-ttu-id="0a1fe-104">Questo problema è risolto a partire da .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="0a1fe-104">This issue is fixed beginning in the .NET Framework 4.6.</span></span>|
|<span data-ttu-id="0a1fe-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="0a1fe-105">Suggestion</span></span>|<span data-ttu-id="0a1fe-106">Questo problema è stato corretto in .NET Framework 4.6 e può essere risolto eseguendo l'aggiornamento a tale versione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0a1fe-106">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>|
|<span data-ttu-id="0a1fe-107">Scope</span><span class="sxs-lookup"><span data-stu-id="0a1fe-107">Scope</span></span>|<span data-ttu-id="0a1fe-108">Minorenne</span><span class="sxs-lookup"><span data-stu-id="0a1fe-108">Minor</span></span>|
|<span data-ttu-id="0a1fe-109">Versione</span><span class="sxs-lookup"><span data-stu-id="0a1fe-109">Version</span></span>|<span data-ttu-id="0a1fe-110">4.5.1</span><span class="sxs-lookup"><span data-stu-id="0a1fe-110">4.5.1</span></span>|
|<span data-ttu-id="0a1fe-111">Type</span><span class="sxs-lookup"><span data-stu-id="0a1fe-111">Type</span></span>|<span data-ttu-id="0a1fe-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="0a1fe-112">Runtime</span></span>|
