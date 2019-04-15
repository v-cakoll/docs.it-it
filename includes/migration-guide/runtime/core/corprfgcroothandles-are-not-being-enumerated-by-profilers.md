---
ms.openlocfilehash: 8433899058c6f569e380999800557dbe8ed0a169
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235455"
---
### <a name="corprfgcroothandles-are-not-being-enumerated-by-profilers"></a><span data-ttu-id="e9168-101">Gli COR_PRF_GC_ROOT_HANDLE non vengono enumerati dai profiler</span><span class="sxs-lookup"><span data-stu-id="e9168-101">COR_PRF_GC_ROOT_HANDLEs are not being enumerated by profilers</span></span>

|   |   |
|---|---|
|<span data-ttu-id="e9168-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e9168-102">Details</span></span>|<span data-ttu-id="e9168-103">In .NET Framework 4.5.1, l'API di profilatura <code>RootReferences2()</code> non restituisce mai <code>COR_PRF_GC_ROOT_HANDLE</code> erroneamente (vengono invece restituiti come <code>COR_PRF_GC_ROOT_OTHER</code>).</span><span class="sxs-lookup"><span data-stu-id="e9168-103">In the .NET Framework v4.5.1, the profiling API <code>RootReferences2()</code> is incorrectly never returning <code>COR_PRF_GC_ROOT_HANDLE</code> (they are returned as <code>COR_PRF_GC_ROOT_OTHER</code> instead).</span></span> <span data-ttu-id="e9168-104">Questo problema è risolto a partire da .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="e9168-104">This issue is fixed beginning in the .NET Framework 4.6.</span></span>|
|<span data-ttu-id="e9168-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="e9168-105">Suggestion</span></span>|<span data-ttu-id="e9168-106">Questo problema è stato corretto in .NET Framework 4.6 e può essere risolto eseguendo l'aggiornamento a tale versione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e9168-106">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>|
|<span data-ttu-id="e9168-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="e9168-107">Scope</span></span>|<span data-ttu-id="e9168-108">Secondario</span><span class="sxs-lookup"><span data-stu-id="e9168-108">Minor</span></span>|
|<span data-ttu-id="e9168-109">Versione</span><span class="sxs-lookup"><span data-stu-id="e9168-109">Version</span></span>|<span data-ttu-id="e9168-110">4.5.1</span><span class="sxs-lookup"><span data-stu-id="e9168-110">4.5.1</span></span>|
|<span data-ttu-id="e9168-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="e9168-111">Type</span></span>|<span data-ttu-id="e9168-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="e9168-112">Runtime</span></span>|
