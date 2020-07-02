---
ms.openlocfilehash: 4f52535e54607cc824500f9c6a14964a1dec9d32
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620211"
---
### <a name="cor_prf_gc_root_handles-are-not-being-enumerated-by-profilers"></a><span data-ttu-id="fceae-101">Gli COR_PRF_GC_ROOT_HANDLE non vengono enumerati dai profiler</span><span class="sxs-lookup"><span data-stu-id="fceae-101">COR_PRF_GC_ROOT_HANDLEs are not being enumerated by profilers</span></span>

#### <a name="details"></a><span data-ttu-id="fceae-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="fceae-102">Details</span></span>

<span data-ttu-id="fceae-103">In .NET Framework 4.5.1, l'API di profilatura <code>RootReferences2()</code> non restituisce mai <code>COR_PRF_GC_ROOT_HANDLE</code> erroneamente (vengono invece restituiti come <code>COR_PRF_GC_ROOT_OTHER</code>).</span><span class="sxs-lookup"><span data-stu-id="fceae-103">In the .NET Framework v4.5.1, the profiling API <code>RootReferences2()</code> is incorrectly never returning <code>COR_PRF_GC_ROOT_HANDLE</code> (they are returned as <code>COR_PRF_GC_ROOT_OTHER</code> instead).</span></span> <span data-ttu-id="fceae-104">Questo problema è risolto a partire da .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="fceae-104">This issue is fixed beginning in the .NET Framework 4.6.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="fceae-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="fceae-105">Suggestion</span></span>

<span data-ttu-id="fceae-106">Questo problema è stato corretto in .NET Framework 4.6 e può essere risolto eseguendo l'aggiornamento a tale versione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fceae-106">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="fceae-107">Nome</span><span class="sxs-lookup"><span data-stu-id="fceae-107">Name</span></span>    | <span data-ttu-id="fceae-108">Valore</span><span class="sxs-lookup"><span data-stu-id="fceae-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="fceae-109">Scope</span><span class="sxs-lookup"><span data-stu-id="fceae-109">Scope</span></span>   |<span data-ttu-id="fceae-110">Minorenne</span><span class="sxs-lookup"><span data-stu-id="fceae-110">Minor</span></span>|
|<span data-ttu-id="fceae-111">Version</span><span class="sxs-lookup"><span data-stu-id="fceae-111">Version</span></span>|<span data-ttu-id="fceae-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="fceae-112">4.5.1</span></span>|
|<span data-ttu-id="fceae-113">Type</span><span class="sxs-lookup"><span data-stu-id="fceae-113">Type</span></span>|<span data-ttu-id="fceae-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="fceae-114">Runtime</span></span>|
