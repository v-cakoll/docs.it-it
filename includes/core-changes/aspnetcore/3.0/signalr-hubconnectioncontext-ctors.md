---
ms.openlocfilehash: 6be98e7ced6608ba0793c635adfe61c8b1a7e9d9
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81274961"
---
### <a name="signalr-hubconnectioncontext-constructors-changed"></a><span data-ttu-id="4bd77-101">SignalR: costruttori HubConnectionContext modificati</span><span class="sxs-lookup"><span data-stu-id="4bd77-101">SignalR: HubConnectionContext constructors changed</span></span>

<span data-ttu-id="4bd77-102">I `HubConnectionContext` costruttori di SignalR sono stati modificati per accettare un tipo di opzioni, anziché più parametri, in opzioni di aggiunta a prova di futuro.</span><span class="sxs-lookup"><span data-stu-id="4bd77-102">SignalR's `HubConnectionContext` constructors changed to accept an options type, rather than multiple parameters, to future-proof adding options.</span></span> <span data-ttu-id="4bd77-103">Questa modifica sostituisce due costruttori con un singolo costruttore che accetta un tipo di opzioni.</span><span class="sxs-lookup"><span data-stu-id="4bd77-103">This change replaces two constructors with a single constructor that accepts an options type.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="4bd77-104">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="4bd77-104">Version introduced</span></span>

<span data-ttu-id="4bd77-105">3.0</span><span class="sxs-lookup"><span data-stu-id="4bd77-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="4bd77-106">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="4bd77-106">Old behavior</span></span>

<span data-ttu-id="4bd77-107">`HubConnectionContext`dispone di due costruttori:</span><span class="sxs-lookup"><span data-stu-id="4bd77-107">`HubConnectionContext` has two constructors:</span></span>

```csharp
public HubConnectionContext(ConnectionContext connectionContext, TimeSpan keepAliveInterval, ILoggerFactory loggerFactory);
public HubConnectionContext(ConnectionContext connectionContext, TimeSpan keepAliveInterval, ILoggerFactory loggerFactory, TimeSpan clientTimeoutInterval);
```

#### <a name="new-behavior"></a><span data-ttu-id="4bd77-108">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="4bd77-108">New behavior</span></span>

<span data-ttu-id="4bd77-109">I due costruttori sono stati rimossi e sostituiti con un costruttore:The two constructors were removed and replaced with one constructor:</span><span class="sxs-lookup"><span data-stu-id="4bd77-109">The two constructors were removed and replaced with one constructor:</span></span>

```csharp
public HubConnectionContext(ConnectionContext connectionContext, HubConnectionContextOptions contextOptions, ILoggerFactory loggerFactory)
```

#### <a name="reason-for-change"></a><span data-ttu-id="4bd77-110">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="4bd77-110">Reason for change</span></span>

<span data-ttu-id="4bd77-111">Il nuovo costruttore utilizza un nuovo oggetto options.</span><span class="sxs-lookup"><span data-stu-id="4bd77-111">The new constructor uses a new options object.</span></span> <span data-ttu-id="4bd77-112">Di conseguenza, `HubConnectionContext` le funzionalità di possono essere espanse in futuro senza apportare più costruttori e modifiche di rilievo.</span><span class="sxs-lookup"><span data-stu-id="4bd77-112">Consequently, the features of `HubConnectionContext` can be expanded in the future without making more constructors and breaking changes.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="4bd77-113">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="4bd77-113">Recommended action</span></span>

<span data-ttu-id="4bd77-114">Anziché utilizzare il seguente costruttore:</span><span class="sxs-lookup"><span data-stu-id="4bd77-114">Instead of using the following constructor:</span></span>

```csharp
HubConnectionContext connectionContext = new HubConnectionContext(
    connectionContext,
    keepAliveInterval: TimeSpan.FromSeconds(15),
    loggerFactory,
    clientTimeoutInterval: TimeSpan.FromSeconds(15));
```

<span data-ttu-id="4bd77-115">Utilizzare il costruttore seguente:Use the following constructor:</span><span class="sxs-lookup"><span data-stu-id="4bd77-115">Use the following constructor:</span></span>

```csharp
HubConnectionContextOptions contextOptions = new HubConnectionContextOptions()
{
    KeepAliveInterval = TimeSpan.FromSeconds(15),
    ClientTimeoutInterval = TimeSpan.FromSeconds(15)
};
HubConnectionContext connectionContext = new HubConnectionContext(connectionContext, contextOptions, loggerFactory);
```

#### <a name="category"></a><span data-ttu-id="4bd77-116">Category</span><span class="sxs-lookup"><span data-stu-id="4bd77-116">Category</span></span>

<span data-ttu-id="4bd77-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4bd77-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4bd77-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="4bd77-118">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.SignalR.HubConnectionContext.%23ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory)>
- <xref:Microsoft.AspNetCore.SignalR.HubConnectionContext.%23ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory,System.TimeSpan)>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.SignalR.HubConnectionContext.#ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory)`
- `M:Microsoft.AspNetCore.SignalR.HubConnectionContext.#ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory,System.TimeSpan)`

-->
