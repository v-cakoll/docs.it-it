---
ms.openlocfilehash: 4e81087431091dfa4d5432d5ea5e2b665be2b130
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774324"
---
### <a name="listtforeach-can-throw-exception-when-modifying-list-item"></a><span data-ttu-id="ebf66-101">List\<T>.ForEach può generare un'eccezione quando si modifica una voce di elenco</span><span class="sxs-lookup"><span data-stu-id="ebf66-101">List\<T>.ForEach can throw exception when modifying list item</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ebf66-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ebf66-102">Details</span></span>|<span data-ttu-id="ebf66-103">A partire da .NET Framework 4.5, un enumeratore <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> genera un'eccezione <xref:System.InvalidOperationException?displayProperty=name> in caso di modifica di un elemento nella raccolta chiamante.</span><span class="sxs-lookup"><span data-stu-id="ebf66-103">Beginning in .NET Framework 4.5, a <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> enumerator will throw an <xref:System.InvalidOperationException?displayProperty=name> exception if an element in the calling collection is modified.</span></span> <span data-ttu-id="ebf66-104">Nelle versioni precedenti questa condizione non genera un'eccezione ma può causare situazioni di race condition.</span><span class="sxs-lookup"><span data-stu-id="ebf66-104">Previously, this would not throw an exception but could lead to race conditions.</span></span>|
|<span data-ttu-id="ebf66-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="ebf66-105">Suggestion</span></span>|<span data-ttu-id="ebf66-106">Idealmente, il codice dovrebbe essere corretto per evitare la modifica degli elenchi durante l'enumerazione dei relativi elementi, perché questa non è mai un'operazione sicura.</span><span class="sxs-lookup"><span data-stu-id="ebf66-106">Ideally, code should be fixed to not modify lists while enumerating their elements because that is never a safe operation.</span></span> <span data-ttu-id="ebf66-107">Per ripristinare il comportamento precedente, tuttavia, un'app può essere destinata a .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="ebf66-107">To revert to the previous behavior, though, an app may target .NET Framework 4.0.</span></span>|
|<span data-ttu-id="ebf66-108">Ambito</span><span class="sxs-lookup"><span data-stu-id="ebf66-108">Scope</span></span>|<span data-ttu-id="ebf66-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ebf66-109">Edge</span></span>|
|<span data-ttu-id="ebf66-110">Versione</span><span class="sxs-lookup"><span data-stu-id="ebf66-110">Version</span></span>|<span data-ttu-id="ebf66-111">4.5</span><span class="sxs-lookup"><span data-stu-id="ebf66-111">4.5</span></span>|
|<span data-ttu-id="ebf66-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="ebf66-112">Type</span></span>|<span data-ttu-id="ebf66-113">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="ebf66-113">Retargeting</span></span>|
|<span data-ttu-id="ebf66-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="ebf66-114">Affected APIs</span></span>|<ul><li><xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})?displayProperty=nameWithType></li></ul>|
