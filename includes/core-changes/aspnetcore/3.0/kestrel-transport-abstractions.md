---
ms.openlocfilehash: f95c3916f4da8164cf927344f60f2845f04ddc5c
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394413"
---
### <a name="kestrel-transport-abstractions-removed-and-made-public"></a>Gheppio: astrazioni del trasporto rimosse e rese pubbliche

Come parte del passaggio dalle API "pubternal", le API del livello di trasporto di gheppio sono esposte come interfaccia pubblica nella libreria `Microsoft.AspNetCore.Connections.Abstractions`.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

- Le astrazioni relative al trasporto erano disponibili nella libreria `Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions`.
- La proprietà `ListenOptions.NoDelay` era disponibile.

#### <a name="new-behavior"></a>Nuovo comportamento

- L'interfaccia `IConnectionListener` è stata introdotta nella libreria `Microsoft.AspNetCore.Connections.Abstractions` per esporre le funzionalità più usate dalla libreria `...Transport.Abstractions`.
- Il `NoDelay` è ora disponibile nelle opzioni di trasporto (`LibuvTransportOptions` e `SocketTransportOptions`).
- `SchedulingMode` non è più disponibile.

#### <a name="reason-for-change"></a>Motivo della modifica

ASP.NET Core 3,0 è stato rimosso dalle API "pubternal".

#### <a name="recommended-action"></a>Azione consigliata

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

Nessuno

<!-- 

### Affected APIs

Not detectable via API analysis

-->
