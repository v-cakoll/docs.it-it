---
ms.openlocfilehash: ca0792a3fd05d28cecceac1d644e3e4bf64722bc
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345233"
---
### <a name="signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package"></a>SignalR: protocollo Hub MessagePack spostato nel pacchetto MessagePack 2.x

Il ASP.NET Core SignalR [MessagePack Protocollo hub](/aspnet/core/signalr/messagepackhubprotocol) utilizza il [pacchetto MessagePack NuGet](https://www.nuget.org/packages/MessagePack) per la serializzazione MessagePack. ASP.NET Core 5.0 aggiorna il pacchetto dalla versione 1.x alla versione più recente del pacchetto 2.x.

Per una discussione su questo problema, vedere [dotnet/aspnetcore-18692](https://github.com/dotnet/aspnetcore/issues/18692).

#### <a name="version-introduced"></a>Versione introdotta

5.0 Anteprima 1

#### <a name="old-behavior"></a>Comportamento precedente

ASP.NET Core SignalR ha usato il pacchetto MessagePack 1.x per serializzare e deserializzare i messaggi MessagePack.

#### <a name="new-behavior"></a>Nuovo comportamento

ASP.NET Core SignalR utilizza il pacchetto MessagePack 2.x per serializzare e deserializzare i messaggi MessagePack.

#### <a name="reason-for-change"></a>Motivo della modifica

I miglioramenti più recenti nel pacchetto MessagePack 2.x aggiungono funzionalità utili.

#### <a name="recommended-action"></a>Azione consigliata

Questa modifica di rilievo si applica quando:

* Impostazione o configurazione <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>di valori su .
* Utilizzando le API MessagePack direttamente e utilizzando il ASP.NET Core SignalR MessagePack Protocollo hub nello stesso progetto. Verrà caricata la versione più recente anziché la versione precedente.

Per indicazioni sulla migrazione dagli autori del pacchetto, vedere [Migrazione da MessagePack v1.x a MessagePack v2.x](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md). Alcuni aspetti della serializzazione e deserializzazione dei messaggi sono interessati. In particolare, sono state [apportate modifiche comportamentali alla modalità](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md#behavioral-changes)di serializzazione dei valori DateTime .

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
