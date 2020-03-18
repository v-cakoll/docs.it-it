---
ms.openlocfilehash: f95c3916f4da8164cf927344f60f2845f04ddc5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394413"
---
### <a name="kestrel-transport-abstractions-removed-and-made-public"></a>Kestrel: Le astrazioni dei trasporti sono state rimosse e rese pubbliche

Come parte dello spostamento dalle API "pubternal", le API del livello di trasporto Kestrel vengono esposte come interfaccia pubblica nella `Microsoft.AspNetCore.Connections.Abstractions` libreria.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

- Le astrazioni relative al trasporto `Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions` erano disponibili nella libreria.
- La `ListenOptions.NoDelay` struttura era disponibile.

#### <a name="new-behavior"></a>Nuovo comportamento

- L'interfaccia `IConnectionListener` è `Microsoft.AspNetCore.Connections.Abstractions` stata introdotta nella libreria `...Transport.Abstractions` per esporre le funzionalità più utilizzate dalla libreria.
- L'oggetto `NoDelay` è ora`LibuvTransportOptions` disponibile `SocketTransportOptions`nelle opzioni di trasporto ( e ).
- `SchedulingMode`non è più disponibile.

#### <a name="reason-for-change"></a>Motivo della modifica

ASP.NET Core 3.0 si è allontanato dalle API "pubternal".

#### <a name="recommended-action"></a>Azione consigliata

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

nessuno

<!-- 

### Affected APIs

Not detectable via API analysis

-->
