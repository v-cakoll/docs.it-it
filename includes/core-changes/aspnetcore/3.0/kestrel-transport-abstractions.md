---
ms.openlocfilehash: fb23418816abcae125106c93b339a546aa9bc2ee
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721134"
---
### <a name="kestrel-transport-abstractions-removed-and-made-public"></a><span data-ttu-id="63f27-101">Gheppio: astrazioni del trasporto rimosse e rese pubbliche</span><span class="sxs-lookup"><span data-stu-id="63f27-101">Kestrel: Transport abstractions removed and made public</span></span>

<span data-ttu-id="63f27-102">Come parte del passaggio dalle API "pubternal", le API del livello di trasporto di gheppio sono esposte come interfaccia pubblica nella `Microsoft.AspNetCore.Connections.Abstractions` libreria.</span><span class="sxs-lookup"><span data-stu-id="63f27-102">As part of moving away from "pubternal" APIs, the Kestrel transport layer APIs are exposed as a public interface in the `Microsoft.AspNetCore.Connections.Abstractions` library.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="63f27-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="63f27-103">Version introduced</span></span>

<span data-ttu-id="63f27-104">3.0</span><span class="sxs-lookup"><span data-stu-id="63f27-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="63f27-105">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="63f27-105">Old behavior</span></span>

- <span data-ttu-id="63f27-106">Le astrazioni relative al trasporto erano disponibili nella `Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions` libreria.</span><span class="sxs-lookup"><span data-stu-id="63f27-106">Transport-related abstractions were available in the `Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions` library.</span></span>
- <span data-ttu-id="63f27-107">La `ListenOptions.NoDelay` proprietà era disponibile.</span><span class="sxs-lookup"><span data-stu-id="63f27-107">The `ListenOptions.NoDelay` property was available.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="63f27-108">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="63f27-108">New behavior</span></span>

- <span data-ttu-id="63f27-109">L' `IConnectionListener` interfaccia è stata introdotta nella `Microsoft.AspNetCore.Connections.Abstractions` libreria per esporre le funzionalità più usate dalla `...Transport.Abstractions` libreria.</span><span class="sxs-lookup"><span data-stu-id="63f27-109">The `IConnectionListener` interface was introduced in the `Microsoft.AspNetCore.Connections.Abstractions` library to expose the most used functionality from the `...Transport.Abstractions` library.</span></span>
- <span data-ttu-id="63f27-110">`NoDelay`È ora disponibile nelle opzioni di trasporto ( `LibuvTransportOptions` e `SocketTransportOptions` ).</span><span class="sxs-lookup"><span data-stu-id="63f27-110">The `NoDelay` is now available in transport options (`LibuvTransportOptions` and `SocketTransportOptions`).</span></span>
- <span data-ttu-id="63f27-111">`SchedulingMode`non è più disponibile.</span><span class="sxs-lookup"><span data-stu-id="63f27-111">`SchedulingMode` is no longer available.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="63f27-112">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="63f27-112">Reason for change</span></span>

<span data-ttu-id="63f27-113">ASP.NET Core 3,0 è stato rimosso dalle API "pubternal".</span><span class="sxs-lookup"><span data-stu-id="63f27-113">ASP.NET Core 3.0 has moved away from "pubternal" APIs.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="63f27-114">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="63f27-114">Recommended action</span></span>

#### <a name="category"></a><span data-ttu-id="63f27-115">Category</span><span class="sxs-lookup"><span data-stu-id="63f27-115">Category</span></span>

<span data-ttu-id="63f27-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="63f27-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="63f27-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="63f27-117">Affected APIs</span></span>

<span data-ttu-id="63f27-118">Nessuno</span><span class="sxs-lookup"><span data-stu-id="63f27-118">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
