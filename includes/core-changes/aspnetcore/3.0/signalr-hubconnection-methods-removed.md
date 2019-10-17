---
ms.openlocfilehash: a56c5fc32b5fd274d5da0d9b295918f5ea3b345e
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393990"
---
### <a name="signalr-hubconnection-resetsendping-and-resettimeout-methods-removed"></a><span data-ttu-id="5cb3b-101">SignalR: HubConnection ResetSendPing e ResetTimeout metodi rimossi</span><span class="sxs-lookup"><span data-stu-id="5cb3b-101">SignalR: HubConnection ResetSendPing and ResetTimeout methods removed</span></span>

<span data-ttu-id="5cb3b-102">I metodi `ResetSendPing` e `ResetTimeout` sono stati rimossi dall'API SignalR `HubConnection`.</span><span class="sxs-lookup"><span data-stu-id="5cb3b-102">The `ResetSendPing` and `ResetTimeout` methods were removed from the SignalR `HubConnection` API.</span></span> <span data-ttu-id="5cb3b-103">Questi metodi sono stati originariamente progettati solo per uso interno, ma sono stati resi pubblici in ASP.NET Core 2,2.</span><span class="sxs-lookup"><span data-stu-id="5cb3b-103">These methods were originally intended only for internal use but were made public in ASP.NET Core 2.2.</span></span> <span data-ttu-id="5cb3b-104">Questi metodi non saranno disponibili a partire dalla versione di ASP.NET Core 3,0 Preview 4.</span><span class="sxs-lookup"><span data-stu-id="5cb3b-104">These methods won't be available starting in the ASP.NET Core 3.0 Preview 4 release.</span></span> <span data-ttu-id="5cb3b-105">Per informazioni, vedere [ASPNET/AspNetCore # 8543](https://github.com/aspnet/AspNetCore/issues/8543).</span><span class="sxs-lookup"><span data-stu-id="5cb3b-105">For discussion, see [aspnet/AspNetCore#8543](https://github.com/aspnet/AspNetCore/issues/8543).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="5cb3b-106">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="5cb3b-106">Version introduced</span></span>

<span data-ttu-id="5cb3b-107">3.0</span><span class="sxs-lookup"><span data-stu-id="5cb3b-107">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="5cb3b-108">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="5cb3b-108">Old behavior</span></span>

<span data-ttu-id="5cb3b-109">API disponibili.</span><span class="sxs-lookup"><span data-stu-id="5cb3b-109">APIs were available.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="5cb3b-110">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="5cb3b-110">New behavior</span></span>

<span data-ttu-id="5cb3b-111">Le API vengono rimosse.</span><span class="sxs-lookup"><span data-stu-id="5cb3b-111">APIs are removed.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="5cb3b-112">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="5cb3b-112">Reason for change</span></span>

<span data-ttu-id="5cb3b-113">Questi metodi sono stati originariamente progettati solo per uso interno, ma sono stati resi pubblici in ASP.NET Core 2,2.</span><span class="sxs-lookup"><span data-stu-id="5cb3b-113">These methods were originally intended only for internal use but were made public in ASP.NET Core 2.2.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="5cb3b-114">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="5cb3b-114">Recommended action</span></span>

<span data-ttu-id="5cb3b-115">Non usare questi metodi.</span><span class="sxs-lookup"><span data-stu-id="5cb3b-115">Don't use these methods.</span></span>

#### <a name="category"></a><span data-ttu-id="5cb3b-116">Category</span><span class="sxs-lookup"><span data-stu-id="5cb3b-116">Category</span></span>

<span data-ttu-id="5cb3b-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5cb3b-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5cb3b-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="5cb3b-118">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetSendPing?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetTimeout?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetSendPing`
- `M:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetTimeout`

-->
