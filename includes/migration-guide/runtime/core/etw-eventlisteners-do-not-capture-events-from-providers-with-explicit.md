---
ms.openlocfilehash: 7d50962b518c15875a5f1a82f5b89ab87a1db02e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620234"
---
### <a name="etw-eventlisteners-do-not-capture-events-from-providers-with-explicit-keywords-like-the-tpl-provider"></a><span data-ttu-id="a0429-101">Gli EventListener ETW non acquisiscono gli eventi dai provider con parole chiave esplicite (come il provider TPL)</span><span class="sxs-lookup"><span data-stu-id="a0429-101">ETW EventListeners do not capture events from providers with explicit keywords (like the TPL provider)</span></span>

#### <a name="details"></a><span data-ttu-id="a0429-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a0429-102">Details</span></span>

<span data-ttu-id="a0429-103">Gli EventListener ETW con una maschera di parole chiave vuota non acquisiscono correttamente gli eventi dai provider con parole chiave esplicite.</span><span class="sxs-lookup"><span data-stu-id="a0429-103">ETW EventListeners with a blank keyword mask do not properly capture events from providers with explicit keywords.</span></span> <span data-ttu-id="a0429-104">In .NET Framework 4.5, il provider TPL ha iniziato a fornire parole chiave esplicite e ha causato questo problema.</span><span class="sxs-lookup"><span data-stu-id="a0429-104">In the .NET Framework 4.5, the TPL provider began providing explicit keywords and triggered this issue.</span></span> <span data-ttu-id="a0429-105">In .NET Framework 4.6, gli EventListener sono stati aggiornati e non presentano più questo problema.</span><span class="sxs-lookup"><span data-stu-id="a0429-105">In the .NET Framework 4.6, EventListeners have been updated to no longer have this issue.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a0429-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="a0429-106">Suggestion</span></span>

<span data-ttu-id="a0429-107">Per risolvere questo problema, sostituire le chiamate a <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)> con chiamate all'overload EnableEvents che specifica in modo esplicito la maschera &quot;qualsiasi parola chiave&quot; da usare: <code>EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))</code>. In alternativa, questo problema è stato corretto in .NET Framework 4.6 e può essere risolto eseguendo l'aggiornamento a tale versione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a0429-107">To work around this problem, replace calls to <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)> with calls to the EnableEvents overload that explicitly specifies the &quot;any keywords&quot; mask to use: <code>EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))</code>.Alternatively, this issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="a0429-108">Nome</span><span class="sxs-lookup"><span data-stu-id="a0429-108">Name</span></span>    | <span data-ttu-id="a0429-109">Valore</span><span class="sxs-lookup"><span data-stu-id="a0429-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a0429-110">Scope</span><span class="sxs-lookup"><span data-stu-id="a0429-110">Scope</span></span>   |<span data-ttu-id="a0429-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a0429-111">Edge</span></span>|
|<span data-ttu-id="a0429-112">Version</span><span class="sxs-lookup"><span data-stu-id="a0429-112">Version</span></span>|<span data-ttu-id="a0429-113">4.5</span><span class="sxs-lookup"><span data-stu-id="a0429-113">4.5</span></span>|
|<span data-ttu-id="a0429-114">Type</span><span class="sxs-lookup"><span data-stu-id="a0429-114">Type</span></span>|<span data-ttu-id="a0429-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="a0429-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a0429-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="a0429-116">Affected APIs</span></span>

-<xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType></li></ul>|
