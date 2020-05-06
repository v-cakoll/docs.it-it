---
ms.openlocfilehash: 80d4bbbfe52ab9685d7ca54f21b80d4b1773da22
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859630"
---
### <a name="webclientcancelasync-doesnt-always-cancel-immediately"></a><span data-ttu-id="b231a-101">WebClient. CancelAsync non viene sempre annullato immediatamente</span><span class="sxs-lookup"><span data-stu-id="b231a-101">WebClient.CancelAsync doesn't always cancel immediately</span></span>

<span data-ttu-id="b231a-102">A partire da .NET Core 2,0, <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> la chiamata a non annulla la richiesta immediatamente se la risposta è stata avviata per il recupero.</span><span class="sxs-lookup"><span data-stu-id="b231a-102">Starting in .NET Core 2.0, calling <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> doesn't cancel the request immediately if the response has started to fetch.</span></span>

#### <a name="change-description"></a><span data-ttu-id="b231a-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="b231a-103">Change description</span></span>

<span data-ttu-id="b231a-104">In precedenza, <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> chiamando immediatamente la richiesta è stata annullata.</span><span class="sxs-lookup"><span data-stu-id="b231a-104">Previously, calling <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> canceled the request immediately.</span></span> <span data-ttu-id="b231a-105">A partire da .NET Core 2,0, <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> la chiamata a Annulla la richiesta immediatamente solo se la risposta non ha iniziato a recuperare.</span><span class="sxs-lookup"><span data-stu-id="b231a-105">Starting in .NET Core 2.0, calling <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> cancels the request immediately only if the response hasn't started fetching.</span></span> <span data-ttu-id="b231a-106">Se la risposta ha iniziato a recuperare, la richiesta viene annullata solo dopo la lettura di una risposta completa.</span><span class="sxs-lookup"><span data-stu-id="b231a-106">If the response has started to fetch, the request is cancelled only after a complete response is read.</span></span>

<span data-ttu-id="b231a-107">Questa modifica è stata implementata <xref:System.Net.WebClient> perché l'API è deprecata a <xref:System.Net.Http.HttpClient>favore di.</span><span class="sxs-lookup"><span data-stu-id="b231a-107">This change was implemented because the <xref:System.Net.WebClient> API is deprecated in favor of <xref:System.Net.Http.HttpClient>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b231a-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="b231a-108">Version introduced</span></span>

<span data-ttu-id="b231a-109">2.0</span><span class="sxs-lookup"><span data-stu-id="b231a-109">2.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b231a-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="b231a-110">Recommended action</span></span>

<span data-ttu-id="b231a-111">Utilizzare la <xref:System.Net.Http.HttpClient?displayProperty=fullName> classe anziché <xref:System.Net.WebClient?displayProperty=fullName>, che è deprecata.</span><span class="sxs-lookup"><span data-stu-id="b231a-111">Use the <xref:System.Net.Http.HttpClient?displayProperty=fullName> class instead of <xref:System.Net.WebClient?displayProperty=fullName>, which is deprecated.</span></span>

#### <a name="category"></a><span data-ttu-id="b231a-112">Categoria</span><span class="sxs-lookup"><span data-stu-id="b231a-112">Category</span></span>

<span data-ttu-id="b231a-113">Rete</span><span class="sxs-lookup"><span data-stu-id="b231a-113">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b231a-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="b231a-114">Affected APIs</span></span>

- <xref:System.Net.WebClient.CancelAsync?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Net.WebClient.CancelAsync`

-->
