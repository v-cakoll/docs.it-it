---
ms.openlocfilehash: a93fbbd787aa50f080337a6170cf8f56d0d24e31
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804233"
---
### <a name="concurrentqueuettrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a><span data-ttu-id="f7ee8-101">ConcurrentQueue\<T>.TryPeek può restituire erroneamente un valore Null tramite il parametro di output</span><span class="sxs-lookup"><span data-stu-id="f7ee8-101">ConcurrentQueue\<T>.TryPeek can return an erroneous null via its out parameter</span></span>

|   |   |
|---|---|
|<span data-ttu-id="f7ee8-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f7ee8-102">Details</span></span>|<span data-ttu-id="f7ee8-103">In alcuni scenari multithread, <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=name> può restituire true, ma popolare il parametro di output con un valore null, anziché il valore corretto, restituito.</span><span class="sxs-lookup"><span data-stu-id="f7ee8-103">In some multi-threaded scenarios, <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=name> can return true, but populate the out parameter with a null value (instead of the correct, peeked value).</span></span>|
|<span data-ttu-id="f7ee8-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="f7ee8-104">Suggestion</span></span>|<span data-ttu-id="f7ee8-105">Questo problema è risolto in .NET Framework 4.5.1.</span><span class="sxs-lookup"><span data-stu-id="f7ee8-105">This issue is fixed in the .NET Framework 4.5.1.</span></span> <span data-ttu-id="f7ee8-106">L'aggiornamento a questa versione di .NET Framework consentirà di risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="f7ee8-106">Upgrading to that Framework will solve the issue.</span></span>|
|<span data-ttu-id="f7ee8-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="f7ee8-107">Scope</span></span>|<span data-ttu-id="f7ee8-108">Principale</span><span class="sxs-lookup"><span data-stu-id="f7ee8-108">Major</span></span>|
|<span data-ttu-id="f7ee8-109">Versione</span><span class="sxs-lookup"><span data-stu-id="f7ee8-109">Version</span></span>|<span data-ttu-id="f7ee8-110">4.5</span><span class="sxs-lookup"><span data-stu-id="f7ee8-110">4.5</span></span>|
|<span data-ttu-id="f7ee8-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="f7ee8-111">Type</span></span>|<span data-ttu-id="f7ee8-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="f7ee8-112">Runtime</span></span>|
|<span data-ttu-id="f7ee8-113">API interessate</span><span class="sxs-lookup"><span data-stu-id="f7ee8-113">Affected APIs</span></span>|<ul><li><xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType></li></ul>|
