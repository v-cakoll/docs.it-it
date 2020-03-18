---
ms.openlocfilehash: f95c3916f4da8164cf927344f60f2845f04ddc5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394413"
---
### <a name="kestrel-transport-abstractions-removed-and-made-public"></a><span data-ttu-id="fbd5f-101">Kestrel: Le astrazioni dei trasporti sono state rimosse e rese pubbliche</span><span class="sxs-lookup"><span data-stu-id="fbd5f-101">Kestrel: Transport abstractions removed and made public</span></span>

<span data-ttu-id="fbd5f-102">Come parte dello spostamento dalle API "pubternal", le API del livello di trasporto Kestrel vengono esposte come interfaccia pubblica nella `Microsoft.AspNetCore.Connections.Abstractions` libreria.</span><span class="sxs-lookup"><span data-stu-id="fbd5f-102">As part of moving away from "pubternal" APIs, the Kestrel transport layer APIs are exposed as a public interface in the `Microsoft.AspNetCore.Connections.Abstractions` library.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="fbd5f-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="fbd5f-103">Version introduced</span></span>

<span data-ttu-id="fbd5f-104">3.0</span><span class="sxs-lookup"><span data-stu-id="fbd5f-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="fbd5f-105">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="fbd5f-105">Old behavior</span></span>

- <span data-ttu-id="fbd5f-106">Le astrazioni relative al trasporto `Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions` erano disponibili nella libreria.</span><span class="sxs-lookup"><span data-stu-id="fbd5f-106">Transport-related abstractions were available in the `Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions` library.</span></span>
- <span data-ttu-id="fbd5f-107">La `ListenOptions.NoDelay` struttura era disponibile.</span><span class="sxs-lookup"><span data-stu-id="fbd5f-107">The `ListenOptions.NoDelay` property was available.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="fbd5f-108">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="fbd5f-108">New behavior</span></span>

- <span data-ttu-id="fbd5f-109">L'interfaccia `IConnectionListener` è `Microsoft.AspNetCore.Connections.Abstractions` stata introdotta nella libreria `...Transport.Abstractions` per esporre le funzionalità più utilizzate dalla libreria.</span><span class="sxs-lookup"><span data-stu-id="fbd5f-109">The `IConnectionListener` interface was introduced in the `Microsoft.AspNetCore.Connections.Abstractions` library to expose the most used functionality from the `...Transport.Abstractions` library.</span></span>
- <span data-ttu-id="fbd5f-110">L'oggetto `NoDelay` è ora`LibuvTransportOptions` disponibile `SocketTransportOptions`nelle opzioni di trasporto ( e ).</span><span class="sxs-lookup"><span data-stu-id="fbd5f-110">The `NoDelay` is now available in transport options (`LibuvTransportOptions` and `SocketTransportOptions`).</span></span>
- <span data-ttu-id="fbd5f-111">`SchedulingMode`non è più disponibile.</span><span class="sxs-lookup"><span data-stu-id="fbd5f-111">`SchedulingMode` is no longer available.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="fbd5f-112">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="fbd5f-112">Reason for change</span></span>

<span data-ttu-id="fbd5f-113">ASP.NET Core 3.0 si è allontanato dalle API "pubternal".</span><span class="sxs-lookup"><span data-stu-id="fbd5f-113">ASP.NET Core 3.0 has moved away from "pubternal" APIs.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="fbd5f-114">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="fbd5f-114">Recommended action</span></span>

#### <a name="category"></a><span data-ttu-id="fbd5f-115">Category</span><span class="sxs-lookup"><span data-stu-id="fbd5f-115">Category</span></span>

<span data-ttu-id="fbd5f-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="fbd5f-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="fbd5f-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="fbd5f-117">Affected APIs</span></span>

<span data-ttu-id="fbd5f-118">nessuno</span><span class="sxs-lookup"><span data-stu-id="fbd5f-118">None</span></span>

<!-- 

### Affected APIs

Not detectable via API analysis

-->
