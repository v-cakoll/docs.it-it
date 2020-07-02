---
ms.openlocfilehash: 02a15f6b9c02002b60c568b9e1d871af49744092
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622049"
---
### <a name="concurrentqueuelttgttrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a><span data-ttu-id="7d54b-101">ConcurrentQueue&lt;T&gt;.TryPeek può restituire erroneamente un valore Null tramite il parametro di output</span><span class="sxs-lookup"><span data-stu-id="7d54b-101">ConcurrentQueue&lt;T&gt;.TryPeek can return an erroneous null via its out parameter</span></span>

#### <a name="details"></a><span data-ttu-id="7d54b-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="7d54b-102">Details</span></span>

<span data-ttu-id="7d54b-103">In alcuni scenari multithread, <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=fullName> può restituire true, ma popolare il parametro di output con un valore null, anziché il valore corretto, restituito.</span><span class="sxs-lookup"><span data-stu-id="7d54b-103">In some multi-threaded scenarios, <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=fullName> can return true, but populate the out parameter with a null value (instead of the correct, peeked value).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7d54b-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="7d54b-104">Suggestion</span></span>

<span data-ttu-id="7d54b-105">Questo problema è risolto in .NET Framework 4.5.1.</span><span class="sxs-lookup"><span data-stu-id="7d54b-105">This issue is fixed in the .NET Framework 4.5.1.</span></span> <span data-ttu-id="7d54b-106">L'aggiornamento a questa versione di .NET Framework consentirà di risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="7d54b-106">Upgrading to that Framework will solve the issue.</span></span>

| <span data-ttu-id="7d54b-107">Nome</span><span class="sxs-lookup"><span data-stu-id="7d54b-107">Name</span></span>    | <span data-ttu-id="7d54b-108">Valore</span><span class="sxs-lookup"><span data-stu-id="7d54b-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7d54b-109">Scope</span><span class="sxs-lookup"><span data-stu-id="7d54b-109">Scope</span></span>   |<span data-ttu-id="7d54b-110">Principale</span><span class="sxs-lookup"><span data-stu-id="7d54b-110">Major</span></span>|
|<span data-ttu-id="7d54b-111">Version</span><span class="sxs-lookup"><span data-stu-id="7d54b-111">Version</span></span>|<span data-ttu-id="7d54b-112">4.5</span><span class="sxs-lookup"><span data-stu-id="7d54b-112">4.5</span></span>|
|<span data-ttu-id="7d54b-113">Type</span><span class="sxs-lookup"><span data-stu-id="7d54b-113">Type</span></span>|<span data-ttu-id="7d54b-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="7d54b-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7d54b-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="7d54b-115">Affected APIs</span></span>

-<xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType></li></ul>|
