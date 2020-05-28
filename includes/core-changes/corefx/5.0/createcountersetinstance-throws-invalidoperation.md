---
ms.openlocfilehash: fabbc9a51f61a703ce97db50ab251e7a13ffe348
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144481"
---
### <a name="countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists"></a><span data-ttu-id="7a5d7-101">Il contatore. CreateCounterSetInstance genera ora InvalidOperationException se l'istanza esiste già</span><span class="sxs-lookup"><span data-stu-id="7a5d7-101">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exists</span></span>

<span data-ttu-id="7a5d7-102">A partire da .NET 5,0, <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType> genera un'eccezione <xref:System.InvalidOperationException> anziché un'eccezione <xref:System.ArgumentException> se l'insieme di contatori esiste già.</span><span class="sxs-lookup"><span data-stu-id="7a5d7-102">Starting in .NET 5.0, <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType> throws an <xref:System.InvalidOperationException> instead of an <xref:System.ArgumentException> if the counter set already exists.</span></span>

#### <a name="change-description"></a><span data-ttu-id="7a5d7-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="7a5d7-103">Change description</span></span>

<span data-ttu-id="7a5d7-104">In .NET Framework e .NET Core 1,0 a 3,1 è possibile creare un'istanza dell'insieme di contatori chiamando <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> .</span><span class="sxs-lookup"><span data-stu-id="7a5d7-104">In .NET Framework and .NET Core 1.0 to 3.1, you can create an instance of the counter set by calling <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>.</span></span> <span data-ttu-id="7a5d7-105">Tuttavia, se l'insieme di contatori esiste già, il metodo genera un' <xref:System.ArgumentException> eccezione.</span><span class="sxs-lookup"><span data-stu-id="7a5d7-105">However, if the counter set already exists, the method throws an <xref:System.ArgumentException> exception.</span></span>

<span data-ttu-id="7a5d7-106">In .NET 5,0 e versioni successive, quando si chiama <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> e l'insieme di contatori esiste, <xref:System.InvalidOperationException> viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="7a5d7-106">In .NET 5.0 and later versions, when you call <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> and the counter set exists, an <xref:System.InvalidOperationException> exception is thrown.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7a5d7-107">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="7a5d7-107">Version introduced</span></span>

<span data-ttu-id="7a5d7-108">5,0 Preview 5</span><span class="sxs-lookup"><span data-stu-id="7a5d7-108">5.0 Preview 5</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7a5d7-109">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="7a5d7-109">Recommended action</span></span>

<span data-ttu-id="7a5d7-110">Se si rilevano <xref:System.ArgumentException> eccezioni nell'app durante la chiamata a <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> , è consigliabile rilevare anche le <xref:System.InvalidOperationException> eccezioni.</span><span class="sxs-lookup"><span data-stu-id="7a5d7-110">If you catch <xref:System.ArgumentException> exceptions in your app when calling <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>, consider also catching <xref:System.InvalidOperationException> exceptions.</span></span>

> [!NOTE]
> <span data-ttu-id="7a5d7-111"><xref:System.ArgumentException>Non è consigliabile intercettare le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="7a5d7-111">Catching <xref:System.ArgumentException> exceptions is not recommended.</span></span>

#### <a name="category"></a><span data-ttu-id="7a5d7-112">Category</span><span class="sxs-lookup"><span data-stu-id="7a5d7-112">Category</span></span>

<span data-ttu-id="7a5d7-113">Principali librerie .NET</span><span class="sxs-lookup"><span data-stu-id="7a5d7-113">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7a5d7-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="7a5d7-114">Affected APIs</span></span>

- <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)`

-->
