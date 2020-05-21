---
ms.openlocfilehash: fb23418816abcae125106c93b339a546aa9bc2ee
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721134"
---
### <a name="kestrel-transport-abstractions-removed-and-made-public"></a>Gheppio: astrazioni del trasporto rimosse e rese pubbliche

Come parte del passaggio dalle API "pubternal", le API del livello di trasporto di gheppio sono esposte come interfaccia pubblica nella `Microsoft.AspNetCore.Connections.Abstractions` libreria.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

- Le astrazioni relative al trasporto erano disponibili nella `Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions` libreria.
- La `ListenOptions.NoDelay` proprietà era disponibile.

#### <a name="new-behavior"></a>Nuovo comportamento

- L' `IConnectionListener` interfaccia è stata introdotta nella `Microsoft.AspNetCore.Connections.Abstractions` libreria per esporre le funzionalità più usate dalla `...Transport.Abstractions` libreria.
- `NoDelay`È ora disponibile nelle opzioni di trasporto ( `LibuvTransportOptions` e `SocketTransportOptions` ).
- `SchedulingMode`non è più disponibile.

#### <a name="reason-for-change"></a>Motivo della modifica

ASP.NET Core 3,0 è stato rimosso dalle API "pubternal".

#### <a name="recommended-action"></a>Azione consigliata

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

Nessuno

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
