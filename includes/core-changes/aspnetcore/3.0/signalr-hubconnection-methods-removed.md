---
ms.openlocfilehash: de06825f1031d05bc83183a83bae165e2f9512ff
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901807"
---
### <a name="signalr-hubconnection-resetsendping-and-resettimeout-methods-removed"></a>SignalR: HubConnection ResetSendPing e ResetTimeout metodi rimossi

I metodi `ResetSendPing` e `ResetTimeout` sono stati rimossi dall'API `HubConnection` di SignalR. Questi metodi sono stati originariamente progettati solo per uso interno, ma sono stati resi pubblici in ASP.NET Core 2,2. Questi metodi non saranno disponibili a partire dalla versione di ASP.NET Core 3,0 Preview 4. Per informazioni, vedere [DotNet/aspnetcore # 8543](https://github.com/dotnet/aspnetcore/issues/8543).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

API disponibili.

#### <a name="new-behavior"></a>Nuovo comportamento

Le API vengono rimosse.

#### <a name="reason-for-change"></a>Motivo della modifica

Questi metodi sono stati originariamente progettati solo per uso interno, ma sono stati resi pubblici in ASP.NET Core 2,2.

#### <a name="recommended-action"></a>Azione consigliata

Non usare questi metodi.

#### <a name="category"></a>Categoria

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

- <xref:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetSendPing?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetTimeout?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetSendPing`
- `M:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetTimeout`

-->
