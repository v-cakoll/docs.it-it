---
ms.openlocfilehash: f95c3916f4da8164cf927344f60f2845f04ddc5c
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394413"
---
### <a name="kestrel-transport-abstractions-removed-and-made-public"></a><span data-ttu-id="072a1-101">Gheppio: astrazioni del trasporto rimosse e rese pubbliche</span><span class="sxs-lookup"><span data-stu-id="072a1-101">Kestrel: Transport abstractions removed and made public</span></span>

<span data-ttu-id="072a1-102">Come parte del passaggio dalle API "pubternal", le API del livello di trasporto di gheppio sono esposte come interfaccia pubblica nella libreria `Microsoft.AspNetCore.Connections.Abstractions`.</span><span class="sxs-lookup"><span data-stu-id="072a1-102">As part of moving away from "pubternal" APIs, the Kestrel transport layer APIs are exposed as a public interface in the `Microsoft.AspNetCore.Connections.Abstractions` library.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="072a1-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="072a1-103">Version introduced</span></span>

<span data-ttu-id="072a1-104">3.0</span><span class="sxs-lookup"><span data-stu-id="072a1-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="072a1-105">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="072a1-105">Old behavior</span></span>

- <span data-ttu-id="072a1-106">Le astrazioni relative al trasporto erano disponibili nella libreria `Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions`.</span><span class="sxs-lookup"><span data-stu-id="072a1-106">Transport-related abstractions were available in the `Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions` library.</span></span>
- <span data-ttu-id="072a1-107">La proprietà `ListenOptions.NoDelay` era disponibile.</span><span class="sxs-lookup"><span data-stu-id="072a1-107">The `ListenOptions.NoDelay` property was available.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="072a1-108">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="072a1-108">New behavior</span></span>

- <span data-ttu-id="072a1-109">L'interfaccia `IConnectionListener` è stata introdotta nella libreria `Microsoft.AspNetCore.Connections.Abstractions` per esporre le funzionalità più usate dalla libreria `...Transport.Abstractions`.</span><span class="sxs-lookup"><span data-stu-id="072a1-109">The `IConnectionListener` interface was introduced in the `Microsoft.AspNetCore.Connections.Abstractions` library to expose the most used functionality from the `...Transport.Abstractions` library.</span></span>
- <span data-ttu-id="072a1-110">Il `NoDelay` è ora disponibile nelle opzioni di trasporto (`LibuvTransportOptions` e `SocketTransportOptions`).</span><span class="sxs-lookup"><span data-stu-id="072a1-110">The `NoDelay` is now available in transport options (`LibuvTransportOptions` and `SocketTransportOptions`).</span></span>
- <span data-ttu-id="072a1-111">`SchedulingMode` non è più disponibile.</span><span class="sxs-lookup"><span data-stu-id="072a1-111">`SchedulingMode` is no longer available.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="072a1-112">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="072a1-112">Reason for change</span></span>

<span data-ttu-id="072a1-113">ASP.NET Core 3,0 è stato rimosso dalle API "pubternal".</span><span class="sxs-lookup"><span data-stu-id="072a1-113">ASP.NET Core 3.0 has moved away from "pubternal" APIs.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="072a1-114">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="072a1-114">Recommended action</span></span>

#### <a name="category"></a><span data-ttu-id="072a1-115">Category</span><span class="sxs-lookup"><span data-stu-id="072a1-115">Category</span></span>

<span data-ttu-id="072a1-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="072a1-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="072a1-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="072a1-117">Affected APIs</span></span>

<span data-ttu-id="072a1-118">Nessuno</span><span class="sxs-lookup"><span data-stu-id="072a1-118">None</span></span>

<!-- 

### Affected APIs

Not detectable via API analysis

-->
