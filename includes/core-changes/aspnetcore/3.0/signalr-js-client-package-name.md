---
ms.openlocfilehash: f202b39f1a45f740625827be25e72df0e403d605
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75902061"
---
### <a name="signalr-javascript-client-package-name-changed"></a><span data-ttu-id="e6e8f-101">SignalR: nome del pacchetto client JavaScript modificato</span><span class="sxs-lookup"><span data-stu-id="e6e8f-101">SignalR: JavaScript client package name changed</span></span>

<span data-ttu-id="e6e8f-102">In ASP.NET Core 3.0 Preview 7, il nome `@aspnet/signalr` del `@microsoft/signalr`pacchetto client JavaScript SignalR è stato modificato da in .</span><span class="sxs-lookup"><span data-stu-id="e6e8f-102">In ASP.NET Core 3.0 Preview 7, the SignalR JavaScript client package name changed from `@aspnet/signalr` to `@microsoft/signalr`.</span></span> <span data-ttu-id="e6e8f-103">The name change reflects the fact that SignalR is useful in more than just ASP.NET Core apps, thanks to the Azure SignalR Service.</span><span class="sxs-lookup"><span data-stu-id="e6e8f-103">The name change reflects the fact that SignalR is useful in more than just ASP.NET Core apps, thanks to the Azure SignalR Service.</span></span>

<span data-ttu-id="e6e8f-104">Per rispondere a questa modifica, modificare i `require` riferimenti nei file `import` *package.json,* nelle istruzioni e nelle istruzioni ECMAScript.</span><span class="sxs-lookup"><span data-stu-id="e6e8f-104">To react to this change, change references in your *package.json* files, `require` statements, and ECMAScript `import` statements.</span></span> <span data-ttu-id="e6e8f-105">Nessuna API cambierà come parte di questa ridenominazione.</span><span class="sxs-lookup"><span data-stu-id="e6e8f-105">No API will change as part of this rename.</span></span>

<span data-ttu-id="e6e8f-106">Per una discussione, vedere [dotnet/aspnetcore-11637](https://github.com/dotnet/aspnetcore/issues/11637).</span><span class="sxs-lookup"><span data-stu-id="e6e8f-106">For discussion, see [dotnet/aspnetcore#11637](https://github.com/dotnet/aspnetcore/issues/11637).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e6e8f-107">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="e6e8f-107">Version introduced</span></span>

<span data-ttu-id="e6e8f-108">3.0</span><span class="sxs-lookup"><span data-stu-id="e6e8f-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="e6e8f-109">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="e6e8f-109">Old behavior</span></span>

<span data-ttu-id="e6e8f-110">Il pacchetto client `@aspnet/signalr`è denominato .</span><span class="sxs-lookup"><span data-stu-id="e6e8f-110">The client package was named `@aspnet/signalr`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="e6e8f-111">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="e6e8f-111">New behavior</span></span>

<span data-ttu-id="e6e8f-112">Il pacchetto client `@microsoft/signalr`è denominato .</span><span class="sxs-lookup"><span data-stu-id="e6e8f-112">The client package is named `@microsoft/signalr`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="e6e8f-113">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="e6e8f-113">Reason for change</span></span>

<span data-ttu-id="e6e8f-114">La modifica del nome chiarisce che SignalR è utile oltre ASP.NET app Core, grazie al servizio SignalR di Azure.The name change chiaris that SignalR is useful beyond ASP.NET Core apps, thanks to the Azure SignalR Service.</span><span class="sxs-lookup"><span data-stu-id="e6e8f-114">The name change clarifies that SignalR is useful beyond ASP.NET Core apps, thanks to the Azure SignalR Service.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e6e8f-115">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="e6e8f-115">Recommended action</span></span>

<span data-ttu-id="e6e8f-116">Passare al nuovo `@microsoft/signalr`pacchetto .</span><span class="sxs-lookup"><span data-stu-id="e6e8f-116">Switch to the new package `@microsoft/signalr`.</span></span>

#### <a name="category"></a><span data-ttu-id="e6e8f-117">Category</span><span class="sxs-lookup"><span data-stu-id="e6e8f-117">Category</span></span>

<span data-ttu-id="e6e8f-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e6e8f-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e6e8f-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="e6e8f-119">Affected APIs</span></span>

<span data-ttu-id="e6e8f-120">nessuno</span><span class="sxs-lookup"><span data-stu-id="e6e8f-120">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
