---
ms.openlocfilehash: a56c5fc32b5fd274d5da0d9b295918f5ea3b345e
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393990"
---
### <a name="signalr-hubconnection-resetsendping-and-resettimeout-methods-removed"></a>SignalR: HubConnection ResetSendPing e ResetTimeout metodi rimossi

I metodi `ResetSendPing` e `ResetTimeout` sono stati rimossi dall'API SignalR `HubConnection`. Questi metodi sono stati originariamente progettati solo per uso interno, ma sono stati resi pubblici in ASP.NET Core 2,2. Questi metodi non saranno disponibili a partire dalla versione di ASP.NET Core 3,0 Preview 4. Per informazioni, vedere [ASPNET/AspNetCore # 8543](https://github.com/aspnet/AspNetCore/issues/8543).

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
