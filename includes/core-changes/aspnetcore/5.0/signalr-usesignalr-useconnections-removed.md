---
ms.openlocfilehash: 329ef39c7626ecd743577f336a4c8cd4a38fb082
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291664"
---
### <a name="signalr-usesignalr-and-useconnections-methods-removed"></a><span data-ttu-id="3b23c-101">SignalR: metodi UseSignalR e UseConnections rimossi</span><span class="sxs-lookup"><span data-stu-id="3b23c-101">SignalR: UseSignalR and UseConnections methods removed</span></span>

<span data-ttu-id="3b23c-102">In ASP.NET Core 3.0, SignalR ha adottato il routing degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="3b23c-102">In ASP.NET Core 3.0, SignalR adopted endpoint routing.</span></span> <span data-ttu-id="3b23c-103">Come parte di tale <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A> <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A>modifica, i metodi , e alcuni metodi correlati sono stati contrassegnati come obsoleti.</span><span class="sxs-lookup"><span data-stu-id="3b23c-103">As part of that change, the <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A>, <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A>, and some related methods were marked as obsolete.</span></span> <span data-ttu-id="3b23c-104">In ASP.NET Core 5.0, tali metodi obsoleti sono stati rimossi.</span><span class="sxs-lookup"><span data-stu-id="3b23c-104">In ASP.NET Core 5.0, those obsolete methods were removed.</span></span> <span data-ttu-id="3b23c-105">Per l'elenco completo dei metodi, vedere [API interessate](#affected-apis).</span><span class="sxs-lookup"><span data-stu-id="3b23c-105">For the full list of methods, see [Affected APIs](#affected-apis).</span></span>

<span data-ttu-id="3b23c-106">Per una discussione su questo problema, vedere [dotnet/aspnetcore-20082](https://github.com/dotnet/aspnetcore/issues/20082).</span><span class="sxs-lookup"><span data-stu-id="3b23c-106">For discussion on this issue, see [dotnet/aspnetcore#20082](https://github.com/dotnet/aspnetcore/issues/20082).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3b23c-107">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="3b23c-107">Version introduced</span></span>

<span data-ttu-id="3b23c-108">5.0 Anteprima 3</span><span class="sxs-lookup"><span data-stu-id="3b23c-108">5.0 Preview 3</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="3b23c-109">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="3b23c-109">Old behavior</span></span>

<span data-ttu-id="3b23c-110">Gli hub SignalR e i gestori di connessione `UseSignalR` possono `UseConnections` essere registrati nella pipeline middleware usando i metodi or .</span><span class="sxs-lookup"><span data-stu-id="3b23c-110">SignalR hubs and connection handlers could be registered in the middleware pipeline using the `UseSignalR` or `UseConnections` methods.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="3b23c-111">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="3b23c-111">New behavior</span></span>

<span data-ttu-id="3b23c-112">Gli hub e i gestori di <xref:Microsoft.AspNetCore.Builder.EndpointRoutingApplicationBuilderExtensions.UseEndpoints%2A> connessione <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A> <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A> SignalR <xref:Microsoft.AspNetCore.Routing.IEndpointRouteBuilder>devono essere registrati all'interno utilizzando i metodi di estensione e su .</span><span class="sxs-lookup"><span data-stu-id="3b23c-112">SignalR hubs and connection handlers should be registered within <xref:Microsoft.AspNetCore.Builder.EndpointRoutingApplicationBuilderExtensions.UseEndpoints%2A> using the <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A> and <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A> extension methods on <xref:Microsoft.AspNetCore.Routing.IEndpointRouteBuilder>.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="3b23c-113">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="3b23c-113">Reason for change</span></span>

<span data-ttu-id="3b23c-114">I metodi precedenti avevano una logica di routing personalizzata che non interagiva con altri componenti di routing in ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="3b23c-114">The old methods had custom routing logic that didn't interact with other routing components in ASP.NET Core.</span></span> <span data-ttu-id="3b23c-115">In ASP.NET Core 3.0 è stato introdotto un nuovo sistema di routing generico, denominato routing degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="3b23c-115">In ASP.NET Core 3.0, a new general-purpose routing system, called endpoint routing, was introduced.</span></span> <span data-ttu-id="3b23c-116">Il routing degli endpoint ha consentito a SignalR di interagire con altri componenti di routing.</span><span class="sxs-lookup"><span data-stu-id="3b23c-116">Endpoint routing enabled SignalR to interact with other routing components.</span></span> <span data-ttu-id="3b23c-117">Il passaggio a questo modello consente agli utenti di sfruttare appieno i vantaggi del routing degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="3b23c-117">Switching to this model allows users to realize the full benefits of endpoint routing.</span></span> <span data-ttu-id="3b23c-118">Di conseguenza, i vecchi metodi sono stati rimossi.</span><span class="sxs-lookup"><span data-stu-id="3b23c-118">Consequently, the old methods have been removed.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3b23c-119">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="3b23c-119">Recommended action</span></span>

<span data-ttu-id="3b23c-120">Rimuovere il `UseSignalR` codice `UseConnections` che chiama `Startup.Configure` o dal metodo del progetto.</span><span class="sxs-lookup"><span data-stu-id="3b23c-120">Remove code that calls `UseSignalR` or `UseConnections` from your project's `Startup.Configure` method.</span></span> <span data-ttu-id="3b23c-121">Sostituirlo con `MapHub` chiamate `MapConnectionHandler`a o , rispettivamente, `UseEndpoints`all'interno del corpo di una chiamata a .</span><span class="sxs-lookup"><span data-stu-id="3b23c-121">Replace it with calls to `MapHub` or `MapConnectionHandler`, respectively, within the body of a call to `UseEndpoints`.</span></span> <span data-ttu-id="3b23c-122">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3b23c-122">For example:</span></span>

<span data-ttu-id="3b23c-123">**Vecchio codice:**</span><span class="sxs-lookup"><span data-stu-id="3b23c-123">**Old code:**</span></span>

```csharp
app.UseSignalR(routes =>
{
    routes.MapHub<SomeHub>("/path");
});
```

<span data-ttu-id="3b23c-124">**Nuovo codice:**</span><span class="sxs-lookup"><span data-stu-id="3b23c-124">**New code:**</span></span>

```csharp
app.UseEndpoints(endpoints =>
{
    endpoints.MapHub<SomeHub>("/path");
});
```

<span data-ttu-id="3b23c-125">In generale, `MapHub` le `MapConnectionHandler` chiamate precedenti possono essere `UseSignalR` trasferite direttamente dal corpo di e `UseConnections` a `UseEndpoints` con un cambiamento poco o nessun a necessità.</span><span class="sxs-lookup"><span data-stu-id="3b23c-125">In general, your previous `MapHub` and `MapConnectionHandler` calls can be transferred directly from the body of `UseSignalR` and `UseConnections` to `UseEndpoints` with little-to-no change needed.</span></span>

#### <a name="category"></a><span data-ttu-id="3b23c-126">Category</span><span class="sxs-lookup"><span data-stu-id="3b23c-126">Category</span></span>

<span data-ttu-id="3b23c-127">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3b23c-127">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3b23c-128">API interessate</span><span class="sxs-lookup"><span data-stu-id="3b23c-128">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnections%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections`
- `Overload:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR`
- `Overload:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnections`
- `Overload:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler`
- `Overload:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub`

-->
