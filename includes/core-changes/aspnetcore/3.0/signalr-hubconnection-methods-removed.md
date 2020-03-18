---
ms.openlocfilehash: de06825f1031d05bc83183a83bae165e2f9512ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901807"
---
### <a name="signalr-hubconnection-resetsendping-and-resettimeout-methods-removed"></a>SignalR: metodi ResetSendPing e ResetTimeout rimossi

I `ResetSendPing` `ResetTimeout` metodi e sono stati `HubConnection` rimossi dall'API SignalR. Questi metodi sono stati originariamente destinati solo per uso interno, ma sono stati resi pubblici in ASP.NET Core 2.2. Questi metodi non saranno disponibili a partire dalla versione di ASP.NET Core 3.0 Preview 4. Per una discussione, vedere [dotnet/aspnetcore-8543](https://github.com/dotnet/aspnetcore/issues/8543).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Api disponibili.

#### <a name="new-behavior"></a>Nuovo comportamento

Le API vengono rimosse.

#### <a name="reason-for-change"></a>Motivo della modifica

Questi metodi sono stati originariamente destinati solo per uso interno, ma sono stati resi pubblici in ASP.NET Core 2.2.

#### <a name="recommended-action"></a>Azione consigliata

Non utilizzare questi metodi.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

- <xref:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetSendPing?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetTimeout?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetSendPing`
- `M:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetTimeout`

-->
