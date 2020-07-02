---
ms.openlocfilehash: a8f51dfa1c82e3b166449d2432dfe8a9b96564b9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620200"
---
### <a name="blockingcollectionlttgttrytakefromany-does-not-throw-anymore"></a><span data-ttu-id="df4b0-101">BlockingCollection&lt;T&gt;.TryTakeFromAny non genera più eccezioni</span><span class="sxs-lookup"><span data-stu-id="df4b0-101">BlockingCollection&lt;T&gt;.TryTakeFromAny does not throw anymore</span></span>

#### <a name="details"></a><span data-ttu-id="df4b0-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="df4b0-102">Details</span></span>

<span data-ttu-id="df4b0-103">Se una delle raccolte di input viene contrassegnata come completata, <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> non restituisce più -1 e <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> non genera più un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="df4b0-103">If one of the input collections is marked completed, <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> no longer returns -1 and <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> no longer throws an exception.</span></span> <span data-ttu-id="df4b0-104">Tale modifica consente di usare le raccolte quando una di esse è vuota o completata, ma l'altra contiene ancora elementi che possono essere recuperati.</span><span class="sxs-lookup"><span data-stu-id="df4b0-104">This change makes it possible to work with collections when one of the collections is either empty or completed, but the other collection still has items that can be retrieved.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="df4b0-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="df4b0-105">Suggestion</span></span>

<span data-ttu-id="df4b0-106">Se il metodo TryTakeFromAny con restituzione di -1 o con generazione di un'eccezione è stato usato per scopi di controllo di flusso in caso di completamento di una raccolta di blocco, tale codice deve ora essere modificato per usare <code>.Any(b =&gt; b.IsCompleted)</code> per rilevare tale condizione.</span><span class="sxs-lookup"><span data-stu-id="df4b0-106">If TryTakeFromAny returning -1 or TakeFromAny throwing were used for control-flow purposes in cases of a blocking collection being completed, such code should now be changed to use <code>.Any(b =&gt; b.IsCompleted)</code> to detect that condition.</span></span>

| <span data-ttu-id="df4b0-107">Nome</span><span class="sxs-lookup"><span data-stu-id="df4b0-107">Name</span></span>    | <span data-ttu-id="df4b0-108">Valore</span><span class="sxs-lookup"><span data-stu-id="df4b0-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="df4b0-109">Scope</span><span class="sxs-lookup"><span data-stu-id="df4b0-109">Scope</span></span>   |<span data-ttu-id="df4b0-110">Minorenne</span><span class="sxs-lookup"><span data-stu-id="df4b0-110">Minor</span></span>|
|<span data-ttu-id="df4b0-111">Version</span><span class="sxs-lookup"><span data-stu-id="df4b0-111">Version</span></span>|<span data-ttu-id="df4b0-112">4.5</span><span class="sxs-lookup"><span data-stu-id="df4b0-112">4.5</span></span>|
|<span data-ttu-id="df4b0-113">Type</span><span class="sxs-lookup"><span data-stu-id="df4b0-113">Type</span></span>|<span data-ttu-id="df4b0-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="df4b0-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="df4b0-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="df4b0-115">Affected APIs</span></span>

-<xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.Int32)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.TimeSpan)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.TimeSpan)?displayProperty=nameWithType></li></ul>|
