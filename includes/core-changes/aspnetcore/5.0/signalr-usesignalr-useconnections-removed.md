---
ms.openlocfilehash: 329ef39c7626ecd743577f336a4c8cd4a38fb082
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291664"
---
### <a name="signalr-usesignalr-and-useconnections-methods-removed"></a>SignalR: metodi UseSignalR e UseConnections rimossi

In ASP.NET Core 3.0, SignalR ha adottato il routing degli endpoint. Come parte di tale <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A> <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A>modifica, i metodi , e alcuni metodi correlati sono stati contrassegnati come obsoleti. In ASP.NET Core 5.0, tali metodi obsoleti sono stati rimossi. Per l'elenco completo dei metodi, vedere [API interessate](#affected-apis).

Per una discussione su questo problema, vedere [dotnet/aspnetcore-20082](https://github.com/dotnet/aspnetcore/issues/20082).

#### <a name="version-introduced"></a>Versione introdotta

5.0 Anteprima 3

#### <a name="old-behavior"></a>Comportamento precedente

Gli hub SignalR e i gestori di connessione `UseSignalR` possono `UseConnections` essere registrati nella pipeline middleware usando i metodi or .

#### <a name="new-behavior"></a>Nuovo comportamento

Gli hub e i gestori di <xref:Microsoft.AspNetCore.Builder.EndpointRoutingApplicationBuilderExtensions.UseEndpoints%2A> connessione <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A> <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A> SignalR <xref:Microsoft.AspNetCore.Routing.IEndpointRouteBuilder>devono essere registrati all'interno utilizzando i metodi di estensione e su .

#### <a name="reason-for-change"></a>Motivo della modifica

I metodi precedenti avevano una logica di routing personalizzata che non interagiva con altri componenti di routing in ASP.NET Core. In ASP.NET Core 3.0 è stato introdotto un nuovo sistema di routing generico, denominato routing degli endpoint. Il routing degli endpoint ha consentito a SignalR di interagire con altri componenti di routing. Il passaggio a questo modello consente agli utenti di sfruttare appieno i vantaggi del routing degli endpoint. Di conseguenza, i vecchi metodi sono stati rimossi.

#### <a name="recommended-action"></a>Azione consigliata

Rimuovere il `UseSignalR` codice `UseConnections` che chiama `Startup.Configure` o dal metodo del progetto. Sostituirlo con `MapHub` chiamate `MapConnectionHandler`a o , rispettivamente, `UseEndpoints`all'interno del corpo di una chiamata a . Ad esempio:

**Vecchio codice:**

```csharp
app.UseSignalR(routes =>
{
    routes.MapHub<SomeHub>("/path");
});
```

**Nuovo codice:**

```csharp
app.UseEndpoints(endpoints =>
{
    endpoints.MapHub<SomeHub>("/path");
});
```

In generale, `MapHub` le `MapConnectionHandler` chiamate precedenti possono essere `UseSignalR` trasferite direttamente dal corpo di e `UseConnections` a `UseEndpoints` con un cambiamento poco o nessun a necessità.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

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
