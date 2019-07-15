---
ms.openlocfilehash: 8dc98b2d9c2c0b5f145ebce48cf8f5e054975c6e
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858570"
---
### <a name="corprfgcroothandles-are-not-being-enumerated-by-profilers"></a><span data-ttu-id="e72b7-101">Gli COR_PRF_GC_ROOT_HANDLE non vengono enumerati dai profiler</span><span class="sxs-lookup"><span data-stu-id="e72b7-101">COR_PRF_GC_ROOT_HANDLEs are not being enumerated by profilers</span></span>

|   |   |
|---|---|
|<span data-ttu-id="e72b7-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e72b7-102">Details</span></span>|<span data-ttu-id="e72b7-103">In .NET Framework 4.5.1, l'API di profilatura <code>RootReferences2()</code> non restituisce mai <code>COR_PRF_GC_ROOT_HANDLE</code> erroneamente (vengono invece restituiti come <code>COR_PRF_GC_ROOT_OTHER</code>).</span><span class="sxs-lookup"><span data-stu-id="e72b7-103">In the .NET Framework v4.5.1, the profiling API <code>RootReferences2()</code> is incorrectly never returning <code>COR_PRF_GC_ROOT_HANDLE</code> (they are returned as <code>COR_PRF_GC_ROOT_OTHER</code> instead).</span></span> <span data-ttu-id="e72b7-104">Questo problema è risolto a partire da .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="e72b7-104">This issue is fixed beginning in the .NET Framework 4.6.</span></span>|
|<span data-ttu-id="e72b7-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="e72b7-105">Suggestion</span></span>|<span data-ttu-id="e72b7-106">Questo problema è stato corretto in .NET Framework 4.6 e può essere risolto eseguendo l'aggiornamento a tale versione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e72b7-106">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>|
|<span data-ttu-id="e72b7-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="e72b7-107">Scope</span></span>|<span data-ttu-id="e72b7-108">Secondario</span><span class="sxs-lookup"><span data-stu-id="e72b7-108">Minor</span></span>|
|<span data-ttu-id="e72b7-109">Versione</span><span class="sxs-lookup"><span data-stu-id="e72b7-109">Version</span></span>|<span data-ttu-id="e72b7-110">4.5.1</span><span class="sxs-lookup"><span data-stu-id="e72b7-110">4.5.1</span></span>|
|<span data-ttu-id="e72b7-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="e72b7-111">Type</span></span>|<span data-ttu-id="e72b7-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="e72b7-112">Runtime</span></span>|

