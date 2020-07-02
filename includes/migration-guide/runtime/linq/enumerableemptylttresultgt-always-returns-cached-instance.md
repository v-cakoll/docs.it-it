---
ms.openlocfilehash: 9131c91b34f4c24653dea37ea39af6be6e072287
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620334"
---
### <a name="enumerableemptylttresultgt-always-returns-cached-instance"></a><span data-ttu-id="f8c88-101">Enumerable.Empty&lt;TResult&gt; restituisce sempre un'istanza memorizzata nella cache</span><span class="sxs-lookup"><span data-stu-id="f8c88-101">Enumerable.Empty&lt;TResult&gt; always returns cached instance</span></span>

#### <a name="details"></a><span data-ttu-id="f8c88-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f8c88-102">Details</span></span>

<span data-ttu-id="f8c88-103">A partire da .NET Framework 4.5, <xref:System.Linq.Enumerable.Empty%60%601> restituisce sempre un <xref:System.Collections.Generic.IEnumerable%601> di un'istanza interna memorizzata nella cache. Nelle versioni precedenti, <xref:System.Linq.Enumerable.Empty%60%601> memorizzava nella cache un <xref:System.Collections.Generic.IEnumerable%601> vuoto al momento della chiamata dell'API e questo significa che in alcune condizioni in cui <xref:System.Linq.Enumerable.Empty%60%601> viene chiamato velocemente e in simultanea, possono essere restituite istanze diverse del tipo per chiamate diverse all'API.</span><span class="sxs-lookup"><span data-stu-id="f8c88-103">Beginning in .NET Framework 4.5, <xref:System.Linq.Enumerable.Empty%60%601> always returns a cached internal instance <xref:System.Collections.Generic.IEnumerable%601>.Previously, <xref:System.Linq.Enumerable.Empty%60%601> would cache an empty <xref:System.Collections.Generic.IEnumerable%601> at the time the API was called, meaning that in some conditions in which <xref:System.Linq.Enumerable.Empty%60%601> was called rapidly and concurrently, different instances of the type could be returned for different calls to the API.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f8c88-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="f8c88-104">Suggestion</span></span>

<span data-ttu-id="f8c88-105">Dato che il comportamento precedente è non deterministico, è improbabile che esista codice dipendente.</span><span class="sxs-lookup"><span data-stu-id="f8c88-105">Because the previous behavior was non-deterministic, code is unlikely to depend on it.</span></span> <span data-ttu-id="f8c88-106">Tuttavia, nel caso improbabile che i tipi enumerabili vuoti vengano usati per confronti prevedendo che talvolta possano essere diversi, è consigliabile creare matrici vuote esplicite (<code>new T[0]</code>) invece di usare <xref:System.Linq.Enumerable.Empty%60%601>.</span><span class="sxs-lookup"><span data-stu-id="f8c88-106">However, in the unlikely case that empty enumerables are being compared and expected to sometimes be unequal, explicit empty arrays should be created (<code>new T[0]</code>) instead of using <xref:System.Linq.Enumerable.Empty%60%601>.</span></span>

| <span data-ttu-id="f8c88-107">Nome</span><span class="sxs-lookup"><span data-stu-id="f8c88-107">Name</span></span>    | <span data-ttu-id="f8c88-108">Valore</span><span class="sxs-lookup"><span data-stu-id="f8c88-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f8c88-109">Scope</span><span class="sxs-lookup"><span data-stu-id="f8c88-109">Scope</span></span>   |<span data-ttu-id="f8c88-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f8c88-110">Edge</span></span>|
|<span data-ttu-id="f8c88-111">Version</span><span class="sxs-lookup"><span data-stu-id="f8c88-111">Version</span></span>|<span data-ttu-id="f8c88-112">4.5</span><span class="sxs-lookup"><span data-stu-id="f8c88-112">4.5</span></span>|
|<span data-ttu-id="f8c88-113">Type</span><span class="sxs-lookup"><span data-stu-id="f8c88-113">Type</span></span>|<span data-ttu-id="f8c88-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="f8c88-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f8c88-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="f8c88-115">Affected APIs</span></span>

-<xref:System.Linq.Enumerable.Empty%60%601?displayProperty=nameWithType></li></ul>|
