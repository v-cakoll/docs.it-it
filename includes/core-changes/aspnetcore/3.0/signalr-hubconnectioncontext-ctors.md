---
ms.openlocfilehash: 6be98e7ced6608ba0793c635adfe61c8b1a7e9d9
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81274961"
---
### <a name="signalr-hubconnectioncontext-constructors-changed"></a>SignalR: costruttori HubConnectionContext modificati

I `HubConnectionContext` costruttori di SignalR sono stati modificati per accettare un tipo di opzioni, anziché più parametri, in opzioni di aggiunta a prova di futuro. Questa modifica sostituisce due costruttori con un singolo costruttore che accetta un tipo di opzioni.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

`HubConnectionContext`dispone di due costruttori:

```csharp
public HubConnectionContext(ConnectionContext connectionContext, TimeSpan keepAliveInterval, ILoggerFactory loggerFactory);
public HubConnectionContext(ConnectionContext connectionContext, TimeSpan keepAliveInterval, ILoggerFactory loggerFactory, TimeSpan clientTimeoutInterval);
```

#### <a name="new-behavior"></a>Nuovo comportamento

I due costruttori sono stati rimossi e sostituiti con un costruttore:The two constructors were removed and replaced with one constructor:

```csharp
public HubConnectionContext(ConnectionContext connectionContext, HubConnectionContextOptions contextOptions, ILoggerFactory loggerFactory)
```

#### <a name="reason-for-change"></a>Motivo della modifica

Il nuovo costruttore utilizza un nuovo oggetto options. Di conseguenza, `HubConnectionContext` le funzionalità di possono essere espanse in futuro senza apportare più costruttori e modifiche di rilievo.

#### <a name="recommended-action"></a>Azione consigliata

Anziché utilizzare il seguente costruttore:

```csharp
HubConnectionContext connectionContext = new HubConnectionContext(
    connectionContext,
    keepAliveInterval: TimeSpan.FromSeconds(15),
    loggerFactory,
    clientTimeoutInterval: TimeSpan.FromSeconds(15));
```

Utilizzare il costruttore seguente:Use the following constructor:

```csharp
HubConnectionContextOptions contextOptions = new HubConnectionContextOptions()
{
    KeepAliveInterval = TimeSpan.FromSeconds(15),
    ClientTimeoutInterval = TimeSpan.FromSeconds(15)
};
HubConnectionContext connectionContext = new HubConnectionContext(connectionContext, contextOptions, loggerFactory);
```

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

- <xref:Microsoft.AspNetCore.SignalR.HubConnectionContext.%23ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory)>
- <xref:Microsoft.AspNetCore.SignalR.HubConnectionContext.%23ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory,System.TimeSpan)>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.SignalR.HubConnectionContext.#ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory)`
- `M:Microsoft.AspNetCore.SignalR.HubConnectionContext.#ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory,System.TimeSpan)`

-->
