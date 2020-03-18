---
ms.openlocfilehash: f202b39f1a45f740625827be25e72df0e403d605
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75902061"
---
### <a name="signalr-javascript-client-package-name-changed"></a>SignalR: nome del pacchetto client JavaScript modificato

In ASP.NET Core 3.0 Preview 7, il nome `@aspnet/signalr` del `@microsoft/signalr`pacchetto client JavaScript SignalR è stato modificato da in . The name change reflects the fact that SignalR is useful in more than just ASP.NET Core apps, thanks to the Azure SignalR Service.

Per rispondere a questa modifica, modificare i `require` riferimenti nei file `import` *package.json,* nelle istruzioni e nelle istruzioni ECMAScript. Nessuna API cambierà come parte di questa ridenominazione.

Per una discussione, vedere [dotnet/aspnetcore-11637](https://github.com/dotnet/aspnetcore/issues/11637).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Il pacchetto client `@aspnet/signalr`è denominato .

#### <a name="new-behavior"></a>Nuovo comportamento

Il pacchetto client `@microsoft/signalr`è denominato .

#### <a name="reason-for-change"></a>Motivo della modifica

La modifica del nome chiarisce che SignalR è utile oltre ASP.NET app Core, grazie al servizio SignalR di Azure.The name change chiaris that SignalR is useful beyond ASP.NET Core apps, thanks to the Azure SignalR Service.

#### <a name="recommended-action"></a>Azione consigliata

Passare al nuovo `@microsoft/signalr`pacchetto .

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

nessuno

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
