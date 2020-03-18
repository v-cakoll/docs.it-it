---
ms.openlocfilehash: 2a65caedea2af65796267aa145e275ebff814bf8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72393943"
---
### <a name="signalr-usesignalr-and-useconnections-methods-marked-obsolete"></a><span data-ttu-id="7c497-101">SignalR: metodi UseSignalR e UseConnections contrassegnati come obsoleti</span><span class="sxs-lookup"><span data-stu-id="7c497-101">SignalR: UseSignalR and UseConnections methods marked obsolete</span></span>

<span data-ttu-id="7c497-102">I `UseConnections` metodi `UseSignalR` e `ConnectionsRouteBuilder` e `HubRouteBuilder` le classi e sono contrassegnati come obsoleti in ASP.NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="7c497-102">The methods `UseConnections` and `UseSignalR` and the classes `ConnectionsRouteBuilder` and `HubRouteBuilder` are marked as obsolete in ASP.NET Core 3.0.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7c497-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="7c497-103">Version introduced</span></span>

<span data-ttu-id="7c497-104">3.0</span><span class="sxs-lookup"><span data-stu-id="7c497-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="7c497-105">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="7c497-105">Old behavior</span></span>

<span data-ttu-id="7c497-106">Il routing dell'hub `UseSignalR` `UseConnections`SignalR è stato configurato utilizzando o .</span><span class="sxs-lookup"><span data-stu-id="7c497-106">SignalR hub routing was configured using `UseSignalR` or `UseConnections`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="7c497-107">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="7c497-107">New behavior</span></span>

<span data-ttu-id="7c497-108">Il vecchio modo di configurare il routing è stato obsoleto e sostituito con il routing endpoint.</span><span class="sxs-lookup"><span data-stu-id="7c497-108">The old way of configuring routing has been obsoleted and replaced with endpoint routing.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="7c497-109">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="7c497-109">Reason for change</span></span>

<span data-ttu-id="7c497-110">Il middleware viene spostato nel nuovo sistema di routing degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="7c497-110">Middleware is being moved to the new endpoint routing system.</span></span> <span data-ttu-id="7c497-111">Il vecchio modo di aggiungere middleware è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="7c497-111">The old way of adding middleware is being obsoleted.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7c497-112">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="7c497-112">Recommended action</span></span>

<span data-ttu-id="7c497-113">Sostituire `UseSignalR` con `UseEndpoints`:</span><span class="sxs-lookup"><span data-stu-id="7c497-113">Replace `UseSignalR` with `UseEndpoints`:</span></span>

<span data-ttu-id="7c497-114">**Vecchio codice:**</span><span class="sxs-lookup"><span data-stu-id="7c497-114">**Old code:**</span></span>

```csharp
app.UseSignalR(routes =>
{
    routes.MapHub<SomeHub>("/path");
});
```

<span data-ttu-id="7c497-115">**Nuovo codice:**</span><span class="sxs-lookup"><span data-stu-id="7c497-115">**New code:**</span></span>

```csharp
app.UseEndpoints(endpoints =>
{
    endpoints.MapHub<SomeHub>("/path");
});
```

#### <a name="category"></a><span data-ttu-id="7c497-116">Category</span><span class="sxs-lookup"><span data-stu-id="7c497-116">Category</span></span>

<span data-ttu-id="7c497-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7c497-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7c497-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="7c497-118">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections(Microsoft.AspNetCore.Builder.IApplicationBuilder,System.Action{Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder})?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR(Microsoft.AspNetCore.Builder.IApplicationBuilder,System.Action{Microsoft.AspNetCore.SignalR.HubRouteBuilder})?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder?displayProperty=fullName>

<!-- 

#### Affected APIs

- `M:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections(Microsoft.AspNetCore.Builder.IApplicationBuilder,System.Action{Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder})`
- `M:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR(Microsoft.AspNetCore.Builder.IApplicationBuilder,System.Action{Microsoft.AspNetCore.SignalR.HubRouteBuilder})`
- `T:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder`
- `T:Microsoft.AspNetCore.SignalR.HubRouteBuilder`

-->
