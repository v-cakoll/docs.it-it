---
ms.openlocfilehash: 2a65caedea2af65796267aa145e275ebff814bf8
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393943"
---
### <a name="signalr-usesignalr-and-useconnections-methods-marked-obsolete"></a><span data-ttu-id="dbff5-101">SignalR: Metodi UseSignalR e UseConnections contrassegnati come obsoleti</span><span class="sxs-lookup"><span data-stu-id="dbff5-101">SignalR: UseSignalR and UseConnections methods marked obsolete</span></span>

<span data-ttu-id="dbff5-102">I metodi `UseConnections` e `UseSignalR` e le classi `ConnectionsRouteBuilder` e `HubRouteBuilder` sono contrassegnati come obsoleti in ASP.NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="dbff5-102">The methods `UseConnections` and `UseSignalR` and the classes `ConnectionsRouteBuilder` and `HubRouteBuilder` are marked as obsolete in ASP.NET Core 3.0.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="dbff5-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="dbff5-103">Version introduced</span></span>

<span data-ttu-id="dbff5-104">3.0</span><span class="sxs-lookup"><span data-stu-id="dbff5-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="dbff5-105">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="dbff5-105">Old behavior</span></span>

<span data-ttu-id="dbff5-106">Il routing dell'hub SignalR è stato configurato con `UseSignalR` o `UseConnections`.</span><span class="sxs-lookup"><span data-stu-id="dbff5-106">SignalR hub routing was configured using `UseSignalR` or `UseConnections`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="dbff5-107">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="dbff5-107">New behavior</span></span>

<span data-ttu-id="dbff5-108">Il modo precedente per configurare il routing è stato obsoleto e sostituito con il routing degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="dbff5-108">The old way of configuring routing has been obsoleted and replaced with endpoint routing.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="dbff5-109">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="dbff5-109">Reason for change</span></span>

<span data-ttu-id="dbff5-110">Il middleware è stato spostato nel nuovo sistema di routing degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="dbff5-110">Middleware is being moved to the new endpoint routing system.</span></span> <span data-ttu-id="dbff5-111">Il modo precedente per aggiungere il middleware è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="dbff5-111">The old way of adding middleware is being obsoleted.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="dbff5-112">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="dbff5-112">Recommended action</span></span>

<span data-ttu-id="dbff5-113">Sostituire `UseSignalR` con `UseEndpoints`:</span><span class="sxs-lookup"><span data-stu-id="dbff5-113">Replace `UseSignalR` with `UseEndpoints`:</span></span>

<span data-ttu-id="dbff5-114">**Codice precedente:**</span><span class="sxs-lookup"><span data-stu-id="dbff5-114">**Old code:**</span></span>

```csharp
app.UseSignalR(routes =>
{
    routes.MapHub<SomeHub>("/path");
});
```

<span data-ttu-id="dbff5-115">**Nuovo codice:**</span><span class="sxs-lookup"><span data-stu-id="dbff5-115">**New code:**</span></span>

```csharp
app.UseEndpoints(endpoints =>
{
    endpoints.MapHub<SomeHub>("/path");
});
```

#### <a name="category"></a><span data-ttu-id="dbff5-116">Category</span><span class="sxs-lookup"><span data-stu-id="dbff5-116">Category</span></span>

<span data-ttu-id="dbff5-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="dbff5-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="dbff5-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="dbff5-118">Affected APIs</span></span>

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
