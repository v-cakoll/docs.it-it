---
ms.openlocfilehash: f202b39f1a45f740625827be25e72df0e403d605
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75902061"
---
### <a name="signalr-javascript-client-package-name-changed"></a>SignalR: nome del pacchetto client JavaScript modificato

In ASP.NET Core 3,0 Preview 7 il nome del pacchetto client JavaScript SignalR è cambiato da `@aspnet/signalr` a `@microsoft/signalr`. La modifica del nome riflette il fatto che SignalR è utile in più di ASP.NET Core app, grazie al servizio Azure SignalR.

Per rispondere a questa modifica, modificare i riferimenti nei file *Package. JSON* , `require` istruzioni e le istruzioni `import` ECMAScript. Nessuna API verrà modificata come parte di questa ridenominazione.

Per informazioni, vedere [DotNet/aspnetcore # 11637](https://github.com/dotnet/aspnetcore/issues/11637).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Il pacchetto client è denominato `@aspnet/signalr`.

#### <a name="new-behavior"></a>Nuovo comportamento

Il pacchetto client è denominato `@microsoft/signalr`.

#### <a name="reason-for-change"></a>Motivo della modifica

La modifica del nome chiarisce che SignalR è utile oltre ASP.NET Core app, grazie al servizio Azure SignalR.

#### <a name="recommended-action"></a>Azione consigliata

Passare al nuovo pacchetto `@microsoft/signalr`.

#### <a name="category"></a>Categoria

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

nessuna

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
