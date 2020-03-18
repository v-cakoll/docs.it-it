---
ms.openlocfilehash: de06825f1031d05bc83183a83bae165e2f9512ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901807"
---
### <a name="signalr-hubconnection-resetsendping-and-resettimeout-methods-removed"></a><span data-ttu-id="85f58-101">SignalR: metodi ResetSendPing e ResetTimeout rimossi</span><span class="sxs-lookup"><span data-stu-id="85f58-101">SignalR: HubConnection ResetSendPing and ResetTimeout methods removed</span></span>

<span data-ttu-id="85f58-102">I `ResetSendPing` `ResetTimeout` metodi e sono stati `HubConnection` rimossi dall'API SignalR.</span><span class="sxs-lookup"><span data-stu-id="85f58-102">The `ResetSendPing` and `ResetTimeout` methods were removed from the SignalR `HubConnection` API.</span></span> <span data-ttu-id="85f58-103">Questi metodi sono stati originariamente destinati solo per uso interno, ma sono stati resi pubblici in ASP.NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="85f58-103">These methods were originally intended only for internal use but were made public in ASP.NET Core 2.2.</span></span> <span data-ttu-id="85f58-104">Questi metodi non saranno disponibili a partire dalla versione di ASP.NET Core 3.0 Preview 4.</span><span class="sxs-lookup"><span data-stu-id="85f58-104">These methods won't be available starting in the ASP.NET Core 3.0 Preview 4 release.</span></span> <span data-ttu-id="85f58-105">Per una discussione, vedere [dotnet/aspnetcore-8543](https://github.com/dotnet/aspnetcore/issues/8543).</span><span class="sxs-lookup"><span data-stu-id="85f58-105">For discussion, see [dotnet/aspnetcore#8543](https://github.com/dotnet/aspnetcore/issues/8543).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="85f58-106">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="85f58-106">Version introduced</span></span>

<span data-ttu-id="85f58-107">3.0</span><span class="sxs-lookup"><span data-stu-id="85f58-107">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="85f58-108">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="85f58-108">Old behavior</span></span>

<span data-ttu-id="85f58-109">Api disponibili.</span><span class="sxs-lookup"><span data-stu-id="85f58-109">APIs were available.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="85f58-110">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="85f58-110">New behavior</span></span>

<span data-ttu-id="85f58-111">Le API vengono rimosse.</span><span class="sxs-lookup"><span data-stu-id="85f58-111">APIs are removed.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="85f58-112">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="85f58-112">Reason for change</span></span>

<span data-ttu-id="85f58-113">Questi metodi sono stati originariamente destinati solo per uso interno, ma sono stati resi pubblici in ASP.NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="85f58-113">These methods were originally intended only for internal use but were made public in ASP.NET Core 2.2.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="85f58-114">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="85f58-114">Recommended action</span></span>

<span data-ttu-id="85f58-115">Non utilizzare questi metodi.</span><span class="sxs-lookup"><span data-stu-id="85f58-115">Don't use these methods.</span></span>

#### <a name="category"></a><span data-ttu-id="85f58-116">Category</span><span class="sxs-lookup"><span data-stu-id="85f58-116">Category</span></span>

<span data-ttu-id="85f58-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="85f58-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="85f58-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="85f58-118">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetSendPing?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetTimeout?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetSendPing`
- `M:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetTimeout`

-->
