---
ms.openlocfilehash: 203d75f5858c8ff039cf579c0539efda0c5c9f02
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474378"
---
### <a name="kestrel-libuv-transport-marked-as-obsolete"></a>Gheppio: trasporto libuv contrassegnato come obsoleto

Nelle versioni precedenti di ASP.NET Core veniva utilizzato libuv come dettaglio di implementazione di come è stato eseguito l'input e l'output asincroni. In ASP.NET Core 2,0 <xref:System.Net.Sockets.Socket> è stato sviluppato un trasporto alternativo basato su. In ASP.NET Core 2,1, gheppio passa a usando il `Socket` trasporto basato su per impostazione predefinita. Il supporto di Libuv è stato mantenuto per motivi di compatibilità.

A questo punto, l'uso del `Socket` trasporto basato su è molto più comune del trasporto libuv. Di conseguenza, il supporto per Libuv è contrassegnato come obsoleto in .NET 5,0 e verrà rimosso interamente in .NET 6,0.

Come parte di questa modifica, il supporto libuv per le nuove piattaforme del sistema operativo (ad esempio Windows ARM64) non verrà aggiunto nell'intervallo di tempo di .NET 5,0.

Per informazioni sul blocco di problemi che richiedono l'uso del trasporto libuv, vedere il problema GitHub in [DotNet/aspnetcore # 23409](https://github.com/dotnet/aspnetcore/issues/23409).

#### <a name="version-introduced"></a>Versione introdotta

5,0 Anteprima 8

#### <a name="old-behavior"></a>Comportamento precedente

Le API libuv non sono contrassegnate come obsolete.

#### <a name="new-behavior"></a>Nuovo comportamento

Le API libuv sono contrassegnate come obsolete.

#### <a name="reason-for-change"></a>Motivo della modifica

Il `Socket` trasporto basato su è il valore predefinito. Non esistono motivi interessanti per continuare a usare il trasporto libuv.

#### <a name="recommended-action"></a>Azione consigliata

Sospendere l'uso del [pacchetto libuv](https://www.nuget.org/packages/Libuv) e dei metodi di estensione.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

- [WebHostBuilderLibuvExtensions](/dotnet/api/microsoft.aspnetcore.hosting.webhostbuilderlibuvextensions?view=aspnetcore-3.0)
- [WebHostBuilderLibuvExtensions.UseLibuv](/dotnet/api/microsoft.aspnetcore.hosting.webhostbuilderlibuvextensions.uselibuv?view=aspnetcore-3.0)
- [Microsoft. AspNetCore. Server. gheppio. Transport. libuv. LibuvTransportOptions](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions?view=aspnetcore-3.0)
- [Microsoft. AspNetCore. Server. gheppio. Transport. libuv. LibuvTransportOptions. ThreadCount](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.threadcount?view=aspnetcore-3.0)
- [Microsoft. AspNetCore. Server. gheppio. Transport. libuv. LibuvTransportOptions. NoDelay](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.nodelay?view=aspnetcore-3.0)
- [Microsoft. AspNetCore. Server. gheppio. Transport. libuv. LibuvTransportOptions. MaxWriteBufferSize](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.maxwritebuffersize?view=aspnetcore-3.0)
- [Microsoft. AspNetCore. Server. gheppio. Transport. libuv. LibuvTransportOptions. MaxReadBufferSize](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.maxreadbuffersize?view=aspnetcore-3.0)
- `Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.Backlog`

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Hosting.WebHostBuilderLibuvExtensions`
- `Overload:Microsoft.AspNetCore.Hosting.WebHostBuilderLibuvExtensions.UseLibuv`
- `T:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.Backlog`

-->
