---
ms.openlocfilehash: f7dcf9c4c3dc7ea536ddc847769a1a30f1298bb2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617214"
---
### <a name="systemuriiswellformeduristring-method-returns-false-for-relative-uris-with-a-colon-char-in-first-segment"></a><span data-ttu-id="efaaf-101">Il metodo System.Uri.IsWellFormedUriString restituisce false per gli URI relativi con un carattere due punti nel primo segmento</span><span class="sxs-lookup"><span data-stu-id="efaaf-101">System.Uri.IsWellFormedUriString method returns false for relative URIs with a colon char in first segment</span></span>

#### <a name="details"></a><span data-ttu-id="efaaf-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="efaaf-102">Details</span></span>

<span data-ttu-id="efaaf-103">A partire da .NET Framework 4.5, <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)> tratterà gli URI relativi con `:` nella primo segmento come non ben formati.</span><span class="sxs-lookup"><span data-stu-id="efaaf-103">Beginning with the .NET Framework 4.5, <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)> will treat relative URIs with a `:` in their first segment as not well formed.</span></span> <span data-ttu-id="efaaf-104">Si tratta di una modifica rispetto al comportamento di <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName> in .NET Framework 4.0, introdotta per conformarsi a RFC3986.</span><span class="sxs-lookup"><span data-stu-id="efaaf-104">This is a change from <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName> behavior in the .NET Framework 4.0 that was made to conform to RFC3986.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="efaaf-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="efaaf-105">Suggestion</span></span>

<span data-ttu-id="efaaf-106">Questa modifica (come molte altre modifiche relative agli URI) influirà solo sulle applicazioni destinate a .NET Framework 4.5 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="efaaf-106">This change (like many other URI changes) will only affect applications targeting the .NET Framework 4.5 (or later).</span></span> <span data-ttu-id="efaaf-107">Per continuare a usare il comportamento precedente, scegliere .NET Framework 4.0 come destinazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="efaaf-107">To keep using the old behavior, target the app against the .NET Framework 4.0.</span></span> <span data-ttu-id="efaaf-108">In alternativa, analizzare l'URI prima di chiamare <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName> per cercare caratteri `:` che è possibile rimuovere ai fini della convalida, se si desidera mantenere il comportamento precedente.</span><span class="sxs-lookup"><span data-stu-id="efaaf-108">Alternatively, scan URI's prior to calling <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName> looking for `:` characters that you may want to remove for validation purposes, if the old behavior is desirable.</span></span>

| <span data-ttu-id="efaaf-109">Nome</span><span class="sxs-lookup"><span data-stu-id="efaaf-109">Name</span></span>    | <span data-ttu-id="efaaf-110">Valore</span><span class="sxs-lookup"><span data-stu-id="efaaf-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="efaaf-111">Scope</span><span class="sxs-lookup"><span data-stu-id="efaaf-111">Scope</span></span>   | <span data-ttu-id="efaaf-112">Minorenne</span><span class="sxs-lookup"><span data-stu-id="efaaf-112">Minor</span></span>       |
| <span data-ttu-id="efaaf-113">Version</span><span class="sxs-lookup"><span data-stu-id="efaaf-113">Version</span></span> | <span data-ttu-id="efaaf-114">4.5</span><span class="sxs-lookup"><span data-stu-id="efaaf-114">4.5</span></span>         |
| <span data-ttu-id="efaaf-115">Type</span><span class="sxs-lookup"><span data-stu-id="efaaf-115">Type</span></span>    | <span data-ttu-id="efaaf-116">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="efaaf-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="efaaf-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="efaaf-117">Affected APIs</span></span>

- <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=nameWithType>
