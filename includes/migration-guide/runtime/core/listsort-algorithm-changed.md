---
ms.openlocfilehash: 9dada93c3330331064b7a944d97d61edb4dea299
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620251"
---
### <a name="listsort-algorithm-changed"></a><span data-ttu-id="1f501-101">L'algoritmo List.Sort è stato modificato</span><span class="sxs-lookup"><span data-stu-id="1f501-101">List.Sort algorithm changed</span></span>

#### <a name="details"></a><span data-ttu-id="1f501-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="1f501-102">Details</span></span>

<span data-ttu-id="1f501-103">A partire da .NET Framework 4.5, l'algoritmo di ordinamento di <xref:System.Collections.Generic.List%601?displayProperty=fullName> è stato modificato in ordinamento introspettivo anziché ordinamento rapido.</span><span class="sxs-lookup"><span data-stu-id="1f501-103">Beginning in .NET Framework 4.5, <xref:System.Collections.Generic.List%601?displayProperty=fullName>'s sort algorithm has changed (to be an introspective sort instead of a quick sort).</span></span> <span data-ttu-id="1f501-104">L'ordinamento di <xref:System.Collections.Generic.List%601?displayProperty=fullName> non è mai stato stabile, ma questa modifica potrebbe determinare un ordinamento instabile in scenari diversi.</span><span class="sxs-lookup"><span data-stu-id="1f501-104"><xref:System.Collections.Generic.List%601?displayProperty=fullName>'s sort has never been stable, but this change may cause different scenarios to sort in unstable ways.</span></span> <span data-ttu-id="1f501-105">Ciò significa semplicemente che l'ordinamento di elementi equivalenti potrebbe risultare diverso nelle successive chiamate dell'API.</span><span class="sxs-lookup"><span data-stu-id="1f501-105">That simply means that equivalent items may sort in different orders in subsequent calls of the API.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1f501-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="1f501-106">Suggestion</span></span>

<span data-ttu-id="1f501-107">Poiché anche l'algoritmo di ordinamento precedente era instabile, anche se in modi leggermente diversi, nessun codice deve dipendere da elementi equivalenti sempre ordinati in un particolare ordine.</span><span class="sxs-lookup"><span data-stu-id="1f501-107">Because the old sort algorithm was also unstable (though in slightly different ways), there should be no code that depends on equivalent items always sorting in a particular order.</span></span> <span data-ttu-id="1f501-108">In presenza di istanze di codice con questo tipo di dipendenza che funzionano correttamente con il vecchio comportamento, è necessario aggiornare il codice in modo che usi un operatore di confronto che ordinerà gli elementi in modo deterministico nell'ordine desiderato.</span><span class="sxs-lookup"><span data-stu-id="1f501-108">If there are instances of code depending upon that and being lucky with the old behavior, that code should be updated to use a comparer that will deterministically sort the items in the desired order.</span></span>

| <span data-ttu-id="1f501-109">Nome</span><span class="sxs-lookup"><span data-stu-id="1f501-109">Name</span></span>    | <span data-ttu-id="1f501-110">Valore</span><span class="sxs-lookup"><span data-stu-id="1f501-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1f501-111">Scope</span><span class="sxs-lookup"><span data-stu-id="1f501-111">Scope</span></span>   |<span data-ttu-id="1f501-112">Modalità trasparente</span><span class="sxs-lookup"><span data-stu-id="1f501-112">Transparent</span></span>|
|<span data-ttu-id="1f501-113">Version</span><span class="sxs-lookup"><span data-stu-id="1f501-113">Version</span></span>|<span data-ttu-id="1f501-114">4.5</span><span class="sxs-lookup"><span data-stu-id="1f501-114">4.5</span></span>|
|<span data-ttu-id="1f501-115">Type</span><span class="sxs-lookup"><span data-stu-id="1f501-115">Type</span></span>|<span data-ttu-id="1f501-116">Runtime</span><span class="sxs-lookup"><span data-stu-id="1f501-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1f501-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="1f501-117">Affected APIs</span></span>

-<xref:System.Collections.Generic.List%601.Sort?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Collections.Generic.IComparer{%600})?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Comparison{%600})?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Int32,System.Int32,System.Collections.Generic.IComparer{%600})?displayProperty=nameWithType></li></ul>|
