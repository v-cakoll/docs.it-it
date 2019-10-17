---
ms.openlocfilehash: acef6d7177ee5ad7e18dc8ba1e383d6f76263623
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394069"
---
### <a name="signalr-javascript-client-package-name-changed"></a>SignalR: nome del pacchetto client JavaScript modificato

In ASP.NET Core 3,0 Preview 7, il nome del pacchetto client JavaScript SignalR è cambiato da `@aspnet/signalr` a `@microsoft/signalr`. La modifica del nome riflette il fatto che SignalR è utile in più di ASP.NET Core app, grazie al servizio Azure SignalR.

Per rispondere a questa modifica, modificare i riferimenti nei file *Package. JSON* , nelle istruzioni `require` e nelle istruzioni ECMAScript `import`. Nessuna API verrà modificata come parte di questa ridenominazione.

Per informazioni, vedere [ASPNET/AspNetCore # 11637](https://github.com/aspnet/AspNetCore/issues/11637).

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

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

Nessuno

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
