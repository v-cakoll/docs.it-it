---
ms.openlocfilehash: 3300a74b81fc9eeba670ee0ceb2c2615fd3925bd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617219"
---
### <a name="listlttgtforeach-can-throw-exception-when-modifying-list-item"></a><span data-ttu-id="4a2c0-101">List&lt;T&gt;.ForEach può generare un'eccezione quando si modifica una voce di elenco</span><span class="sxs-lookup"><span data-stu-id="4a2c0-101">List&lt;T&gt;.ForEach can throw exception when modifying list item</span></span>

#### <a name="details"></a><span data-ttu-id="4a2c0-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="4a2c0-102">Details</span></span>

<span data-ttu-id="4a2c0-103">A partire da .NET Framework 4.5, un enumeratore <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> genera un'eccezione <xref:System.InvalidOperationException?displayProperty=fullName> in caso di modifica di un elemento nella raccolta chiamante.</span><span class="sxs-lookup"><span data-stu-id="4a2c0-103">Beginning in .NET Framework 4.5, a <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> enumerator will throw an <xref:System.InvalidOperationException?displayProperty=fullName> exception if an element in the calling collection is modified.</span></span> <span data-ttu-id="4a2c0-104">Nelle versioni precedenti questa condizione non genera un'eccezione ma può causare situazioni di race condition.</span><span class="sxs-lookup"><span data-stu-id="4a2c0-104">Previously, this would not throw an exception but could lead to race conditions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4a2c0-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="4a2c0-105">Suggestion</span></span>

<span data-ttu-id="4a2c0-106">Idealmente, il codice dovrebbe essere corretto per evitare la modifica degli elenchi durante l'enumerazione dei relativi elementi, perché questa non è mai un'operazione sicura.</span><span class="sxs-lookup"><span data-stu-id="4a2c0-106">Ideally, code should be fixed to not modify lists while enumerating their elements because that is never a safe operation.</span></span> <span data-ttu-id="4a2c0-107">Per ripristinare il comportamento precedente, tuttavia, un'app può essere destinata a .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="4a2c0-107">To revert to the previous behavior, though, an app may target .NET Framework 4.0.</span></span>

| <span data-ttu-id="4a2c0-108">Nome</span><span class="sxs-lookup"><span data-stu-id="4a2c0-108">Name</span></span>    | <span data-ttu-id="4a2c0-109">Valore</span><span class="sxs-lookup"><span data-stu-id="4a2c0-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4a2c0-110">Scope</span><span class="sxs-lookup"><span data-stu-id="4a2c0-110">Scope</span></span>   | <span data-ttu-id="4a2c0-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="4a2c0-111">Edge</span></span>        |
| <span data-ttu-id="4a2c0-112">Version</span><span class="sxs-lookup"><span data-stu-id="4a2c0-112">Version</span></span> | <span data-ttu-id="4a2c0-113">4.5</span><span class="sxs-lookup"><span data-stu-id="4a2c0-113">4.5</span></span>         |
| <span data-ttu-id="4a2c0-114">Type</span><span class="sxs-lookup"><span data-stu-id="4a2c0-114">Type</span></span>    | <span data-ttu-id="4a2c0-115">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="4a2c0-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="4a2c0-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="4a2c0-116">Affected APIs</span></span>

- <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})?displayProperty=nameWithType>
